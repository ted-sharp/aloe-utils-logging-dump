# Aloe.Utils.Logging.Dump

[![NuGet Version](https://img.shields.io/nuget/v/Aloe.Utils.Logging.Dump.svg)](https://www.nuget.org/packages/Aloe.Utils.Logging.Dump)
[![NuGet Downloads](https://img.shields.io/nuget/dt/Aloe.Utils.Logging.Dump.svg)](https://www.nuget.org/packages/Aloe.Utils.Logging.Dump)
[![License](https://img.shields.io/github/license/ted-sharp/aloe-utils-logging-dump.svg)](LICENSE)
[![.NET](https://img.shields.io/badge/.NET-9.0-blue.svg)](https://dotnet.microsoft.com/download/dotnet/9.0)

`Aloe.Utils.Logging.Dump` is a lightweight and easy-to-use library for logging byte arrays in hexadecimal dump format.
It is primarily used in applications that require debugging and binary data analysis.

## Key Features

* Log byte arrays in hexadecimal dump format
* Line breaks every 16 bytes
* Performance-optimized implementation (using ValueStringBuilder)
* Integration with Microsoft.Extensions.Logging

## Supported Environments

* .NET 9 and later

## Installation

Using NuGet Package Manager:

```cmd
Install-Package Aloe.Utils.Logging.Dump
```

Or using .NET CLI:

```cmd
dotnet add package Aloe.Utils.Logging.Dump
```

## Usage Example

```csharp
using Microsoft.Extensions.Logging;
using Aloe.Utils.Logging.Dump;

// Create logger factory
using var loggerFactory = LoggerFactory.Create(builder =>
{
    builder
        .SetMinimumLevel(LogLevel.Debug)
        .AddConsole();
});

// Get logger
var logger = loggerFactory.CreateLogger<Program>();

// Create sample data
byte[] sampleData =
[
    0x00, 0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07,
    0x08, 0x09, 0x0A, 0x0B, 0x0C, 0x0D, 0x0E, 0x0F,
    0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16, 0x17,
    0x18, 0x19, 0x1A, 0x1B, 0x1C, 0x1D, 0x1E, 0x1F,
];

// Execute dump output
logger.DumpDebug(sampleData);
```

Output example:
```
00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
-- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
10 11 12 13 14 15 16 17 18 19 1A 1B 1C 1D 1E 1F
```

## License

MIT License

## Contributing

Please report bugs and feature requests through GitHub Issues. Pull requests are welcome.
