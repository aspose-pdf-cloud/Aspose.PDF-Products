---
title: تحويل CGM إلى PDF عبر Cloud Node.js SDK
url: nodejs/conversion/cgm-to-pdf/
description: قم بتحويل رسومات CGM المتجهة إلى PDF عبر Node.js باستخدام Aspose.PDF Cloud SDK. حافظ على الدقة والتخطيط.
lastmod: 2022-03-17
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="تحويل CGM إلى PDF في Node.js SDK" h2="تصدير مستندات CGM إلى عدة تنسيقات بما في ذلك PDF باستخدام Aspose.PDF Cloud Node.js SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="كيفية تحويل CGM إلى PDF باستخدام Node.js SDK" %}}

لتحويل CGM إلى PDF، سنستخدم
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/)
تساعد هذه الحزمة البرمجية السحابية مبرمجي Node.js في تطوير تطبيقات خالق PDF السحابية، والمعلق، والمحرر، والمحولات باستخدام لغة برمجة Node.js عبر Aspose.PDF REST API. افتح
[NPM](https://www.npmjs.com/package/asposepdfcloud)
مدير الحزم، ابحث عن
Aspose.PDF Cloud،
وقم بتثبيتها. يمكنك أيضًا استخدام الأمر التالي من وحدة التحكم في مدير الحزم.

{{% blocks/products/pf/agp/code-block title="أمر وحدة التحكم في مدير الحزم" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="خطوات تحويل CGM إلى PDF عبر Node.js" %}}

{{% blocks/products/pf/agp/text %}}

يمكن لمطوري Aspose.PDF Cloud Node.js تحميل وتحويل ملفات CGM إلى PDF بسهولة في بضع سطور من الكود.

{{% /blocks/products/pf/agp/text %}}

1. تحميل مفتاح التطبيق السري والمفتاح من ملف JSON أو تعيين الاعتمادات بطريقة أخرى
1. إنشاء كائن للاتصال بواجهة برمجة التطبيقات السحابية
1. تحميل ملف المستند الخاص بك
1. قم بإجراء التحويل باستخدام putImageInStorageToPdf
1. تنزيل النتيجة إذا لزم الأمر

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="هذا الكود النموذجي يوضح تحويل CGM إلى PDF بواسطة Cloud Node.js SDK" offSpacer="" %}}

```js

    const fs = require("fs");
    const credentials = require("./credentials.json");
    const { PdfApi } = require("asposepdfcloud");
    const { ImageTemplatesRequest } = require("asposepdfcloud/src/models/imageTemplatesRequest");
    const { ImageTemplate } = require("asposepdfcloud/src/models/imageTemplate");
    const { ImageSrcType } = require("asposepdfcloud/src/models/imageSrcType");

    // Load your Application Secret and Key from the JSON file or set credentials in another way
    async function convertCGMtoPDF() {
        const localImageFileName = "C:\\Samples\\sample.cgm";
        const storageImageFileName = "sample.cgm";
        const pdfApi = new PdfApi(credentials.id, credentials.key);

        try {
            let fileData = await fs.readFile(localImageFileName);
            let uploadResult = await pdfApi.uploadFile(storageImageFileName, fileData);
            console.log(uploadResult.response.text);
        }
        catch (error) {
            console.error(error.response.text);
        }
        s
        let imageTemplateList = [];
        let imageTemplate = new ImageTemplate();
        imageTemplate.imagePath = storageImageFileName;
        imageTemplate.imageSrcType = ImageSrcType.Common;
        imageTemplateList.push(imageTemplate);

        let imageTemplatesRequest = new ImageTemplatesRequest()
        imageTemplatesRequest.IsOCR = false;
        imageTemplatesRequest.imagesList = imageTemplateList;

        try {
            let convertResult = await pdfApi.putImageInStorageToPdf("sample-cgm-to-pdf.pdf", imageTemplatesRequest);
            console.log(convertResult.response.text);
            const buffer = await pdfApi.downloadFile(STORAGE_FILENAME);
        } catch (error) {
            console.error(error.response.text);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< blocks/products/pf/agp/other-supported-section title="عمليات تحويل أخرى مدعومة" subTitle="يمكنك أيضًا تحويل MD إلى العديد من تنسيقات الملفات الأخرى بما في ذلك عدد قليل مدرج أدناه." >}}

{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/bmp-to-pdf/" name="BMP TO PDF" description="صورة نقطية" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/cgm-to-pdf/" name="CGM TO PDF" description="تنسيق ثنائي لكلمات مايكروسوفت" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/emf-to-pdf/" name="EMF TO PDF" description="مستند كلمات أوفيس 2007+" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/epub-to-pdf/" name="EPUB TO PDF" description="تنسيق ملف تعريف محسن" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/gif-to-pdf/" name="GIF TO PDF" description="تنسيق تبادل الرسوم" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/html-to-pdf/" name="HTML TO PDF" description="لغة ترميز النص التشعبي" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/jpeg-to-pdf/" name="JPEG TO PDF" description="مجموعة خبراء التصوير الفوتوغرافي المتحدين" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/latex-to-pdf/" name="LATEX TO PDF" description="نص إخراج LaTeX" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pcl-to-pdf/" name="PCL TO PDF" description="لغة أوامر الطابعة" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/md-to-pdf/" name="MD TO PDF" description="ماركداون" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-bmp/" name="PDF TO BMP" description="صورة نقطية" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-epub/" name="PDF TO EPUB" description="تنسيق الكتاب الإلكتروني" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-gif/" name="PDF TO GIF" description="تنسيق تبادل الرسوم" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-html/" name="تحويل PDF إلى HTML" description="لغة توصيف النص التشعبي" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-jpeg/" name="تحويل PDF إلى JPEG" description="مجموعة خبراء التصوير الفوتوغرافي" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-pdfa/" name="تحويل PDF إلى PDF/A" description="تنسيق المستندات المحمولة" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-png/" name="تحويل PDF إلى PNG" description="رسومات الشبكة المحمولة" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-pptx/" name="تحويل PDF إلى PPTX" description="مايكروسوفت بوربوينت" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-svg/" name="تحويل PDF إلى SVG" description="رسومات المتجهات القابلة للتحجيم" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-tex/" name="تحويل PDF إلى TEX" description="نظام الرسوم الحاسوبية" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-tiff/" name="تحويل PDF إلى TIFF" description="تنسيق الصور الموسوم" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-word/" name="تحويل PDF إلى WORD" description="تنسيق مايكروسوفت وورد الثنائي" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-xlsx/" name="تحويل PDF إلى XLSX" description="ملف جدول البيانات بتنسيق Microsoft Excel Open XML" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-xps/" name="تحويل PDF إلى XPS" description="مواصفات ورق XML" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/png-to-pdf/" name="تحويل PNG إلى PDF" description="رسومات الشبكة المحمولة" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/ps-to-pdf/" name="تحويل PS إلى PDF" description="بوستسكريبت" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/svg-to-pdf/" name="تحويل SVG إلى PDF" description="رسومات المتجهات القابلة للتحجيم" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/text-to-pdf/" name="تحويل TEXT إلى PDF" description="مستند نصي" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/tiff-to-pdf/" name="تحويل TIFF إلى PDF" description="تنسيق الصور الموسوم" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/xps-to-pdf/" name="تحويل XPS إلى PDF" description="مواصفات ورق XML" >}}

{{< /blocks/products/pf/agp/other-supported-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
