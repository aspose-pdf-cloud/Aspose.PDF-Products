---
title: Merge several PDF Documents | PHP
description: Merge multiple PDF documents into a single file using PHP and Aspose.PDF Cloud SDK.
weight: 40
url: /php/merge
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Merge PDF in PHP SDK" h2="Merge several PDF files in PHP Cloud API without the use of any software like Adobe PDF." logoImageSrc="/sdk/aspose_pdf-for-php.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for PHP" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for PHP" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="/sdk/aspose_pdf-for-php.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/php/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="https://reference.aspose.cloud/pdf/" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="How to Merge several PDF Files Using Cloud API for PHP " %}}

Now, managing and organizing documents is essential for businesses and individuals. Merging multiple PDF files into one document simplifies sharing, archiving, and printing. Whether you need to combine multiple reports, invoices, or contracts, merging PDFs offers a clean, organized solution. With Aspose Cloud PHP Library, you can easily merge multiple PDF documents programmatically using the power of cloud computing. This guide will walk you through merging PDF files using Aspose's Cloud API in PHP.

**Why do I need to merge multiple PDF documents?**

Combine multiple related documents into a single file for easy management. Merge invoices, receipts, or reports for a client into a single file for streamlined sharing. Reduce the number of files in storage by consolidating them into one compact document. Save time by automating the process of merging multiple files.

**Merge PDFs with PHP**

The PDF Cloud PHP SDK offers an easy-to-use and secure API for merging PDF files quickly and accurately, even when dealing with complex formatting. Instead of manually combining files, you can merge them in seconds with just a single method call from the PHP SDK. There's no need to install additional software—document merging happens in the cloud, offloading the process from your local system and saving resources.

{{% blocks/products/pf/agp/code-block title="Package Manager Console Command" offSpacer="true" %}}

```bash
     
    composer install

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Steps for Merging PDF via Cloud PHP SDK" %}}

{{% blocks/products/pf/agp/text %}}

A basic merging pdfs programmatically with
[Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/)
APIs can be done with just few lines of code.

{{% /blocks/products/pf/agp/text %}}

1. Install [PHP SDK](https://pypi.org/project/asposepdfcloud/).
1. Go to the [Aspose Cloud Dashboard](https://dashboard.aspose.cloud/).
1. Create a new [Account](https://docs.aspose.cloud/display/storagecloud/Creating+and+Managing+Account) to access all applications and services or Sign In to your account.
1. Click on Applications in the left menu to get Client Id and Client Secret.
1. Check out the [Developer Guide](https://docs.aspose.cloud/pdf/merge-multiple-pdf-files/) to merge a PDF in PHP.
1. Check out our [GitHub repository](https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-php) for a complete API list along with working examples.
1. Check out the [API Reference page](https://reference.aspose.cloud/pdf/#/Document) for the description of APIs parameters.

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Merge several PDF Files using PHP" offSpacer="" %}}

```php

	$nameList = ['4pages.pdf', 'PdfWithImages2.pdf', 'marketing.pdf'];
	foreach ($nameList as $name)
	{
		$this->uploadFile($name);
	}

	$resultName = 'MergingResult.pdf';

	$mergeDocuments = new Aspose\PDF\Model\MergeDocuments();

	$i = 0;
	foreach ($nameList as $name)
	{
		$nameList[$i] = $this->tempFolder . '/' . $name;
		$i++;
	}

	$mergeDocuments->setList($nameList);

	$folder = $this->tempFolder;

	$response = $this->pdfApi->putMergeDocuments($resultName, $mergeDocuments, $storage = null, $folder);
	$this->assertNotNull($response);
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Combine Features and Capabilities" %}}

We offer top-tier document processing capabilities through our continually advancing Cloud SDKs, which support a variety of programming languages and major platforms. These tools empower developers to fully control and tailor document merging options to meet their unique requirements.

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
+ You can try out our [free App](https://products.aspose.app/pdf/merger) to merge PDF files online and test the functionality.

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