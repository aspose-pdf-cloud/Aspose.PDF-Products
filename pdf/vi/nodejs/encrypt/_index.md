---
title: Mã hóa PDF trong Node.js SDK
url: nodejs/encrypt/
description: Aspose.PDF Cloud cho phép bạn mã hóa Tài liệu PDF. Kiểm tra mã nguồn Node.js để mã hóa tệp PDF.
lastmod: 2025-04-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Bảo vệ bằng mật khẩu PDF trong Node.js SDK" h2="API để mã hóa tài liệu PDF bằng Cloud Node.js SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Cách mã hóa PDF qua Node.js SDK" %}}

Để mã hóa tài liệu PDF, chúng tôi sẽ sử dụng
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). SDK Đám mây này hỗ trợ các lập trình viên Node.js phát triển ứng dụng tạo, ghi chú, chỉnh sửa và chuyển đổi PDF dựa trên đám mây bằng ngôn ngữ lập trình Node.js thông qua Aspose.PDF REST API. Chỉ cần tạo tài khoản tại [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) và nhận thông tin ứng dụng của bạn. Khi bạn có App SID & key, bạn đã sẵn sàng để sử dụng Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="Lệnh Package Manager Console" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Các bước mã hóa PDF qua Cloud Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Các nhà phát triển Aspose.PDF Cloud có thể dễ dàng tải và mã hóa PDF chỉ trong vài dòng mã.

{{% /blocks/products/pf/agp/text %}}

1. Đọc tệp PDF cục bộ.
1. Tải tệp PDF lên lưu trữ Aspose.PDF Cloud.
1. Mã hóa nó trong đám mây bằng mã hóa mạnh và mật khẩu.
1. Tải xuống kết quả nếu cần.

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Mã hóa PDF bằng Node.js" offSpacer="" %}}

```js

    import credentials from "../../../Credentials/credentials.json"  with { type: "json" };    // json-file in this format: { "id": "*****", "key": "*******" }
    import fs from 'node:fs/promises';
    import path from 'node:path';
    import { PdfApi } from "../../src/api/api.js";
    import { CryptoAlgorithm } from "../../src/models/cryptoAlgorithm.js";

    const configParams = {
        LOCAL_FOLDER: "C:\\Samples\\",
        PDF_DOCUMENT_NAME: "sample.pdf",
        LOCAL_RESULT_DOCUMENT_NAME: "output_sample.pdf",
        ENCRYPT_ALGORITHM: CryptoAlgorithm.AESx256,
        USER_PASSWORD: "User-Password",
        OWNER_PASSWORD: "Owner-Password",
    };

    const pdfApi = new PdfApi(credentials.id, credentials.key);

    const pdfEncoder = {
        async uploadDocument () {
            const fileNamePath = path.join(configParams.LOCAL_FOLDER, configParams.PDF_DOCUMENT_NAME);
            const pdfFileData = await fs.readFile(fileNamePath);
            await pdfApi.uploadFile(configParams.PDF_DOCUMENT_NAME, pdfFileData)
                .then(() => console.log("File: '" + configParams.PDF_DOCUMENT_NAME +"' successfully uploaded."));
        },

        async downloadResult() {
            const changedPdfData = await pdfApi.downloadFile(configParams.PDF_DOCUMENT_NAME);
            const filePath = path.join(configParams.LOCAL_FOLDER, configParams.LOCAL_RESULT_DOCUMENT_NAME);
            await fs.writeFile(filePath, changedPdfData.body);
            console.log("Downloaded: " + filePath);
        },

        async encrypt_document() {
            const user_password_encoded = btoa(configParams.USER_PASSWORD)

            const owner_password_encoded = btoa(configParams.OWNER_PASSWORD)

            const response = await pdfApi.postEncryptDocumentInStorage(configParams.PDF_DOCUMENT_NAME, user_password_encoded, owner_password_encoded, configParams.ENCRYPT_ALGORITHM);
            
            if (response.body.code == 200)
                console.log("encrypt_document(): Document #'" + configParams.PDF_DOCUMENT_NAME + "' successfully encrypted.")
            else
                throw new Error("encrypt_document(): Failed to encrypt document #'" + configParams.PDF_DOCUMENT_NAME + "'. Response code: {" + response.code + "}")
        },
        
    }

    async function main() {
        try {
            await pdfEncoder.uploadDocument();
            await pdfEncoder.encrypt_document();
            await pdfEncoder.downloadResult();
        } catch (error) {
            console.error("Error:", error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Mã hóa PDF" %}}

Mã hóa một tài liệu PDF là một cách đơn giản nhưng mạnh mẽ để bảo vệ nội dung nhạy cảm, đảm bảo quyền riêng tư và duy trì quyền kiểm soát cách tài liệu được sử dụng. Cho dù bạn đang chia sẻ hợp đồng kinh doanh, báo cáo tài chính hay hồ sơ cá nhân, mã hóa giúp bảo vệ thông tin của bạn khỏi truy cập trái phép, can thiệp hoặc lạm dụng.

Bằng cách áp dụng mã hóa và thiết lập các quyền phù hợp, bạn tăng cường bảo mật tài liệu, đảm bảo tuân thủ các quy định ngành và xây dựng niềm tin với khán giả của bạn. Trong thế giới kỹ thuật số ngày nay, mã hóa PDF không chỉ là một tính năng—nó là một nhu cầu cần thiết cho việc xử lý dữ liệu có trách nhiệm.
Mã hóa tài liệu PDF với [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

**Với thư viện Node.js của chúng tôi, bạn có thể:**

+ Thêm tiêu đề & chân trang tài liệu PDF ở định dạng văn bản hoặc hình ảnh.
+ Thêm bảng & tem (văn bản hoặc hình ảnh) vào tài liệu PDF.
+ Thêm nhiều tài liệu PDF vào một tệp hiện có.
+ Làm việc với tệp đính kèm, chú thích & trường biểu mẫu của PDF.
+ Áp dụng mã hóa hoặc giải mã cho tài liệu PDF & đặt mật khẩu.
+ Xóa tất cả tem & bảng từ một trang hoặc toàn bộ tài liệu PDF.
+ Xóa một tem hoặc bảng cụ thể khỏi tài liệu PDF bằng ID của nó.
+ Thay thế một hoặc nhiều trường hợp văn bản trên một trang PDF hoặc từ toàn bộ tài liệu.
+ Hỗ trợ rộng rãi cho việc chuyển đổi tài liệu PDF sang các định dạng tệp khác nhau.
+ Trích xuất các yếu tố khác nhau của tệp PDF và tối ưu hóa tài liệu PDF.
+ Bạn có thể thử các [ứng dụng miễn phí](https://products.aspose.app/pdf/family/) của chúng tôi để kiểm tra chức năng trực tuyến.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Tài nguyên Học tập" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Tài liệu" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Mã nguồn" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-nodejs" >}}
{{< blocks/products/pf/slr-element name="Tham chiếu API" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Hỗ trợ sản phẩm" tabId="support" >}}
{{< blocks/products/pf/slr-element name="Hỗ trợ miễn phí" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="Hỗ trợ trả phí" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="Blog" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Tại sao chọn Aspose.PDF Cloud cho Node.js?" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="Danh sách khách hàng" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="Bảo mật" href="https://company.aspose.cloud/legal/security" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< /blocks/products/pf/support-learning-resources >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}



