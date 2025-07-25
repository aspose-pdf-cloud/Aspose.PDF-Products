---
title: PDFドキュメントからメタデータを取得する方法 — Cloud .NET SDK
url: net/metadata/get/
description: Aspose.PDF Cloud SDK for .NETを使用してPDFのメタデータを取得します。APIを使用してドキュメントの詳細を簡単に分析します。
lastmod: 2022-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="PDFからメタデータを取得する方法 in .NET SDK" h2="サーバーサイドAPIを使用して、クラウドアプリを構築します。" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for .NET" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-net.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-words-cloud-dotnet" >}}

{{% blocks/products/pf/agp/content h2="Cloud .NET SDKを使用してPDFドキュメントからメタデータを取得する方法" %}}

Cloud .NET SDK を使用してメタデータを取得する方法
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
このCloud SDKは、C#、ASP.NET、またはその他の.NET言語で、さまざまなクラウドプラットフォーム向けのクラウドベースのPDF作成、編集、および変換アプリケーションを簡単に構築することを可能にします。を開く
[NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
パッケージマネージャー
Aspose.PDF Cloud
を検索してインストールします。また、次のコマンドをパッケージマネージャーコンソールから実行することもできます。

{{% blocks/products/pf/agp/code-block title="パッケージマネージャーコンソールコマンド" offSpacer="true" %}}

```powershell

     
    PM> Install-Package Aspose.Pdf-Cloud
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title=".NET SDKを使用してメタデータを取得する手順" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud開発者は、わずか数行のコードでPDFのメタデータを簡単にロード＆取得できます。

{{% /blocks/products/pf/agp/text %}}

1. アプリケーションシークレットとキーを使用して新しい構成オブジェクトを作成
1. クラウドAPIに接続するためのオブジェクトを作成します。
1. ドキュメントファイルをアップロードします
1. GetDocumentPropertiesを使用してすべてのプロパティを取得します
1. プロパティを処理する、例：コンソールにプリントします

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="このサンプルコードは、PDFドキュメントからメタデータを取得する方法を示しています。" offSpacer="" %}}

```cs

    public static void GetMetadata()
    {
        const string localPdfFileName = @"C:\Samples\sample.pdf";
        const string storageFileName = "sample.pdf";


        // Get your AppSid and AppSecret https://dashboard.aspose.cloud (free registration required).
        var pdfApi = new PdfApi(AppSecret, AppSid);

        if (pdfApi.GetFilesList("").Value.All(f => f.Name != "sample.pdf"))
        {
            using var file = File.OpenRead(localPdfFileName);
            var uploadResult = pdfApi.UploadFile(storageFileName, file);
            Console.WriteLine(uploadResult.Uploaded[0]);
        }

        var response = pdfApi.GetDocumentProperties(storageFileName);
        foreach (var item in response.DocumentProperties.List)
        {
            Console.WriteLine($"Name: {item.Name} Value: {item.Value}");
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

