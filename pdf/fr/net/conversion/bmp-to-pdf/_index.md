---
title: Convertir BMP en PDF via Cloud .NET SDK
url: net/conversion/bmp-to-pdf/
description: Convertissez des images BMP en PDF avec Aspose.PDF Cloud SDK pour .NET. Transformez sans effort des fichiers bitmap en PDF de haute qualité.
lastmod: 2022-03-17
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Convertir BMP en PDF dans le SDK .NET" h2="Exportez des documents BMP vers plusieurs formats, y compris PDF avec Aspose.PDF Cloud .NET SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK pour .NET" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-net.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-dotnet" >}}

{{% blocks/products/pf/agp/content h2="Comment convertir BMP en PDF en utilisant le SDK pour .NET" %}}

Pour convertir BMP en PDF, nous utiliserons
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
Ce SDK Cloud vous permet de créer facilement des applications de création, d'édition et de conversion de PDF basées sur le cloud en C#, ASP.NET ou d'autres langages .NET pour diverses plateformes cloud. Ouvrez
[NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
gestionnaire de packages, recherchez
Aspose.PDF Cloud
et installez. Vous pouvez également utiliser la commande suivante depuis la console du gestionnaire de packages.

{{% blocks/products/pf/agp/code-block title="Commande de la console du gestionnaire de packages" offSpacer="true" %}}

```powershell

     
    PM> Install-Package Aspose.Pdf-Cloud
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Étapes pour convertir BMP en PDF via le SDK .NET" %}}

{{% blocks/products/pf/agp/text %}}

Les développeurs Aspose.PDF Cloud peuvent facilement charger et convertir des fichiers BMP en PDF en seulement quelques lignes de code.

{{% /blocks/products/pf/agp/text %}}

1. Créez un nouvel objet Configuration avec votre Secret et Clé d'application
1. Créez un objet pour se connecter à l'API Cloud
1. Téléchargez votre fichier document
1. Effectuez la conversion
1. Téléchargez le résultat

{{% /blocks/products/pf/agp/feature-section-col %}}



{{% blocks/products/pf/agp/code-block title="Cet exemple de code montre la conversion BMP en PDF avec le SDK Cloud .NET" offSpacer="" %}}

```cs

    public static void ConvertBmpToPdf()
    {
        const string localImageFileName = @"C:\Samples\sample.bmp";
        const string storageImageFileName = "sample.bmp";
        const string resultFileName = "sample-bmp-to-pdf.pdf";
        
        // Get your AppSid and AppSecret https://dashboard.aspose.cloud (free registration required).
        var pdfApi = new PdfApi(AppSecret, AppSid);

        using var file = File.OpenRead(localImageFileName);
        pdfApi.UploadFile(storageImageFileName, file);

        var imageTemplatesRequest = new ImageTemplatesRequest(IsOCR: false,
            ImagesList: [new ImageTemplate(ImagePath: storageImageFileName, ImageSrcType: ImageSrcType.Common)]
        );
        
        var response = pdfApi.PutImageInStorageToPdf(resultFileName, imageTemplatesRequest);
        Console.WriteLine($"BMP to PDF result: {response.Status}");
        pdfApi.DownloadFile(resultFileName)
            .CopyTo(File.Create(resultFileName));
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< blocks/products/pf/agp/other-supported-section title="Autres conversions prises en charge" subTitle="Vous pouvez également convertir de nombreux autres formats de fichiers" >}}

{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/bmp-to-pdf/" name="BMP EN PDF" description="Image Bitmap" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/emf-to-pdf/" name="EMF EN PDF" description="Format Metafile Amélioré" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/epub-to-pdf/" name="EPUB EN PDF" description="Format E-book" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/gif-to-pdf/" name="GIF EN PDF" description="Format d'Échange Graphique" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/html-to-pdf/" name="HTML-EN-PDF" description="Langage de Balisage Hypertexte" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/jpeg-to-pdf/" name="JPEG EN PDF" description="Image JPEG" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/md-to-pdf/" name="MD EN PDF" description="Markdown" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pcl-to-pdf/" name="PCL EN PDF" description="Langage de Commande Imprimante" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-bmp/" name="PDF EN BMP" description="Image Bitmap" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-docx/" name="PDF EN DOCX" description="Document Words Office 2007+" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-emf/" name="PDF EN EMF" description="Format Metafile Amélioré" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-epub/" name="PDF EN EPUB" description="Format E-book" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-gif/" name="PDF EN GIF" description="Format d'Échange Graphique" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-html/" name="PDF VERS HTML" description="Langage de balisage hypertexte" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-jpeg/" name="PDF VERS JPEG" description="Image JPEG" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pdfa/" name="PDF VERS PDF/A" description="Format de document portable/A" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-png/" name="PDF VERS PNG" description="Graphiques réseau portables" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pptx/" name="PDF VERS PPTX" description="Format de présentation Open XML" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-svg/" name="PDF VERS SVG" description="Graphiques vectoriels évolutifs" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-tex/" name="PDF VERS TEX" description="Texte de sortie LaTeX" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-tiff/" name="PDF VERS TIFF" description="Format d'image étiqueté" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-txt/" name="PDF VERS TXT" description="Document texte" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-xlsx/" name="PDF VERS XLSX" description="Fichier Excel OOXML" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-xps/" name="PDF VERS XPS" description="Spécifications de papier XML" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pptx/" name="PDF VERS PPTX" description="Format de présentation Open XML" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/png-to-pdf/" name="PNG VERS PDF" description="Graphiques réseau portables" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/svg-to-pdf/" name="SVG VERS PDF" description="Graphiques vectoriels évolutifs" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/tex-to-pdf/" name="TEX VERS PDF" description="Texte de sortie LaTeX" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/text-to-pdf/" name="TEXTE VERS PDF" description="Document texte" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/tiff-to-pdf/" name="TIFF VERS PDF" description="Format d'image étiqueté" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/xps-to-pdf/" name="XPS VERS PDF" description="Spécifications de papier XML" >}}

{{< /blocks/products/pf/agp/other-supported-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
