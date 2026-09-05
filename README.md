# ISO 6346 Container & Chassis Check-Digit Validator — .NET / C# SDK

[![NuGet version](https://img.shields.io/nuget/v/StanzaApi.ContainerValidator.svg)](https://www.nuget.org/packages/StanzaApi.ContainerValidator/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Stanza API](https://img.shields.io/badge/Powered%20by-Stanza-blue)](https://stanzaapi.com)

> MOD-11 check digit validator and ISO 6346 size/type decoder for intermodal shipping containers, chassis, and trailers.

Official high-performance .NET client library for **ISO 6346 Container & Chassis Check-Digit Validator**, built on the [Stanza Micro-API Network](https://stanzaapi.com). Fully compatible with .NET Standard 2.0, .NET 6.0, .NET 7.0, and .NET 8.0+.

* 🌐 **Online Interactive Sandbox:** [Test your inputs live](https://stanzaapi.com/tools/container-validator)
* 📚 **API Reference & Schemas:** [View documentation on Stanza](https://stanzaapi.com/tools/container-validator)
* ⚡ **Platform Overview:** [Explore the Stanza Developer Network](https://stanzaapi.com)

---

## 📦 Installation

```bash
dotnet add package StanzaApi.ContainerValidator
```

---

## 🚀 Quickstart

```csharp
using System;
using System.Threading.Tasks;
using StanzaApi.ContainerValidator;

class Program
{
    static async Task Main()
    {
        // Initialize client (reads STANZA_API_KEY from environment if not passed)
        var client = new ContainerValidatorClient();

        // Perform deterministic verification
        string responseJson = await client.ValidateAsync("MSKU0123456");
        Console.WriteLine(responseJson);
    }
}
```

---

## 📄 Example Response

```json
{
  "success": true,
  "data": {
    "valid": true,
    "owner_code": "MSK",
    "category": "U",
    "serial_number": "012345",
    "check_digit": 6
  }
}
```

---

## ⚙️ Configuration

Pass options directly to the `ContainerValidatorClient` constructor:

```csharp
var client = new ContainerValidatorClient(
    apiKey: "your_api_key_here",
    baseUrl: "https://stanzaapi.com"
);
```

---

## 🔗 Useful Links

* [ISO 6346 Container & Chassis Check-Digit Validator Interactive Sandbox](https://stanzaapi.com/tools/container-validator)
* [Stanza Developer Directory](https://stanzaapi.com)
* [Source Code & Issue Tracker](https://github.com/stanzaapi/container-validator-csharp)

## 📄 License

MIT © Stanza — Powered by [Stanza](https://stanzaapi.com).
