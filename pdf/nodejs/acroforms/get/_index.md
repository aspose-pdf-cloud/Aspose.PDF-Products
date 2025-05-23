---
title: Get Form Fields from PDF Document via Cloud Node.js SDK
url: /nodejs/acroforms/get/
description: Get and extract form field values from PDF AcroForms using Aspose.PDF Cloud SDK for Node.js.
lastmod: "2024-11-19"
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Get PDF Forms in Node.js SDK" h2="Get all of the Form Fields from a PDF Document using Node.js Cloud SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Get an AcroForms from PDF document via Cloud Node.js SDK" %}}

In order to get an AcroForms from PDF, we'll use
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). This Cloud SDK assists Node.js programmers in developing cloud-based PDF creator, annotator, editor, and converter apps using Node.js programming language via Aspose.PDF REST API. Simply create an account at [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) and get your application information. Once you have the App SID & key, you are ready to give the Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="Package Manager Console Command" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Steps to get AcroForms via Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud developers can easily load & get acroforms from PDF in just a few lines of code.

{{% /blocks/products/pf/agp/text %}}

1. Upload the PDF file to the Aspose.PDF Cloud service.
1. Log any errors that occur during the file upload.
1. Retrieve the form fields from the PDF file in the Aspose.PDF Cloud storage.
1. Iterate through the form fields and log the field names and values to the console.
1. Log any errors that occur during the field retrieval
1. Download the result if needed it

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="This sample code shows getting an AcroForms from PDF documents using Node.js" offSpacer="" %}}

```js

    import credentials from "./credentials.json" with { type: "json" };
    import fs from 'node:fs/promises';
    import { PdfApi } from "asposepdfcloud";
    import { Border } from "asposepdfcloud/src/models/border";
    import { TextBoxField } from "asposepdfcloud/src/models/textBoxField";
    import { Dash } from "asposepdfcloud/src/models/dash";
    import { Rectangle } from "asposepdfcloud/src/models/rectangle";
    import { Field } from "asposepdfcloud/src/models/field";
    import { FieldType } from "asposepdfcloud/src/models/fieldType";
    import { Fields } from "asposepdfcloud/src/models/fields";

    async function getFormFields() {
        const localFileName = "C:\\Samples\\StudentInfoFormElectronic.pdf";
        const storageFileName = "StudentInfoFormElectronic.pdf";

        const pdfApi = new PdfApi(credentials.id, credentials.key);
        try {
            let fileData = await fs.readFile(localFileName);
            let uploadResult = await pdfApi.uploadFile(storageFileName, fileData);
            console.log(uploadResult.response.text);
        }
        catch (error) {
            console.error(error.message);
        }

        try {
            let response = await pdfApi.getFields(storageFileName);
            for (const item of response.body.fields.list) {
                if (item.type == "List") {
                    console.log(`Name: [${item.Name}] Value: [${item.Values.join()}]`);
                }
                else {
                    console.log(`Name: [${item.name}] Value: [${item.values[0]}]`);
                }
            }
        } catch (error) {
            console.error(error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Work with the AcroForms via Node.js SDK" %}}

Extracting AcroForm data allows you to compile and analyze information collected from users efficiently, such as surveys or application responses. Retrieved AcroForm data can be integrated into databases, spreadsheets, or other systems for further processing or record-keeping. Extracting AcroForms helps in auditing filled-out forms to verify the accuracy, authenticity, or completeness of the provided data. Retrieving AcroForms is essential when transferring forms to other document management systems or creating backups.
Get the AcroForms from PDF documents with [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

**With our Node.js library you can**

+ Add PDF document's header & footer in text or image format.
+ Add tables & stamps (text or image) to PDF documents.
+ Append multiple PDF documents to an existing file.
+ Work with PDF attachments, annotations, & form fields.
+ Apply encryption or decryption to PDF documents & set a password.
+ Delete all stamps & tables from a page or entire PDF document.
+ Delete a specific stamp or table from the PDF document by its ID.
+ Replace single or multiple instances of text on a PDF page or from the entire document.
+ Extensive support for converting PDF documents to various other file formats.
+ Extract various elements of PDF files & make PDF documents optimized.
+ You can try out our [free App](https://products.aspose.app/pdf/xfa) to get the AcroForms from PDF files online and test the functionality.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Learning Resources" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Documentation" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Source Code" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-nodejs" >}}
{{< blocks/products/pf/slr-element name="API References" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Product Support" tabId="support" >}}
{{< blocks/products/pf/slr-element name="Free Support" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="Paid Support" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="Blog" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Why Aspose.PDF Cloud for Node.js?" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="Customers List" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="Security" href="https://company.aspose.cloud/legal/security" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< /blocks/products/pf/support-learning-resources >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}


