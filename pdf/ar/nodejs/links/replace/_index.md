---
title: استبدال الروابط في PDF عبر Cloud Node.js SDK
url: nodejs/links/replace/
description: استبدل الروابط في ملفات PDF باستخدام Aspose.PDF Cloud SDK لـ Node.js. قم بتحديث عناوين URL بكفاءة.
lastmod: 2025-02-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="استبدال الروابط في PDF في Node.js SDK" h2="استبدل الروابط في مستند PDF باستخدام Cloud Node.js SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="كيفية استبدال الروابط في PDF عبر Node.js SDK" %}}

لاستبدال الروابط في PDF، سنستخدم
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). يساعد هذا الـ Cloud SDK مبرمجي Node.js في تطوير تطبيقات إنشاء وتحرير وتعليق وتحويل مستندات PDF المستندة إلى السحابة باستخدام لغة برمجة Node.js عبر Aspose.PDF REST API. ببساطة قم بإنشاء حساب في [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) واحصل على معلومات التطبيق الخاصة بك. بمجرد أن يكون لديك App SID & key، تكون جاهزًا لاستخدام Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="أمر وحدة إدارة الحزم" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="خطوات استبدال الروابط باستخدام Node.js" %}}

{{% blocks/products/pf/agp/text %}}

يمكن لمطوري Aspose.PDF Cloud تحميل واستبدال الروابط في PDF بسهولة في بضعة أسطر من التعليمات البرمجية.

{{% /blocks/products/pf/agp/text %}}

1. قم بإنشاء كائن للاتصال بـ Pdf.Cloud API
1. قم بتحميل ملف المستند الخاص بك
1. قم بإنشاء تعليق توضيحي للرابط الجديد بالخصائص المطلوبة
1. أضف تعليق الرابط الجديد إلى المستند باستخدام وظيفة postPageLinkAnnotations()
1. قم ببعض الإجراءات بعد الإضافة الناجحة
1. قم بتنزيل النتيجة إذا لزم الأمر

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="استبدال الروابط في PDF باستخدام Node.js" offSpacer="" %}}

```js

 
    import credentials from "./credentials.json"  with { type: "json" };    // json-file in this format: { "id": "*****", "key": "*******" }
    import fs from 'node:fs/promises';
    import path from 'node:path';
    import { PdfApi } from "asposepdfcloud";;

    const configParams = {
        LOCAL_FOLDER: "C:\\Samples\\",
        PDF_DOCUMENT_NAME: "sample.pdf",
        LOCAL_RESULT_DOCUMENT_NAME: "output_sample.pdf",
        LINK_REMOVE_ID: "GI5UO32UN5KVESKBMN2GS33OHMZTEMJMGUYDQLBTGYYCYNJSGE",
        NEW_LINK_ACTION: "https://reference.aspose.cloud/pdf/#/",
        PAGE_NUMBER: 2,     // Your document page number...
    };

    const pdfApi = new PdfApi(credentials.id, credentials.key);

    const pdfLinks = {
    async uploadDocument() {
            const pdfFilePath = path.join(configParams.LOCAL_FOLDER, configParams.PDF_DOCUMENT_NAME);
            const pdfFileData = await fs.readFile(pdfFilePath);
            await pdfApi.uploadFile(configParams.PDF_DOCUMENT_NAME, pdfFileData);
        },
        
        async downloadResult() {
            const changedPdfData = await pdfApi.downloadFile(configParams.PDF_DOCUMENT_NAME);
            const filePath = path.join(configParams.LOCAL_FOLDER, configParams.LOCAL_RESULT_DOCUMENT_NAME);
            await fs.writeFile(filePath, changedPdfData.body);
            console.log("Downloaded: " + filePath);
        },

        async replaceLink () {
            const link = await pdfLinks.getLinkById(configParams.LINK_REMOVE_ID);

            link.action = configParams.NEW_LINK_ACTION;
            
            var updResponse = await pdfApi.putLinkAnnotation(configParams.PDF_DOCUMENT_NAME, configParams.LINK_REMOVE_ID, link);

            if (updResponse.body.code == 200 && updResponse.body.link) {
                pdfLinks.showLinks( [ updResponse.body.link ], "drop");
                return updResponse.body.link;
            }
            else
                console.Error("Unexpected error : can't append link!!!");
        },

        async getLinkById () {
            const resultLinks = await pdfApi.getPageLinkAnnotation(configParams.PDF_DOCUMENT_NAME, configParams.PAGE_NUMBER, configParams.LINK_REMOVE_ID);

            if (resultLinks.body.code == 200 && resultLinks.body.link) {
                this.showLinks( [ resultLinks.body.link ], "found");
                return resultLinks.body.link;
            }
            else
                console.Error("Unexpected error : can't get link !!!");
        },

        showLinks (links, prefix) {
            if (Array.isArray(links) && links.length > 0)
            {
                links.forEach(function(link) {
                    console.log(prefix +" => '" + link.id + "', '" + link.action);
                });
            }
            else
                console.error("showLinks() error: array of links is empty!")
        },

    }

    async function main() {
        try {
            await pdfLinks.uploadDocument();
            await pdfLinks.replaceLink();
            await pdfLinks.downloadResult();
        } catch (error) {
            console.error("Error:", error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="العمل مع الروابط في PDF" %}}

من خلال مراجعة وتحديث الروابط بانتظام في مستندات PDF الخاصة بك، يمكنك الحفاظ على ملاءمتها ودقتها وأمانها، مما يوفر تجربة أفضل لقرائك.
استبدل الروابط في مستندات PDF باستخدام [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

**باستخدام مكتبة Node.js الخاصة بنا يمكنك:**

+ إضافة رأس وتذييل مستند PDF بتنسيق نص أو صورة.
+ إضافة جداول وختمات (نص أو صورة) إلى مستندات PDF.
+ إلحاق مستندات PDF متعددة بملف موجود.
+ العمل مع مرفقات PDF والتعليقات التوضيحية وحقول النماذج.
+ تطبيق التشفير أو فك التشفير على مستندات PDF وتعيين كلمة مرور.
+ حذف جميع الأختام والجداول من صفحة أو مستند PDF بالكامل.
+ حذف ختم أو جدول محدد من مستند PDF بواسطة معرفه.
+ استبدال مثيل واحد أو عدة مثيلات للنص في صفحة PDF أو من المستند بالكامل.
+ دعم واسع لتحويل مستندات PDF إلى تنسيقات ملفات أخرى متنوعة.
+ استخراج عناصر متنوعة من ملفات PDF وجعل مستندات PDF محسنة.
+ يمكنك تجربة [التطبيق المجاني](https://products.aspose.app/pdf/family) لاختبار الوظائف عبر الإنترنت.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="موارد التعلم" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="التوثيق" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="كود المصدر" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-nodejs" >}}
{{< blocks/products/pf/slr-element name="مراجع API" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="دعم المنتج" tabId="support" >}}
{{< blocks/products/pf/slr-element name="دعم مجاني" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="دعم مدفوع" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="مدونة" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="لماذا Aspose.PDF Cloud لـ Node.js؟" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="قائمة العملاء" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="الأمان" href="https://company.aspose.cloud/legal/security" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< /blocks/products/pf/support-learning-resources >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}



