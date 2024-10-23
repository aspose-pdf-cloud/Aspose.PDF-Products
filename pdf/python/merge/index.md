---
title: Merge PDF Documents | Python 
description: Merge or combine multiple PDF Documents in Python with Cloud API. 
weight: 40
url: /python/merge
---

{{< blocks/products/pf/main-wrap-class >}}
<div id="fh">
<div class="container">
<div class="row">
<h1>Merge PDF Documents in Python</h1>
</div>
</div>
</div>
<div class="wmh">
<div class="container">
<div class="row">
<h1>Merge PDF Documents in Python</h1>
</div>
</div>
</div>
<div id="fm" data-nosnippet="">
<div class="container">
<div class="row">
<p class="navbar-text"><a href="/pdf/family/">PDF Cloud</a> / <a id="sdk" href="/pdf/python/"> Python</a> / Merge</p>
</div>
</div>
</div>
<div class="wgray">
<div class="container">
<div class="row">
<div class="w"><p>Now, managing and organizing documents is essential for businesses and individuals. Merging multiple PDF files into one document simplifies sharing, archiving, and printing. Whether you need to combine multiple reports, invoices, or contracts, merging PDFs offers a clean, organized solution. With Aspose Cloud Python Library, you can easily merge multiple PDF documents programmatically using the power of cloud computing. This guide will walk you through merging PDF files using Aspose's Cloud API in Python.</p>
<h2>Why do I need to merge multiple PDF documents?</h2>
<p>Combine multiple related documents into a single file for easy management. Merge invoices, receipts, or reports for a client into a single file for streamlined sharing. Reduce the number of files in storage by consolidating them into one compact document. Save time by automating the process of merging multiple files.</p>
<h2>Merge PDFs with Python</h2>
<p>The PDF Cloud Python SDK offers an easy-to-use and secure API for merging PDF files quickly and accurately, even when dealing with complex formatting. Instead of manually combining files, you can merge them in seconds with just a single method call from the Python SDK. There's no need to install additional software—document merging happens in the cloud, offloading the process from your local system and saving resources.</p>
<p>To start, you should have Python and the <a href="https://pypi.org/project/asposepdfcloud/" target="_blank" rel="noopener">PDF Cloud Python SDK</a> installed on your system.</p>
<h2>Combine Features and Capabilities</h2>
<p>We offer top-tier document processing capabilities through our continually advancing Cloud SDKs, which support a variety of programming languages and major platforms. These tools empower developers to fully control and tailor document merging options to meet their unique requirements.</p>
<p>With our Python library you can:</p>
<ul>
<li>Combine PDF documents.</li>
<li>Splitt PDF Files.</li>
<li>Convert PDF to other formats, and vice versa.</li>
<li>Manipulate Annotations.</li>
<li>Work with Images in PDF, etc.</li>
</ul>
<p>You can try out our <a href="https://products.aspose.app/pdf/merger" target="_blank">free App</a> to merge PDF files online and test the functionality.</p>
<h1>How to Merge a PDF in Python</h1>
<ol>
<li>Install <a href="https://pypi.org/project/asposepdfcloud/" target="_blank" rel="noopener">Python SDK</a>.</li>	<li>Go to the <a href="https://dashboard.aspose.cloud/" target="_blank">Aspose Cloud Dashboard</a>.</li>
<li>Create <a href="https://docs.aspose.cloud/display/storagecloud/Creating+and+Managing+Account" target="_blank">a
		new Account</a> to access all applications and services or Sign In to your account.
	</li>
<li>Click on <strong>Applications</strong> in the left menu to get <strong>Client Id</strong> and <strong>Client Secret</strong>.</li>
<li>Check out the <a href="https://docs.aspose.cloud/pdf/merge-multiple-pdf-files/" target="_blank">Developer
		Guide</a> to merge a PDF in Python.
	</li>
<li>Check out our <a href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python/" target="_blank">GitHub repository</a> for a complete API list along
		with working examples.
	</li>
<li>Check out the <a href="https://reference.aspose.cloud/pdf/#/Merge" target="_blank">API Reference page</a>
		for the description of APIs parameters.
	</li>
</ol>
<br/>
<div class="codeblock nf">
<div class="codeheader">Merge 2 PDF documents</div>
<pre data-nosnippet><code class="python hljs" >
      file_name_list = ['4pages.pdf', 'PdfWithImages2.pdf', 'marketing.pdf']
      for file_name in file_name_list:
            self.uploadFile(file_name)
        
        result_name = 'MergingResult.pdf'

        i = 0
        for el in file_name_list:
            file_name_list[i] = self.temp_folder + '/' + el
            i += 1

        merge_documents = asposepdfcloud.models.MergeDocuments(file_name_list)

        opts = {
              "merge_documents" : merge_documents,
              "folder" : self.temp_folder
        }

        response = self.pdf_api.put_merge_documents(result_name, **opts)
        self.assertEqual(response.code, 200)</code></pre>
</div>
<br /><br /></div>
</div>
</div>

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Learning Resources" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Documentation" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Source Code" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python/" >}}
{{< blocks/products/pf/slr-element name="API References" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Product Support" tabId="support" >}}
{{< blocks/products/pf/slr-element name="Free Support" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="Paid Support" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="Blog" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Why Aspose.PDF Cloud for Python?" tabId="success-stories" >}}
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

{{< /blocks/products/pf/offers-section >}}

{{< /blocks/products/pf/main-wrap-class >}}