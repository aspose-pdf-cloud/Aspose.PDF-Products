---
title: Ajouter des Pages au PDF via Cloud Node.js SDK
url: nodejs/pages/add/
description: Ajouter de nouvelles pages aux fichiers PDF en utilisant Node.js et Aspose.PDF Cloud SDK.
lastmod: 2025-02-20
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Ajouter des Pages au PDF dans Node.js SDK" h2="Ajouter des Pages au Document PDF en utilisant Cloud Node.js SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Comment ajouter des Pages via Node.js SDK" %}}

Pour ajouter des Pages au PDF, nous utiliserons
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). Ce Cloud SDK aide les programmeurs Node.js à développer des applications créatrices, annotatrices, éditrices et convertisseuses de PDF basées sur le cloud en utilisant le langage de programmation Node.js via Aspose.PDF REST API. Créez simplement un compte sur [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) et obtenez les informations de votre application. Une fois que vous avez l'App SID & la clé, vous êtes prêt à utiliser le Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="Commande de la console du gestionnaire de packages" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Étapes pour ajouter des Pages via Cloud Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Les développeurs Aspose.PDF Cloud peuvent facilement ajouter des Pages au PDF en seulement quelques lignes de code.

{{% /blocks/products/pf/agp/text %}}

1. Créez un objet pour se connecter à l'API Pdf.Cloud
1. Téléchargez votre fichier document
1. Ajoutez une nouvelle page au PDF
1. Téléchargez le résultat si nécessaire

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Ce code d'exemple montre comment ajouter des Pages en utilisant Node.js" offSpacer="" %}}

```js

    import credentials from "./credentials.json"  with { type: "json" };
    import fs from 'node:fs/promises';
    import path from 'node:path';
    import { PdfApi } from "asposepdfcloud";

    const configParams = {
        LOCAL_FOLDER: "C:\\Samples\\",
        PDF_DOCUMENT_NAME: "sample.pdf",
        LOCAL_RESULT_DOCUMENT_NAME: "output_sample.pdf"
    };

    const pdfApi = new PdfApi(credentials.id, credentials.key);

    const pdfPages = {
        async uploadDocument () {
            const fileNamePath = path.join(configParams.LOCAL_FOLDER, configParams.PDF_DOCUMENT_NAME);
            const pdfFileData = await fs.readFile(fileNamePath);
            await pdfApi.uploadFile(configParams.PDF_DOCUMENT_NAME, pdfFileData);
            },
        
        async downloadResult () {
                const changedPdfData = await pdfApi.downloadFile(configParams.PDF_DOCUMENT_NAME);
                const filePath = path.join(configParams.LOCAL_FOLDER, configParams.LOCAL_RESULT_DOCUMENT_NAME);
                await fs.writeFile(filePath, changedPdfData.body);
                console.log("Downloaded: " + filePath);
            },

        async addPage () {
            const resultPages = await pdfApi.putAddNewPage(configParams.PDF_DOCUMENT_NAME);

            if (resultPages.body.code == 200 && resultPages.body.pages) {
                this.showPages( [ resultPages.body.pages.list[resultPages.body.pages.list.length - 1] ], "new page");
                return resultPages.body.pages.list[resultPages.body.pages.list.length - 1];
            }
            else
                console.error("Unexpected error : can't get pages!!!");
        },

        showPages (pages, prefix) {
            if (Array.isArray(pages) && pages.length > 0)
            {
                pages.forEach(function(page) {
                    console.log(prefix +" => id: '" + page.id + "', lLx: '" + page.rectangle.lLX + "', lLY: '" + page.rectangle.lLY + "', uRX: '" + page.rectangle.uRX + "', uRY: '" + page.rectangle.uRY + "'");
                });
            }
            else
                console.error("showPages() error: array of pages is empty!")
        },
    }

    async function main() {
        try {
            await pdfPages.uploadDocument();
            await pdfPages.addPage();
            await pdfPages.downloadResult();
        } catch (error) {
            console.error("Error:", error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Travailler avec les Pages via Node.js SDK" %}}

​Ajouter des pages à un document PDF est une tâche courante qui sert divers objectifs, améliorant la fonctionnalité, l'organisation et l'exhaustivité du document. Souvent, il est nécessaire d'inclure du contenu supplémentaire tel que des annexes, des références ou des données mises à jour qui n'étaient pas disponibles lors de la création initiale du document. L'ajout de nouvelles pages permet l'intégration transparente de ces informations supplémentaires, garantissant que le document reste actuel et complet. Ajouter des pages à un PDF est une pratique polyvalente qui répond à de nombreux besoins, de l'amélioration du contenu et de la structure à la garantie de la conformité et à la facilitation de la collaboration. En comprenant les exigences spécifiques et en utilisant les outils appropriés, les utilisateurs peuvent gérer et modifier efficacement leurs documents PDF pour répondre à divers objectifs.
Ajoutez les Pages aux documents PDF avec [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

**Avec notre bibliothèque Node.js vous pouvez**

+ Ajouter l'en-tête et le pied de page du document PDF au format texte ou image.
+ Ajouter des tableaux et des tampons (texte ou image) aux documents PDF.
+ Joindre plusieurs documents PDF à un fichier existant.
+ Travailler avec les pièces jointes, annotations et champs de formulaire PDF.
+ Appliquer le chiffrement ou le déchiffrement aux documents PDF et définir un mot de passe.
+ Supprimer tous les tampons et tableaux d'une page ou de l'ensemble du document PDF.
+ Supprimer un tampon ou un tableau spécifique du document PDF par son ID.
+ Remplacer une ou plusieurs instances de texte sur une page PDF ou dans l'ensemble du document.
+ Support étendu pour la conversion de documents PDF en divers autres formats de fichiers.
+ Extraire divers éléments des fichiers PDF et optimiser les documents PDF.
+ Vous pouvez essayer nos [applications gratuites](https://products.aspose.app/pdf/family/) pour tester la fonctionnalité en ligne.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Ressources d'apprentissage" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Documentation" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Code Source" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-nodejs" >}}
{{< blocks/products/pf/slr-element name="Références API" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Support Produit" tabId="support" >}}
{{< blocks/products/pf/slr-element name="Support Gratuit" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="Support Payant" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="Blog" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Pourquoi Aspose.PDF Cloud pour Node.js ?" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="Liste des Clients" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="Sécurité" href="https://company.aspose.cloud/legal/security" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< /blocks/products/pf/support-learning-resources >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}



