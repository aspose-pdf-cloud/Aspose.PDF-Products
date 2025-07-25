---
title: Adjuntar archivos adjuntos en documentos PDF a través del SDK de Aspose.Pdf Cloud para .NET
url: net/attachments/add/
description: Agregue archivos adjuntos a archivos PDF con Aspose.PDF Cloud SDK para .NET. Incruste documentos, imágenes y más en sus PDF.
lastmod: 2024-10-29
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Agregar archivos adjuntos a PDF en el SDK de .NET" h2="API para agregar archivos adjuntos en documentos PDF con Aspose.PDF Cloud .NET SDK" logoImageSrc="https://www.aspose.cloud/templates/aspose/img/products/pdf/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="para .NET" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK para .NET" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://www.aspose.cloud/templates/aspose/img/products/pdf/aspose_pdf-for-net.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://downloads.aspose.cloud/pdf/net" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="Cómo adjuntar archivos en documentos PDF utilizando la API en la nube C#" %}}

Para agregar archivos adjuntos a documentos PDF, utilizaremos
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
Este SDK en la nube le permite crear fácilmente aplicaciones basadas en la nube para la creación, edición y conversión de PDF en C#, ASP.NET u otros lenguajes .NET para diversas plataformas en la nube. Abra
[NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
el administrador de paquetes, busque
Aspose.PDF Cloud
e instálelo. También puede usar el siguiente comando desde la consola del administrador de paquetes.

{{% blocks/products/pf/agp/code-block title="Comando" offSpacer="true" %}}

```powershell

PM> Install-Package Aspose.Pdf-Cloud 



```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Pasos para agregar archivos adjuntos utilizando el SDK de .NET" %}}

{{% blocks/products/pf/agp/text %}}

Un método básico para agregar archivos adjuntos de manera programática con
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
APIs puede lograrlo con solo unas pocas líneas de código.

{{% /blocks/products/pf/agp/text %}}

1. Crear un objeto AttachmentInfo
1. Cargar los archivos en el almacenamiento en la nube
1. Agregar el archivo adjunto al PDF
1. Verificar la respuesta y guardar el PDF actualizado

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/feature-section-col title="Requisitos del sistema" %}}

{{% blocks/products/pf/agp/text %}}

Los desarrolladores de Aspose.PDF Cloud .NET pueden extraer y agregar archivos adjuntos en documentos PDF fácilmente. Los desarrolladores solo necesitan unas pocas líneas de código.

+ .NET Framework 2.0 o posterior
+ JSON.NET

{{% /blocks/products/pf/agp/text %}}

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Este código de ejemplo muestra cómo agregar archivos adjuntos de un documento PDF utilizando C#" offSpacer="" %}}

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
