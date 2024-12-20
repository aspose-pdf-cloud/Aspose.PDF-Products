---
title: Extract attachments from PDF documents via Aspose.Pdf Cloud PHP SDK
url: /nodejs/attachments/
description: Sample code for extracting attachments from PDF document using Cloud PHP SDK. Use API example code for working with attachments in PDF documents with Aspose.PDF Cloud PHP SDK.
lastmod: "2024-10-29"
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Extract, Append & Replace attachments in PDF documents via Cloud PHP SDK" h2="API for working with attachments in PDF documents with Aspose.PDF Cloud PHP SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-php.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="PHP SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-php.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-php" >}}

{{% blocks/products/pf/agp/content h2="How to extract, append & replace attachments in PDF documents using Cloud PHP SDK" %}}

 For working with attachments in PDF documents, we'll use
 [Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/)
 This Cloud SDK SDK assists PHP programmers in developing cloud-based PDF creator, annotator, editor, and converter apps using PHP programming language via Aspose.PDF REST API. Open
 [NPM](https://www.npmjs.com/package/asposepdfcloud)
 package manager, search for  Aspose.PDF Cloud, and install. 

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Steps to extract attachments from PDF documents via Cloud PHP SDK" %}}

{{% blocks/products/pf/agp/text %}}

 Aspose.PDF Cloud PHP developers can easily extract, append & replace attachments in PDF documents. Developers need just a few lines of code.

{{% /blocks/products/pf/agp/text %}}

1. Configuration and connection: create a Configuration instance and a PdfApi instance by passing the key and SID.
1. Call parameters: specify the name of the PDF file and the attachment index that we want to get.
1. Get the attachment: call <b>getDocumentAttachments</b> with specified parameters.
1. Processing result: check the answer code and, if successful, we output attachment information (attachmant name, for eaxample).

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/feature-section-col title="System Requirements" %}}

{{% blocks/products/pf/agp/text %}}

It is easy to get started with Aspose.PDF Cloud PHP SDK and there is nothing to install. Simply create an account at Aspose for Cloud and get your application information. Once you have the App SID & key, you are ready to give the Aspose.PDF Cloud PHP SDK.

* CPU: 1GHz
* RAM: 512Mb
* Free space on disk: 20Mb
* Any OS Microsoft Windows, Mac OS, Linux x32/x64
* PHP v4.8 or higher

{{% /blocks/products/pf/agp/text %}}

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="This sample code shows extracting all attachments of PDF document using PDF Cloud PHP SDK" offSpacer="" %}}

```php
<?php

require_once 'path/to/PdfApi.php';  // Path to Your PdfApi.php
use Aspose\PDF\Api\PdfApi;
use Aspose\PDF\Configuration;

// API Settings
$config = new Configuration();
$config->setAppKey('YOUR_APP_KEY');  // Replace with your own key
$config->setAppSID('YOUR_APP_SID');  // Replace with your SID

// Create PdfApi instance
$pdfApi = new PdfApi(null, $config);

try {
    // Please specify the name of the PDF file you want to attach
    $fileName = 'example.pdf';

    // Get attachments from PDF
    $response = $pdfApi->getDocumentAttachments($fileName);

    // Check the answer and get a list of attachments
    if ($response->getCode() === 200) {
        $attachments = $response->getAttachments()->getList();
        foreach ($attachments as $attachment) {
            echo "Attachment: " . $attachment->getName() . "\n";
        }
    } else {
        echo "Error: Unable to retrieve attachments.\n";
    }

} catch (Exception $e) {
    echo 'Exception when calling PdfApi->getDocumentAttachments: ', $e->getMessage(), PHP_EOL;
}
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

<!-- aboutfile Starts -->

{{< blocks/products/pf/agp/democard icon="fa-cogs" text=" No need to download or setup anything." >}}
{{< blocks/products/pf/agp/democard icon="fa-edit" text=" No need to write any code." >}}
{{< blocks/products/pf/agp/democard icon="fa-file-text" text=" Just upload your BMP file and hit the \"Convert\" button." >}}
{{< blocks/products/pf/agp/democard icon="fa-download" text=" You will instantly receive a link to download the result." >}}

{{% blocks/products/pf/agp/content h3="About Aspose.PDF Cloud PHP SDK" %}}

Aspose.PDF Cloud is a true REST API that enables you to perform a wide range of document processing operations including creation, manipulation, conversion and rendering of PDF documents in the cloud.

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/about-file-section >}}

{{< blocks/products/pf/agp/about-file-text fileFormat="PDF" readMoreLink="https://docs.fileformat.com/view/pdf/" >}}
Portable Document Format (PDF) is a type of document created by Adobe back in 1990s. The purpose of this file format was to introduce a standard for representation of documents and other reference material in a format that is independent of application software, hardware as well as Operating System. PDF files can be opened in Adobe Acrobat Reader/Writer as well in most modern browsers like Chrome, Safari, Firefox via extensions/plug-ins. Most of the commercially available software suites also offer conversion of their documents to PDF file format without the requirement of any additional software component. Thus, PDF file format has full capability to contain information like text, images, hyperlinks, form-fields, rich media, digital signatures, attachments, metadata, Geospatial features and 3D objects in it that can become as part of source document.

{{< /blocks/products/pf/agp/about-file-text >}}

{{< /blocks/products/pf/agp/about-file-section >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}