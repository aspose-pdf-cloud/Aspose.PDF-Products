---
title: Phân chia các tài liệu PDF đơn lẻ | Python
description: Phân chia các tệp PDF thành những phần nhỏ hơn trong Python với Aspose.PDF Cloud SDK.
weight: 40
url: python/split/
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Phân chia PDF trong Python SDK" h2="Phân chia tệp PDF sử dụng Python Cloud SDK" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="Cách phân chia tệp PDF bằng Python Cloud API" %}}

**Tại sao tôi cần phải phân chia tài liệu PDF?** Phân chia PDF bằng Python có thể là bắt buộc khi quản lý và tổ chức tài liệu lớn hoặc làm việc trong môi trường xử lý dữ liệu. ఫে ზ Indic A Selection Containing a Specific Section or Set of Pages. Phân chia PDF cho phép bạn highlight và trích xuất các trang tương ứng mà không cần tài liệu còn lại.

Cũng với việc gửi hoặc chia sẻ tất cả các PDFs có thể không hiệu quả, szczególnie jeśli tài liệu sangat besar dan mengandung lebih banyak informasi daripada yang diperlukan. Khi phân chia PDFs, bạn chỉ cần phân chia các trang tương ứng, điều này làm cho quá trình nhanh hơn và tiết kiệm băng thông.

Phân chia PDF thành những phần nhỏ hơn có thể giảm kích thước tệp, điều này hữu ích khi bạn gặp vấn đề lưu trữ hoặc tải tài liệu lên hệ thống có giới hạn kích thước.

Để bắt đầu, bạn nên cóPython và [PDF Cloud Python SDK](https://pypi.org/project/asposepdfcloud/) được cài đặt trên hệ thống của bạn.

{{% blocks/products/pf/agp/code-block title="Cài đặt từ Github" offSpacer="true" %}}

```bash

     
    pip install git+https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python.git


```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/code-block title="Lệnh Manager Console" offSpacer="true" %}}

```bash
     
    pip install asposepdfcloud

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Bước để Phân chia PDF qua Cloud Python SDK" %}}

{{% blocks/products/pf/agp/text %}}

Phân chia cơ bản PDFs programmatic với 
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/)
APIs có thể được thực hiện chỉ với một số dòng mã.

{{% /blocks/products/pf/agp/text %}}

1. Install [Python SDK](https://pypi.org/project/asposepdfcloud/).
1. Go to the [Aspose Cloud Dashboard](https://dashboard.aspose.cloud/).
1. Create a new [Account](https://docs.aspose.cloud/display/storagecloud/Creating+and+Managing+Account) to access all applications and services or Sign In to your account.
1. Click on Applications in the left menu to get Client Id and Client Secret.
1. Check out the [Developer Guide](https://docs.aspose.cloud/pdf/split-pdf-files/) to split a PDF in Python.
1. Check out our [GitHub repository](https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python/) for a complete API list along with working examples.
1. Check out the [API Reference page](https://reference.aspose.cloud/pdf/#/Document) for the description of APIs parameters.

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Phân chia các tệp PDF đơn lẻ bằng Python" offSpacer="" %}}

```python

    def split_single_pages():
        local_file_path = "C:/Samples/Sample-Document-01.pdf"
        storage_file_name = "Sample-Document-01.pdf"

        pdf_api_client = asposepdfcloud.ApiClient(app_secret, app_sid)
        pdf_api = asposepdfcloud.PdfApi(pdf_api_client)

        # Check if the file exists in cloud storage
        files = pdf_api.get_files_list("/")
        if not any(f.name == storage_file_name for f in files.value):
            upload_result = pdf_api.upload_file(storage_file_name, local_file_path )
            print(upload_result.status)
            print(upload_result.uploaded[0])

        # Split the document into single pages
        count = 1
        response = pdf_api.post_split_document(storage_file_name)
        for page in response.result.documents:
            res = pdf_api.download_file(page.href)
            shutil.move(res, "page" + str(count)+".pdf")
            count = count + 1
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Với thư viện Python của chúng tôi bạn có thể:" %}}

+ Combine PDF documents.
+ Split PDF Files.
+ Convert PDF to other formats, and vice versa.
+ Manipulate Annotations.
+ Work with Images in PDF, etc.
+ You can try out our [free App](https://products.aspose.app/pdf/split-pdf) to split PDF files online and test the functionality.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Learning Resources" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Documentation" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Source Code" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python/" >}}
{{< blocks/products/pf/slr-element name="API References" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Hỗ trợ sản phẩm" tabId="support" >}}
{{< blocks/products/pf/slr-element name="Hỗ trợ miễn phí" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="Hỗ trợ trả phí" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="Blog" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Tại sao chọn Aspose.PDF Cloud cho Python?" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="Danh sách khách hàng" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="Bảo mật" href="https://company.aspose.cloud/legal/security" >}}
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

<!-- aboutfile Kết thúc -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
