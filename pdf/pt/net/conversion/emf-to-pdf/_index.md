---
title: Converter EMF para PDF via Cloud .NET SDK
url: net/conversion/emf-to-pdf/
description: Converta arquivos EMF para o formato PDF usando Aspose.PDF Cloud SDK para .NET. Mantenha a qualidade e o layout vetorial em cada arquivo.
lastmod: 2022-03-17
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Converter EMF para PDF no .NET SDK" h2="Exporte documentos EMF para múltiplos formatos, incluindo PDF com Aspose.PDF Cloud .NET SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK para .NET" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-net.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-dotnet" >}}

{{% blocks/products/pf/agp/content h2="Como Converter EMF para PDF Usando SDK para .NET" %}}

Para converter EMF para PDF, usaremos
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
Este SDK Cloud permite que você construa facilmente aplicativos criadores, editores e conversores de PDF baseados em cloud em C#, ASP.NET ou outras linguagens .NET para várias plataformas em nuvem. Abra
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

{{% blocks/products/pf/agp/feature-section-col title="Passos para Converter EMF para PDF via .NET SDK" %}}

{{% blocks/products/pf/agp/text %}}

Os desenvolvedores do Aspose.PDF Cloud podem facilmente carregar e converter arquivos EMF para PDF em apenas algumas linhas de código.

{{% /blocks/products/pf/agp/text %}}

1. Crie um novo objeto Configuration com seu Application Secret e Key
1. Crie um objeto para conectar à API Cloud
1. Faça upload do seu arquivo de documento
1. Realize a conversão
1. Baixe o resultado

{{% /blocks/products/pf/agp/feature-section-col %}}



{{% blocks/products/pf/agp/code-block title="Este código de exemplo mostra a Conversão EMF para PDF Cloud .NET SDK" offSpacer="" %}}

```cs

    public static void ConvertEmfToPdf()
    {
        const string localImageFileName = @"C:\Samples\Conversion\sample.emf";
        const string storageImageFileName = "sample.emf";
        const string resultFileName = "sample-emf-to-pdf.pdf";
        
        // Get your AppSid and AppSecret https://dashboard.aspose.cloud (free registration required).
        var pdfApi = new PdfApi(AppSecret, AppSid);
        using var file = File.OpenRead(localImageFileName);
        pdfApi.UploadFile(storageImageFileName, file);

        var imageTemplatesRequest = new ImageTemplatesRequest(IsOCR: false,
            ImagesList: [new ImageTemplate(ImagePath: storageImageFileName, ImageSrcType: ImageSrcType.Emf)]
        );
        
        var response = pdfApi.PutImageInStorageToPdf(resultFileName, imageTemplatesRequest);
        Console.WriteLine($"EMF to PDF result: {response.Status}");
        pdfApi.DownloadFile(resultFileName)
            .CopyTo(File.Create(resultFileName));
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< blocks/products/pf/agp/other-supported-section title="Outras Conversões Suportadas" subTitle="Você também pode converter muitos outros formatos de arquivo" >}}

{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/bmp-to-pdf/" name="BMP PARA PDF" description="Imagem Bitmap" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/emf-to-pdf/" name="EMF PARA PDF" description="Formato de Metarquivo Aprimorado" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/epub-to-pdf/" name="EPUB PARA PDF" description="Formato de Livro Eletrônico" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/gif-to-pdf/" name="GIF PARA PDF" description="Formato de Intercâmbio de Gráficos" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/html-to-pdf/" name="HTML-PARA-PDF" description="Linguagem de Marcação de Hipertexto" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/jpeg-to-pdf/" name="JPEG PARA PDF" description="Imagem JPEG" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/md-to-pdf/" name="MD PARA PDF" description="Markdown" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pcl-to-pdf/" name="PCL PARA PDF" description="Linguagem de Comando de Impressora" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-bmp/" name="PDF PARA BMP" description="Imagem Bitmap" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-docx/" name="PDF PARA DOCX" description="Documento do Office 2007+" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-emf/" name="PDF PARA EMF" description="Formato de Metarquivo Aprimorado" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-epub/" name="PDF PARA EPUB" description="Formato de Livro Eletrônico" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-gif/" name="PDF PARA GIF" description="Formato de Intercâmbio de Gráficos" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-html/" name="PDF PARA HTML" description="Linguagem de Marcação de Hipertexto" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-jpeg/" name="PDF PARA JPEG" description="Imagem JPEG" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pdfa/" name="PDF PARA PDF/A" description="Formato de Documento Portátil/A" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-png/" name="PDF PARA PNG" description="Gráficos de Rede Portátil" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pptx/" name="PDF PARA PPTX" description="Formato de Apresentação Open XML" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-svg/" name="PDF PARA SVG" description="Gráficos Vetoriais Escaláveis" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-tex/" name="PDF PARA TEX" description="Texto de Saída LaTeX" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-tiff/" name="PDF PARA TIFF" description="Formato de Imagem Etiquetada" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-txt/" name="PDF PARA TXT" description="Documento de Texto" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-xlsx/" name="PDF PARA XLSX" description="Arquivo Excel OOXML" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-xps/" name="PDF PARA XPS" description="Especificações de Papel XML" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pptx/" name="PDF PARA PPTX" description="Formato de Apresentação Open XML" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/png-to-pdf/" name="PNG PARA PDF" description="Gráficos de Rede Portátil" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/svg-to-pdf/" name="SVG PARA PDF" description="Gráficos Vetoriais Escaláveis" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/tex-to-pdf/" name="TEX PARA PDF" description="Texto de Saída LaTeX" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/text-to-pdf/" name="TEXTO PARA PDF" description="Documento de Texto" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/tiff-to-pdf/" name="TIFF PARA PDF" description="Formato de Imagem Etiquetada" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/xps-to-pdf/" name="XPS PARA PDF" description="Especificações de Papel XML" >}}

{{< /blocks/products/pf/agp/other-supported-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

