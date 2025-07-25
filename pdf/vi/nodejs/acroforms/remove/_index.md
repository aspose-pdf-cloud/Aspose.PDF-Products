---
title: Xóa Trường Biểu Mẫu khỏi Tài Liệu PDF qua Cloud Node.js SDK
url: nodejs/acroforms/remove/
description: Xóa các trường biểu mẫu không mong muốn khỏi PDF với Node.js sử dụng Aspose.PDF Cloud. Làm sạch và tối ưu hóa biểu mẫu của bạn.
lastmod: 2024-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Xóa Biểu Mẫu PDF trong Node.js SDK" h2="Xóa tất cả các trường biểu mẫu khỏi Tài Liệu PDF sử dụng Node.js Cloud SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Xóa AcroForms khỏi tài liệu PDF qua Cloud Node.js SDK" %}}

Để xóa AcroForms khỏi PDF, chúng ta sẽ sử dụng
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). Cloud SDK này hỗ trợ các lập trình viên Node.js trong việc phát triển ứng dụng tạo, chú thích, chỉnh sửa và chuyển đổi PDF dựa trên đám mây sử dụng ngôn ngữ lập trình Node.js thông qua Aspose.PDF REST API. Chỉ cần tạo một tài khoản tại [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) và lấy thông tin ứng dụng của bạn. Khi đã có App SID & key, bạn đã sẵn sàng sử dụng Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="Lệnh Package Manager Console" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Các bước để xóa AcroForms sử dụng Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Các nhà phát triển Aspose.PDF Cloud có thể dễ dàng tải và xóa acroforms khỏi PDF chỉ với một vài dòng mã.

{{% /blocks/products/pf/agp/text %}}

1. Tải lên tệp PDF lên dịch vụ Aspose.PDF Cloud.
1. Xóa trường biểu mẫu được chỉ định khỏi tệp đã tải lên.
1. Tải xuống kết quả nếu cần

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Mã mẫu này cho thấy cách xóa AcroForms khỏi tài liệu PDF sử dụng Node.js" offSpacer="" %}}

```js

    import credentials from "./credentials.json" with { type: "json" };
    import fs from 'node:fs/promises';
    import { PdfApi } from "asposepdfcloud";
    import { Border } from "asposepdfcloud/src/models/border";
    import { TextBoxField } from "asposepdfcloud/src/models/textBoxField";
    import { Dash } from "asposepdfcloud/src/models/dash";
    import { Rectangle } from "asposepdfcloud/src/models/rectangle";
    import { Field } from "asposepdfcloud/src/models/field";
    import { FieldType } from "asposepdfcloud/src/models/fieldType";
    import { Fields } from "asposepdfcloud/src/models/fields";

    async function removeFormField() {
        const localFileName = "C:\\Samples\\StudentInfoFormElectronic.pdf";
        const storageFileName = "StudentInfoFormElectronic.pdf";

        const pdfApi = new PdfApi(credentials.id, credentials.key);
        try {
            let fileData = await fs.readFile(localFileName);
            let uploadResult = await pdfApi.uploadFile(storageFileName, fileData);
            console.log(uploadResult.response.text);
        }
        catch (error) {
            console.error(error.message);
        }

        try {
            let response = await pdfApi.deleteField(storageFileName, "First Name");
            console.log(response.body.status);
        }
        catch (error) {
            console.log(error.message);
        }

    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Làm việc với AcroForms qua Node.js SDK" %}}

Nếu một biểu mẫu đã lỗi thời, không liên quan hoặc không còn cần thiết, xóa nó sẽ giúp tài liệu gọn gàng và phù hợp hơn. Xóa biểu mẫu có thể làm cho PDF trở nên đơn giản và dễ đọc hơn, đặc biệt nếu biểu mẫu không còn được dùng để tương tác. Các yếu tố tương tác như AcroForms có thể làm tăng kích thước tệp của PDF. Xóa chúng có thể tối ưu hóa tài liệu để chia sẻ hoặc lưu trữ nhanh hơn.
Xóa AcroForms khỏi tài liệu PDF với [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

**Với thư viện Node.js của chúng tôi, bạn có thể**

+ Thêm tiêu đề & chân trang trong văn bản hoặc định dạng hình ảnh cho tài liệu PDF.
+ Thêm bảng & con dấu (văn bản hoặc hình ảnh) vào tài liệu PDF.
+ Ghép nối nhiều tài liệu PDF vào một tệp hiện có.
+ Làm việc với tệp đính kèm, chú thích & trường biểu mẫu của PDF.
+ Áp dụng mã hóa hoặc giải mã cho tài liệu PDF & đặt mật khẩu.
+ Xóa tất cả con dấu & bảng từ một trang hoặc toàn bộ tài liệu PDF.
+ Xóa con dấu hoặc bảng cụ thể từ tài liệu PDF theo ID của nó.
+ Thay thế một hoặc nhiều trường hợp văn bản trên một trang PDF hoặc từ toàn bộ tài liệu.
+ Hỗ trợ rộng rãi cho việc chuyển đổi tài liệu PDF sang nhiều định dạng tệp khác.
+ Trích xuất các yếu tố khác nhau của tệp PDF & tối ưu hóa tài liệu PDF.
+ Bạn có thể thử [ứng dụng miễn phí của chúng tôi](https://products.aspose.app/pdf/xfa) để xóa AcroForms khỏi tệp PDF trực tuyến và kiểm tra chức năng.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Tài Nguyên Học Tập" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Tài Liệu" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Mã Nguồn" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-nodejs" >}}
{{< blocks/products/pf/slr-element name="Tham Khảo API" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Hỗ Trợ Sản Phẩm" tabId="support" >}}
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



