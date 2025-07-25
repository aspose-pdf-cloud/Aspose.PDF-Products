---
title: Ajouter des pièces jointes dans des documents PDF via Aspose.Pdf Cloud .NET SDK
url: net/attachments/add/
description: Ajouter des pièces jointes à des fichiers PDF avec Aspose.PDF Cloud SDK pour .NET. Intégrer des documents, des images et plus encore dans vos PDF.<|vq_5659|>
lastmod: 2024-10-29
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Ajouter des pièces jointes à PDF dans le SDK .NET" h2="API pour ajouter des pièces jointes dans des documents PDF avec Aspose.PDF Cloud .NET SDK" logoImageSrc="https://www.aspose.cloud/templates/aspose/img/products/pdf/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="pour .NET" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK pour .NET" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://www.aspose.cloud/templates/aspose/img/products/pdf/aspose_pdf-for-net.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://downloads.aspose.cloud/pdf/net" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="Comment ajouter des pièces jointes dans des documents PDF en utilisant l'API C# Cloud" %}}

Pour ajouter des pièces jointes dans des documents PDF, nous utiliserons
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
Ce SDK Cloud vous permet de créer facilement des applications créatrices, éditrices et convertisseuses de PDF basées sur le cloud en C#, ASP.NET ou d'autres langages .NET pour diverses plateformes cloud. Ouvrez
[NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
gestionnaire de paquets, recherchez
Aspose.PDF Cloud
et installez-le. Vous pouvez également utiliser la commande suivante depuis la console du gestionnaire de paquets.

{{% blocks/products/pf/agp/code-block title="Commande" offSpacer="true" %}}

```powershell

PM> Install-Package Aspose.Pdf-Cloud 



```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Étapes pour ajouter des pièces jointes en utilisant le SDK .NET" %}}

{{% blocks/products/pf/agp/text %}}

Une addition de base de pièces jointes de manière programmatique avec
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
APIs peut être réalisée en quelques lignes de code.

{{% /blocks/products/pf/agp/text %}}

1. Créer un objet AttachmentInfo
1. Télécharger les fichiers sur le stockage cloud
1. Ajouter la pièce jointe au PDF
1. Vérifier la réponse et enregistrer le PDF mis à jour

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/feature-section-col title="Exigences du système" %}}

{{% blocks/products/pf/agp/text %}}

Les développeurs Aspose.PDF Cloud .NET peuvent facilement extraire et ajouter des pièces jointes dans des documents PDF. Les développeurs n'ont besoin que de quelques lignes de code.

+ .NET Framework 2.0 ou ultérieur
+ JSON.NET

{{% /blocks/products/pf/agp/text %}}

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Ce code exemple montre l'ajout de pièces jointes de document PDF en utilisant C#" offSpacer="" %}}

```cs

public static void AddAttachment()
{
    var STORAGE_FILE_NAME = "sample_attachment.pdf";
    var STORAGE_ATTACHMENT_FILE_NAME = "file_example_MP3_700KB.mp3";
    var LOCAL_FILE_NAME = @"C:\Samples\Attachments\sample_attachment.pdf";
    var LOCAL_ATTACHMENT_FILE_NAME = @"C:\Samples\Attachments\file_example_MP3_700KB.mp3";
    var RESULT_FILE_NAME = @"C:\Samples\Attachments\sample_attachment_new.pdf";

    var attachmentInfo = new AttachmentInfo(
        STORAGE_ATTACHMENT_FILE_NAME,
        "Sample attachment",
        Path.GetFileName(LOCAL_ATTACHMENT_FILE_NAME),
        "audio/mpeg");

    PdfApi.UploadFile(STORAGE_FILE_NAME, File.OpenRead(LOCAL_FILE_NAME));
    PdfApi.UploadFile(STORAGE_ATTACHMENT_FILE_NAME, File.OpenRead(LOCAL_ATTACHMENT_FILE_NAME));
    var response = PdfApi.PostAddDocumentAttachment(STORAGE_FILE_NAME, attachmentInfo);
    Console.WriteLine(response.Code);
    if (response.Code == 200)
    {
        PdfApi.DownloadFile(STORAGE_FILE_NAME)
            .CopyTo(File.OpenWrite(RESULT_FILE_NAME));
    }
}
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
