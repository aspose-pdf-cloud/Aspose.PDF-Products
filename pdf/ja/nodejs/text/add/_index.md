---
title: Cloud Node.js SDKを使用してPDFにテキストを追加
url: nodejs/text/add/
description: Aspose.PDF Cloud SDKを使用してNode.jsでPDFファイルに新しいテキストを挿入します。
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Node.js SDKでPDFにテキストを追加" h2="Cloud Node.js SDKを使用してPDFドキュメントにテキストを追加" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Node.js SDKでPDFにテキストを追加する方法" %}}

以下のAspose.PDFによるコードスニペットは、PDFとカスタムフォントファイルを読み込み、カスタムスタイル（テキストカラー、背景色、フォント、回転、整列、間隔）を持つアイテムを定義し、段落をページ上のどの矩形に配置するかを指定します。これはPDFページの特定のエリアにスタイライズされたテキストを追加するのに便利です。

PDFにテキストを追加するには、
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/)を使用します。このCloud SDKは、Node.jsプログラマーがAspose.PDF REST APIを介してNode.jsプログラミング言語を使用して、クラウドベースのPDF作成、注釈、編集、変換アプリを開発するのを支援します。[Aspose for Cloud](https://dashboard.aspose.cloud/#/apps)でアカウントを作成し、アプリケーション情報を取得するだけです。App SID & キーを取得したら、Aspose.PDF Cloud Node.js SDKを使用できる準備が整います。

{{% blocks/products/pf/agp/code-block title="パッケージマネージャーコンソールコマンド" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Cloud Node.jsを介してPDFにテキストを追加する手順" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud開発者は、わずか数行のコードで簡単にPDFにテキストを読み込んで追加できます。

{{% /blocks/products/pf/agp/text %}}

1. ローカルPDFファイルを読み込む。
1. PDFファイルをAspose.PDF Cloudストレージにアップロードする。
1. フォーマットオプション（フォント、サイズ、色など）を持つTextStateオブジェクトを作成する。
1. テキストコンテンツとTextStateを持つSegmentオブジェクトを作成する。
1. Segmentを持つTextLineオブジェクトを作成する。
1. TextLine、フォーマットオプション、位置を持つParagraphオブジェクトを作成する。
1. PdfApi.putAddText()メソッドを使用してPDFファイルにParagraphを追加する。
1. 操作のステータスをログに記録する。
1. 必要に応じて結果をダウンロードする。

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Node.jsを使用してPDFにテキストを追加" offSpacer="" %}}

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

{{% blocks/products/pf/agp/content h2="PDFでテキストを操作する" %}}

テキストは特定のユーザーに合わせてPDFをカスタマイズするために動的に追加できます。例えば、名前やパーソナライズされたメッセージを追加することができます。これはマーケティング資料やパーソナライズされたレポートでよく使用されます。特定のフォント、色、整列でテキストを追加することで、特定のセクションをより読みやすく視覚的に魅力的にし、より良いユーザーエクスペリエンスを提供します。テキストの追加は、手動編集を避け、異なるPDFバージョン間で一貫した情報を維持し、重要な情報を確保するのに役立ちます。
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/)を使用してPDFドキュメントにテキストを追加します。

**私たちのNode.jsライブラリを使用すると、次のことができます:**

+ PDFドキュメントのヘッダーとフッターをテキストまたは画像形式で追加。
+ PDFドキュメントにテーブルとスタンプ（テキストまたは画像）を追加。
+ 複数のPDFドキュメントを既存のファイルに追加。
+ PDFの添付ファイル、注釈、フォームフィールドを操作。
+ PDFドキュメントに暗号化や復号化を適用し、パスワードを設定。
+ ページまたはPDFドキュメント全体からすべてのスタンプとテーブルを削除。
+ PDFドキュメントからIDで特定のスタンプまたはテーブルを削除。
+ PDFページまたはドキュメント全体からテキストの単一または複数のインスタンスを置換。
+ PDFドキュメントをさまざまな他のファイル形式に変換するための広範なサポート。
+ PDFファイルのさまざまな要素を抽出し、PDFドキュメントを最適化。
+ 無料の[アプリ](https://products.aspose.app/pdf/editor)を試して、オンラインでPDFファイルにテキストを追加し、機能をテストできます。

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="学習リソース" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="ドキュメント" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="ソースコード" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-nodejs" >}}
{{< blocks/products/pf/slr-element name="APIリファレンス" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="製品サポート" tabId="support" >}}
{{< blocks/products/pf/slr-element name="無料サポート" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="有料サポート" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="ブログ" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="なぜNode.js向けAspose.PDF Cloudなのか？" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="顧客リスト" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="セキュリティ" href="https://company.aspose.cloud/legal/security" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< /blocks/products/pf/support-learning-resources >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}



