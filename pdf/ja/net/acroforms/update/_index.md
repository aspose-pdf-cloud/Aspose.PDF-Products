---
title: Cloud .NET SDKを使用してPDFドキュメントのフォームフィールドを更新
url: net/acroforms/update/
description: Aspose.PDF Cloud SDK for .NETを使用してPDFの既存のAcroFormフィールドを更新。高速、正確で柔軟なフォーム処理。

lastmod: 2022-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1=".NET SDKでPDFフォームを更新" h2="Aspose.PDF Cloud .NET APIを使用してPDFドキュメントのすべてのフォームフィールドを更新" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for .NET" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-net.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-words-cloud-dotnet" >}}

{{% blocks/products/pf/agp/content h2="Cloud .NET SDKを使用してPDFドキュメントのフォームフィールドを更新する方法" %}}

AcroFormをCloud .NET SDKで更新するには、
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
このCloud SDKを使用すると、C#、ASP.NET、または他の.NET言語で、各種クラウドプラットフォーム向けのPDF作成、編集、変換アプリを簡単に構築できます。
[NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
パッケージマネージャを開き、
Aspose.PDF Cloud
を検索してインストールします。パッケージマネージャーコンソールから以下のコマンドを使用することもできます。

{{% blocks/products/pf/agp/code-block title="パッケージマネージャーコンソールコマンド" offSpacer="true" %}}

```powershell

     
    PM> Install-Package Aspose.Pdf-Cloud
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title=".NET SDKでAcroFormsを更新する手順" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud開発者は、わずか数行のコードで簡単にPDF内のAcroFormsを読み込み、更新できます。

{{% /blocks/products/pf/agp/text %}}

1. アプリケーションシークレットとキーで新しいConfigオブジェクトを作成
1. Cloud APIに接続するためのオブジェクトを作成
1. ドキュメントファイルをアップロード
1. 更新を実行
1. 結果をダウンロード

{{% /blocks/products/pf/agp/feature-section-col %}}



{{% blocks/products/pf/agp/code-block title="このサンプルコードはPDFドキュメント内のAcroFormsを更新する方法を示している" offSpacer="" %}}

```cs

    public static void UpdateFormFields()
    {
        const string localImageFileName = @"C:\Samples\StudentInfoFormElectronic.pdf";
        const string storageFileName = "StudentInfoFormElectronic.pdf";
        // Get your AppSid and AppSecret from https://dashboard.aspose.cloud (free registration required).            
        var pdfApi = new PdfApi(AppSecret, AppSid);
        var filesOnStorage = pdfApi.GetFilesList("");
        if (filesOnStorage.Value.All(f => f.Name != storageFileName))
        {
            using var file = File.OpenRead(localImageFileName);
            var uploadResult = pdfApi.UploadFile(storageFileName, file);
            Console.WriteLine(uploadResult.Uploaded[0]);
        }
        var fieldList = new List<Field>
        {
            new Field(
                    Name: "First Name",
                    Type: FieldType.Text,
                    Values: ["James"],
                    Rect: new Rectangle(125, 735, 200, 752))
        };

        var fields = new Fields(List: fieldList);

        var response = pdfApi.PutUpdateFields(storageFileName, fields);
        Console.WriteLine(response.Status);
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

