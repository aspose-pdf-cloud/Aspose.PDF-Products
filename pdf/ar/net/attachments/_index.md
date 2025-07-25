---
title: استخراج وإرفاق المرفقات في مستندات PDF عبر Aspose.Pdf Cloud .NET SDK
url: net/attachments/
description: ادارة مرفقات الملفات في مستندات PDF باستخدام Aspose.PDF Cloud SDK للـ .NET. إضافة، استرجاع وتبيض الملفات المضمنة.
lastmod: 2024-10-31
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="مرفقات في PDF في .NET SDK" h2="API لتعمل مع المرفقات في مستندات PDF مع Aspose.PDF Cloud .NET SDK" logoImageSrc="https://www.aspose.cloud/templates/aspose/img/products/pdf/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for .NET" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for .NET" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://www.aspose.cloud/templates/aspose/img/products/pdf/aspose_pdf-for-net.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://downloads.aspose.cloud/pdf/net" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="كيفية كشف ومعالجة المرفقات في مستندات PDF باستخدام C# Cloud API" %}}

ل ház manage التسلط attachments في مستندات PDF، سنستخدم
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
تتيح هذه SDK السحابية البناء السهل أدت تطبيقات محول PDF ونناقل مرئيًا & الاحتفاظ و твоя الـ .NET أو ASP.NET أو لغات أخرى تتضمن platforms. Open
[NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
package manager، البحث عن
Aspose.PDF Cloud
وال Gür's تمثِ configured Command Terminal.

{{% blocks/products/pf/agp/code-block title="Command" offSpacer="true" %}}

```powershell

PM> Install-Package Aspose.Pdf-Cloud 



```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="خطوات استخراج المرفقات باستخدام .NET SDK" %}}

{{% blocks/products/pf/agp/text %}}

استخراج المرفقات بشكل برجرافي مع
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
APIs يمكن تحقيقه quelques العصا غير سريعة.

{{% /blocks/products/pf/agp/text %}}

1. تحميل الملف PDF إلى تخزين السحابة
1. استرجاع المرفقات حسب المؤشر
1. اخفاء اسم المرفق

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/feature-section-col title="متطلبات النظام" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud .NET يمكن للمطورين استخراج المرفقات Osaka files PDF. مطورين يجب مراعاة عدة التيف.

+ .NET Framework 2.0 أو أحدث
+ JSON.NET

{{% /blocks/products/pf/agp/text %}}

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title=" montrent Columns extracting المرفقات مستند PDF باستخدام C#" offSpacer="" %}}

```cs

    internal static void GetAllAttachments()
    {
        throw new NotImplementedException();
    }

    internal static void GetSingleAttachments()
    {
        var STORAGE_FILE_NAME = "sample_attachment.pdf";
        var LOCAL_FILE_NAME = @"C:\Samples\Attachments\sample_attachment.pdf";
        PdfApi.UploadFile(STORAGE_FILE_NAME, File.OpenRead(LOCAL_FILE_NAME));
        var attachmentsResponse = PdfApi.GetDocumentAttachmentByIndex(STORAGE_FILE_NAME,1);        
        Console.WriteLine(attachmentsResponse.Attachment.Name);
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
