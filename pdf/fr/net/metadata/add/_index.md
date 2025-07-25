---
title: Ajout de métadonnées via le SDK Cloud .NET
url: net/metadata/add/
description: Ajoutez des métadonnées aux fichiers PDF à l'aide du SDK Cloud Aspose.PDF pour .NET. Améliorez la découvrabilité et l'indexation.
lastmod: 2022-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Ajouter des métadonnées à un PDF dans le SDK .NET" h2="Ajoutez des métadonnées à un document PDF en utilisant l'API serveur-side .NET." logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="SDK Aspose.PDF Cloud " subTitlepfName="pour .NET" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-net.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-words-cloud-dotnet" >}}

{{% blocks/products/pf/agp/content h2="Comment créer des métadonnées via le SDK Cloud .NET " %}}

Afin de créer des métadonnées via le SDK Cloud .NET, nous utiliserons
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
Ce SDK Cloud vous permet de créer facilement des applications basées sur le cloud pour la création, l'édition et la conversion de PDF en C#, ASP.NET, ou d'autres langages .NET pour diverses plateformes cloud. Ouvrez
[NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
le gestionnaire de packages, recherchez
Aspose.PDF Cloud
et installez. Vous pouvez également utiliser la commande suivante à partir de la console du gestionnaire de packages.

{{% blocks/products/pf/agp/code-block title="Commande de la console du gestionnaire de packages" offSpacer="true" %}}

```powershell

     
    PM> Install-Package Aspose.Pdf-Cloud
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Étapes pour créer des métadonnées via le SDK .NET" %}}

{{% blocks/products/pf/agp/text %}}

Les développeurs Aspose.PDF Cloud peuvent facilement charger et créer des métadonnées dans un PDF en quelques lignes de code.

{{% /blocks/products/pf/agp/text %}}

1. Créez un nouvel objet Configuration avec votre Secret d'Application et votre Clé
1. Créez un nouvel objet pour vous connecter à l'API Cloud
1. Télechargez votre fichier de document
1. Définiissez les propriétés souhaitées en utilisant PutSetProperty
1. Téléchargez le résultat si nécessaire

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Ce code exemple montre la création de métadonnées dans des documents PDF" offSpacer="" %}}

```cs

    public static void AddMetadata()
    {
        const string localImageFileName = @"C:\Samples\sample.pdf";
        const string storageFileName = "sample.pdf";
        
        // Get your AppSid and AppSecret https://dashboard.aspose.cloud (free registration required).
        var pdfApi = new PdfApi(AppSecret, AppSid);
        var filesOnStorage = pdfApi.GetFilesList("");
        if (filesOnStorage.Value.All(f => f.Name != "sample.pdf"))
        {
            using var file = File.OpenRead(localImageFileName);
            var uploadResult = pdfApi.UploadFile(storageFileName, file);
            Console.WriteLine(uploadResult.Uploaded[0]);
        }
        var response = pdfApi.PutSetProperty(storageFileName, "xmp:ArchiveDate", 
            DateTime.Today.ToString(CultureInfo.InvariantCulture));
        Console.WriteLine(response.Status);
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

