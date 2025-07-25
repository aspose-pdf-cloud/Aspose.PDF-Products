---
title: クラウド .NET SDK でTEXをPDFに変換
url: net/conversion/tex-to-pdf/
description: Aspose.PDF Cloud SDK for .NETを使用してLaTeX .texファイルをPDFに変換します。科学的および学術的な出版に最適です。
lastmod: 2022-03-17
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1=".NET SDKでTEXをPDFに変換" h2="Aspose.PDF Cloud .NET SDKを使用して、TEXドキュメントをPDFを含む複数の形式にエクスポート" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for .NET" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-net.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-dotnet" >}}

{{% blocks/products/pf/agp/content h2=".NET SDKを使用してTEXをPDFに変換する方法" %}}

TEXをPDFに変換するために、
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
このクラウドSDKを使用すると、C#、ASP.NET、その他の.NET言語で、さまざまなクラウドプラットフォームで簡単にクラウドベースのPDF作成、編集、変換アプリを構築できます。
[NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
パッケージマネージャーを開き、
Aspose.PDF Cloud
を検索してインストールします。パッケージマネージャーコンソールから次のコマンドを使用することもできます。

{{% blocks/products/pf/agp/code-block title="パッケージマネージャーコンソールコマンド" offSpacer="true" %}}

```powershell

     
    PM> Install-Package Aspose.Pdf-Cloud
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title=".NET SDKを介してTEXをPDFに変換する手順" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloudの開発者は、わずか数行のコードでTEXファイルをPDFに簡単にロードおよび変換できます。

{{% /blocks/products/pf/agp/text %}}

1. アプリケーションシークレットとキーを使用して新しいConfigurationオブジェクトを作成
1. クラウドAPIに接続するためのオブジェクトを作成
1. ドキュメントファイルをアップロード
1. 変換を実行
1. 結果をダウンロード

{{% /blocks/products/pf/agp/feature-section-col %}}



{{% blocks/products/pf/agp/code-block title="このサンプルコードはTEXからPDFへのCloud .NET SDK変換を示しています" offSpacer="" %}}

```cs

    public static void ConvertLaTeXtoPDF()
    {
        var localHtmlFileName = @"C:\Samples\Conversion\sample.tex";
        var storageHtmlFileName = "sample.tex";

        // Get your ClientId and ClientSecret from https://dashboard.aspose.cloud (free registration required).
        var config = new Configuration(AppSecret, AppKey);

        var pdfApi = new PdfApi(config);

        using (var file = File.OpenRead(localHtmlFileName))
        {
            var uploadResult = pdfApi.UploadFile(storageHtmlFileName, file);
        }
        var response = pdfApi.PutTeXInStorageToPdf("sample-TeX-to-pdf.pdf", storageHtmlFileName);
        Console.WriteLine($"TeX to PDF result: {response.Status}");
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< blocks/products/pf/agp/other-supported-section title="その他のサポートされている変換" subTitle="他の多くのファイル形式を変換することもできます" >}}

{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/bmp-to-pdf/" name="BMP TO PDF" description="ビットマップ画像" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/emf-to-pdf/" name="EMF TO PDF" description="拡張メタファイル形式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/epub-to-pdf/" name="EPUB TO PDF" description="電子書籍形式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/gif-to-pdf/" name="GIF TO PDF" description="グラフィカルインターチェンジフォーマット" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/html-to-pdf/" name="HTML-TO-PDF" description="ハイパーテキストマークアップ言語" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/jpeg-to-pdf/" name="JPEG TO PDF" description="JPEG画像" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/md-to-pdf/" name="MD TO PDF" description="マークダウン" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pcl-to-pdf/" name="PCL TO PDF" description="プリンターコマンド言語" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-bmp/" name="PDF TO BMP" description="ビットマップ画像" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-docx/" name="PDF TO DOCX" description="Office 2007+ Wordドキュメント" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-emf/" name="PDF TO EMF" description="拡張メタファイル形式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-epub/" name="PDF TO EPUB" description="電子書籍形式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-gif/" name="PDF TO GIF" description="グラフィカルインターチェンジフォーマット" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-html/" name="PDF TO HTML" description="ハイパーテキストマークアップ言語" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-jpeg/" name="PDF TO JPEG" description="JPEG画像" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pdfa/" name="PDF TO PDF/A" description="ポータブルドキュメントフォーマット/A" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-png/" name="PDF TO PNG" description="ポータブルネットワークグラフィックス" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pptx/" name="PDF TO PPTX" description="オープンXMLプレゼンテーションフォーマット" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-svg/" name="PDF TO SVG" description="スケーラブルベクターグラフィックス" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-tex/" name="PDF TO TEX" description="LaTeX出力テキスト" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-tiff/" name="PDF TO TIFF" description="タグ付き画像形式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-txt/" name="PDF TO TXT" description="テキストドキュメント" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-xlsx/" name="PDF TO XLSX" description="OOXML Excelファイル" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-xps/" name="PDF TO XPS" description="XMLペーパー仕様" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pptx/" name="PDF TO PPTX" description="オープンXMLプレゼンテーションフォーマット" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/png-to-pdf/" name="PNG TO PDF" description="ポータブルネットワークグラフィックス" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/svg-to-pdf/" name="SVG TO PDF" description="スケーラブルベクターグラフィックス" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/tex-to-pdf/" name="TEX TO PDF" description="LaTeX出力テキスト" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/text-to-pdf/" name="TEXT TO PDF" description="テキストドキュメント" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/tiff-to-pdf/" name="TIFF TO PDF" description="タグ付き画像形式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/xps-to-pdf/" name="XPS TO PDF" description="XMLペーパー仕様" >}}

{{< /blocks/products/pf/agp/other-supported-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}


