IronQR - The QR Library for .NET
=============================================================
Quickstart:  https://ironsoftware.com/csharp/qr/

Compatibility
=============================================================
Supports applications and websites developed in:
- .NET Framework 4.6.2 (and above) for Windows, Linux, MacOs, Android, and Azure
- .NET Core 2, 3 (and above) Windows, Linux, MacOs, Android, and Azure
- .NET 5 for Windows, Linux, MacOs, Android, and Azure
- .NET 6 for Windows, Linux, MacOs, Android, and Azure
- .NET 7 for Windows, Linux, MacOs, Android, and Azure
- .NET 8 for Windows, Linux, MacOs, Android, and Azure


C# Code Example
=============================================================
```
using IronQr;
using IronSoftware.Drawing;

// Create QR Code
QrCode myQr = QrWriter.Write("hello world");
AnyBitmap qrBitmap = myQr.Save();
qrBitmap.SaveAs("qr.png");

// Read QR Code
var qrReader = new QrReader(settings: optionalQrReaderSettings);
IEnumerable<QrResult> results = qrReader.Read(new QrImageInput("image.jpg"));
```


Documentation
=============================================================

- API Reference : https://ironsoftware.com/csharp/qr/object-reference/api/
- Licensing : https://ironsoftware.com/csharp/qr/licensing/
- Support : support@ironsoftware.com
