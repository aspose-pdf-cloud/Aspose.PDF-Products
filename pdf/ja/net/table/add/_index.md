---
title: PDF .cloud NET SDKを使用した画像の追加
url: net/table/add/
description: Aspose.PDF Cloud SDK for .NETを使用してPDFに表を追加します。 ドキュメントに構造化されたレイアウトを動的に生成します。
lastmod: 2024-11-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="NET SDKでPDFに表を追加" h2="サーバーサイド.NET APIを使用してPDF文書に表を追加します。" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for .NET" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-net.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-words-cloud-dotnet" >}}

{{% blocks/products/pf/agp/content h2="Cloud .NET SDKを使用してPDFに表を追加する方法" %}}

クライアウント .NET SDKを使用してPDFに表を追加するために,
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
このクラウドSDKは、C＃、ASP.NET、または他の.NET言語で、さまざまなクラウドプラットフォームにPDF作成、編集、変換アプリを簡単に構築できます。を開きます
[NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
パッケージマネージャーで検索します
Aspose.PDF Cloud
インストールすることも可能です。 また、パッケージマネージャー コンソールから以下のコマンドを使用することもできます。

{{% blocks/products/pf/agp/code-block title="パッケージマネージャー コンソール コマンド" offSpacer="true" %}}

```powershell

    PM> Install-Package Aspose.Pdf-Cloud

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title=".NET SDKを使用してPDFに表を追加する手順" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud開発者は、わずか数行のコードでPDFに表を読み込み追加できます。

{{% /blocks/products/pf/agp/text %}}

1. ファイルをクラウドストレージにアップロード
1. 表の外観を定義します。
1. 表の内容を定義し
1. 表をPDFに追加
1. 更新ファイルをダウンロード

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="このサンプルコードは、PDF文書に表を追加する方法を示します。" offSpacer="" %}}

```cs

    public static void Add()
    {
        const string localImageFileName = @"C:\Samples\sample-test.pdf";
        const string storageFileName = "Sample-Document-02.pdf";
        const string resultFileName = "Sample-Document-02.pdf";

        // Get your AppSid and AppSecret from https://dashboard.aspose.cloud (free registration required).
        var pdfApi = new PdfApi(AppSecret, AppSid);
        if (pdfApi.GetFilesList(".").Value.All(f => f.Name != storageFileName))
        {
            using var file = File.OpenRead(localImageFileName);
            var uploadResult = pdfApi.UploadFile(storageFileName, file);
            Console.WriteLine(uploadResult.Uploaded[0]);
        }
        var decor = new GraphInfo(
            Color: new Color(255, 0, 0, 255),
            LineWidth: 2,
            IsDoubled: true);

        List<Cell> cells = [
            new(HtmlFragment : "<strong>Cell 1</strong>"),
            new(HtmlFragment : "<strong>Cell 2</strong>")];
        var rows = new List<Row>()
        {
            new(Cells:cells)
        };

        Table demoTable = new(Rows: rows, Top: 600, Left: 10)
        {
            Border = new BorderInfo(decor, decor, decor, decor),
            ColumnWidths = "150 300"
        };

        List<Table> tables = [demoTable];
        pdfApi.PostPageTables(storageFileName, pageNumber: 1, tables);
        pdfApi.DownloadFile(storageFileName)
            .CopyTo(File.Create(resultFileName));
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="PDFで表操作" %}}

表は、データを体系的に提示するための構造化フォーマットを提供し、読み手が情報を理解、分析しやすくします。 また、文章の美観を向上させ、プロフェッショナルさと組織化を追加します。 数値データまたは比較データを扱う場合、表は関連情報を読みやすい形式でグループ化することで明確さを向上させます。 また、表にはリアルタイムまたは動的に生成されたコンテンツ、例えばデータベースや分析ダッシュボードの情報を含めることができます。
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/net/) でPDFドキュメントに表を追加します。

**当社の.NETライブラリでは以下が可能です:**

+ PDF文書のヘッダーとフッターをテキストまたは画像形式で追加します。
+ PDF文書に表やスタンプ(テキストまたは画像)を追加します。
+ 複数のPDF文書を既存のファイルに追加します。
+ PDF添付ファイル、注釈、およびフォームフィールドを操作します。
+ PDF文書に暗号化または復号化を適用し、パスワードを設定します。
+ ページまたはPDF文書全体から全てのスタンプと表を削除します。
+ PDF文書からIDで特定のスタンプや表を削除します。
+ PDFページまたは全文書からテキストの単一または複数のインスタンスを置き換えます。
+ PDF文書を他のさまざまなファイル形式に変換するための拡張サポート。
+ PDFファイルの要素を抽出し、PDF文書を最適化します。
+ [無料アプリ](https://products.aspose.app/pdf/table-extraction)を使用して、PDFファイルから表を抽出し、機能を試すことができます。

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

