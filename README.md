# OpenEEW

Let's create [earthquake early-warning systems](https://en.wikipedia.org/wiki/Earthquake_warning_system/) for every seismically-vulnerable community in the world! 

Grillo will be sharing years of raw historic sensor data, including magnitude 6 and 7 earthquakes. This will allow you to develop new detection algorithmns and train machine learning models. Grillo will also be sharing code examples to get you started, and hardware schematics to make your own sensors.

## Getting Started

We are almost ready to deploy !! stay tuned.

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Authors

* **Grillo** - *Initial work* - [Grillo](https://grillo.io)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

OpenEEW data on AWS is licensed under CC BY-SA 4.0 (https://creativecommons.org/licenses/by-sa/4.0/).

## Acknowledgments

* Inspired by Stamford's Quake Catcher Network - [QCN](http://qcn.stanford.edu/)

# Accessing OpenEEW data on AWS
Files are organized into folders based on country, device and UTC date corresponding to the data; the precise logic to assign data to a file based on date is explained in more detail below. A typical file path will have this form:
```
records/country_code=<country_code>/device_id=<device_id>/year=<year>/month=<month>/day=<day>/hour=<hour>/<minute>.jsonl
```
Here:
- `<country_code>` is the ISO 3166 two-digit country code of the country in which device is deployed, as lowercase. e.g. mx, cl
- `<device_id>`, of variable length, is the string identifier of the device, e.g. 000, 001. This can be used in conjunction with the device metadata file (see below). It is unique per country
- `<year>` is the UTC year with century of the data, e.g. 2019
- `<month>` is the UTC month of the data as a zero-padded decimal, e.g. 01, 02, 11, 12
- `<day>` is the UTC day of the data as a zero-padded decimal, e.g. 01, 31
- `<hour>` is the UTC hour (24-hour clock) of the data as a zero-padded decimal e.g. 00, 23
- `<minute>` is the UTC minute used to label the five-minute bucket to which the data belongs as a zero-padded decimal, e.g. 00, 05, 55

The .jsonl file extension indicates that data is stored as newline-delimited JSON objects (see http://jsonlines.org/).

## Data fields
Accelerometer data is stored with the same structure as received from the devices in order that any processing applied to the archived data could straightforwardly be applied to the data in real time.

Each file row contains a JSON object with the following fields:
- `country_code`: same as the folder parameter (see above)
- `device_id`: same as the folder parameter (see above)
- `x`: array of accelerometer x-axis decimal values in Gals
- `y`: array of accelerometer y-axis decimal values in Gals
- `z`: array of accelerometer z-axis decimal values in Gals
- `device_t`: device Unix time corresponding to final values of the `x`, `y` and `z` arrays
- `cloud_t`: Unix time when data was received in the cloud
- `sr`: sample rate, number of values per second

Note that the `x`, `y` and `z` arrays are of the same length and correspond to the same measurement times, i.e. the nth value in the `x`, `y` and `z` arrays correspond to the same measurement time. The length of the arrays, typically 32, is independent of the sample rate `sr`.

Typically, `cloud_t` and `device_t` differ by less than one second, but occasionally the device time drifts so we suggest to use `cloud_t` as the more reliable measurement timestamp. Ordering data by `cloud_t` and then `device_t` is suggested in rare cases where two records have the same value of `cloud_t`.

Individual timestamps can be assigned to each data point in the arrays using the values `cloud_t` (or `device_t`) and the `sr`, i.e. by subtracting from the timestamp a multiple of `1/sr` based on the array index value.

## How records are assigned to a file
Records are assigned to a file based on the UTC value of the `cloud_t` field. The minute, MM, of the file, together with the containing year, month, day and hour, should be such that:
```
year-month-day hour:MM <= cloud_t < year-month-day hour:MM + 5 minutes
```

## Device metadata
Device metadata is stored in the following filepath:
```
devices/country_code=<country_code>/devices.jsonl
```

For consistency, we use the same newline-delimited JSON format as used for accelerometer records. Each JSON contains the following fields:
- `country_code`: same as records folder parameter
- `device_id`: same as records folder parameter
- `latitude`: device latitude to 2 decimal places
- `longitude`: device longitude to 2 decimal places
- `effective_from`: integer Unix time from which the metadata is valid
- `effective_to`: integer Unix time until which the metadata is valid
- `is_current_row`: either 1 or 0 to indicate if the row is currently effective, as an alternative to checking effective dates when searching for current values
- `vertical_axis`: 'x', 'y' or 'z' to specify which axis has vertical orientation

The `effective_from` and `effective_to` are such that there is no overlap, so it is sufficient to check
```
effective_from <= Unix time <= effective_to
```

This means in a SQL query a `BETWEEN` clause could be used. For the currently effective rows, the `effective_to` is set to the Unix time corresponding to `9999-12-31T23:59:59Z`.
