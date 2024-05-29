# Bary.McProtocol
- McProtocol over Serial Port use 1C frame
# Installation 
Nuget Packages are provided:
- McProtocol.Serial.Frame1C.net
# Example
```

var comPort = "COM1";
var baudRate = 9600;
var dataBit = 8;
var parity = Parity.None;
var stopBits = StopBits.One;

var _plcClient = new FxRS485Client(comPort, baudRate, dataBit, parity, stopBits, 5);

string stationNo = "00";
string pcNo = "FF";

var readWord = _plcClient.WordRead(stationNo, pcNo, "D0800", 50);
var writeWord = _plcClient.WordWrite(stationNo, pcNo, "D0845", 1, "1A2B");
var getFlag = _plcClient.BitRead(stationNo, pcNo, "M0502", 1);
var setFlag = _plcClient.BitWrite(stationNo, pcNo, "M0502", 1, "0");

```
