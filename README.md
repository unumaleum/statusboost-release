# StatusBoost

StatusBoost monitors Exeltech KC power systems over your network: the battery, inverter, utility and output values, alarms, power modules and transfer switches, for one system or several stacked cages.

StatusBoost is free to use, copy and distribute; see the [license](LICENSE.txt).

> **Release candidate, not signed yet.** StatusBoost 2.0 is in testing with trusted testers. Its installer is not digitally signed yet, so Windows names the publisher as "Unknown publisher" instead of Exeltech:
>
> - **When you open the downloaded `.msi`,** Windows may show "Windows protected your PC". Click **More info**, then **Run anyway**.
> - **Windows' administrator prompt** shows "Publisher: Unknown". Click **Yes**.
>
> Check the download's SHA256 hash first, as described below. The user guide describes the signed installer, which shows Exeltech as the publisher. The signed release will have a higher version number, and installing it replaces this one.

## Requirements

- Windows 10 or 11, 64-bit.
- A network connection to the system. StatusBoost finds the system on the local network; its PC and the system must be able to reach each other.
- Nothing else: the installer includes the Java runtime StatusBoost needs.

## Install

1. Open **[Releases](../../releases)** and download `StatusBoost-<version>.msi` from the newest release.
2. Check the download, as described below.
3. Run the `.msi`, accept the license and choose the folder. Windows asks for administrator rights; click **Yes**.
4. Start StatusBoost from the Start menu (folder "Exeltech") or the desktop shortcut.

**The firewall rule:** the installer also adds a Windows Firewall rule that lets StatusBoost receive the systems' answers from your local network only, so Windows doesn't ask about the firewall the first time StatusBoost searches for systems.

## Check the download

Each release lists the SHA256 hash of its installer, in `SHA256SUMS.txt` and in the release notes. A matching hash shows the file is complete and unchanged.

In PowerShell, in the folder you downloaded to:

```powershell
Get-FileHash .\StatusBoost-<version>.msi -Algorithm SHA256
```

Or in a Command Prompt:

```
certutil -hashfile StatusBoost-<version>.msi SHA256
```

Compare the result with the release's hash; upper or lower case doesn't matter. If they differ, don't run the file; download it again.

## First connection

Choose **Tools → Device Connection → Find...**, select your system and click **OK**. The user guide (Section 5.2) explains the steps, including stacked systems.

## Upgrade

Run the newer `.msi`. It replaces the installed version, and your settings are kept: StatusBoost stores them in `%APPDATA%\StatusBoost`, not in its install folder.

## Uninstall

Windows **Settings → Apps → StatusBoost → Uninstall**, and click **Yes** when Windows asks for administrator rights.

- **Removed with it:** its firewall rule.
- **Kept:** your settings, in `%APPDATA%\StatusBoost`. Delete that folder to remove them too.

## User guide

`sbguide.pdf` is attached to each release, and StatusBoost opens it from **Help → User Guide**.

## Privacy

Exeltech does not collect any information through StatusBoost. It sends nothing about you, your PC, your systems or how you use it to Exeltech or anyone else: no analytics, no telemetry, no update checks, no accounts.

StatusBoost talks only to the Exeltech systems on your network:

| What | How |
|---|---|
| Finds systems on the local network | UDP broadcast, port 6006 |
| Reads and configures a system | Modbus TCP, port 502 |
| Network Feature Setup | SNMP, UDP port 161 |

What it reads stays on your PC, and its settings are stored only on your PC, in `%APPDATA%\StatusBoost`. The links in the Help menu and the About box open Exeltech's website in your browser, and only when you click them.

## Support

Contact Exeltech technical support: <https://www.exeltech.com>.

## License

StatusBoost is free, under the [StatusBoost License Agreement](LICENSE.txt), which the installer also shows. It includes third-party software under its own licenses, listed in section 10 of the agreement.
