---
title: Trích Xuất Dấu Trang từ PDF qua Cloud PHP SDK
url: php/bookmarks/extract/
description: Trích xuất dấu trang từ PDF bằng Aspose.PDF Cloud SDK cho PHP. Lấy cấu trúc tài liệu một cách lập trình.
lastmod: 2025-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Trích Xuất Dấu Trang từ PDF trong PHP SDK" h2="API làm việc với Dấu Trang trong tài liệu PDF bằng Cloud PHP SDK." h2="Xây dựng ứng dụng PHP của riêng bạn để lấy dấu trang vào các tệp PDF sử dụng API phía máy chủ." logoImageSrc="/sdk/aspose_pdf-for-php.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for PHP" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for PHP" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="/sdk/aspose_pdf-for-php.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/php/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="https://reference.aspose.cloud/pdf/" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="Cách lấy Dấu Trang từ PDF qua Cloud PHP SDK" %}}

Để trích xuất Dấu Trang từ PDF, chúng ta sẽ sử dụng
[Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/)
Cloud SDK này hỗ trợ lập trình viên PHP phát triển ứng dụng tạo, chú thích, chỉnh sửa và chuyển đổi PDF dựa trên đám mây bằng ngôn ngữ lập trình PHP thông qua Aspose.PDF REST API. Chỉ cần tạo tài khoản tại [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) và lấy thông tin ứng dụng của bạn. Khi bạn đã có App SID & key, bạn đã sẵn sàng sử dụng Aspose.PDF Cloud PHP SDK.

{{% blocks/products/pf/agp/code-block title="Lệnh trong Package Manager Console" offSpacer="true" %}}

```bash
     
    composer install

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Các bước để lấy Dấu Trang từ PDF qua Cloud PHP" %}}

{{% blocks/products/pf/agp/text %}}

Các nhà phát triển Aspose.PDF Cloud có thể dễ dàng tải & lấy Dấu Trang từ PDF chỉ trong vài dòng mã.

{{% /blocks/products/pf/agp/text %}}

1. Tải lên một Tài Liệu PDF
1. Lấy Dấu Trang theo Đường Dẫn
1. Tải xuống Tài Liệu PDF đã Xử lý

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Trích Xuất Dấu Trang từ PDF bằng PHP" offSpacer="" %}}

```php

    private function _create_rest_api() {
        $credentials = json_decode(file_get_contents("./Credentials/credentials.json"), true);

        $configAuth = new Configuration();
        $configAuth->setAppKey($credentials['key']);
        $configAuth->setAppSid($credentials['id']);

        $this->pdfApi = new PdfApi(null, $configAuth);
     }

    public function __construct($config) {
        $this->configParams = $config;
        $this->_create_rest_api();
    }

    public function uploadDocument() {
        $filePath = $this->configParams['LOCAL_FOLDER'] . $this->configParams['PDF_DOCUMENT_NAME'];
        $fileData = file_get_contents($filePath);

        $response = $this->pdfApi->uploadFile($this->configParams['PDF_DOCUMENT_NAME'], $fileData);
        if ($response->getCode() === 200) {
            echo "Uploaded file: {$this->configParams['PDF_DOCUMENT_NAME']}\n";
        } else {
            echo "Failed to upload file.";
        }
    }

    public function getBookmarkByPath()  {
        $resultBookmark = $this->pdfApi->getBookmarks($this->configParams['PDF_DOCUMENT_NAME'], $this->configParams['BOOKMARK_PATH']);
        if ($resultBookmark->getCode() === 200) 
            echo "Found bookmark title: {$resultBookmark->getBookmark()->getTitle()}";
        else
            echo "Unexpected error : Bookmark not found!";
    }

function main() {
    global $configParams;

    try {
        $pdfBookmarks = new PdfBookmarks($configParams);
        $pdfBookmarks->uploadDocument();
        $pdfBookmarks->getBookmarkByPath();
    } catch (\Exception $e) {
        echo "Error: " . $e->getMessage() . "\n";
    }
}
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Làm việc với Dấu Trang trong PDF" %}}

Trích xuất dấu trang từ PDF cải thiện khả năng sử dụng tài liệu, tự động hóa xử lý nội dung và tăng cường khả năng tìm kiếm. Nó đặc biệt hữu ích cho các doanh nghiệp, nhà nghiên cứu và chuyên gia xử lý các tài liệu PDF lớn hoặc có cấu trúc.
Trích xuất Dấu Trang từ tài liệu PDF với [Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/).

**Với thư viện PHP của chúng tôi bạn có thể:**

+ Thêm đầu & chân trang của tài liệu PDF dưới dạng văn bản hoặc hình ảnh.
+ Thêm bảng & tem (văn bản hoặc hình ảnh) vào tài liệu PDF.
+ Thêm nhiều tài liệu PDF vào tệp hiện có.
+ Làm việc với tệp đính kèm PDF, chú thích, & trường biểu mẫu.
+ Áp dụng mã hóa hoặc giải mã cho tài liệu PDF & đặt mật khẩu.
+ Xóa tất cả các tem & bảng khỏi một trang hoặc toàn bộ tài liệu PDF.
+ Xóa một tem hoặc bảng cụ thể khỏi tài liệu PDF theo ID của nó.
+ Thay thế một hoặc nhiều phiên bản của văn bản trên một trang PDF hoặc từ toàn bộ tài liệu.
+ Hỗ trợ rộng rãi cho việc chuyển đổi tài liệu PDF sang nhiều định dạng tệp khác.
+ Trích xuất các yếu tố khác nhau của tệp PDF & tối ưu hóa tài liệu PDF.
+ Bạn có thể thử [ứng dụng miễn phí của chúng tôi](https://products.aspose.app/pdf/family) để kiểm tra chức năng trực tuyến.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}
{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Tài Nguyên Học Tập" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Tài Liệu" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Mã Nguồn" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-php" >}}
{{< blocks/products/pf/slr-element name="Tham Khảo API" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Hỗ Trợ Sản Phẩm" tabId="support" >}}
{{< blocks/products/pf/slr-element name="Hỗ trợ miễn phí" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="Hỗ trợ trả phí" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="Blog" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Tại sao nên chọn Aspose.PDF Cloud cho PHP?" tabId="success-stories" >}}
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

{{< blocks/products/pf/offers-section-item link="/pdf/aws/" imgSrc="/sdk/aspose_pdf-for-go.svg" platform="AWS" >}}

{{< /blocks/products/pf/offers-section >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
