---
title: Aspose.Pdf Cloud Node.js SDKを使用してPDFドキュメントから添付ファイルを抽出
url: nodejs/attachments/get/
description: Node.jsおよびAspose.PDF Cloud SDKを使用してPDF添付ファイルを抽出します。APIを介して埋め込みコンテンツにアクセスします。
lastmod: 2024-10-29
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Node.js SDKでPDFから添付ファイルを抽出" h2="Aspose.PDF Cloud Node.js SDKでPDFドキュメントの添付ファイルを抽出するためのAPI" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Cloud Node.js SDKを使用してPDFドキュメントから添付ファイルを抽出する方法" %}}

PDFドキュメントの添付ファイルを操作するには、
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/)
このCloud SDK SDKは、Node.jsプログラマーがAspose.PDF REST APIを介してクラウドベースのPDF作成、注釈付け、編集、および変換アプリをNode.jsプログラミング言語を使用して開発するのを支援します。
[NPM](https://www.npmjs.com/package/asposepdfcloud)
パッケージマネージャを開き、
Aspose.PDF Cloudを検索し、
インストールします。パッケージマネージャコンソールから次のコマンドを使用することもできます。

{{% blocks/products/pf/agp/code-block title="パッケージマネージャコンソールコマンド" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Node.jsを使用して添付ファイルを抽出する手順" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud Node.jsの開発者は、PDFドキュメント内の添付ファイルを簡単に抽出、追加、および置換できます。開発者は数行のコードを必要とします。

{{% /blocks/products/pf/agp/text %}}

1. JSONファイルからアプリケーションシークレットとキーを読み込み、または他の方法で資格情報を設定します
1. Cloud APIに接続するためのオブジェクトを作成します
1. ドキュメントファイルをアップロードします
1. PDFドキュメントの添付ファイル抽出アクションを実行します
1. 必要に応じて結果をダウンロードします

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="このサンプルコードは、PDF Cloud Node.js SDKを使用してPDFドキュメントの添付ファイルを抽出する方法を示しています" offSpacer="" %}}

```js

    import credentials from "./credentials.json" with { type: "json" };
    import fs from 'node:fs/promises';
    import path from 'node:path';
    import { PdfApi } from "asposepdfcloud";
    import { AttachmentInfo } from "asposepdfcloud/src/models/attachmentInfo.js";

    async function getAllAttachments() {
        const LOCAL_PATH = "C:\\Samples\\";
        const LOCAL_FILE_NAME = "C:\\Samples\\Attachments\\sample_attachment.pdf";
        const STORAGE_FILE_NAME = "sample_attachment.pdf";
        try {
            const pdfApi = new PdfApi(credentials.id, credentials.key);
            const pdfData = await fs.readFile(LOCAL_FILE_NAME);
            await pdfApi.uploadFile(STORAGE_FILE_NAME, pdfData);

            const result = await pdfApi.getDocumentAttachments(STORAGE_FILE_NAME);

            if (result.body.code === 200 && result.body.attachments) {
                const attachmentList = result.body.attachments.list || [];
                if (!attachmentList.length) {
                    console.error("No attachments found.");
                    return;
                }

                const downloadTasks = attachmentList.map(async (attachment) => {
                    try {
                        const attachmentUrl = attachment.links[0].href;
                        const info = await pdfApi.getDocumentAttachmentByIndex(STORAGE_FILE_NAME, attachmentUrl);
                        const download = await pdfApi.getDownloadDocumentAttachmentByIndex(STORAGE_FILE_NAME, attachmentUrl);
                        await fs.writeFile(path.join(LOCAL_PATH, info.body.attachment.name), download.body);
                    } catch (error) {
                        console.error("Failed to download attachment:", error);
                    }
                });

                await Promise.all(downloadTasks);
            } else {
                console.error("Failed to retrieve attachments. Status:", result.statusCode);
            }
        } catch (error) {
            console.error("Error processing PDF attachments:", error);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Node.js SDKを介してPDFの添付ファイルを操作" %}}

PDFから添付ファイルを取得することは、補足コンテンツにアクセスし、ワークフロー効率を向上させ、コンプライアンスを確保し、セキュリティを強化するために重要です。重要なファイルを取得し、文書処理を自動化し、業務、法務、および技術アプリケーションでの文書管理を最適化するのに役立ちます。
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/)を使用してPDFドキュメントから添付ファイルを取得します。

**Node.jsライブラリを使用してできること**

+ テキストまたは画像形式でPDFドキュメントのヘッダーとフッターを追加します。
+ PDFドキュメントにテーブルとスタンプ（テキストまたは画像）を追加します。
+ 複数のPDFドキュメントを既存のファイルに追加します。
+ PDFの添付ファイル、注釈、およびフォームフィールドを操作します。
+ PDFドキュメントに暗号化または復号化を適用し、パスワードを設定します。
+ ページまたはPDF全体からすべてのスタンプとテーブルを削除します。
+ IDで指定された特定のスタンプまたはテーブルをPDFドキュメントから削除します。
+ PDFページまたはドキュメント全体の単一または複数のテキストインスタンスを置換します。
+ PDFドキュメントをさまざまな他のファイル形式に変換するための広範なサポート。
+ PDFファイルのさまざまな要素を抽出し、PDFドキュメントを最適化します。
+ [無料アプリ](https://products.aspose.app/pdf/xfa)を使用してオンラインでPDFファイルにAcroFormsを追加し、機能をテストできます。

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
