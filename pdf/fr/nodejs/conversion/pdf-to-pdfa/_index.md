---
title: Convertir PDF en PDF/A via Cloud Node.js SDK
url: nodejs/conversion/pdf-to-pdfa/
description: Archiver des PDF au format PDF/A en utilisant Aspose.PDF Cloud SDK pour Node.js. Assurez la conformité à long terme.
lastmod: 2022-03-17
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Convertir PDF en PDF/A dans Node.js SDK" h2="Exporter des documents PDF vers plusieurs formats, y compris PDF/A avec Aspose.PDF Cloud Node.js SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Comment convertir PDF en PDF/A en utilisant Node.js SDK" %}}

Pour convertir PDF en PDF/A, nous utiliserons
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/)
Ce Cloud SDK aide les programmeurs Node.js à développer des applications créatrices, annotatrices, éditrices et de conversion de PDF basées sur le cloud en utilisant le langage de programmation Node.js via Aspose.PDF REST API. Ouvrir
[NPM](https://www.npmjs.com/package/asposepdfcloud)
gestionnaire de paquets, recherchez
Aspose.PDF Cloud,
et installez. Vous pouvez également utiliser la commande suivante à partir de la console du gestionnaire de paquets.

{{% blocks/products/pf/agp/code-block title="Commande de la console du gestionnaire de paquets" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Étapes pour convertir PDF en PDF/A via Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Les développeurs Aspose.PDF Cloud Node.js peuvent facilement charger et convertir des fichiers PDF en PDF/A en seulement quelques lignes de code.

{{% /blocks/products/pf/agp/text %}}

1. Chargez votre clé secrète et clé d'application à partir du fichier JSON ou définissez les identifiants autrement
1. Créez un objet pour se connecter à l'API Cloud
1. Téléchargez votre fichier document
1. Effectuez la conversion en utilisant getPdfInStorageToPdfA
1. Téléchargez le résultat si nécessaire

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Ce code d'exemple montre la conversion du PDF en PDF/A Cloud Node.js SDK" offSpacer="" %}}

```js

    const fs = require("fs");
    const credentials = require("./credentials.json");
    const { PdfApi } = require("asposepdfcloud");

    // Load your Application Secret and Key from the JSON file or set credentials in another way
    async function convertPDFtoPDFA() {
        const localFileName = "C:\\Samples\\sample.pdf";
        const storageFileName = "sample.pdf";
        const pdfApi = new PdfApi(credentials.id, credentials.key);

        try {
            let uploadResult = await pdfApi.uploadFile(storageFileName, fileData);
            console.log(uploadResult.response.text);
        }
        catch (error) {
            console.error(error.response.text);
        }

        try {
            let convertResult = await pdfApi.getPdfInStorageToPdfA(storageFileName, PdfAType.PDFA3A,);
            fs.writeFileSync("sample-pdfa.pdf", convertResult.body);
            const buffer = await pdfApi.downloadFile(STORAGE_FILENAME);
        } catch (error) {
            console.error(error);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< blocks/products/pf/agp/other-supported-section title="Autres conversions prises en charge" subTitle="Vous pouvez également convertir MD en de nombreux autres formats de fichiers, y compris quelques-uns listés ci-dessous." >}}

{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/bmp-to-pdf/" name="BMP EN PDF" description="Image Bitmap" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/cgm-to-pdf/" name="CGM EN PDF" description="Format binaire Microsoft Word" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/emf-to-pdf/" name="EMF EN PDF" description="Document Words Office 2007+" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/epub-to-pdf/" name="EPUB EN PDF" description="Format de métadonnées amélioré" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/gif-to-pdf/" name="GIF EN PDF" description="Format d'échange graphique" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/html-to-pdf/" name="HTML EN PDF" description="Langage de balisage hypertexte" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/jpeg-to-pdf/" name="JPEG EN PDF" description="Groupe d'experts en photographie" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/latex-to-pdf/" name="LATEX EN PDF" description="Texte de sortie LaTeX" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pcl-to-pdf/" name="PCL EN PDF" description="Langage de commande d'imprimante" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/md-to-pdf/" name="MD EN PDF" description="Markdown" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-bmp/" name="PDF EN BMP" description="Image Bitmap" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-epub/" name="PDF EN EPUB" description="Format de livre électronique" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-gif/" name="PDF EN GIF" description="Format d'échange graphique" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-html/" name="PDF VERS HTML" description="Hyper Text Markup Language" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-jpeg/" name="PDF VERS JPEG" description="Joint Photographic Experts Group" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-pdfa/" name="PDF VERS PDF/A" description="Portable Document Format" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-png/" name="PDF VERS PNG" description="Portable Network Graphics" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-pptx/" name="PDF VERS PPTX" description="Microsoft PowerPoint" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-svg/" name="PDF VERS SVG" description="Scalable Vector Graphics" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-tex/" name="PDF VERS TEX" description="Computer Graphics System" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-tiff/" name="PDF VERS TIFF" description="Tagged Image Format" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-word/" name="PDF VERS WORD" description="Microsoft Word Binary Format" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-xlsx/" name="PDF VERS XLSX" description="Microsoft Excel Open XML Format Spreadsheet file" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-xps/" name="PDF VERS XPS" description="XML Paper Specifications" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/png-to-pdf/" name="PNG VERS PDF" description="Portable Network Graphics" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/ps-to-pdf/" name="PS VERS PDF" description="PostScript" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/svg-to-pdf/" name="SVG VERS PDF" description="Scalable Vector Graphics" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/text-to-pdf/" name="TEXTE VERS PDF" description="Text Document" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/tiff-to-pdf/" name="TIFF VERS PDF" description="Tagged Image Format" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/xps-to-pdf/" name="XPS VERS PDF" description="XML Paper Specifications" >}}

{{< /blocks/products/pf/agp/other-supported-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

