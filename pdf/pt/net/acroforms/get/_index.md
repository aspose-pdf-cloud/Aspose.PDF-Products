---
title: Obter Campos de Formulário de Documento PDF via SDK Cloud .NET
url: net/acroforms/get/
description: Recupere dados de AcroForm de PDFs usando Aspose.PDF Cloud SDK para .NET. Extração fácil de campos de formulário via API REST.
lastmod: 2022-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Obter Formulários PDF em SDK .NET" h2="Construa seus próprios aplicativos em nuvem para obter arquivos de documentos preenchíveis usando APIs do lado do servidor." logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK para .NET" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-net.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-words-cloud-dotnet" >}}

{{% blocks/products/pf/agp/content h2="Como obter campos de formulário de documentos PDF usando SDK Cloud .NET" %}}

Para obter um AcroForm usando SDK Cloud .NET , usaremos
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
Este SDK em nuvem permite que você crie facilmente aplicativos criadores, editores e conversores de PDF baseados em nuvem em C#, ASP.NET ou outros idiomas .NET para várias plataformas de nuvem. Abra
[NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
gerenciador de pacotes, procure por
Aspose.PDF Cloud
e instale. Você também pode usar o seguinte comando no Console do Gerenciador de Pacotes.

{{% blocks/products/pf/agp/code-block title="Comando do Console do Gerenciador de Pacotes" offSpacer="true" %}}

```powershell

     
    PM> Install-Package Aspose.Pdf-Cloud
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Passos para obter AcroForms via SDK .NET" %}}

{{% blocks/products/pf/agp/text %}}

Os desenvolvedores do Aspose.PDF Cloud podem carregar e obter acroforms em PDF com apenas algumas linhas de código.

{{% /blocks/products/pf/agp/text %}}

1. Crie um novo objeto Configuration com sua Secret da Aplicação e Key
1. Crie um objeto para conectar à API em nuvem
1. Faça upload do seu arquivo de documento
1. Execute a obtenção
1. Baixe o resultado

{{% /blocks/products/pf/agp/feature-section-col %}}



{{% blocks/products/pf/agp/code-block title="Este código de exemplo mostra a obtenção de AcroForms em documentos PDF" offSpacer="" %}}

```cs

    public static void GetFormFields()
    {
        const string localImageFileName = @"C:\Samples\StudentInfoFormElectronic.pdf";
        const string storageFileName = "StudentInfoFormElectronic.pdf";

        // Get your AppSid and AppSecret from https://dashboard.aspose.cloud (free registration required).            
        var pdfApi = new PdfApi(AppSecret, AppSid);

        if (pdfApi.GetFilesList("").Value.All(f => f.Name != storageFileName))
        {
            using var file = File.OpenRead(localImageFileName);
            var uploadResult = pdfApi.UploadFile(storageFileName, file);
            Console.WriteLine(uploadResult.Uploaded[0]);
        }

        var response = pdfApi.GetFields(storageFileName);
        foreach (var item in response.Fields.List)
        {
            if (item.Type == FieldType.List)
            {
                Console.Write($"Name: [{item.Name}] Value:");
                foreach (var listItem in item.Values)
                {
                    Console.WriteLine($"{listItem} ");
                }
            }
            else
            {
                Console.WriteLine($"Name: [{item.Name}] Value: [{item.Values.FirstOrDefault()}]");
            }

        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

