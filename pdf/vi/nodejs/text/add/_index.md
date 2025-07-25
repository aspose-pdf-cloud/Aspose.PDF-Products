---
title: Thêm Văn Bản vào PDF qua Cloud Node.js SDK
url: nodejs/text/add/
description: Chèn văn bản mới vào các tập tin PDF sử dụng Aspose.PDF Cloud SDK trong Node.js.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Thêm Văn Bản vào PDF trong Node.js SDK" h2="Thêm Văn Bản vào Tài Liệu PDF sử dụng Cloud Node.js SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Cách thêm Văn Bản vào PDF qua Node.js SDK" %}}

Đoạn mã sau, bởi Aspose.PDF, tải một tập tin PDF và tập tin phông chữ tùy chỉnh, định nghĩa mục với kiểu dáng tùy chỉnh (màu văn bản, màu nền, phông chữ, xoay, căn chỉnh và khoảng cách), và chỉ định hình chữ nhật trong đó đoạn văn bản nên được đặt trên trang. Điều này hữu ích cho việc thêm văn bản kiểu dáng vào một khu vực nhất định của trang PDF.

Để thêm văn bản vào PDF, chúng ta sẽ sử dụng
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). Cloud SDK này hỗ trợ các lập trình viên Node.js phát triển các ứng dụng tạo, chú thích, chỉnh sửa và chuyển đổi PDF dựa trên đám mây sử dụng ngôn ngữ lập trình Node.js qua Aspose.PDF REST API. Chỉ cần tạo một tài khoản tại [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) và nhận thông tin ứng dụng của bạn. Khi bạn đã có App SID & key, bạn đã sẵn sàng sử dụng Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="Lệnh Console Trình Quản Lý Gói" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Các bước để thêm Văn Bản vào PDF qua Cloud Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Các nhà phát triển Aspose.PDF Cloud có thể dễ dàng tải & thêm Văn Bản vào PDF chỉ với vài dòng mã.

{{% /blocks/products/pf/agp/text %}}

1. Đọc tập tin PDF địa phương.
1. Tải tập tin PDF lên lưu trữ Aspose.PDF Cloud.
1. Tạo một đối tượng TextState với các tùy chọn định dạng (phông chữ, kích thước, màu sắc, v.v.).
1. Tạo một đối tượng Segment với nội dung văn bản và TextState.
1. Tạo một đối tượng TextLine với Segment.
1. Tạo một đối tượng Paragraph với TextLine, các tùy chọn định dạng và vị trí.
1. Thêm Paragraph vào tập tin PDF sử dụng phương thức PdfApi.putAddText().
1. Ghi lại trạng thái của hoạt động.
1. Tải xuống kết quả nếu cần

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Thêm Văn Bản vào PDF sử dụng Node.js" offSpacer="" %}}

