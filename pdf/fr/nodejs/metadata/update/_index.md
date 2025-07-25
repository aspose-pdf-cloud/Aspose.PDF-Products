---
title: Mettre à jour les métadonnées dans un document PDF via le Cloud SDK Node.js
url: nodejs/metadata/update/
description: Mettre à jour les propriétés des métadonnées PDF en utilisant Node.js et Aspose.PDF Cloud SDK.
lastmod: 2024-11-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Mettre à jour les métadonnées dans un PDF dans le SDK Node.js" h2="Mettez à jour toutes les métadonnées du document PDF en utilisant le Cloud SDK Node.js" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Comment mettre à jour les métadonnées via le SDK Node.js" %}}

Pour mettre à jour les métadonnées, nous utiliserons
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). Ce Cloud SDK aide les programmeurs Node.js à développer des applications créatrices, annotatrices, éditrices, et convertisseuses de PDF basées sur le cloud en utilisant le langage de programmation Node.js via Aspose.PDF REST API. Créez simplement un compte sur [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) et obtenez vos informations d'application. Une fois que vous avez l'App SID & la clé, vous êtes prêt à utiliser l'Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="Commande de la console du gestionnaire de packages" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Étapes pour mettre à jour des métadonnées via Cloud Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Les développeurs Aspose.PDF Cloud peuvent facilement charger et mettre à jour les métadonnées dans un PDF en seulement quelques lignes de code.

{{% /blocks/products/pf/agp/text %}}

1. Lire un fichier PDF depuis le système de fichiers local.
1. Téléchargez le fichier PDF sur le stockage Aspose.PDF Cloud.
1. Lire les métadonnées XMP du document PDF en utilisant l'API Aspose.PDF Cloud.
1. Mettez à jour la propriété des métadonnées XMP en utilisant l'API Aspose.PDF Cloud.
1. Lire des métadonnées XMP mises à jour du document PDF en utilisant l'API Aspose.PDF Cloud.
1. Enregistrez dans la console que la propriété des métadonnées XMP a été mise à jour.

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="mettre à jour les métadonnées dans un PDF en utilisant Node.js" offSpacer="" %}}

```js

    const fs = require("fs");
    const { PdfApi } = require("asposepdfcloud");

    async function updateXmpMetadataProperty()
    {
        const api = new PdfApi("YOUR_API_SID", "YOUR_API_KEY");
        const fileName = "Sample.pdf";
        const folder = "Documents";
        const storage = null;
        const password = null;
        const xmpMetadataProperty = "dc:title";
    
        const buffer = fs.readFileSync(fileName);
        await api.uploadFile(folder + "/" +fileName, buffer, storage)
        var metadata = await api.getXmpMetadataJson(fileName, folder, storage, password);
        var titleProperty = metadata.body.properties.find(property => property.key == xmpMetadataProperty);
        titleProperty.value = "New title";

        const xmpMetadata = {
            properties: [titleProperty]
        };
        const result = await api.postXmpMetadata(fileName, xmpMetadata, folder, storage, password);
        console.log(result.body.status);

        metadata = await api.getXmpMetadataJson(fileName, folder, storage, password);
        titleProperty = metadata.body.properties.find(property => property.key == xmpMetadataProperty);
        console.log("Updated xmpMetadataProperty: " + titleProperty.key + "=" + titleProperty.value);
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Travailler avec les métadonnées dans un PDF" %}}

Travailler avec les métadonnées dans les fichiers PDF est important. Les métadonnées telles que le champ titre, l'auteur et le thème aident à classer les documents, ce qui facilite la gestion de grandes collections de documents en fournissant un aperçu rapide du contenu sans ouvrir les fichiers.
Les métadonnées améliorent également la recherche de fichiers en permettant de rechercher par mots-clés et attributs. Cela est particulièrement précieux dans les systèmes où la récupération rapide de documents est essentielle.
Ajoutez des métadonnées dans les documents PDF avec [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

**Avec notre bibliothèque Node.js, vous pouvez :**

+ Ajouter en-tête et pied de page du document PDF au format texte ou image.
+ Ajouter des tableaux et des tampons (texte ou image) aux documents PDF.
+ Joindre plusieurs documents PDF à un fichier existant.
+ Travailler avec des pièces jointes PDF, des annotations et des champs de formulaire.
+ Appliquer le chiffrement ou le déchiffrement aux documents PDF et définir un mot de passe.
+ Supprimer tous les tampons et tableaux d'une page ou d'un document PDF entier.
+ Supprimer un tampon ou un tableau spécifique du document PDF par son ID.
+ Remplacer une ou plusieurs instances de texte sur une page PDF ou dans l'ensemble du document.
+ Support étendu pour convertir des documents PDF en divers autres formats de fichiers.
+ Extraire divers éléments de fichiers PDF et optimiser les documents PDF.
+ Vous pouvez essayer notre [application gratuite](https://products.aspose.app/pdf/metadata) pour mettre à jour les métadonnées dans les fichiers PDF en ligne et tester la fonctionnalité.

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



