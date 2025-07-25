---
title: التحقق من التوقيع في PDF عبر Cloud Node.js SDK
url: nodejs/signature/verify/
description: تتيح لك Aspose.PDF Cloud التحقق من التوقيع في مستند PDF. تحقق من شفرة المصدر Node.js للتحقق من التوقيع في ملف PDF.
lastmod: 2024-11-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="التحقق من التوقيع في PDF في Node.js SDK" h2="واجهة برمجة التطبيقات للعمل مع التوقيع في مستندات PDF باستخدام Cloud Node.js SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="كيفية التحقق من التوقيع في PDF عبر Node.js SDK" %}}

للتحقق من التوقيع في PDF، سنستخدم
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). يساعد هذا SDK السحابي مبرمجي Node.js في تطوير تطبيقات إنشاء وتوضيح وتحرير وتحويل PDF السحابية باستخدام لغة البرمجة Node.js عبر Aspose.PDF REST API. ببساطة قم بإنشاء حساب في [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) واحصل على معلومات التطبيق الخاصة بك. بمجرد أن يكون لديك App SID والمفتاح، أنت جاهز لاستخدام Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="أمر وحدة التحكم في مدير الحزم" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="خطوات التحقق من التوقيع في PDF عبر Cloud Node.js" %}}

{{% blocks/products/pf/agp/text %}}

يمكن لمطوري Aspose.PDF Cloud تحميل والتحقق من التوقيع في PDF بسهولة في بضع سطور من الشفرة.

{{% /blocks/products/pf/agp/text %}}

1. تحميل مستند PDF
1. التحقق من التوقيع باستخدام طريقة getVerifySignature()
1. تحميل ملف PDF المحدث من تخزين Aspose PDF Cloud.

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="التحقق من التوقيع في PDF باستخدام Node.js" offSpacer="" %}}

```js

    import credentials from "../../../Credentials/credentials.json"  with { type: "json" };
    import fs from 'node:fs/promises';
    import path from 'node:path';
    import { PdfApi } from "../../src/api/api.js";


    const configParams = {
        LOCAL_FOLDER: "C:\\Samples\\",
        PDF_DOCUMENT_NAME: "sample-signed.pdf",
        SIGNATURE_NAME: 'sign1',
    }

    const pdfApi = new PdfApi(credentials.id, credentials.key);

    const pdfSignatures = {
        async uploadDocument () {
            const fileNamePath = path.join(configParams.LOCAL_FOLDER, configParams.PDF_DOCUMENT_NAME);
            const pdfFileData = await fs.readFile(fileNamePath);
            await pdfApi.uploadFile(configParams.PDF_DOCUMENT_NAME, pdfFileData);
            console.log("File '" + configParams.PDF_DOCUMENT_NAME + "' successfully uploaded!");
        },

        async verifySignature () {
            if (pdfApi)
            {
                const response = await pdfApi.getVerifySignature(configParams.PDF_DOCUMENT_NAME, configParams.SIGNATURE_NAME);

                if (response.body.code == 200) {
                    if (response.body.valid == true)
                        console.log("verifySignature(): Signature is VALID for the '" + configParams.PDF_DOCUMENT_NAME + "' document.");
                    else
                    console.log("verifySignature(): Signature is NOT VALID for the '" + configParams.PDF_DOCUMENT_NAME + "' document.");
                }
                else
                    console.error("verifySignature(): Failed to extract signatures in the document. Response code: " + response.body.code);
            }
        },
    }

    async function main() {
        try {
            await pdfSignatures.uploadDocument();
            await pdfSignatures.verifySignature();
        } catch (error) {
            console.error("Error:", error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="العمل مع التوقيع في PDF" %}}

التحقق من التوقيع في ملف PDF ضروري لضمان أصالة وسلامة المستند. يؤكد أن المحتوى لم يتم تغييره منذ توقيعه وأن التوقيع تم من مصدر موثوق. يعد التحقق من التوقيع أمرًا حيويًا في السياقات القانونية والمالية والتجارية حيث يجب تأكيد صلاحية المستندات الرقمية لمنع الاحتيال وضمان الامتثال للوائح.
تحقق من التوقيع في مستندات PDF باستخدام [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

**مع مكتبتنا لـ Node.js يمكنك:**

+ إضافة رأس وتذييل لمستند PDF بتنسيق نص أو صورة.
+ إضافة جداول وأختام (نص أو صورة) إلى مستندات PDF.
+ إلحاق مستندات PDF متعددة إلى ملف موجود.
+ العمل مع مرفقات PDF والتعليقات التوضيحية وحقول النماذج.
+ تطبيق التشفير أو فك التشفير على مستندات PDF وتعيين كلمة مرور.
+ حذف جميع الأختام والجداول من صفحة أو مستند PDF بالكامل.
+ حذف ختم أو جدول محدد من مستند PDF بناءً على معرفه.
+ استبدال مثيل واحد أو متعدد من النص في صفحة PDF أو من المستند بأكمله.
+ دعم واسع لتحويل مستندات PDF إلى تنسيقات ملفات أخرى مختلفة.
+ استخراج عناصر مختلفة من ملفات PDF وجعل مستندات PDF محسّنة.
+ يمكنك تجربة [تطبيقاتنا المجانية](https://products.aspose.app/pdf/family/) لاختبار الوظائف عبر الإنترنت.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="موارد التعلم" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="التوثيق" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="شفرة المصدر" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-nodejs" >}}
{{< blocks/products/pf/slr-element name="مراجع API" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="دعم المنتج" tabId="support" >}}
{{< blocks/products/pf/slr-element name="دعم مجاني" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="دعم مدفوع" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="مدونة" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="لماذا Aspose.PDF Cloud for Node.js؟" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="قائمة العملاء" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="الأمان" href="https://company.aspose.cloud/legal/security" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< /blocks/products/pf/support-learning-resources >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}



