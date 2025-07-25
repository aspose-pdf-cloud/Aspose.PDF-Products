---
title: تحويل PDF إلى TIFF عبر Cloud Node.js SDK
url: nodejs/conversion/pdf-to-tiff/
description: تحويل ملفات PDF إلى صور TIFF باستخدام Aspose.PDF Cloud SDK لـ Node.js. مثالي لأغراض الأرشفة ومسح المستندات.
lastmod: 2022-03-17
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="تحويل PDF إلى TIFF في Node.js SDK" h2="تصدير وثائق PDF إلى تنسيقات متعددة بما في ذلك TIFF مع Aspose.PDF Cloud Node.js SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="كيفية تحويل PDF إلى TIFF باستخدام Node.js SDK" %}}

لتحويل PDF إلى TIFF، سنستخدم
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/)
يساعد هذا الـ SDK السحابي مبرمجي Node.js في تطوير تطبيقات إنشاء وتعليق وتحرير وتحويل PDF عبر السحابة باستخدام لغة البرمجة Node.js عبر Aspose.PDF REST API. افتح
[NPM](https://www.npmjs.com/package/asposepdfcloud)
مدير الحزم، ابحث عن
Aspose.PDF Cloud,
وقم بتثبيته. يمكنك أيضًا استخدام الأمر التالي من وحدة التحكم في مدير الحزم.

{{% blocks/products/pf/agp/code-block title="أمر وحدة التحكم في مدير الحزم" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="خطوات تحويل PDF إلى TIFF عبر Node.js" %}}

{{% blocks/products/pf/agp/text %}}

يمكن لمطوري Aspose.PDF Cloud Node.js تحميل وتحويل ملفات PDF إلى TIFF بسهولة في بضعة أسطر من الشيفرة.

{{% /blocks/products/pf/agp/text %}}

1. قم بتحميل مفتاح التطبيق والسر من ملف JSON أو تعيين بيانات الاعتماد بطريقة أخرى
1. إنشاء كائن للاتصال بـ Cloud API
1. تحميل ملف المستند الخاص بك
1. قم بتنفيذ التحويل باستخدام getPageConvertToTiff
1. قم بتنزيل النتيجة إذا لزم الأمر

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="تظهر هذه الشيفرة النموذجية تحويل PDF إلى TIFF Cloud Node.js SDK" offSpacer="" %}}

```js

    const fs = require("fs");
    const credentials = require("./credentials.json");
    const { PdfApi } = require("asposepdfcloud");

    // Load your Application Secret and Key from the JSON file or set credentials in another way
    async function convertPDFtoTIFF() {
        const localFileName = "C:\\Samples\\sample.pdf";
        const storageFileName = "sample.pdf";
        const pdfApi = new PdfApi(credentials.id, credentials.key);
        let fileData = await fs.readFile(localImageFileName);
        try {
            let uploadResult = await pdfApi.uploadFile(storageFileName, fileData);
            console.log(uploadResult.response.text);
        }
        catch (error) {
            console.error(error.response.text);
        }

        try {
            let convertResult = await pdfApi.getPageConvertToTiff(storageFileName, 1);
            fs.writeFileSync("sample.tiff", convertResult.body);
            const buffer = await pdfApi.downloadFile(STORAGE_FILENAME);
        } catch (error) {
            console.error(error.response.text);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< blocks/products/pf/agp/other-supported-section title="تحويلات مدعومة أخرى" subTitle="يمكنك أيضًا تحويل MD إلى العديد من تنسيقات الملفات الأخرى بما في ذلك القليل منها المذكور أدناه." >}}

{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/bmp-to-pdf/" name="BMP إلى PDF" description="صورة نقطية" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/cgm-to-pdf/" name="CGM إلى PDF" description="تنسيق ثنائي لملفات Microsoft Word" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/emf-to-pdf/" name="EMF إلى PDF" description="وثيقة Office 2007+ Words" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/epub-to-pdf/" name="EPUB إلى PDF" description="تنسيق Enhanced Metafile" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/gif-to-pdf/" name="GIF إلى PDF" description="تنسيق تبادل الرسومات" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/html-to-pdf/" name="HTML إلى PDF" description="لغة ترميز النص الفائق" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/jpeg-to-pdf/" name="JPEG إلى PDF" description="مجموعة خبراء التصوير الرقمي" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/latex-to-pdf/" name="LATEX إلى PDF" description="نص إخراج LaTeX" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pcl-to-pdf/" name="PCL إلى PDF" description="لغة أوامر الطابعات" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/md-to-pdf/" name="MD إلى PDF" description="لغة ترميز النص Markdown" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-bmp/" name="PDF إلى BMP" description="صورة نقطية" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-epub/" name="PDF إلى EPUB" description="تنسيق الكتاب الإلكتروني" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-gif/" name="PDF إلى GIF" description="تنسيق تبادل الرسومات" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-html/" name="تحويل PDF إلى HTML" description="لغة ترميز النص التشعبي" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-jpeg/" name="تحويل PDF إلى JPEG" description="مجموعة خبراء التصوير الفوتوغرافي المشتركة" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-pdfa/" name="تحويل PDF إلى PDF/A" description="تنسيق المستندات المحمولة" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-png/" name="تحويل PDF إلى PNG" description="رسومات الشبكة المحمولة" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-pptx/" name="تحويل PDF إلى PPTX" description="مايكروسوفت باوربوينت" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-svg/" name="تحويل PDF إلى SVG" description="رسومات المتجهات القابلة للتطوير" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-tex/" name="تحويل PDF إلى TEX" description="نظام الرسوميات بالحاسوب" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-tiff/" name="تحويل PDF إلى TIFF" description="تنسيق الصورة الموسوم" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-word/" name="تحويل PDF إلى WORD" description="تنسيق مايكروسوفت وورد الثنائي" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-xlsx/" name="تحويل PDF إلى XLSX" description="ملف جدول بيانات مايكروسوفت إكسل بتنسيق XML المفتوح" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-xps/" name="تحويل PDF إلى XPS" description="مواصفات الورق XML" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/png-to-pdf/" name="تحويل PNG إلى PDF" description="رسومات الشبكة المحمولة" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/ps-to-pdf/" name="تحويل PS إلى PDF" description="بوست سكريبت" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/svg-to-pdf/" name="تحويل SVG إلى PDF" description="رسومات المتجهات القابلة للتطوير" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/text-to-pdf/" name="تحويل TEXT إلى PDF" description="وثيقة نصية" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/tiff-to-pdf/" name="تحويل TIFF إلى PDF" description="تنسيق الصورة الموسوم" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/xps-to-pdf/" name="تحويل XPS إلى PDF" description="مواصفات الورق XML" >}}

{{< /blocks/products/pf/agp/other-supported-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}


