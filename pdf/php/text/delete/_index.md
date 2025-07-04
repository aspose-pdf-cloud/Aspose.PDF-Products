---
title: Remove Text from PDF via Cloud PHP SDK 
url: /php/text/remove/
description: Remove unwanted text from PDFs using PHP with Aspose.PDF Cloud SDK. Clean up and streamline files.
lastmod: "2024-10-19"
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Remove Text from PDF in PHP SDK" h2="API for working with Text in PDF documents using Cloud PHP SDK." logoImageSrc="/sdk/aspose_pdf-for-php.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for PHP" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for PHP" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="/sdk/aspose_pdf-for-php.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/php/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="https://reference.aspose.cloud/pdf/" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="How to delete Text from PDF via Cloud PHP SDK" %}}

In order to remove Text from PDF, we'll use
[Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/)
This Cloud SDK assists PHP programmers in developing cloud-based PDF creator, annotator, editor, and converter apps using PHP programming language via Aspose.PDF REST API. Simply create an account at [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) and get your application information. Once you have the App SID & key, you are ready to give the Aspose.PDF Cloud PHP SDK.

{{% blocks/products/pf/agp/code-block title="Package Manager Console Command" offSpacer="true" %}}

```bash
     
    composer install

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Steps to delete Text from PDF via PHP SDK" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud developers can easily load & delete Text from PDF in just a few lines of code.

{{% /blocks/products/pf/agp/text %}}

1. Upload the PDF File.
1. Define the Rectangle Area.
1. Configure Text Replacement.
1. Create Text Replacement List.
1. Execute the Text Replacement.
1. Save the Updated PDF.

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Remove Text from PDF using PHP" offSpacer="" %}}

```php

    $name = "sample.pdf";
    $this->uploadFile($name);

    $rect = new Aspose\PDF\Model\Rectangle();
    $rect->setLlx(100);
    $rect->setLly(100);
    $rect->setUrx(300);
    $rect->setUry(300);

    $textReplace = new Aspose\PDF\Model\TextReplace();
    $textReplace->setOldValue("market");
    $textReplace->setNewValue("m_a_r_k_e_t");
    $textReplace->setRect($rect);
    $textReplace->setRegex(false);
    
    $textReplaceList = new Aspose\PDF\Model\TextReplaceListRequest();
    $textReplaceList->setTextReplaces([$textReplace]);
    $textReplaceList->setStartIndex(0);
    $textReplaceList->setCountReplace(0);

    $folder = $this->tempFolder;
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Work with Text in PDF" %}}

Certain information, like personal details, confidential data, or financial information, may need to be deleted from PDFs before sharing to ensure privacy and data protection. No longer accurate text, such as old contact information, pricing, or policy terms, may need to be removed to keep the document current and relevant.
Removing unnecessary text, redundant information, or clutter from a PDF can make it more readable and visually appealing for the audience. 
These are the main reasons for removing text from DPF, which will make your document more organized, easier to read, and easier to understand.

Remove the Text from PDF documents with [Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/).

**With our PHP library you can:**

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
+ You can try out our [free App](https://products.aspose.app/pdf/redaction) to replace text in PDF files online and test the functionality.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Learning Resources" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Documentation" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Source Code" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-php" >}}
{{< blocks/products/pf/slr-element name="API References" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Product Support" tabId="support" >}}
{{< blocks/products/pf/slr-element name="Free Support" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="Paid Support" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="Blog" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Why Aspose.PDF Cloud for PHP?" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="Customers List" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="Security" href="https://company.aspose.cloud/legal/security" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< /blocks/products/pf/support-learning-resources >}}

{{< blocks/products/pf/offers-section pfName="Aspose.PDF" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/curl/" imgSrc="/sdk/aspose_pdf-for-curl.svg" platform="cURL" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/net/" imgSrc="/sdk/aspose_pdf-for-net.svg" platform=".NET" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/java/" imgSrc="/sdk/aspose_pdf-for-java.svg" platform="Java" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/php/" imgSrc="/sdk/aspose_pdf-for-php.svg" platform="PHP" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/android/" imgSrc="/sdk/aspose_pdf-for-android.svg" platform="Android" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/python/" imgSrc="/sdk/aspose_pdf-for-python.svg" platform="Python" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/ruby/" imgSrc="/sdk/aspose_pdf-for-ruby.svg" platform="Ruby" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/nodejs/" imgSrc="/sdk/aspose_pdf-for-node.svg" platform="Node.js" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/swift/" imgSrc="/sdk/aspose_pdf-for-swift.svg" platform="Swift" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/go/" imgSrc="/sdk/aspose_pdf-for-go.svg" platform="Go" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/aws/" imgSrc="https://products-qa.aspose.app/pdf/installer/aspose_pdf-for-aws.svg" platform="AWS" >}}

{{< /blocks/products/pf/offers-section >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}