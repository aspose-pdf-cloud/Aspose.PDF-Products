---
title: Thêm Văn Bản vào Chân Trang của PDF qua Cloud PHP SDK
url: php/footer/text/
description: Thêm chân trang dạng văn bản vào các trang PDF trong PHP sử dụng Aspose.PDF Cloud. Tùy chỉnh báo cáo và bố cục tài liệu.
lastmod: 2025-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Thêm Văn Bản vào Chân Trang của PDF trong PHP SDK" h2="Thêm Văn Bản vào Chân Trang trong tài liệu PDF sử dụng Cloud PHP SDK." logoImageSrc="/sdk/aspose_pdf-for-php.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for PHP" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for PHP" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="/sdk/aspose_pdf-for-php.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/php/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="https://reference.aspose.cloud/pdf/" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="Cách thêm Văn Bản vào Chân Trang của PDF qua Cloud PHP SDK" %}}

Để thêm Văn Bản vào Chân Trang của PDF, chúng ta sẽ sử dụng
[Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/)
Cloud SDK này hỗ trợ các lập trình viên PHP phát triển ứng dụng tạo, chú thích, chỉnh sửa và chuyển đổi PDF dựa trên đám mây sử dụng ngôn ngữ lập trình PHP qua Aspose.PDF REST API. Chỉ cần tạo một tài khoản tại [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) và lấy thông tin ứng dụng của bạn. Sau khi có App SID & key, bạn đã sẵn sàng sử dụng Aspose.PDF Cloud PHP SDK.

{{% blocks/products/pf/agp/code-block title="Lệnh của Package Manager Console" offSpacer="true" %}}

```bash
     
    composer install

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Các bước để thêm Văn Bản vào Chân Trang qua Cloud PHP" %}}

{{% blocks/products/pf/agp/text %}}

Các nhà phát triển Aspose.PDF Cloud có thể dễ dàng tải và thêm Văn Bản vào Chân Trang của PDF chỉ trong vài dòng mã.

{{% /blocks/products/pf/agp/text %}}

1. Tải lên một Tài liệu PDF
1. Chỉnh sửa PDF bằng cách thêm một chân trang văn bản
1. Tải xuống tài liệu đã cập nhật

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Thêm Văn Bản vào Chân Trang của PDF sử dụng PHP" offSpacer="" %}}

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
            echo "Uploaded file: {$filePath}\n";
        } else {
            echo 'Failed to upload file.';
        }
    }

    public function downloadResult() {
        $response = $this->pdfApi->downloadFile($this->configParams['PDF_DOCUMENT_NAME']);
        $filePath = $this->configParams['LOCAL_FOLDER'] . $this->configParams['LOCAL_RESULT_DOCUMENT_NAME'];

        if ($response->getCode() === 200) {
            file_put_contents($filePath, $response->getContents());
            echo "Downloaded: $filePath\n";
        } else {
            echo "Failed to download file.";
        }
    }

    public function addTextFooter () {
        $textFooter = new TextFooter(array(
            'background' => true,
            'value' => $this->configParams['FOOTER_VALUE'],
            'horizontal_alignment' => \Aspose\PDF\Model\HorizontalAlignment::CENTER,
        ));
        $resultFooter = $this->pdfApi->postDocumentTextFooter($this->configParams['PDF_DOCUMENT_NAME'], $textFooter);

        if ($resultFooter->getCode() === 200) {
            echo 'Successfully appended text footer "' . $this->configParams['FOOTER_VALUE'] . '"';
        }
        else
            throw new Error("Unexpected error : can't append text footer!");
    }

    function main() {
        global $configParams;

        try {
            $pdfHeaderFooter = new PdfHeaderFooter($configParams);
            $pdfHeaderFooter->uploadDocument();
            $pdfHeaderFooter->addTextFooter();
            $pdfHeaderFooter->downloadResult();
        } catch (\Exception $e) {
            echo "Error: " . $e->getMessage() . "\n";
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Làm việc với Chân Trang trong PDF" %}}

Thêm văn bản vào chân trang của PDF cải thiện tổ chức tài liệu, tính chuyên nghiệp và khả năng sử dụng. Nó rất cần thiết cho thương hiệu, tuân thủ pháp luật, điều hướng và bảo mật, làm cho nó trở thành một tính năng có giá trị cho tài liệu kinh doanh, học thuật và chính thức.
Thêm Chân Trang vào tài liệu PDF với [Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/).

**Với thư viện PHP của chúng tôi bạn có thể:**

+ Thêm tiêu đề & chân trang của tài liệu PDF dưới dạng văn bản hoặc hình ảnh.
+ Thêm bảng & dấu (văn bản hoặc hình ảnh) vào tài liệu PDF.
+ Ghép nối nhiều tài liệu PDF vào một tệp hiện có.
+ Làm việc với tệp đính kèm PDF, chú thích & trường biểu mẫu.
+ Áp dụng mã hóa hoặc giải mã cho tài liệu PDF & đặt mật khẩu.
+ Xóa tất cả dấu & bảng từ một trang hoặc toàn bộ tài liệu PDF.
+ Xóa một dấu hoặc bảng cụ thể từ tài liệu PDF theo ID của nó.
+ Thay thế một hoặc nhiều phiên bản văn bản trên một trang PDF hoặc từ toàn bộ tài liệu.
+ Hỗ trợ rộng rãi cho việc chuyển đổi tài liệu PDF sang nhiều định dạng tệp khác.
+ Trích xuất các phần tử khác nhau của tệp PDF & tối ưu hóa tài liệu PDF.
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
{{< blocks/products/pf/slr-element name="Hỗ Trợ Miễn Phí" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="Hỗ Trợ Trả Phí" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="Blog" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Tại Sao Chọn Aspose.PDF Cloud cho PHP?" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="Danh Sách Khách Hàng" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="Bảo Mật" href="https://company.aspose.cloud/legal/security" >}}
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
