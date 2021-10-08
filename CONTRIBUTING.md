# Contributing to YamlDotNet

**Welcome!**  
Thanks for your interest in contributing to this project. Any contribution will
be gladly accepted, provided that they are generally useful and follow the
conventions of the project.

If you are considering a contribution, please read and follow these guidelines.

## Pull requests

All contributions should be submitted as pull requests.

1. Please create **one pull request for each feature**. This results in smaller pull requests that are easier to review and validate.

1. **Avoid reformatting existing code** unless you are making other changes to it.
   * Cleaning-up of `using`s is acceptable, if you made other changes to that file.
   * If you believe that some code is badly formatted and needs fixing, isolate that change in a separate pull request.

1. Always add one or more **unit tests** that prove that the feature / fix you are submitting is working correctly.

1. Please **describe the motivation** behind the pull request. Explain what was the problem / requirement. Unless the implementation is self-explanatory, also describe the solution.
   * Of course, there's no need to be too verbose. Usually one or two lines will be enough.

## Project organization

The main project, YamlDotNet.csproj, is organized in three main namespaces: `Core`, `RepresentationModel` and `Serialization`. The `Core` namespace contains everything that is related to reading and writing YAML. The `RepresentationModel` has classes that represent a YAML stream, similar to XmlDocument for XML. The `Serialization` namespace contains classes to serialize and deserialize object graphs to / from YAML.

Unit tests are all contained in the project named YamlDotNet.Test.csproj.

The PerformanceTests folder contains various projects that contain performance tests that compare various versions of YamlDotNet to detect the impact of new features.

## Building / multiplatform

This repository uses submodules. **Before building, make sure that you update them** using the following command:
```
git submodule update --init
```

In order to build locally, you need at least to install the [.NET Core 3.1 SDK](https://dotnet.microsoft.com/download). Alternat