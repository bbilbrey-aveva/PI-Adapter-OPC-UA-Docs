---
uid: SystemRequirements
---

# System requirements

[!include[product](../_includes/inline/product-name.md)] is supported on a variety of platforms and processors. Install kits are available for the following platforms:

| Operating System | Platform | Installation Kit | Processor(s) |
|-------------------|-------------|----------------------------------|-------------|
| Windows 10 Enterprise <br> Windows 10 IoT Enterprise <br> Windows 11 Enterprise <br> Windows Server 2019 <br> Windows Server 2022 | x64 | <code>[!include[installer](../_includes/inline/installer-name.md)]-x64_.msi</code>     | Intel/AMD 64-bit processors |
| Debian 10, 11<br>Ubuntu 20.04, 22.04 | x64 | <code>[!include[installer](../_includes/inline/installer-name.md)]-x64_.deb</code>     | Intel/AMD 64-bit processors |
| Debian 10, 11<br>Ubuntu 20.04, 22.04 | ARM32 | <code>[!include[installer](../_includes/inline/installer-name.md)]-arm_.deb</code>  | ARM 32-bit processors |
| Debian 10, 11<br>Ubuntu 20.04, 22.04 | ARM64 | <code>[!include[installer](../_includes/inline/installer-name.md)]-arm64_.deb</code>  | ARM 64-bit processors |

Alternatively, you can use tar.gz files with binaries to build your own custom installers or containers for Linux. For more information on installing the adapter with Docker containers, see <xref:InstallUsingDocker>.

## PI Web API compatibility

This version of [!include[product](../_includes/inline/product-name.md)] is compatible with PI Web API 2021 and later.

## AVEVA Adapter for OPC UA upgrade

If you are upgrading AVEVA Adapter for OPC UA from version 1.1 to 1.3 and are sending data to PI Web API 2019, AVEVA Data Hub, or both, read [OPC UA Adapter - Upgrade from v1.1 to v1.3](https://osisoft.lightning.force.com/lightning/r/Knowledge__kav/ka08W000000frOFQAY/view). This knowledge article contains important information about upgrade scenarios.
