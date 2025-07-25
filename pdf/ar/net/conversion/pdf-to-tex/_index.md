---
title: تحويل PDF إلى TEX عبر Cloud .NET SDK
url: net/conversion/pdf-to-tex/
description: حوّل ملفات PDF إلى ملفات LaTeX (TeX) باستخدام Aspose.PDF Cloud SDK لـ .NET. لعمليات العمل الأكاديمية والتقنية المتقدمة.
lastmod: 2022-03-17
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="تحويل PDF إلى TEX في .NET SDK" h2="تحويل مستندات PDF إلى تنسيق TEX باستخدام Aspose.PDF Cloud .NET SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for .NET" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-net.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-dotnet" >}}

{{% blocks/products/pf/agp/content h2="كيفية تحويل PDF إلى TEX باستخدام SDK لـ .NET" %}}

من أجل تحويل PDF إلى TEX، سنستخدم
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
تسمح لك هذه السحابة SDK ببناء تطبيقات إنشاء وتحرير وتحويل PDF قائمة على السحابة بسهولة باستخدام C#، ASP.NET، أو لغات .NET الأخرى لمنصات السحابة المختلفة. افتح
[NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
مدير الحزم، وابحث عن
Aspose.PDF Cloud
وقم بتثبيته. يمكنك أيضًا استخدام الأمر التالي من وحدة التحكم في مدير الحزم.

{{% blocks/products/pf/agp/code-block title="أمر وحدة التحكم في مدير الحزم" offSpacer="true" %}}

```powershell

     
    PM> Install-Package Aspose.Pdf-Cloud
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="خطوات تحويل PDF إلى TEX عبر .NET SDK" %}}

{{% blocks/products/pf/agp/text %}}

يمكن لمطوري Aspose.PDF Cloud بسهولة تحميل وتحويل ملفات PDF إلى TEX في بضع سطور من التعليمات البرمجية.

{{% /blocks/products/pf/agp/text %}}

1. قم بإنشاء كائن تكوين جديد مع سر التطبيق والمفتاح الخاص بك
1. أنشئ كائنًا للاتصال بـ Cloud API
1. قم بتحميل ملف المستند الخاص بك
1. قم بتنفيذ التحويل
1. قم بتنزيل النتيجة

{{% /blocks/products/pf/agp/feature-section-col %}}



{{% blocks/products/pf/agp/code-block title="يعرض هذا الرمز النموذجي تحويل PDF إلى TEX باستخدام Cloud .NET SDK" offSpacer="" %}}

```cs

    public static void ConvertPdfToLaTex()
    {
        const string localImageFileName = @"C:\Samples\sample.pdf";
        const string storageImageFileName = "sample.pdf";
        const string resultFileName = "sample-tex.zip";

        // Get your AppSid and AppSecret https://dashboard.aspose.cloud (free registration required).
        var pdfApi = new PdfApi(AppSecret, AppSid);
        using var file = File.OpenRead(localImageFileName);
        pdfApi.UploadFile(storageImageFileName, file);

        var response = pdfApi.GetPdfInStorageToTeX(storageImageFileName);
        response.CopyTo(File.OpenWrite(resultFileName));
        Console.WriteLine($"PDF to LaTeX result: {response.Length} bytes");
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< blocks/products/pf/agp/other-supported-section title="تحويلات أخرى مدعومة" subTitle="يمكنك أيضًا تحويل العديد من تنسيقات الملفات الأخرى" >}}

{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/bmp-to-pdf/" name="BMP إلى PDF" description="صورة نقطية" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/emf-to-pdf/" name="EMF إلى PDF" description="تنسيق ملف ميتافايل محسّن" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/epub-to-pdf/" name="EPUB إلى PDF" description="تنسيق الكتاب الإلكتروني" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/gif-to-pdf/" name="GIF إلى PDF" description="تنسيق تبادل الرسوم" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/html-to-pdf/" name="HTML إلى PDF" description="لغة ترميز النص التشعبي" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/jpeg-to-pdf/" name="JPEG إلى PDF" description="صورة JPEG" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/md-to-pdf/" name="MD إلى PDF" description="ماركداون" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pcl-to-pdf/" name="PCL إلى PDF" description="لغة أوامر الطابعة" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-bmp/" name="PDF إلى BMP" description="صورة نقطية" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-docx/" name="PDF إلى DOCX" description="مستندات Office 2007+" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-emf/" name="PDF إلى EMF" description="تنسيق ملف ميتافايل محسّن" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-epub/" name="PDF إلى EPUB" description="تنسيق الكتاب الإلكتروني" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-gif/" name="PDF إلى GIF" description="تنسيق تبادل الرسوم" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-html/" name="PDF إلى HTML" description="لغة ترميز النص التشعبي" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-jpeg/" name="PDF إلى JPEG" description="صورة JPEG" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pdfa/" name="PDF إلى PDF/A" description="تنسيق المستند المحمول/A" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-png/" name="PDF إلى PNG" description="رسومات الشبكة المحمولة" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pptx/" name="PDF إلى PPTX" description="تنسيق العرض التقديمي XML المفتوح" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-svg/" name="PDF إلى SVG" description="رسومات متجهة قابلة للتطوير" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-tex/" name="PDF إلى TEX" description="نص إخراج LaTeX" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-tiff/" name="PDF إلى TIFF" description="تنسيق الصورة الموسومة" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-txt/" name="PDF إلى TXT" description="مستند نصي" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-xlsx/" name="PDF إلى XLSX" description="ملف Excel OOXML" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-xps/" name="PDF إلى XPS" description="مواصفات ورق XML" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pptx/" name="PDF إلى PPTX" description="تنسيق العرض التقديمي XML المفتوح" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/png-to-pdf/" name="PNG إلى PDF" description="رسومات الشبكة المحمولة" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/svg-to-pdf/" name="SVG إلى PDF" description="رسومات متجهة قابلة للتطوير" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/tex-to-pdf/" name="TEX إلى PDF" description="نص إخراج LaTeX" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/text-to-pdf/" name="TEXT إلى PDF" description="مستند نصي" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/tiff-to-pdf/" name="TIFF إلى PDF" description="تنسيق الصورة الموسومة" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/xps-to-pdf/" name="XPS إلى PDF" description="مواصفات ورق XML" >}}

{{< /blocks/products/pf/agp/other-supported-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}


