---
title: クラウド .NET SDKを使用してPDFファイルをマージ
url: net/merge/
description: Aspose.PDF Cloud SDK for .NETで複数のPDFを1つにマージ。REST APIを通じてドキュメントをシームレスに結合。
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="NET SDKでPDFをマージ" h2="C#Cloud APIを使用してAdobe PDFのようなソフトウェアを使用せずに2つのPDFファイルを1つにマージ。" logoImageSrc="https://www.aspose.cloud/templates/aspose/img/products/pdf/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for .NET" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for .NET" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://www.aspose.cloud/templates/aspose/img/products/pdf/aspose_pdf-for-net.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://downloads.aspose.cloud/pdf/net" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="C# Cloud APIを使用して複数のPDFファイルをマージする方法" %}}

2つのPDFファイルをマージするために、我々は、
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
このクラウドSDKは、C#、ASP.NET、または他の.NET言語を使用して、さまざまなクラウドプラットフォーム向けのクラウドベースのPDF作成、編集、変換アプリを簡単に構築できるようにします。開く、
[NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
パッケージマネージャー、
Aspose.PDF Cloud
を検索し、インストールします。また、パッケージマネージャーコンソールから以下のコマンドを使用することもできます。

{{% blocks/products/pf/agp/code-block title="コマンド" offSpacer="true" %}}

```powershell

PM> Install-Package Aspose.Pdf-Cloud 



```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="クラウド .NET SDKを使用してPDFをマージする手順" %}}

{{% blocks/products/pf/agp/text %}}

数行のコードで、
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
APIを使用してPDFをプログラムでマージする基本的な方法。

{{% /blocks/products/pf/agp/text %}}

アプリケーションキーとシークレットで新しい設定オブジェクトを作成します
クラウドAPIに接続するオブジェクトを作成します
ドキュメントファイルをアップロードします
マージを実行します
結果をダウンロードします

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="C#を使用して2つのPDFファイルをマージ" offSpacer="" %}}

```cs

    internal static void MergePdf()
    {
        const string localImageFileName = @"C:\Samples\sample.pdf";
        const string storageFileName1 = "sample1.pdf";
        const string storageFileName2 = "sample2.pdf";
        const string resultFileName = "merged-doc.pdf";

        // Get your AppSid and AppSecret https://dashboard.aspose.cloud (free registration required).
        var pdfApi = new PdfApi(AppSecret, AppSid);
        using var file = File.OpenRead(localImageFileName);
        pdfApi.UploadFile(storageFileName1, file);
        pdfApi.CopyFile(storageFileName1, storageFileName2);

        var documentsToBeMerged = new List<string>()
        {
            storageFileName1, storageFileName2
        };

        var documents = new Aspose.Pdf.Cloud.Sdk.Model.MergeDocuments(documentsToBeMerged);
        
        pdfApi.PutMergeDocuments(resultFileName, documents);
        var response = pdfApi.DownloadFile(resultFileName);
        response.CopyTo(File.OpenWrite(resultFileName));
        Console.WriteLine();
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
