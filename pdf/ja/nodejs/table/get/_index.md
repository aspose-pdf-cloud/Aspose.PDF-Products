---
title: Cloud Node.js SDKを使用してPDFからテーブルを取得
url: nodejs/table/get/
description: Aspose.PDF Cloudを使用すると、PDFドキュメントからテーブルを取得できます。Node.jsのソースコードを確認して、PDFファイルからテーブルを取得してください。
lastmod: 2024-11-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Node.js SDKでPDFからテーブルを抽出" h2="Cloud Node.js SDKを使用してPDFドキュメント内のテーブルを操作するためのAPI" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Node.js SDKを介してPDFからテーブルを取得する方法" %}}

PDFからテーブルを取得するには、
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/)を使用します。このCloud SDKは、Node.jsプログラマーがAspose.PDF REST APIを介してクラウドベースのPDF作成、注釈付け、編集、変換アプリをNode.jsプログラミング言語で開発するのを支援します。[Aspose for Cloud](https://dashboard.aspose.cloud/#/apps)でアカウントを作成し、アプリケーション情報を取得してください。App SIDとキーを取得したら、Aspose.PDF Cloud Node.js SDKを使用する準備が整います。

{{% blocks/products/pf/agp/code-block title="パッケージマネージャーコンソールコマンド" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Cloud Node.jsを介してPDFからテーブルを取得する手順" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud開発者は、わずか数行のコードでPDFからテーブルを簡単にロードおよび取得できます。

{{% /blocks/products/pf/agp/text %}}

1. ローカルPDFファイルを読み取ります。
1. ローカルPDFをAspose Cloudにアップロードします。
1. 検出されたすべてのテーブルを取得して表示します。
1. IDで指定された1つのテーブルを取得して表示します。
1. Aspose PDF Cloudストレージから更新されたPDFファイルをダウンロードします。

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Node.jsを使用してPDFからテーブルを取得" offSpacer="" %}}

```js

    import credentials from "../../../../Credentials/credentials.json"  with { type: "json" };
    import fs from 'node:fs/promises';
    import path from 'node:path';
    import { PdfApi } from "../../../src/api/api.js";

    const configParams = {
        LOCAL_FOLDER: "C:\\Samples\\",
        PDF_DOCUMENT_NAME: "sample.pdf",
        PAGE_NUMBER: 2,                                 // Your document page number...
        TABLE_ID: "GE5TCOZSGAYCYNRQGUWDINZVFQ3DGMA",    // Your table id...
    };

    const pdfApi = new PdfApi(credentials.id, credentials.key);

    const pdfTables = {
        async uploadDocument () {
            const fileNamePath = path.join(configParams.LOCAL_FOLDER, configParams.PDF_DOCUMENT_NAME);
            const pdfFileData = await fs.readFile(fileNamePath);
            await pdfApi.uploadFile(configParams.PDF_DOCUMENT_NAME, pdfFileData);
        },
                            
        async getAllTables () {
            const resultTabs = await pdfApi.getDocumentTables(configParams.PDF_DOCUMENT_NAME);

            if (resultTabs.body.code == 200 && resultTabs.body.tables) {
                if (!Array.isArray(resultTabs.body.tables.list) || resultTabs.body.tables.list.length === 0) {
                    throw new Error("Unexpected error : tables is null or empty!!!");
                }
                this.showTablesInfo(resultTabs.body.tables.list, "All tables");
                return resultTabs.body.tables.list;
            }
            else
                console.error("Unexpected error : can't get links!!!");
        },

        async getTableById () {
            const resultTabs = await pdfApi.getTable(configParams.PDF_DOCUMENT_NAME, configParams.TABLE_ID);

            if (resultTabs.body.code == 200 && resultTabs.body.table) {
                this.showTablesInfo( [ resultTabs.body.table ], "Table by Id");
                return resultTabs.body.table;
            }
            else
                console.error("Unexpected error : can't get links!!!");
        },

        showTablesInfo(tables, prefix) {
            if (Array.isArray(tables) && tables.length > 0)
            {
                tables.forEach(function(table) {
                    console.log(prefix +" => id: '" + table.id + "', page: '" + table.pageNum + "', rows: '" + table.rowList.length + "', columns: '" + table.rowList[0].cellList.length + "'");
                });
            }
            else
                console.error("showBoormarks() error: array of tables is empty!")
        },
    }

    async function main() {
        try {
            await pdfTables.uploadDocument();
            await pdfTables.getAllTables();
            await pdfTables.getTableById();
        } catch (error) {
            console.error("Error:", error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="PDFからテーブルを取得" %}}

PDFドキュメントからテーブルを抽出することは、静的で非構造化なコンテンツを使用可能な構造化データに変換するために不可欠です。これにより、効率的なデータ分析、自動化、ビジネスシステムとの統合、デジタルトランスフォーメーションが可能になります。このプロセスは時間を節約し、精度を向上させ、大規模なドキュメント処理をサポートし、レポート、アプリケーション、監査でデータを簡単に再利用できるようにします。
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/)を使用してPDFドキュメントからテーブルを抽出します。

**Node.jsライブラリでできること:**

+ PDFドキュメントのヘッダーとフッターをテキストまたは画像形式で追加します。
+ PDFドキュメントにテーブルやスタンプ（テキストまたは画像）を追加します。
+ 複数のPDFドキュメントを既存のファイルに追加します。
+ PDF添付ファイル、注釈、およびフォームフィールドを操作します。
+ PDFドキュメントに暗号化または復号化を適用し、パスワードを設定します。
+ ページまたはPDFドキュメント全体からすべてのスタンプとテーブルを削除します。
+ IDで指定されたPDFドキュメントから特定のスタンプまたはテーブルを削除します。
+ PDFページまたはドキュメント全体からテキストの単一または複数のインスタンスを置換します。
+ PDFドキュメントをさまざまな他のファイル形式に変換するための広範なサポート。
+ PDFファイルのさまざまな要素を抽出し、PDFドキュメントを最適化します。
+ [無料アプリ](https://products.aspose.app/pdf/table-extraction)を試して、オンラインでPDFファイルにテーブルを抽出し、機能をテストできます。

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

{{< blocks/products/pf/slr-tab tabTitle="なぜ Aspose.PDF Cloud for Node.js なのか？" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="顧客リスト" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="セキュリティ" href="https://company.aspose.cloud/legal/security" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< /blocks/products/pf/support-learning-resources >}}

<!-- aboutfile 終了 -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}



