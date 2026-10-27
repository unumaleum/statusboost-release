# StatusBoost release notes

## 2.0.1 release candidate 2 (2026-10-27, not signed)

- **Checksum file:** `SHA256SUMS.txt` now works with `sha256sum -c` and `shasum -c`. In release candidate 1, its Windows line endings made those tools report the installer as missing.
- **Installing it replaces release candidate 1.** Your settings are kept.
- StatusBoost itself is unchanged, apart from its version number, 2.0.1.

## 2.0.0 release candidate 1 (2026-10-27, not signed)

A test release for trusted testers. The signed release follows with a higher version number.

- **Installer:** StatusBoost now comes as a Windows installer that includes its own Java. You no longer need to install Java.
- **Stacked systems:** combine several cages into one system in Find Device. Each further cage is shown with its own power modules and alarms.
- **Connection loss:** when a system stops answering, StatusBoost shows "Disconnected" with blank fields, and reconnects by itself.
- **AB Bus:** the field is shown only when AB-bus monitoring is enabled, and shows "Fail" when the system reports an AB-bus fault.
- **Transfer switches:** KC Skinny transfer switches show the transfer switch fields too.
- **Safer configuration:** each change is sent separately and confirmed by the system.
- **Network Feature Setup:** checks the addresses, asks before restarting the network card, sends only what changed, and no longer turns off the SNMP agent and web server.
