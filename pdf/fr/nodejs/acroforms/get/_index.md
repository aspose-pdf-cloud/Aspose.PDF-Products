---
title: Obtenir des champs de formulaire à partir d'un document PDF via Cloud Node.js SDK
url: nodejs/acroforms/get/
description: Obtenez et extrayez les valeurs des champs de formulaire des AcroForms PDF en utilisant Aspose.PDF Cloud SDK pour Node.js.
lastmod: 2024-11-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Obtenez des formulaires PDF dans Node.js SDK" h2="Obtenez tous les champs de formulaire d'un document PDF en utilisant Node.js Cloud SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Obtenez un AcroForms à partir d'un document PDF via Cloud Node.js SDK" %}}

Pour obtenir un AcroForms à partir d'un PDF, nous utiliserons
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). Ce SDK Cloud aide les programmeurs Node.js à développer des applications de création, annotation, édition et conversion de PDF basées sur le cloud en utilisant le langage de programmation Node.js via Aspose.PDF REST API. Créez simplement un compte sur [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) et obtenez vos informations d'application. Une fois que vous avez le SID & la clé de l'application, vous êtes prêt à utiliser Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="Commande de la console du gestionnaire de packages" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Étapes pour obtenir des AcroForms via Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Les développeurs Aspose.PDF Cloud peuvent facilement charger et obtenir des acroforms à partir de PDF en quelques lignes de code.

{{% /blocks/products/pf/agp/text %}}

1. Téléchargez le fichier PDF sur le service Aspose.PDF Cloud.
1. Enregistrez toutes les erreurs qui se produisent lors du téléchargement du fichier.
1. Récupérez les champs de formulaire du fichier PDF dans le stockage Aspose.PDF Cloud.
1. Parcourez les champs de formulaire et enregistrez les noms et valeurs des champs dans la console.
1. Enregistrez toutes les erreurs qui se produisent lors de la récupération des champs
1. Téléchargez le résultat si nécessaire

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Ce code d'exemple montre comment obtenir un AcroForms à partir de documents PDF en utilisant Node.js" offSpacer="" %}}

```js

    import credentials from "./credentials.json" with { type: "json" };
    import fs from 'node:fs/promises';
    import { PdfApi } from "asposepdfcloud";
    import { Border } from "asposepdfcloud/src/models/border";
    import { TextBoxField } from "asposepdfcloud/src/models/textBoxField";
    import { Dash } from "asposepdfcloud/src/models/dash";
    import { Rectangle } from "asposepdfcloud/src/models/rectangle";
    import { Field } from "asposepdfcloud/src/models/field";
    import { FieldType } from "asposepdfcloud/src/models/fieldType";
    import { Fields } from "asposepdfcloud/src/models/fields";

    async function getFormFields() {
        const localFileName = "C:\\Samples\\StudentInfoFormElectronic.pdf";
        const storageFileName = "StudentInfoFormElectronic.pdf";

        const pdfApi = new PdfApi(credentials.id, credentials.key);
        try {
            let fileData = await fs.readFile(localFileName);
            let uploadResult = await pdfApi.uploadFile(storageFileName, fileData);
            console.log(uploadResult.response.text);
        }
        catch (error) {
            console.error(error.message);
        }

        try {
            let response = await pdfApi.getFields(storageFileName);
            for (const item of response.body.fields.list) {
                if (item.type == "List") {
                    console.log(`Name: [${item.Name}] Value: [${item.Values.join()}]`);
                }
                else {
                    console.log(`Name: [${item.name}] Value: [${item.values[0]}]`);
                }
            }
        } catch (error) {
            console.error(error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Travailler avec les AcroForms via Node.js SDK" %}}

L'extraction des données AcroForm vous permet de compiler et d'analyser efficacement les informations collectées auprès des utilisateurs, telles que les enquêtes ou les réponses aux applications. Les données AcroForm récupérées peuvent être intégrées dans des bases de données, des feuilles de calcul ou d'autres systèmes pour un traitement ultérieur ou une tenue de dossiers. L'extraction des AcroForms aide à auditer les formulaires remplis pour vérifier l'exactitude, l'authenticité ou l'exhaustivité des données fournies. La récupération des AcroForms est essentielle lors du transfert de formulaires vers d'autres systèmes de gestion de documents ou pour la création de sauvegardes.
Obtenez les AcroForms à partir de documents PDF avec [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

**Avec notre bibliothèque Node.js, vous pouvez**

+ Ajouter l'en-tête et le pied de page d'un document PDF au format texte ou image.
+ Ajouter des tableaux et des tampons (texte ou image) aux documents PDF.
+ Ajouter plusieurs documents PDF à un fichier existant.
+ Travailler avec les pièces jointes, annotations et champs de formulaire PDF.
+ Appliquer un cryptage ou un décryptage aux documents PDF et définir un mot de passe.
+ Supprimer tous les tampons et tableaux d'une page ou de l'ensemble du document PDF.
+ Supprimer un tampon ou un tableau spécifique du document PDF par son ID.
+ Remplacer une ou plusieurs instances de texte sur une page PDF ou dans l'ensemble du document.
+ Support étendu pour la conversion de documents PDF vers divers autres formats de fichiers.
+ Extraire divers éléments des fichiers PDF et optimiser les documents PDF.
+ Vous pouvez essayer notre [application gratuite](https://products.aspose.app/pdf/xfa) pour obtenir les AcroForms à partir de fichiers PDF en ligne et tester la fonctionnalité.

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



