---
title: Lấy Siêu Dữ Liệu từ Tài Liệu PDF qua Cloud Node.js SDK
url: nodejs/metadata/get/
description: Truy xuất siêu dữ liệu từ tài liệu PDF sử dụng Node.js và Aspose.PDF Cloud SDK.
lastmod: 2024-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Lấy Siêu Dữ Liệu từ PDF trong Node.js SDK" h2="Lấy tất cả siêu dữ liệu từ tài liệu PDF sử dụng Cloud Node.js SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Cách lấy Siêu Dữ Liệu qua Node.js SDK" %}}

Để lấy Siêu Dữ Liệu, chúng ta sẽ sử dụng
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). Cloud SDK này hỗ trợ lập trình viên Node.js phát triển ứng dụng tạo PDF, ghi chú, chỉnh sửa và chuyển đổi dựa trên đám mây sử dụng ngôn ngữ lập trình Node.js qua Aspose.PDF REST API. Chỉ cần tạo tài khoản tại [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) và nhận thông tin ứng dụng của bạn. Khi bạn có App SID & key, bạn đã sẵn sàng để sử dụng Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="Lệnh Console Quản Lý Gói" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Các bước để lấy Siêu Dữ Liệu qua Cloud Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Các nhà phát triển Aspose.PDF Cloud có thể dễ dàng tải và lấy siêu dữ liệu từ PDF chỉ với vài dòng mã.

{{% /blocks/products/pf/agp/text %}}

1. Đọc tệp PDF từ hệ thống tệp cục bộ.
1. Tải lên tệp PDF lên lưu trữ Aspose.PDF Cloud.
1. Truy xuất các thuộc tính siêu dữ liệu XMP từ tệp PDF.
1. Ghi lại các thuộc tính siêu dữ liệu XMP ra console.

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Lấy Siêu Dữ Liệu từ PDF sử dụng Node.js" offSpacer="" %}}

```js

    const fs = require("fs");
    const { PdfApi } = require("asposepdfcloud");

    async function getXmpMetadataProperty()
    {
        const api = new PdfApi("YOUR_API_SID", "YOUR_API_KEY");
        const fileName = "Sample.pdf";
        const folder = "Documents";
        const storage = null;
        const password = null;
        
        const buffer = fs.readFileSync(fileName);
        await api.uploadFile(folder + "/" +fileName, buffer, storage)

        const metadata = await api.getXmpMetadataJson(fileName, folder, storage, password);  
        console.log("XMP metadata:");
        metadata.body.properties.forEach(property => 
        {
            console.log("    " + property.key + " = " + property.value);
        });
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Làm việc với Siêu Dữ Liệu trong PDF" %}}

Làm việc với siêu dữ liệu trong các tệp PDF là quan trọng. Siêu dữ liệu như trường tiêu đề, tác giả và chủ đề giúp phân loại tài liệu, làm cho việc quản lý các bộ sưu tập tài liệu lớn dễ dàng hơn bằng cách cung cấp cái nhìn tổng quan nhanh về nội dung mà không cần mở tệp.
Siêu dữ liệu cũng cải thiện việc tìm kiếm tệp bằng cách cho phép tìm kiếm theo từ khóa và thuộc tính. Đây là điều đặc biệt có giá trị trong các hệ thống nơi khả năng truy xuất tài liệu nhanh chóng là điều cần thiết.
Thêm siêu dữ liệu vào tài liệu PDF với [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

**Với thư viện Node.js của chúng tôi, bạn có thể:**

+ Thêm tiêu đề & chân trang của tài liệu PDF dưới dạng văn bản hoặc hình ảnh.
+ Thêm bảng & con dấu (văn bản hoặc hình ảnh) vào tài liệu PDF.
+ Nối nhiều tài liệu PDF vào một tệp hiện có.
+ Làm việc với các tệp đính kèm PDF, ghi chú, & trường mẫu.
+ Áp dụng mã hóa hoặc giải mã cho tài liệu PDF & đặt mật khẩu.
+ Xóa tất cả con dấu & bảng từ một trang hoặc toàn bộ tài liệu PDF.
+ Xóa một con dấu hoặc bảng cụ thể từ tài liệu PDF theo ID của nó.
+ Thay thế một hoặc nhiều lần xuất hiện của văn bản trên một trang PDF hoặc từ toàn bộ tài liệu.
+ Hỗ trợ rộng rãi cho việc chuyển đổi tài liệu PDF sang nhiều định dạng tệp khác nhau.
+ Trích xuất các phần tử khác nhau của các tệp PDF & tối ưu hóa tài liệu PDF.
+ Bạn có thể thử [ứng dụng miễn phí](https://products.aspose.app/pdf/metadata) của chúng tôi để lấy siêu dữ liệu từ các tệp PDF trực tuyến và kiểm tra chức năng.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Tài Nguyên Học Tập" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Tài Liệu" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Mã Nguồn" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-nodejs" >}}
{{< blocks/products/pf/slr-element name="Tham chiếu API" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Hỗ trợ Sản phẩm" tabId="support" >}}
{{< blocks/products/pf/slr-element name="Hỗ trợ Miễn phí" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="Hỗ trợ Trả phí" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="Blog" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Tại sao chọn Aspose.PDF Cloud cho Node.js?" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="Danh sách Khách hàng" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="Bảo mật" href="https://company.aspose.cloud/legal/security" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< /blocks/products/pf/support-learning-resources >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}



