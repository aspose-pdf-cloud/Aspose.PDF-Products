---
title: Trích Xuất Trang từ PDF qua Cloud PHP SDK
url: php/pages/extract/
description: Trích xuất các trang cụ thể từ PDF bằng PHP với Aspose.PDF Cloud SDK. Tách hoặc phân tích nội dung dễ dàng.
lastmod: 2025-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Trích Xuất Trang từ PDF trong PHP SDK" h2="Trích xuất một trang từ tài liệu PDF sử dụng Cloud PHP SDK." logoImageSrc="/sdk/aspose_pdf-for-php.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for PHP" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for PHP" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="/sdk/aspose_pdf-for-php.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/php/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="https://reference.aspose.cloud/pdf/" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="Cách Trích Xuất Trang từ PDF qua Cloud PHP SDK" %}}

Để trích xuất các trang vào PDF, chúng ta sẽ sử dụng
[Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/)
Cloud SDK này hỗ trợ các lập trình viên PHP phát triển các ứng dụng tạo, chú thích, chỉnh sửa và chuyển đổi PDF dựa trên đám mây sử dụng ngôn ngữ lập trình PHP qua Aspose.PDF REST API. Chỉ cần tạo tài khoản tại [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) và lấy thông tin ứng dụng của bạn. Khi bạn đã có App SID & key, bạn đã sẵn sàng để sử dụng Aspose.PDF Cloud PHP SDK.

{{% blocks/products/pf/agp/code-block title="Lệnh Trình Quản Lý Gói" offSpacer="true" %}}

```bash
     
    composer install

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Các Bước để Trích Xuất Trang từ PDF qua Cloud PHP" %}}

{{% blocks/products/pf/agp/text %}}

Các nhà phát triển Aspose.PDF Cloud có thể dễ dàng tải & lấy các trang từ PDF chỉ với vài dòng mã.

{{% /blocks/products/pf/agp/text %}}

1. Tải Lên Tài Liệu PDF
1. Lấy thông tin chi tiết cho tất cả các trang trong tài liệu
1. Truy xuất thông tin trang cụ thể

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Trích Xuất Trang từ PDF sử dụng PHP" offSpacer="" %}}

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
        $pdfFilePath = $this->configParams['LOCAL_FOLDER'] . $this->configParams['PDF_DOCUMENT_NAME'];
        $pdfFileData = file_get_contents($pdfFilePath);
        $this->pdfApi->uploadFile($this->configParams['PDF_DOCUMENT_NAME'], $pdfFileData);
    }

    public function getAllPagesInfo () {
        $resultPages = $this->pdfApi->getPages($this->configParams['PDF_DOCUMENT_NAME']);

        if ($resultPages->getCode() == 200) {
            echo "All pages:";
            var_dump($resultPages->getPages()->getList());
        }
        else
            echo "Unexpected error : can't get pages!!!";
    }
       
    public function getPageInfoByPageNumber () {
        $resultPage = $this->pdfApi->getPage($this->configParams['PDF_DOCUMENT_NAME'], $this->configParams['PAGE_NUMBER']);

        if ($resultPage->getCode() == 200) {
            echo "Page {$this->configParams['PAGE_NUMBER']} info:";
            var_dump($resultPage->getPage());
        }
        else
            echo "Unexpected error : can't get page {$this->configParams['PAGE_NUMBER']} info!!!";
    }

    function main() {
        global $configParams;

        try {
            $pdfPages = new PdfPages($configParams);
            $pdfPages->uploadDocument();
            $pdfPages->getAllPagesInfo();
            $pdfPages->getPageInfoByPageNumber();
        } catch (\Exception $e) {
            echo "Error: " . $e->getMessage() . "\n";
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Làm Việc với Các Trang trong PDF" %}}

Trích xuất các trang từ một PDF là một nhiệm vụ phổ biến phục vụ nhiều mục đích khác nhau trong các ngữ cảnh khác nhau. Quá trình này bao gồm việc chọn các trang cụ thể từ một tài liệu lớn hơn để tạo ra một tệp PDF mới, tách biệt. Hiểu lý do đằng sau việc này có thể giúp quản lý và sử dụng tài liệu PDF hiệu quả hơn. Tệp PDF lớn có thể gây khó khăn khi chia sẻ hoặc lưu trữ. Bằng cách chỉ trích xuất các trang cần thiết, người dùng có thể tạo ra các tệp nhỏ hơn, dễ quản lý hơn. Điều này đặc biệt hữu ích khi chỉ có một phần của tài liệu là liên quan đến một mục đích cụ thể. Chẳng hạn, việc loại bỏ các trang không cần thiết có thể giảm đáng kể kích thước tệp, làm cho nó dễ xử lý và phân phối hơn.
Trích xuất các trang cho phép người dùng tái sử dụng nội dung cho các ứng dụng khác nhau. Ví dụ, một người có thể trích xuất các trang từ một báo cáo toàn diện để tạo một bản tóm tắt độc lập hoặc để cô lập dữ liệu cụ thể để phân tích. Điều này cho phép tái sử dụng nội dung hiện có mà không cần phải tạo lại thông tin từ đầu. Trích xuất các Trang từ tài liệu PDF với [Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/).

**Với thư viện PHP của chúng tôi, bạn có thể:**

+ Thêm tiêu đề & chân trang của tài liệu PDF ở định dạng văn bản hoặc hình ảnh.
+ Thêm bảng & con dấu (văn bản hoặc hình ảnh) vào tài liệu PDF.
+ Nối nhiều tài liệu PDF vào một tệp hiện có.
+ Làm việc với các tệp đính kèm, chú thích & trường biểu mẫu của PDF.
+ Áp dụng mã hóa hoặc giải mã cho tài liệu PDF & đặt mật khẩu.
+ Xóa tất cả các con dấu & bảng khỏi một trang hoặc toàn bộ tài liệu PDF.
+ Xóa một con dấu hoặc bảng cụ thể khỏi tài liệu PDF bằng ID của nó.
+ Thay thế một hoặc nhiều lần xuất hiện của văn bản trên một trang PDF hoặc từ toàn bộ tài liệu.
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

{{< blocks/products/pf/slr-tab tabTitle="Tại sao chọn Aspose.PDF Cloud cho PHP?" tabId="success-stories" >}}
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
