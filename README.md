# Serilog.Sinks.SQLite.Maui

The fork of [Serilog.Sinks.SQLite](https://github.com/saleem-mirza/serilog-sinks-sqlite)

Referring to this issue https://github.com/saleem-mirza/serilog-sinks-sqlite/issues/24#issuecomment-608555305

It can run normally in Maui(.NET 7)

I made the following changes

- Replace SQLite with SQLiteNetPcl
- Replace Newtonsoft.Json with System.Text.Json
- add program annotation in `LoggerConfigurationSQLiteExtensions.cs`. Because there will be an exception where the reference object instance is null in Maui's Android.
```
//if (!sqliteDbPathUri.IsAbsoluteUri) {
//    var basePath = System.Reflection.Assembly.GetEntryAssembly().Location;
//    sqliteDbPath = Path.Combine(Path.GetDirectoryName(basePath) ?? throw new NullReferenceException(), sqliteDbPath);
//}
```