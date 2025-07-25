---
title: Definir Campos de Formulário a partir de Documento PDF via Cloud .NET SDK
url: net/acroforms/set/
description: Defina campos AcroForm em documentos PDF usando o Aspose.PDF Cloud SDK para .NET. Automatize a criação de formulários interativos facilmente.
lastmod: 2022-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Definir Formulários PDF no SDK .NET" h2="Construa seus próprios aplicativos em nuvem para definir arquivos de documentos preenchíveis usando APIs do lado do servidor." logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK para .NET" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-net.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-words-cloud-dotnet" >}}

{{% blocks/products/pf/agp/content h2="Como Definir Campos de Formulário a partir de Documento PDF usando Cloud .NET SDK" %}}

Para definir um AcroForm via Cloud .NET SDK, usaremos
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
Este SDK em nuvem permite que você crie facilmente aplicativos criadores, editores e conversores de PDF baseados em nuvem em C#, ASP.NET ou outras linguagens .NET para várias plataformas em nuvem. Abra
[NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
gerenciador de pacotes, procure por
Aspose.PDF Cloud
e instale. Você também pode usar o seguinte comando a partir do Console do Gerenciador de Pacotes.

{{% blocks/products/pf/agp/code-block title="Comando do Console do Gerenciador de Pacotes" offSpacer="true" %}}

```powershell

     
    PM> Install-Package Aspose.Pdf-Cloud
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Passos para definir AcroForms via .NET SDK" %}}

{{% blocks/products/pf/agp/text %}}

Desenvolvedores do Aspose.PDF Cloud podem facilmente carregar e definir acroforms em PDF com apenas algumas linhas de código.

{{% /blocks/products/pf/agp/text %}}

1. Crie um novo objeto de Configuração com sua Chave e Aplicação Secreta
1. Crie um objeto para se conectar à API em nuvem
1. Faça o upload do seu arquivo de documento
1. Realize a definição
1. Baixe o resultado

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/feature-section-col title="Requisitos do Sistema" %}}

{{% blocks/products/pf/agp/text %}}

É fácil começar com o Aspose.PDF Cloud .NET SDK e não há nada para instalar. Basta criar uma conta na Aspose para Cloud e definir suas informações de aplicação. Uma vez que você tenha o App SID & key, está pronto para usar o Aspose.PDF Cloud .NET SDK.

* .NET Framework 2.0 ou posterior
* JSON.NET

{{% /blocks/products/pf/agp/text %}}

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Este código de exemplo mostra a definição de AcroForms em documentos PDF" offSpacer="" %}}

```cs

    public static void SetFormField()
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

        var response = pdfApi.PutUpdateField(storageFileName, "First Name", new Field(
            Name: "First Name",
            Type: FieldType.Text,
            Values: ["James"],
            Rect: new Rectangle(125, 735, 200, 752)
        ));
        Console.WriteLine(response.Status);
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

