---
title: تحويل PDF إلى صور BMP عبر Cloud .NET SDK
url: net/conversion/pdf-to-bmp/
description: قم بتحويل ملفات PDF إلى تنسيق صورة BMP باستخدام Aspose.PDF Cloud SDK for .NET. إخراج عالي الدقة لملفات PDF الخاصة بك.
lastmod: 2022-03-17
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="تحويل PDF إلى BMP في .NET SDK" h2="قم بتحويل مستندات PDF إلى تنسيق BMP باستخدام Aspose.PDF Cloud .NET SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for .NET" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-net.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-dotnet" >}}

{{% blocks/products/pf/agp/content h2="كيفية تحويل PDF إلى BMP باستخدام SDK for .NET" %}}

من أجل تحويل PDF إلى BMP، سنستخدم
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
يسمح لك هذا الـ Cloud SDK ببناء تطبيقات منشئ ومحرر ومحول PDF قائمة على السحابة بسهولة في C#، ASP.NET، أو لغات .NET الأخرى لمختلف المنصات السحابية. افتح
[NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
مدير الحزم، وابحث عن
Aspose.PDF Cloud
وقم بتثبيته. يمكنك أيضاً استخدام الأمر التالي من وحدة تحكم مدير الحزم.

{{% blocks/products/pf/agp/code-block title="أمر وحدة تحكم مدير الحزم" offSpacer="true" %}}

```powershell

     
    PM> Install-Package Aspose.Pdf-Cloud
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="خطوات تحويل PDF إلى BMP عبر .NET SDK" %}}

{{% blocks/products/pf/agp/text %}}

يمكن لمطوري Aspose.PDF Cloud تحميل وتحويل ملفات PDF إلى BMP بسهولة في بضعة أسطر من الكود.

{{% /blocks/products/pf/agp/text %}}

1. قم بإنشاء كائن Configuration جديد مع المفتاح السري والتطبيق الخاص بك
1. قم بإنشاء كائن للاتصال بـ Cloud API
1. قم برفع ملف المستند الخاص بك
1. قم بإجراء التحويل
1. قم بتنزيل النتيجة

{{% /blocks/products/pf/agp/feature-section-col %}}



{{% blocks/products/pf/agp/code-block title="يظهر هذا الكود عينة لتحويل PDF إلى BMP باستخدام Cloud .NET SDK" offSpacer="" %}}

```cs

    public static void ConvertPdfToBmp()
    {
        const string localImageFileName = @"C:\Samples\sample.pdf";
        const string storageImageFileName = "sample.pdf";
        const string resultFileName = "sample.bmp";
        
        // Get your AppSid and AppSecret https://dashboard.aspose.cloud (free registration required).
        var pdfApi = new PdfApi(AppSecret, AppSid);
        using var file = File.OpenRead(localImageFileName);
        pdfApi.UploadFile(storageImageFileName, file);

        var response = pdfApi.GetPageConvertToBmp(storageImageFileName, 1);
        response.CopyTo(File.OpenWrite(resultFileName));
        Console.WriteLine($"PDF to BMP result: {response.Length} bytes");
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< blocks/products/pf/agp/other-supported-section title="تحويلات أخرى مدعومة" subTitle="يمكنك أيضاً تحويل العديد من تنسيقات الملفات الأخرى" >}}

{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/bmp-to-pdf/" name="BMP TO PDF" description="صورة نقطية" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/emf-to-pdf/" name="EMF TO PDF" description="تنسيق ملف التعريف المحسّن" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/epub-to-pdf/" name="EPUB TO PDF" description="تنسيق الكتاب الإلكتروني" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/gif-to-pdf/" name="GIF TO PDF" description="تنسيق تبادل الرسومات" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/html-to-pdf/" name="HTML-TO-PDF" description="لغة ترميز النص الفائق" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/jpeg-to-pdf/" name="JPEG TO PDF" description="صورة JPEG" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/md-to-pdf/" name="MD TO PDF" description="ماركداون" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pcl-to-pdf/" name="PCL TO PDF" description="لغة أوامر الطابعة" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-bmp/" name="PDF TO BMP" description="صورة نقطية" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-docx/" name="PDF TO DOCX" description="وثيقة Office 2007+ Words" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-emf/" name="PDF TO EMF" description="تنسيق ملف التعريف المحسّن" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-epub/" name="PDF TO EPUB" description="تنسيق الكتاب الإلكتروني" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-gif/" name="PDF TO GIF" description="تنسيق تبادل الرسومات" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-html/" name="تحويل PDF إلى HTML" description="لغة توصيف النص التشعبي" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-jpeg/" name="تحويل PDF إلى JPEG" description="صورة JPEG" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pdfa/" name="تحويل PDF إلى PDF/A" description="تنسيق المستندات المحمولة/A" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-png/" name="تحويل PDF إلى PNG" description="رسومات الشبكة المحمولة" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pptx/" name="تحويل PDF إلى PPTX" description="تنسيق العرض التقديمي XML المفتوح" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-svg/" name="تحويل PDF إلى SVG" description="رسوميات متجهية قابلة للتوسع" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-tex/" name="تحويل PDF إلى TEX" description="نص مخرجات LaTeX" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-tiff/" name="تحويل PDF إلى TIFF" description="تنسيق الصورة الموسوم" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-txt/" name="تحويل PDF إلى TXT" description="وثيقة نصية" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-xlsx/" name="تحويل PDF إلى XLSX" description="ملف Excel OOXML" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-xps/" name="تحويل PDF إلى XPS" description="مواصفات ورق XML" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pptx/" name="تحويل PDF إلى PPTX" description="تنسيق العرض التقديمي XML المفتوح" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/png-to-pdf/" name="تحويل PNG إلى PDF" description="رسومات الشبكة المحمولة" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/svg-to-pdf/" name="تحويل SVG إلى PDF" description="رسوميات متجهية قابلة للتوسع" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/tex-to-pdf/" name="تحويل TEX إلى PDF" description="نص مخرجات LaTeX" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/text-to-pdf/" name="تحويل النص إلى PDF" description="وثيقة نصية" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/tiff-to-pdf/" name="تحويل TIFF إلى PDF" description="تنسيق الصورة الموسوم" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/xps-to-pdf/" name="تحويل XPS إلى PDF" description="مواصفات ورق XML" >}}

{{< /blocks/products/pf/agp/other-supported-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}



