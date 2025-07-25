---
title: Créer un PDF via Cloud Node.js SDK
url: nodejs/create/
description: Aspose.PDF Cloud vous permet de créer un document PDF. Consultez le code source Node.js pour créer un fichier PDF.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Créer un PDF dans Node.js Cloud API" h2="API pour travailler avec la création de documents PDF en utilisant Cloud Node.js SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Comment créer un PDF via Node.js SDK" %}}

Pour créer un PDF, nous utiliserons
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). Ce Cloud SDK aide les programmeurs Node.js à développer des applications créatrices, annotatrices, éditrices et convertisseuses de PDF basées sur le cloud en utilisant le langage de programmation Node.js via Aspose.PDF REST API. Créez simplement un compte sur [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) et obtenez les informations de votre application. Une fois que vous avez le SID de l'application et la clé, vous êtes prêt à utiliser Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="Commande de la console du gestionnaire de paquets" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Étapes pour créer un PDF via Cloud Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Les développeurs Aspose.PDF Cloud peuvent facilement charger et créer un PDF en seulement quelques lignes de code.

{{% /blocks/products/pf/agp/text %}}

1. Initialiser l'API Aspose PDF
1. Définir l'objet PdfPageChanges avec les méthodes PDF
1. Appeler createPdfDocument() pour générer le PDF dans le cloud.

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Créer un PDF en utilisant Node.js" offSpacer="" %}}

```js

    import credentials from "../../../Credentials/credentials.json"  with { type: "json" };    // json-file in this format: { "id": "*****", "key": "*******" }
    import fs from 'node:fs/promises';
    import path from 'node:path';
    import { PdfApi } from "../../src/api/api.js";
    import { DocumentConfig } from "../../src/models/documentConfig.js" 
    import { DocumentProperties } from "../../src/models/documentProperties.js"
    import { DocumentProperty } from "../../src/models/documentProperty.js"
    import { DisplayProperties } from "../../src/models/displayProperties.js"
    import { DefaultPageConfig } from "../../src/models/defaultPageConfig.js"
    import { Direction } from "../../src/models/direction.js";
    import { PageMode } from "../../src/models/pageMode.js";
    import { PageLayout } from "../../src/models/pageLayout.js";

    const configParams = {
        LOCAL_FOLDER: "C:\\Samples\\",
        TEMP_FOLDER : 'TempPdfCloud',
        LOCAL_RESULT_DOCUMENT_NAME: "output_sample.pdf",
        PAGE_WIDTH: 590,
        PAGE_HEIGHT: 894,
        PAGES_COUNT: 5,
    };

    const pdfApi = new PdfApi(credentials.id, credentials.key);

    const PdfPageChanges = {
        async downloadResult() {
            const fileName = path.join( configParams.TEMP_FOLDER, configParams.LOCAL_RESULT_DOCUMENT_NAME);
            const changedPdfData = await pdfApi.downloadFile(fileName);
            const filePath = path.join(configParams.LOCAL_FOLDER, configParams.LOCAL_RESULT_DOCUMENT_NAME);
            await fs.writeFile(filePath, changedPdfData.body);
            console.log("Downloaded: " + filePath);
        },

        async createPdfDocument() {
            const pdfConfig = new DocumentConfig();
            pdfConfig.pagesCount = configParams.PAGES_COUNT;
            
            pdfConfig.displayProperties = new DisplayProperties();
            pdfConfig.displayProperties.centerWindow = true;
            pdfConfig.displayProperties.hideMenuBar = true;
            pdfConfig.displayProperties.direction = Direction.L2R;
            pdfConfig.displayProperties.displayDocTitle = true;
            pdfConfig.displayProperties.hideToolBar = true;
            pdfConfig.displayProperties.hideWindowUI = true;
            pdfConfig.displayProperties.nonFullScreenPageMode = PageMode.UseThumbs;
            pdfConfig.displayProperties.pageLayout = PageLayout.TwoPageLeft;
            pdfConfig.displayProperties.pageMode = PageMode.UseThumbs;

            pdfConfig.documentProperties = new DocumentProperties();
            const docProperty = new DocumentProperty();
            docProperty.builtIn = false;
            docProperty.name = "prop1";
            docProperty.value = "Val1";

            pdfConfig.documentProperties.list = [ docProperty ];
            
            pdfConfig.defaultPageConfig = new DefaultPageConfig();
            pdfConfig.defaultPageConfig.height = configParams.CROP_HEIGHT;
            pdfConfig.defaultPageConfig.width = configParams.CROP_WIDTH;

            const response = await pdfApi.postCreateDocument(configParams.LOCAL_RESULT_DOCUMENT_NAME, pdfConfig, null, configParams.TEMP_FOLDER);
            console.log("Document #" + configParams.LOCAL_RESULT_DOCUMENT_NAME + " created.")
            return response;
        },
    };

    async function main() {
        try {
            await PdfPageChanges.createPdfDocument();
            await PdfPageChanges.downloadResult();
        } catch (error) {
            console.error("Error:", error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Avec notre bibliothèque Node.js, vous pouvez" %}}

Créer des documents PDF avec [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

+ Ajouter l'en-tête et le pied de page du document PDF au format texte ou image.
+ Ajouter des tableaux et des tampons (texte ou image) aux documents PDF.
+ Ajouter plusieurs documents PDF à un fichier existant.
+ Travailler avec les pièces jointes, annotations et champs de formulaire PDF.
+ Appliquer le chiffrement ou le déchiffrement aux documents PDF et définir un mot de passe.
+ Supprimer tous les tampons et tableaux d'une page ou de l'ensemble du document PDF.
+ Supprimer un tampon ou un tableau spécifique du document PDF par son ID.
+ Remplacer une ou plusieurs occurrences de texte sur une page PDF ou dans l'ensemble du document.
+ Support étendu pour la conversion de documents PDF en divers autres formats de fichiers.
+ Extraire divers éléments des fichiers PDF et optimiser les documents PDF.
+ Vous pouvez essayer notre [application gratuite](https://products.aspose.app/pdf/table-extraction) pour extraire une table dans des fichiers PDF en ligne et tester la fonctionnalité.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Ressources d'apprentissage" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Documentation" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Code Source" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-nodejs" >}}
{{< blocks/products/pf/slr-element name="Références API" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Support produit" tabId="support" >}}
{{< blocks/products/pf/slr-element name="Support gratuit" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="Support Payant" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="Blog" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Pourquoi Aspose.PDF Cloud pour Node.js ?" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="Liste des Clients" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="Sécurité" href="https://company.aspose.cloud/legal/security" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< /blocks/products/pf/support-learning-resources >}}

<!-- aboutfile Termine -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}



