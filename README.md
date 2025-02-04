# Metro Transit Vehicle Data

## Vehicle position and passenger data

This folder holds data from Metro Transit in `data/cline_2022_present`:

- `apc.parquet`: Automated passenger counts (APC). Each row is a stop on a trip on a specific day.
- `stop_crossings.parquet`: Automated vehicle locations (AVL). Each row is a vehicle position for a vehicle on a specific trip on a specific day.
- `cline_sch.parquet`: operational information for bus schedules.

It also has historical

See [2-analyze-passengers.md](2-analyze-passengers.md) for a simple rendered report.

## Historical GTFS schedule data

I've concatenated GTFS schedule data going back to `2020-11-28` in `data/1-gtfs_schedules_combined`. Each file has a `feed_date` column, which indicates the date the feed started on.

There are also these convenient tables:

- `data/1-daily_feed_dates.parquet`: Tracks which feed is "active" on any date. Each row is a date, with its corresponding feed_date.
- `data/1-daily_service.parquet`: Tracks which trips are in service on any day. Each row is a daily date between a trip's start and end, with a column indicating if it's in service.
- `data/1-gtfs_trip_shapes.parquet`: Each row is a trip, with a geometry column for plotting its path (through stops).
