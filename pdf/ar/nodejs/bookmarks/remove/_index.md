---
title: إزالة الإشارات المرجعية عبر Cloud Node.js SDK
url: nodejs/bookmarks/remove/
description: إزالة الإشارات المرجعية في PDF باستخدام Node.js وAspose.PDF Cloud SDK. تبسيط هيكل الوثيقة.
lastmod: 2025-02-20
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="إزالة الإشارات المرجعية من PDF في Node.js SDK" h2="حذف الإشارات المرجعية من مستند PDF باستخدام Cloud Node.js SDK." logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="كيفية إزالة الإشارات المرجعية عبر Node.js SDK" %}}

لإزالة الإشارات المرجعية من PDF، سنستخدم
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). يساعد هذا الـ Cloud SDK مبرمجي Node.js في تطوير تطبيقات إنشاء وتوضيح وتحرير وتحويل PDF قائمة على السحابة باستخدام لغة البرمجة Node.js عبر Aspose.PDF REST API. ببساطة قم بإنشاء حساب في [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) واحصل على معلومات التطبيق الخاصة بك. بمجرد أن يكون لديك الـ App SID والمفتاح، يمكنك البدء باستخدام Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="أمر وحدة إدارة الحزم" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="خطوات إزالة الإشارات المرجعية عبر Cloud Node.js" %}}

{{% blocks/products/pf/agp/text %}}

يمكن لمطوري Aspose.PDF Cloud إزالة الإشارات المرجعية من PDF بسهولة في بضع خطوات من التعليمات البرمجية.

{{% /blocks/products/pf/agp/text %}}

1. إنشاء كائن للاتصال بـ Pdf.Cloud API
1. رفع ملف الوثيقة الخاص بك
1. حذف الإشارات المرجعية المطلوبة من الوثيقة باستخدام دالة deleteBookmark()
1. تنفيذ بعض الإجراءات بعد إزالة الإشارة المرجعية بنجاح من الوثيقة
1. تحميل النتيجة إذا لزم الأمر

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="يظهر هذا الكود المثال حذف الإشارات المرجعية من مستندات PDF باستخدام Node.js" offSpacer="" %}}

```js

    import credentials from "credentials.json"  with { type: "json" };    // json-file in this format: { "id": "*****", "key": "*******" }
    import fs from 'node:fs/promises';
    import path from 'node:path';
    import { PdfApi } from "asposepdfcloud";

    const configParams = {
        LOCAL_FOLDER: "C:\\Samples\\",
        PDF_DOCUMENT_NAME: "sample.pdf",
        LOCAL_RESULT_DOCUMENT_NAME: "output_sample.pdf",    
        DROP_BOOKMARK_PATH: "/1"
    };

    const pdfApi = new PdfApi(credentials.id, credentials.key);

    const pdfBookmarks = {
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

        async deleteBookmark(){
            const dropResult = await pdfApi.deleteBookmark(configParams.PDF_DOCUMENT_NAME, configParams.DROP_BOOKMARK_PATH);
            
            if (dropResult.body.code == 200) {
                console.log("Bookmark '" + configParams.DROP_BOOKMARK_PATH + "' successfully deleted!");
                return true;
            }
            else
                throw new Error("Unexpected error : can't get bookmarks list!!!");
        },
    };

    async function main() {
        try
        {
            await pdfBookmarks.uploadDocument();
            await pdfBookmarks.deleteBookmark();
            await pdfBookmarks.downloadResult();
        }
        catch(error) {
            console.log(error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="التعامل مع الإشارات المرجعية عبر Node.js SDK" %}}

إزالة الإشارات المرجعية من PDF مفيدة للحفاظ على دقة الوثيقة، وتحسين الأداء، وتعزيز الأمان، وضمان التنسيق المناسب. إنها مهمة بشكل خاص لإنهاء الوثائق قبل المشاركة أو الطباعة أو الأرشفة.
حذف الإشارات المرجعية من مستندات PDF باستخدام [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

**مع مكتبة Node.js الخاصة بنا يمكنك**

+ إضافة رأس وتذييل لمستند PDF بتنسيق نص أو صورة.
+ إضافة جداول وأختام (نص أو صورة) إلى مستندات PDF.
+ إلحاق مستندات PDF متعددة إلى ملف موجود.
+ التعامل مع مرفقات PDF، والتعليقات التوضيحية، وحقول النماذج.
+ تطبيق التشفير أو فك التشفير على مستندات PDF وتعيين كلمة مرور.
+ حذف جميع الأختام والجداول من صفحة أو مستند PDF بالكامل.
+ حذف ختم أو جدول معين من مستند PDF عن طريق معرفه.
+ استبدال ظهور أو أكثر من النص في صفحة PDF أو من المستند بأكمله.
+ دعم واسع لتحويل مستندات PDF إلى تنسيقات ملفات أخرى مختلفة.
+ استخراج عناصر مختلفة من ملفات PDF وجعل مستندات PDF محسنة.
+ يمكنك تجربة [تطبيقاتنا المجانية](https://products.aspose.app/pdf/family/) لاختبار الوظائف عبر الإنترنت.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="موارد التعلم" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="التوثيق" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="الشيفرة المصدرية" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-nodejs" >}}
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



