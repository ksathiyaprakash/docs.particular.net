---
title: Assembly scanning in NServiceBus
summary: To enable automatic detection of various features NServiceBus scans your assemblies for well known types
tags: []
---

By default, NServiceBus scans all assemblies in the endpoint bin folder to find types implementing its interfaces so that it can configure them automatically. 

NOTE: During the scanning process, the core dlls for NServiceBus namely `NServiceBus.Core.dll`, `NServiceBus.dll` (in versions prior to Version 5) and if in use `NServiceBus.Host.exe` are automatically included since the endpoint needs them to function properly.

## Controlling the assemblies to scan

There are some cases where you need fine grained control over which assemblies are loaded:

- To limit the number of assemblies being scanned and hence provide improvements to startup time.
- If you are hosting multiple endpoints out of the same directory (made possible in Version 5) i.e. each endpoint would want to load a subset of assemblies.
- In versions prior to Version 4.1, non .NET assemblies, e.g. COM dlls might need to be excluded. Starting with Version 4.1, non .NET assemblies are automatically excluded.
 
NOTE: Extension (like NServiceBus.Distributor.MSMQ.dll or NServiceBus.RavenDB for example) are not considered core dlls and will need to be explicitly added if you customize assembly scanning.

### By default all types in your bin directory is scanned if you call:

<!-- import ScanningDefault -->
 
### You can pass a list of assemblies:

<!-- import ScanningListOfAssemblies -->

### You can pass the assemblies one by one:

<!-- import ScanningParamArrayOfAssemblies -->

###You can exclude specific assemblies by name:

<!-- import ScanningExcludeByName -->

### You can include assemblies using pattern matching:

<!-- import ScanningIncludeByPattern -->

### You can mix includes and excludes:

<!-- import ScanningMixingIncludeAndExclude -->

### You can specify the directory to scan:

<!-- import ScanningCustomDirectory -->

### And if you need to control the exact types that NServiceBus uses you can pass them in:

<!-- import ScanningListOfTypes -->

