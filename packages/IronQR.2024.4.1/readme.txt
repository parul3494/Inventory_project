IronQR is a library developed and maintained by Iron Software that helps C# Software Engineers to detect, read, and create QR Codes in .NET applications & websites with a sophisticated custom Machine Learning model.

Visit our website for a quick-start guide at  https://ironsoftware.com/csharp/qr/

C# Code Example
========================
using IronQr;
using IronSoftware.Drawing;

// Create QR Code
QrCode myQr = QrWriter.Write("hello world"); // Embedded value as string
AnyBitmap qrBitmap = myQr.Save(); // Bitmap object able to export as bytes or file
qrBitmap.SaveAs("qr.png"); // Save to disk

// Read QR Code
var qrReader = new QrReader(settings: optionalQrReaderSettings); // Create reader
IEnumerable<QrResult> results = qrReader.Read(new QrImageInput("image.jpg")); // Reader calls ML Model to detect and read
IEnumerable<QrResult> asyncResults = await qrReader.ReadAsync(new QrImageInput("image.jpg")); // Async version

// Advanced QR Creation
var optionalOptions = new QrOptions(QrErrorCorrectionLevel.High, 20); // Advanced QR Generation Options

QrCode myQr = QrWriter.Write("hello world", options: optionalOptions); // QR code created with options

var fancyBrandedQrSettings = new QrStyleOptions // Add logo, branding, coloring, rouding, etc.
{
    Dimensions = 300, // px
    Margins = 10, // px
    Color = Color.Black,
    Logo = new QrLogo
    {
        Bitmap = new AnyBitmap(new Uri("website.com/image.svg")),
        Width = 50,
        Height = 50,
        CornerRadius = 2
    }
};
AnyBitmap qrWithBranding = myQr.Save(fancyBrandedQrSettings);
qrWithBranding.SaveAs("qr_fancy.png");

Documentation Links
========================
API Reference : https://ironsoftware.com/csharp/qr/object-reference/api/
Licensing : https://ironsoftware.com/csharp/qr/licensing/
Support : support@ironsoftware.com

Compatibility
========================
* C#, F#, and VB.NET
* .NET 8, .NET 7, .NET 6, .NET 5, Core 2x & 3x, Standard 2.0 & 2.1, and Framework 4.6.2+
* Mobile, Console, Web, and Desktop Application
* Windows 10+, Mac 10.14, Linux (Debian, CentOS, Ubuntu), Android, iOS 12, Docker, Azure, and AWS
* Microsoft Visual Studio or Jetbrains ReSharper & Rider
