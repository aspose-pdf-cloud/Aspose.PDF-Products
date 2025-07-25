---
title: إضافة صفحات إلى PDF عبر Cloud Node.js SDK
url: nodejs/pages/add/
description: إضافة صفحات جديدة إلى ملفات PDF باستخدام Node.js وAspose.PDF Cloud SDK.
lastmod: 2025-02-20
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="إضافة صفحات إلى PDF في Node.js SDK" h2="إضافة صفحات إلى مستند PDF باستخدام Cloud Node.js SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="كيفية إضافة الصفحات عبر Node.js SDK" %}}

من أجل إضافة الصفحات إلى PDF، سنستخدم
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). يساعد هذا الـ Cloud SDK مبرمجي Node.js في تطوير تطبيقات إنشاء وتحرير وتحويل ملفات PDF المستندة إلى السحابة باستخدام لغة برمجة Node.js عبر Aspose.PDF REST API. ببساطة قم بإنشاء حساب في [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) واحصل على معلومات التطبيق الخاص بك. بمجرد حصولك على App SID والمفتاح، أنت جاهز لاستخدام Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="أمر وحدة إدارة الحزم" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="خطوات إضافة الصفحات عبر Cloud Node.js" %}}

{{% blocks/products/pf/agp/text %}}

يمكن لمطوري Aspose.PDF Cloud إضافة صفحات إلى PDF بسهولة ببضع سطور من الشفرة.

{{% /blocks/products/pf/agp/text %}}

1. إنشاء كائن للاتصال بـ Pdf.Cloud API
1. تحميل ملف المستند الخاص بك
1. إضافة صفحة جديدة إلى PDF
1. تنزيل النتيجة إذا لزم الأمر

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="تُظهر هذه الشفرة المثال كيفية إضافة الصفحات باستخدام Node.js" offSpacer="" %}}

```js

    import credentials from "./credentials.json"  with { type: "json" };
    import fs from 'node:fs/promises';
    import path from 'node:path';
    import { PdfApi } from "asposepdfcloud";

    const configParams = {
        LOCAL_FOLDER: "C:\\Samples\\",
        PDF_DOCUMENT_NAME: "sample.pdf",
        LOCAL_RESULT_DOCUMENT_NAME: "output_sample.pdf"
    };

    const pdfApi = new PdfApi(credentials.id, credentials.key);

    const pdfPages = {
        async uploadDocument () {
            const fileNamePath = path.join(configParams.LOCAL_FOLDER, configParams.PDF_DOCUMENT_NAME);
            const pdfFileData = await fs.readFile(fileNamePath);
            await pdfApi.uploadFile(configParams.PDF_DOCUMENT_NAME, pdfFileData);
            },
        
        async downloadResult () {
                const changedPdfData = await pdfApi.downloadFile(configParams.PDF_DOCUMENT_NAME);
                const filePath = path.join(configParams.LOCAL_FOLDER, configParams.LOCAL_RESULT_DOCUMENT_NAME);
                await fs.writeFile(filePath, changedPdfData.body);
                console.log("Downloaded: " + filePath);
            },

        async addPage () {
            const resultPages = await pdfApi.putAddNewPage(configParams.PDF_DOCUMENT_NAME);

            if (resultPages.body.code == 200 && resultPages.body.pages) {
                this.showPages( [ resultPages.body.pages.list[resultPages.body.pages.list.length - 1] ], "new page");
                return resultPages.body.pages.list[resultPages.body.pages.list.length - 1];
            }
            else
                console.error("Unexpected error : can't get pages!!!");
        },

        showPages (pages, prefix) {
            if (Array.isArray(pages) && pages.length > 0)
            {
                pages.forEach(function(page) {
                    console.log(prefix +" => id: '" + page.id + "', lLx: '" + page.rectangle.lLX + "', lLY: '" + page.rectangle.lLY + "', uRX: '" + page.rectangle.uRX + "', uRY: '" + page.rectangle.uRY + "'");
                });
            }
            else
                console.error("showPages() error: array of pages is empty!")
        },
    }

    async function main() {
        try {
            await pdfPages.uploadDocument();
            await pdfPages.addPage();
            await pdfPages.downloadResult();
        } catch (error) {
            console.error("Error:", error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="العمل مع الصفحات عبر Node.js SDK" %}}

إضافة الصفحات إلى مستند PDF هو مهمة شائعة تخدم أغراضًا مختلفة، مما يعزز من وظيفة المستند وتنظيمه وشموليته. في كثير من الأحيان، يكون من الضروري تضمين محتوى إضافي مثل الملاحق أو المراجع أو البيانات المحدثة التي لم تكن متوفرة أثناء إنشاء المستند الأصلي. إضافة صفحات جديدة تسمح بالتكامل السلس لهذه المعلومات الإضافية، مما يضمن بقاء المستند حاليًا وشاملاً. إضافة الصفحات إلى PDF هي ممارسة متعددة الاستخدامات تلبي احتياجات متعددة، من تعزيز المحتوى والبنية إلى ضمان الامتثال وتسهيل التعاون. من خلال فهم المتطلبات المحددة واستخدام الأدوات المناسبة، يمكن للمستخدمين إدارة وتعديل مستندات PDF الخاصة بهم بشكل فعال لتلبية أغراض متعددة.
أضف الصفحات إلى مستندات PDF باستخدام [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

مع مكتبتنا لـ Node.js يمكنك

+ إضافة رأس وتذييل مستند PDF بتنسيق نصي أو صورة.
+ إضافة جداول وأختام (نصية أو صورة) إلى مستندات PDF.
+ إلحاق مستندات PDF متعددة بملف موجود.
+ العمل مع مرفقات PDF، التعليقات التوضيحية، وحقول النماذج.
+ تطبيق التشفير أو فك التشفير على مستندات PDF وتعيين كلمة مرور.
+ حذف جميع الأختام والجداول من صفحة أو مستند PDF بالكامل.
+ حذف ختم أو جدول محدد من مستند PDF بواسطة معرفه.
+ استبدال مثيل واحد أو متعدد من النص على صفحة PDF أو من المستند بأكمله.
+ دعم واسع لتحويل مستندات PDF إلى تنسيقات ملفات أخرى متنوعة.
+ استخراج عناصر مختلفة من ملفات PDF وجعل مستندات PDF محسنة.
+ يمكنك تجربة [التطبيقات المجانية](https://products.aspose.app/pdf/family/) لاختبار الوظائف عبر الإنترنت.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="موارد التعلم" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="التوثيق" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="كود المصدر" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-nodejs" >}}
{{< blocks/products/pf/slr-element name="مراجع API" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="دعم المنتج" tabId="support" >}}
{{< blocks/products/pf/slr-element name="الدعم المجاني" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="الدعم المدفوع" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="المدونة" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="لماذا Aspose.PDF Cloud لـ Node.js؟" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="قائمة العملاء" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="الأمان" href="https://company.aspose.cloud/legal/security" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< /blocks/products/pf/support-learning-resources >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}