```js

    import credentials from "./credentials.json"  with { type: "json" };
    import fs from 'node:fs/promises';
    import { PdfApi } from "asposepdfcloud";
    import { Color } from "asposepdfcloud/src/models/color.js";
    import { FontStyles } from "asposepdfcloud/src/models/fontStyles.js";
    import { LineSpacing } from "asposepdfcloud/src/models/lineSpacing.js";
    import { Paragraph } from "asposepdfcloud/src/models/paragraph.js";
    import { TextHorizontalAlignment } from "asposepdfcloud/src/models/textHorizontalAlignment.js";
    import { VerticalAlignment } from "asposepdfcloud/src/models/verticalAlignment.js";
    import { WrapMode } from "asposepdfcloud/src/models/wrapMode.js";
    import { TextLine } from "asposepdfcloud/src/models/textLine.js";
    import { Segment } from "asposepdfcloud/src/models/segment.js";
    import { Rectangle } from "asposepdfcloud/src/models/rectangle.js";
    import { TextState } from "asposepdfcloud/src/models/textState.js";

    const LOCAL_FILE_NAME = "c:\\Samples\\sample.pdf";
    const STORAGE_FILENAME = "sample.pdf";
    const PAGE_NUMBER = 1;
    const TEXT_CONTENT = "Lorem ipsum dolor sit amet, consectetur adipiscing elit.";

    async function add() {
        const pdfApi = new PdfApi(credentials.id, credentials.key);
        try {

            const fileBuffer = await fs.readFile(LOCAL_FILE_NAME);
            await pdfApi.uploadFile(STORAGE_FILENAME, fileBuffer);

            const textState = Object.assign(new TextState(), {
                fontSize: 20,
                font: "Arial",
                foregroundColor: Object.assign(new Color(), { a: 255, r: 0, g: 0, b: 255 }),
                backgroundColor: Object.assign(new Color(), { a: 255, r: 255, g: 255, b: 0 }),
                fontStyle: FontStyles.Regular,
                underline: true
            });

            const segment = Object.assign(new Segment(),
                {
                    value: TEXT_CONTENT,
                    textState: textState
                });

            const textLine = Object.assign(new TextLine(), { segments: [segment] });

            const paragraph = Object.assign(new Paragraph(), {
                lineSpacing: LineSpacing.FullSize,
                wrapMode: WrapMode.ByWords,
                rectangle: Object.assign(new Rectangle(), { lLX: 10, lLY: 10, uRX: 300, uRY: 500 }),
                horizontalAlignment: TextHorizontalAlignment.FullJustify,
                verticalAlignment: VerticalAlignment.Center,
                lines: [textLine]
            });

            const result = await pdfApi.putAddText(
                STORAGE_FILENAME,
                PAGE_NUMBER,
                paragraph
            );

            console.log(result.body.status);
            const buffer = await pdfApi.downloadFile(STORAGE_FILENAME);
        } catch (error) {
            console.error("Error adding text to PDF:", error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Làm việc với Văn Bản trong PDF" %}}

Văn bản có thể được thêm vào một cách động để tùy chỉnh PDF cho một người dùng cụ thể, chẳng hạn như thêm tên của họ hoặc thông điệp cá nhân hóa. Điều này thường được sử dụng trong tài liệu tiếp thị hoặc cho các báo cáo cá nhân hóa. Thêm văn bản với các phông chữ, màu sắc và căn chỉnh cụ thể có thể làm cho một số phần dễ đọc hơn và thu hút hơn về mặt thị giác, tạo ra trải nghiệm người dùng tốt hơn. Việc thêm văn bản có thể giúp duy trì thông tin nhất quán giữa các phiên bản PDF khác nhau, tránh các chỉnh sửa thủ công và đảm bảo rằng thông tin quan trọng vẫn được giữ nguyên.
Thêm Văn Bản vào tài liệu PDF với [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

**Với thư viện Node.js của chúng tôi, bạn có thể:**

+ Thêm tiêu đề & chân trang của tài liệu PDF ở định dạng văn bản hoặc hình ảnh.
+ Thêm bảng & con dấu (văn bản hoặc hình ảnh) vào tài liệu PDF.
+ Nối nhiều tài liệu PDF vào một tập tin hiện có.
+ Làm việc với các tệp đính kèm PDF, chú thích và trường biểu mẫu.
+ Áp dụng mã hóa hoặc giải mã cho tài liệu PDF & đặt mật khẩu.
+ Xóa tất cả con dấu & bảng từ một trang hoặc toàn bộ tài liệu PDF.
+ Xóa một con dấu hoặc bảng cụ thể từ tài liệu PDF bằng ID của nó.
+ Thay thế một hoặc nhiều trường hợp của văn bản trên một trang PDF hoặc từ toàn bộ tài liệu.
+ Hỗ trợ rộng rãi cho việc chuyển đổi tài liệu PDF sang nhiều định dạng tập tin khác.
+ Trích xuất các yếu tố khác nhau của tập tin PDF & tối ưu hóa tài liệu PDF.
+ Bạn có thể thử [Ứng dụng miễn phí của chúng tôi](https://products.aspose.app/pdf/editor) để thêm văn bản vào các tập tin PDF trực tuyến và kiểm tra chức năng.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Tài nguyên học tập" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Tài liệu" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Mã nguồn" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-nodejs" >}}
{{< blocks/products/pf/slr-element name="Tham khảo API" href="https://reference.aspose.cloud/pdf/" >}}
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



