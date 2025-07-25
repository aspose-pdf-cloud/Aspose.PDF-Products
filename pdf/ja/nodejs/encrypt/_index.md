---
title: Node.js SDKでPDFを暗号化
url: nodejs/encrypt/
description: Aspose.PDF Cloudを使用すると、PDFドキュメントを暗号化できます。PDFファイルを暗号化するためのNode.jsソースコードを確認してください。
lastmod: 2025-04-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Node.js SDKでPDFをパスワード保護" h2="Cloud Node.js SDKを使用してPDFドキュメントを暗号化するためのAPI" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Node.js SDKでPDFを暗号化する方法" %}}

PDFドキュメントを暗号化するために、
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/)を使用します。このCloud SDKは、Node.jsプログラマーがAspose.PDF REST APIを通じてクラウドベースのPDF作成、注釈付け、編集、変換アプリをNode.jsプログラミング言語を使用して開発することを支援します。[Aspose for Cloud](https://dashboard.aspose.cloud/#/apps)でアカウントを作成し、アプリケーション情報を取得してください。App SIDとキーを取得したら、Aspose.PDF Cloud Node.js SDKを試す準備が整います。

{{% blocks/products/pf/agp/code-block title="パッケージマネージャーコンソールコマンド" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Cloud Node.jsを介してPDFを暗号化する手順" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloudの開発者は、数行のコードで簡単にPDFを読み込み、暗号化できます。

{{% /blocks/products/pf/agp/text %}}

1. ローカルのPDFファイルを読み込みます。
1. PDFファイルをAspose.PDF Cloudストレージにアップロードします。
1. 強力な暗号化とパスワードを使用してクラウドで暗号化します。
1. 必要に応じて結果をダウンロードします。

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Node.jsを使用してPDFを暗号化" offSpacer="" %}}

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

{{% blocks/products/pf/agp/content h2="PDFを暗号化" %}}

PDFドキュメントを暗号化することは、機密コンテンツを保護し、プライバシーを確保し、ドキュメントの使用方法を制御するためのシンプルで強力な方法です。ビジネス契約、財務報告書、個人記録を共有する場合でも、暗号化は不正アクセス、改ざん、または誤用から情報を保護するのに役立ちます。

暗号化を適用し、適切な権限を設定することで、ドキュメントのセキュリティを強化し、業界規制に準拠し、オーディエンスとの信頼を築きます。今日のデジタル世界では、PDFの暗号化は単なる機能ではなく、責任あるデータ処理のための必要性です。
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/)を使用してPDFドキュメントを暗号化します。

**Node.jsライブラリでできること：**

+ PDFドキュメントのヘッダーとフッターをテキストまたは画像形式で追加。
+ PDFドキュメントにテーブルやスタンプ（テキストまたは画像）を追加。
+ 複数のPDFドキュメントを既存のファイルに追加。
+ PDFの添付ファイル、注釈、フォームフィールドを操作。
+ PDFドキュメントに暗号化または復号化を適用し、パスワードを設定。
+ ページまたはPDFドキュメント全体からすべてのスタンプとテーブルを削除。
+ PDFドキュメントからIDを指定して特定のスタンプまたはテーブルを削除。
+ PDFページやドキュメント全体のテキストの単一または複数のインスタンスを置換。
+ PDFドキュメントをさまざまな他のファイル形式に変換するための広範なサポート。
+ PDFファイルのさまざまな要素を抽出し、PDFドキュメントを最適化。
+ [無料アプリ](https://products.aspose.app/pdf/family/)で機能をオンラインでお試しください。

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="学習リソース" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="ドキュメント" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="ソースコード" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-nodejs" >}}
{{< blocks/products/pf/slr-element name="API リファレンス" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="製品サポート" tabId="support" >}}
{{< blocks/products/pf/slr-element name="無料サポート" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="有料サポート" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="ブログ" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="なぜ Aspose.PDF Cloud for Node.js？" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="顧客リスト" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="セキュリティ" href="https://company.aspose.cloud/legal/security" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< /blocks/products/pf/support-learning-resources >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}



