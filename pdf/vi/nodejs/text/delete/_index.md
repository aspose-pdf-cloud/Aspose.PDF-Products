---
title: Xóa Văn Bản khỏi PDF qua Cloud Node.js SDK
url: nodejs/text/remove/
description: Xóa các phần tử văn bản cụ thể khỏi PDF với Node.js sử dụng Aspose.PDF Cloud SDK.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Xóa Văn Bản khỏi PDF trong Node.js SDK" h2="Xóa một Văn Bản khỏi Tài liệu PDF bằng Cloud Node.js SDK." logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Cách xóa Văn Bản khỏi PDF qua Node.js SDK" %}}

Để xóa văn bản khỏi PDF, chúng ta sẽ sử dụng
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). SDK Cloud này hỗ trợ các lập trình viên Node.js phát triển ứng dụng tạo, chú thích, chỉnh sửa, và chuyển đổi PDF dựa trên đám mây sử dụng ngôn ngữ lập trình Node.js qua Aspose.PDF REST API. Chỉ cần tạo một tài khoản tại [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) và lấy thông tin ứng dụng của bạn. Khi đã có App SID & key, bạn đã sẵn sàng sử dụng Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="Lệnh trên Package Manager Console" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Các bước để xóa Văn Bản sử dụng Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Các nhà phát triển Aspose.PDF Cloud có thể dễ dàng tải & xóa Văn Bản khỏi PDF chỉ trong vài dòng mã.

{{% /blocks/products/pf/agp/text %}}

1. Tải Bí mật Ứng dụng và Khóa của bạn từ tệp JSON hoặc thiết lập thông tin đăng nhập theo cách khác
1. Tạo một đối tượng để kết nối với Cloud API
1. Tải lên tệp tài liệu của bạn
1. Thực hiện thao tác xóa văn bản sử dụng hàm pdfApi.postDocumentTextReplace
1. Tải xuống kết quả nếu cần

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Xóa Văn Bản khỏi PDF sử dụng Node.js" offSpacer="" %}}

```js

    async function () {
        const pdfApi = new PdfApi(credentials.id, credentials.key);
        try {
            const fileBuffer = await fs.readFile(LOCAL_FILE_NAME);
            await pdfApi.uploadFile(STORAGE_FILENAME, fileBuffer);
            const textReplaceList =
            {
                textReplaces:
                    [
                        { oldValue: "text", newValue: "" },
                        { oldValue: "1", newValue: "" }
                    ]
            }
            const result = await pdfApi.postDocumentTextReplace(STORAGE_FILENAME, textReplaceList);
            console.log("Status:", result.body.status);
            const downloadRes = await pdfApi.downloadFile(STORAGE_FILENAME);
            await fs.writeFile(RESULT_FILENAME, downloadRes.body);
        }
        catch (error) {
            console.error(error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Với công cụ Node.js của chúng tôi, bạn có thể:" %}}

+ Thêm tiêu đề & chân trang cho tài liệu PDF dưới dạng văn bản hoặc hình ảnh.
+ Thêm bảng & tem (văn bản hoặc hình ảnh) vào tài liệu PDF.
+ Nối nhiều tài liệu PDF vào một tệp hiện có.
+ Làm việc với tệp đính kèm, chú thích, & trường biểu mẫu của PDF.
+ Áp dụng mã hóa hoặc giải mã tài liệu PDF & thiết lập mật khẩu.
+ Xóa tất cả tem & bảng từ một trang hoặc toàn bộ tài liệu PDF.
+ Xóa một tem hoặc bảng cụ thể từ tài liệu PDF theo ID của nó.
+ Thay thế một hoặc nhiều trường hợp văn bản trên một trang PDF hoặc từ toàn bộ tài liệu.
+ Hỗ trợ rộng rãi cho việc chuyển đổi tài liệu PDF sang các định dạng tệp khác nhau.
+ Trích xuất các phần tử khác nhau của tệp PDF & tối ưu hóa tài liệu PDF.
+ Bạn có thể thử [ứng dụng miễn phí của chúng tôi](https://products.aspose.app/pdf/redaction) để thay thế văn bản trong tệp PDF trực tuyến và kiểm tra chức năng.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Tài nguyên Học tập" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Tài liệu" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Mã Nguồn" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-nodejs" >}}
{{< blocks/products/pf/slr-element name="Tham khảo API" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Hỗ trợ Sản phẩm" tabId="support" >}}
{{< blocks/products/pf/slr-element name="Hỗ Trợ Miễn Phí" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="Hỗ Trợ Trả Phí" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="Blog" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Tại Sao Nên Chọn Aspose.PDF Cloud cho Node.js?" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="Danh Sách Khách Hàng" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="Bảo Mật" href="https://company.aspose.cloud/legal/security" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< /blocks/products/pf/support-learning-resources >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}



