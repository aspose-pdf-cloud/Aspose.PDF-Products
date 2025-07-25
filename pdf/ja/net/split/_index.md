---
title: Cloud .NET SDKでPDFファイルを分割
url: net/split/single/
description: Aspose.PDF Cloud SDK for .NETを使用して単一のPDFを複数の部分に分割します。ドキュメントの分離を自動化します。
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1=".NET SDKでPDFを分割" h2="特定のソフトウェア（例：Adobe PDF）を使用せずに、C#クラウドAPIで単一のPDFページを分割します。" logoImageSrc="https://www.aspose.cloud/templates/aspose/img/products/pdf/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for .NET" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for .NET" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://www.aspose.cloud/templates/aspose/img/products/pdf/aspose_pdf-for-net.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://downloads.aspose.cloud/pdf/net" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="C# Cloud APIを使用して単一のPDFファイルを分割する方法" %}}

PDFファイルを分割するためには
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
このクラウドSDKは、C#、ASP.NET、その他の.NET言語で簡単にクラウドベースのPDF作成者、エディタ、コンバータアプリを構築できるようにします。を開きます。
[NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
パッケージマネージャーを検索
Aspose.PDF Cloud
そしてインストールします。パッケージマネージャーコンソールから以下のコマンドを使用することもできます。

{{% blocks/products/pf/agp/code-block title="コマンド" offSpacer="true" %}}

```powershell

    PM> Install-Package Aspose.Pdf-Cloud 



```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Cloud .NET SDKでPDFを分割する手順" %}}

{{% blocks/products/pf/agp/text %}}

[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
APIを使用して、PDFをプログラム的に結合する基本的な方法
は、わずか数行のコードで実行できます。

{{% /blocks/products/pf/agp/text %}}

1. アプリケーションセCRETとキーを使用して新しいConfigurationオブジェクトを作成します
1. Cloud APIに接続するオブジェクトを作成します
1. ドキュメントファイルをアップロードします
1. 分割を実行します
1. 結果をダウンロードします

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/feature-section-col title="システム要件" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud .NET SDKを開始するのは簡単で、インストールするものはありません。Aspose for Cloudでアカウントを作成して、アプリケーショの情報を取得します。App SIDとキーがあれば、Aspose.PDF Cloud .NET SDKを使用する準備ができています。

+ .NET Framework 2.0以降
+ JSON.NET

{{% /blocks/products/pf/agp/text %}}

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="C#を使用して単一のPDFファイルを分割" offSpacer="" %}}

```cs

    public static void SplitSinglePages()
    {
        const string localImageFileName = @"C:\Samples\Sample-Document-01.pdf";
        const string storageFileName = "Sample-Document-01.pdf";
        
        // Get your AppSid and AppSecret from https://dashboard.aspose.cloud (free registration required).
        var pdfApi = new PdfApi(AppSecret, AppSid);

        if (pdfApi.GetFilesList("").Value.All(f => f.Name != storageFileName))
        {
            using var file = File.OpenRead(localImageFileName);
            var uploadResult = pdfApi.UploadFile(storageFileName, file);
            Console.WriteLine(uploadResult.Uploaded[0]);
        }

        var response = pdfApi.PostSplitDocument(storageFileName);
        uint index = 1;
        foreach (var fileName in response.Result.Documents.Select(document=>document.Href))
        {
            pdfApi.DownloadFile(fileName)
                .CopyTo(File.OpenWrite($"page{index++}.pdf"));
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
