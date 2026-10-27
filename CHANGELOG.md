# StatusBoost release notes

## 2.0.0 (not released yet)

- **Installer:** StatusBoost now comes as a Windows installer that includes its own Java. You no longer need to install Java.
- **Stacked systems:** combine several cages into one system in Find Device. Each further cage is shown with its own power modules and alarms.
- **Connection loss:** when a system stops answering, StatusBoost shows "Disconnected" with blank fields, and reconnects by itself.
- **AB Bus:** the field is shown only when AB-bus monitoring is enabled, and shows "Fail" when the system reports an AB-bus fault.
- **Transfer switches:** KC Skinny transfer switches show the transfer switch fields too.
- **Safer configuration:** each change is sent separately and confirmed by the system.
- **Network Feature Setup:** checks the addresses, asks before restarting the network card, sends only what changed, and no longer turns off the SNMP agent and web server.
