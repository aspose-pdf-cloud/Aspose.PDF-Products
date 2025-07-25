---
title: تحويل PDF إلى EPUB عبر Cloud .NET SDK
url: net/conversion/pdf-to-epub/
description: قم بتحويل مستندات PDF إلى كتب إلكترونية بصيغة EPUB باستخدام Aspose.PDF Cloud SDK for .NET. إعادة تدفق المحتوى لقراءة الجوال.
lastmod: 2022-03-17
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="تحويل PDF إلى EPUB في .NET SDK" h2="تحويل مستندات PDF إلى صيغة EPUB باستخدام Aspose.PDF Cloud .NET SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for .NET" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-net.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-dotnet" >}}

{{% blocks/products/pf/agp/content h2="كيفية تحويل PDF إلى EPUB باستخدام SDK لـ .NET" %}}

من أجل تحويل PDF إلى EPUB، سنستخدم
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
يتيح لك هذا الـ Cloud SDK بسهولة بناء تطبيقات إنشاء وتحرير وتحويل PDF قائمة على السحابة بـ C#، ASP.NET، أو لغات .NET الأخرى لمختلف منصات السحابة. افتح
[NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
مدير الحزم، ابحث عن
Aspose.PDF Cloud
وقم بتثبيته. يمكنك أيضًا استخدام الأمر التالي من وحدة تحكم مدير الحزم.

{{% blocks/products/pf/agp/code-block title="أمر وحدة تحكم مدير الحزم" offSpacer="true" %}}

```powershell

     
    PM> Install-Package Aspose.Pdf-Cloud
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="خطوات تحويل PDF إلى EPUB عبر .NET SDK" %}}

{{% blocks/products/pf/agp/text %}}

يمكن لمطوري Aspose.PDF Cloud بسهولة تحميل وتحويل ملفات PDF إلى EPUB في بضع سطور من الكود.

{{% /blocks/products/pf/agp/text %}}

1. إنشاء كائن تكوين جديد بمفتاح وتطبيق السر الخاص بك
1. إنشاء كائن للاتصال بـ Cloud API
1. تحميل ملف المستند الخاص بك
1. إجراء التحويل
1. تنزيل النتيجة

{{% /blocks/products/pf/agp/feature-section-col %}}



{{% blocks/products/pf/agp/code-block title="يعرض هذا المثال كود تحويل PDF إلى EPUB باستخدام Cloud .NET SDK" offSpacer="" %}}

```cs

    public static void ConvertPdfToEpub()
    {
        const string localImageFileName = @"C:\Samples\sample.pdf";
        const string storageImageFileName = "sample.pdf";
        const string resultFileName = "sample.epub";
        
        // Get your AppSid and AppSecret https://dashboard.aspose.cloud (free registration required).
        var pdfApi = new PdfApi(AppSecret, AppSid);
        using var file = File.OpenRead(localImageFileName);
        pdfApi.UploadFile(storageImageFileName, file);

        var response = pdfApi.GetPdfInStorageToEpub(storageImageFileName);
        response.CopyTo(File.OpenWrite(resultFileName));
        Console.WriteLine($"PDF to EPUB result: {response.Length} bytes");
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< blocks/products/pf/agp/other-supported-section title="تحويلات أخرى مدعومة" subTitle="يمكنك أيضًا تحويل العديد من صيغ الملفات الأخرى" >}}

{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/bmp-to-pdf/" name="BMP إلى PDF" description="صورة نقطية" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/emf-to-pdf/" name="EMF إلى PDF" description="تنسيق ملف التعريف المحسن" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/epub-to-pdf/" name="EPUB إلى PDF" description="تنسيق الكتاب الإلكتروني" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/gif-to-pdf/" name="GIF إلى PDF" description="صيغة تبادل الرسومات" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/html-to-pdf/" name="HTML إلى PDF" description="لغة توصيف النص الفائق" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/jpeg-to-pdf/" name="JPEG إلى PDF" description="صورة JPEG" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/md-to-pdf/" name="MD إلى PDF" description="ماركداون" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pcl-to-pdf/" name="PCL إلى PDF" description="لغة أوامر الطابعة" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-bmp/" name="PDF إلى BMP" description="صورة نقطية" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-docx/" name="PDF إلى DOCX" description="وثيقة كلمات أوفيس 2007+" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-emf/" name="PDF إلى EMF" description="تنسيق ملف التعريف المحسن" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-epub/" name="PDF إلى EPUB" description="تنسيق الكتاب الإلكتروني" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-gif/" name="PDF إلى GIF" description="صيغة تبادل الرسومات" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-html/" name="PDF TO HTML" description="لغة توصيف النص الفائق" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-jpeg/" name="PDF TO JPEG" description="صورة JPEG" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pdfa/" name="PDF TO PDF/A" description="تنسيق المستند المحمول/A" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-png/" name="PDF TO PNG" description="رسومات الشبكة المحمولة" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pptx/" name="PDF TO PPTX" description="تنسيق عرض XML المفتوح" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-svg/" name="PDF TO SVG" description="رسومات متجهة قابلة للتحجيم" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-tex/" name="PDF TO TEX" description="نص إخراج LaTeX" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-tiff/" name="PDF TO TIFF" description="تنسيق صورة موسوم" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-txt/" name="PDF TO TXT" description="مستند نصي" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-xlsx/" name="PDF TO XLSX" description="ملف Excel OOXML" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-xps/" name="PDF TO XPS" description="مواصفات الورق XML" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pptx/" name="PDF TO PPTX" description="تنسيق عرض XML المفتوح" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/png-to-pdf/" name="PNG TO PDF" description="رسومات الشبكة المحمولة" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/svg-to-pdf/" name="SVG TO PDF" description="رسومات متجهة قابلة للتحجيم" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/tex-to-pdf/" name="TEX TO PDF" description="نص إخراج LaTeX" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/text-to-pdf/" name="TEXT TO PDF" description="مستند نصي" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/tiff-to-pdf/" name="TIFF TO PDF" description="تنسيق صورة موسوم" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/xps-to-pdf/" name="XPS TO PDF" description="مواصفات الورق XML" >}}

{{< /blocks/products/pf/agp/other-supported-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}



