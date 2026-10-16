# Windows Server Lifecycle Audit Tool

PowerShell-based Active Directory server inventory and lifecycle reporting.

This repository contains a PowerShell script that discovers Windows Server computer objects in Active Directory, tests connectivity, gathers operating system and hardware details through CIM, and exports the results to CSV or Excel.

## Overview

The tool is intended for infrastructure assessment, lifecycle planning, and inventory review. It provides a timestamped report of Windows Server systems found in Active Directory and highlights the oldest servers based on the operating system installation date.

## Features

- Discovers Active Directory computer objects whose operating system contains `Server`.
- Tests basic network reachability before attempting remote inventory.
- Collects operating system, build, installation date, last boot time, manufacturer, model, and BIOS date.
- Classifies systems as virtual or physical using the reported hardware model.
- Calculates estimated years in service from the operating system installation date.
- Exports reports as UTF-8 CSV or formatted XLSX.
- Displays progress, online and offline totals, and the ten oldest servers.

## Prerequisites

- Windows PowerShell 5.1 or a compatible Windows PowerShell environment.
- Network connectivity to a domain controller.
- [ActiveDirectory PowerShell module](https://learn.microsoft.com/en-us/powershell/module/activedirectory/?view=windowsserver2025-ps), typically installed through RSAT.
- Read access to Active Directory computer objects.
- Administrative permissions on target servers for remote CIM inventory.
- Windows Remote Management and the required firewall rules enabled on target servers.
- For XLSX export, the third-party [ImportExcel module](https://github.com/dfinke/ImportExcel).

### PowerShell modules

The script requires the ActiveDirectory module. CSV export uses built-in PowerShell capabilities. Excel export depends on ImportExcel.

```powershell
Install-Module -Name ImportExcel -Scope CurrentUser
```

## Repository layout

```text
README.md
WindowsServerLifecycleAudit.ps1
```

## Usage

1. Clone or download the repository.
2. Open Windows PowerShell using an account that can read Active Directory and remotely query the target servers.
3. Run the script from the repository directory.

```powershell
.\WindowsServerLifecycleAudit.ps1
```

When prompted, enter an export folder and select an output format:

- `1` — CSV
- `2` — Excel XLSX

The script creates the export folder when it does not exist and writes a timestamped file such as `ServerAudit_20261016_132500.csv`.

## Report fields

| Field | Description |
|---|---|
| `ServerName` | Active Directory computer name. |
| `Reachable` | `Yes`, `No`, or `Error` based on connectivity and collection results. |
| `OperatingSystem` | Operating system caption returned by CIM, or the Active Directory value when offline. |
| `BuildNumber` | Windows build number. |
| `InstallDate` | Operating system installation date. |
| `YearsInService` | Estimated age in years, calculated from `InstallDate`. |
| `LastBootTime` | Most recent operating system start time. |
| `ServerType` | Virtual or Physical, inferred from the reported model. |
| `Manufacturer` | System manufacturer. |
| `Model` | System model. |
| `BIOSDate` | BIOS release date. |

## How it works

1. [`Get-ADComputer`](https://learn.microsoft.com/en-us/powershell/module/activedirectory/get-adcomputer?view=windowsserver2025-ps) retrieves computer objects with an operating system value matching `Server`.
2. Each computer is tested with a single ICMP echo request.
3. Reachable systems are queried with [`Get-CimInstance`](https://learn.microsoft.com/en-us/powershell/module/cimcmdlets/get-ciminstance?view=powershell-7.6) for `Win32_OperatingSystem`, `Win32_ComputerSystem`, and `Win32_BIOS`.
4. The collected objects are exported in the selected format.
5. A console summary reports discovered, online, and offline totals and lists the ten oldest systems.

## Limitations

- Discovery depends on the Active Directory `OperatingSystem` attribute being populated and containing `Server`.
- A server that blocks ICMP is recorded as offline even when CIM is available.
- `YearsInService` reflects the current operating system installation date, not the hardware purchase or deployment date.
- Virtual or physical classification is heuristic and may not recognize every hypervisor or vendor model.
- The script does not evaluate Microsoft product lifecycle dates or determine support status.
- The script processes systems sequentially and may take time in large environments.

## Troubleshooting

### Unable to query Active Directory

- Confirm the ActiveDirectory module is installed and can be imported.
- Verify domain connectivity and DNS resolution.
- Run `Get-ADComputer` manually to validate directory access.

### Server shown as offline

- Confirm the server resolves in DNS.
- Check whether ICMP echo requests are blocked by host or network firewalls.
- Validate the computer object is current and has not been decommissioned.

### Reachable server returns `Error`

- Confirm the current account has administrative rights on the target server.
- Verify Windows Remote Management and CIM access.
- Check firewall rules, network segmentation, and name resolution.
- Test a direct query using `Get-CimInstance` before rerunning the audit.

### Excel export fails

- Confirm the ImportExcel module is installed and can be imported.
- Verify access to PowerShell Gallery if the script must install the module.
- Use CSV export in restricted or offline environments.

## Security considerations

- Use a dedicated administrative workstation or approved management host.
- Apply least privilege while ensuring the account has the rights required for remote CIM queries.
- Review generated reports before sharing because they contain infrastructure inventory data.
- Do not commit generated CSV or XLSX reports to a public repository.
- Review third-party modules in accordance with organizational software supply-chain requirements.

## Contributing

Issues and pull requests are welcome. Keep changes focused, document new parameters or output fields, and test against both reachable and unreachable systems before submission.

## License

Add an approved `LICENSE` file to the repository before publishing or redistributing the script. This README does not grant rights to Microsoft names, logos, trademarks, or third-party modules.

## Disclaimer

This sample is provided for illustration and testing. Validate it in a non-production environment before operational use. The script is not a substitute for an authoritative configuration management database, hardware asset system, or Microsoft product lifecycle assessment.

## Microsoft documentation

- [Get-ADComputer](https://learn.microsoft.com/en-us/powershell/module/activedirectory/get-adcomputer?view=windowsserver2025-ps)
- [ActiveDirectory module](https://learn.microsoft.com/en-us/powershell/module/activedirectory/?view=windowsserver2025-ps)
- [Get-CimInstance](https://learn.microsoft.com/en-us/powershell/module/cimcmdlets/get-ciminstance?view=powershell-7.6)
- [Collecting information about computers with PowerShell](https://learn.microsoft.com/en-us/powershell/scripting/samples/collecting-information-about-computers?view=powershell-7.6)

## Third-party dependency

- [ImportExcel on GitHub](https://github.com/dfinke/ImportExcel)

