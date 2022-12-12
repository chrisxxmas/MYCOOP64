
# YamlDotNet

| Appveyor | NuGet |
|----------|-------|
|[![Build status](https://ci.appveyor.com/api/projects/status/github/aaubry/yamldotnet?svg=true)](https://ci.appveyor.com/project/aaubry/yamldotnet/branch/master)|  [![NuGet](https://img.shields.io/nuget/v/YamlDotNet.svg)](https://www.nuget.org/packages/YamlDotNet/)


YamlDotNet is a YAML library for [netstandard and other .NET runtimes](#the-yamldotnet-library).

YamlDotNet provides low level parsing and emitting of YAML as well as a high level object model similar to XmlDocument. A serialization library is also included that allows to read and write objects from and to YAML streams.

YamlDotNet's conformance with YAML specifications:

|            YAML Spec                | YDN Parser | YDN Emitter |
|:-----------------------------------:|:----------:|:-----------:|
|  [v1.1](https://yaml.org/spec/1.1/)  |     ✓      |      ✓      |
|  [v1.2](https://yaml.org/spec/1.2/spec.html)  |     ✓      |             |


## What is YAML?

YAML, which stands for "YAML Ain't Markup Language", is described as "a human friendly data serialization standard for all programming languages". Like XML, it allows to represent about any kind of data in a portable, platform-independent format. Unlike XML, it is "human friendly", which means that it is easy for a human to read or produce a valid YAML document.

## The YamlDotNet library

The library has now been successfully used in multiple projects and is considered fairly stable. It is compatible with the following runtimes:

* netstandard 2.0
* netstandard 2.1
* .NET 6.0
* .NET 7.0
* .NET Framework 4.7
* .NET Framework 4.5
* Unity Subset v3.5

The following runtimes are also supported, with a few features missing:

* .NET Framework 3.5

The library is compatible with mono's [Ahead-of-Time compilation](https://www.mono-project.com/docs/advanced/aot/) (AOT), and should work correctly on platforms that depend on it, such as Unity.

## Quick start

Here are some quick samples to get you started which can be viewed in [this fiddle](https://dotnetfiddle.net/CQ7ZKi).

### Serialization from an object to a string

```c#
using YamlDotNet.Serialization;
using YamlDotNet.Serialization.NamingConventions;
...

 var person = new Person
{
    Name = "Abe Lincoln",
    Age = 25,
    HeightInInches = 6f + 4f / 12f,
    Addresses = new Dictionary<string, Address>{
        { "home", new  Address() {
                Street = "2720  Sundown Lane",
                City = "Kentucketsville",
                State = "Calousiyorkida",
                Zip = "99978",
            }},
        { "work", new  Address() {
                Street = "1600 Pennsylvania Avenue NW",
                City = "Washington",
                State = "District of Columbia",
                Zip = "20500",