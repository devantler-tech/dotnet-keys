# 🗝️ .NET Keys

[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Test](https://github.com/devantler-tech/dotnet-keys/actions/workflows/test.yaml/badge.svg)](https://github.com/devantler-tech/dotnet-keys/actions/workflows/test.yaml)
[![codecov](https://codecov.io/gh/devantler-tech/dotnet-keys/graph/badge.svg?token=RhQPb4fE7z)](https://codecov.io/gh/devantler-tech/dotnet-keys)

A simple .NET library with a collection of common assymetric and symmetric key models.

## Prerequisites

- [.NET](https://dotnet.microsoft.com/en-us/)

## 🚀 Getting Started

To get started, you can install the packages from NuGet.

```bash
# For the Age key model
dotnet add package DevantlerTech.Keys.Age
```

If you need to create a new key model, you can install the `Core` package from NuGet. This package includes the base classes and interfaces for creating new key models.

```bash
dotnet add package DevantlerTech.Keys.Core
```

## 📝 Usage

The library currently supports the following key models:

- [Age](#the-age-key-model)

### The Age Key Model

The Age key model is a simple key model that represents an Age key. To create a new Age key, you can use the `AgeKey` class. To create an age key with a current created date, you can construct the `AgeKey` class with the public and private keys.

```csharp
string publicKey = "age1wrczv4ll5att0mm8tmp4052z4fadw5zefxvefuqxu8rqtpe47chskk9dgn";
string privateKey = "AGE-SECRET-KEY-1PW4MMMJ9KMZ94C2N2FM3UPLPQPEF8G9QHXP8VX6V6GW3EN9QMSVQX0ATHQ";

var ageKey = new AgeKey(publicKey, privateKey);
```

If you want to create a new Age key with a specific created date, you can use the `AgeKey` class with the public and private keys and the created date.

```csharp
string publicKey = "age1wrczv4ll5att0mm8tmp4052z4fadw5zefxvefuqxu8rqtpe47chskk9dgn";
string privateKey = "AGE-SECRET-KEY-1PW4MMMJ9KMZ94C2N2FM3UPLPQPEF8G9QHXP8VX6V6GW3EN9QMSVQX0ATHQ";
DateTime createdDate = DateTime.UtcNow;

var ageKey = new AgeKey(publicKey, privateKey, createdDate);
```

And if you want to serialize the Age key, you can use the `ToString()` method.

```csharp
string serializedAgeKey = ageKey.ToString();

Console.WriteLine(serializedAgeKey);

// Output:
// # created: 1920-08-18T01:00:00+01:00
// # public key: age1wrczv4ll5att0mm8tmp4052z4fadw5zefxvefuqxu8rqtpe47chskk9dgn
// AGE-SECRET-KEY-1PW4MMMJ9KMZ94C2N2FM3UPLPQPEF8G9QHXP8VX6V6GW3EN9QMSVQX0ATHQ
```

> [!NOTE]
> If you are looking for a library to help generate Age keys you can use the [`DevantlerTech.AgeCLI` library](https://github.com/devantler-tech/dotnet-age-cli), which embeds the `age-keygen` binary to generate Age keys to files or in-memory. It also uses the `AgeKey` class so the generated keys are easy to use in your .NET applications.
