---
title: Décrypter PDF via Cloud PHP
url: php/decrypt/
description: Aspose.PDF Cloud vous permet de décrypter un document PDF. Consultez le code source PHP pour décrypter un fichier PDF.
lastmod: 2025-04-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Décrypter PDF dans PHP SDK" h2="API pour décrypter les documents PDF en utilisant Cloud PHP SDK." logoImageSrc="/sdk/aspose_pdf-for-php.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="pour PHP" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK pour PHP" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="/sdk/aspose_pdf-for-php.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/php/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="https://reference.aspose.cloud/pdf/" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="Comment décrypter un PDF via Cloud PHP SDK" %}}

Pour décrypter un PDF, nous utiliserons
[Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/)
Ce SDK Cloud aide les programmeurs PHP à développer des applications basées sur le cloud pour créer, annoter, éditer et convertir des PDF en utilisant le langage de programmation PHP via Aspose.PDF REST API. Créez simplement un compte sur [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) et obtenez les informations de votre application. Une fois que vous avez le SID et la clé de l'application, vous êtes prêt à utiliser l'Aspose.PDF Cloud PHP SDK.

{{% blocks/products/pf/agp/code-block title="Commande de la console du gestionnaire de packages" offSpacer="true" %}}

```bash
     
    composer install

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Étapes pour décrypter un PDF via Cloud PHP SDK" %}}

{{% blocks/products/pf/agp/text %}}

Les développeurs Aspose.PDF Cloud peuvent facilement charger et décrypter un PDF en seulement quelques lignes de code.

{{% /blocks/products/pf/agp/text %}}

1. Téléchargez les fichiers PDF nécessaires.
1. Décryptez-le en utilisant le mot de passe fourni, et
1. Téléchargez le PDF décrypté de nouveau sur la machine locale

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Décrypter PDF en utilisant PHP" offSpacer="" %}}

```php

    require __DIR__.'\..\..\vendor\autoload.php';

    use Aspose\PDF\Configuration;
    use Aspose\PDF\Api\PdfApi;

    $credentials = json_decode(file_get_contents(__DIR__ . "/../../../Credentials/credentials.json"), true);

    $configParams = [
        'LOCAL_FOLDER' => 'C:\\Samples\\',
        'PDF_DOCUMENT_NAME' => 'sample_encrypted.pdf',
        'LOCAL_RESULT_DOCUMENT_NAME' => 'output_sample.pdf',
        'DOCUMENT_PASSWORD' => 'Owner-Password',
    ];

    class PdfEncoder {
        private $pdfApi;
        private $configParams;

        private function _create_rest_api() {
            $credentials = json_decode(file_get_contents("./Credentials/credentials.json"), true);

            $configAuth = new Configuration();
            $configAuth->setAppKey($credentials['key']);
            $configAuth->setAppSid($credentials['id']);

            $this->pdfApi = new PdfApi(null, $configAuth);
        }

        public function __construct($config) {
            $this->configParams = $config;
            $this->_create_rest_api();
        }

        public function uploadDocument() {
            $filePath = $this->configParams['LOCAL_FOLDER'] . $this->configParams['PDF_DOCUMENT_NAME'];
            $fileData = file_get_contents($filePath);

            $this->pdfApi->uploadFile($this->configParams['PDF_DOCUMENT_NAME'], $fileData);
            echo "File: '{$this->configParams['PDF_DOCUMENT_NAME']}' successfully uploaded.\n";
        }

        public function downloadResult() {
            $result = $this->pdfApi->downloadFile($this->configParams['PDF_DOCUMENT_NAME']);
            $outputPath = $this->configParams['LOCAL_FOLDER'] . $this->configParams['LOCAL_RESULT_DOCUMENT_NAME'];
            file_put_contents($outputPath, $result['body']);
            echo "Downloaded: {$outputPath}\n";
        }

        public function decryptDocument() {
            $documentPassword = base64_encode($this->configParams['DOCUMENT_PASSWORD']);

            $response = $this->pdfApi->postDecryptDocumentInStorage(
                $this->configParams['PDF_DOCUMENT_NAME'],
                $documentPassword
            );

            if ($response['body']['code'] == 200) {
                echo "decryptDocument(): Document '{$this->configParams['PDF_DOCUMENT_NAME']}' successfully decryped.\n";
            } else {
                throw new Exception("decryptDocument(): Failed to decrypt document '{$this->configParams['PDF_DOCUMENT_NAME']}'. Response code: {$response['code']}");
            }
        }
    }

    function main() {
        global $configParams;

        $encoder = new PdfEncoder($configParams);

        try {
            $encoder->uploadDocument();
            $encoder->decryptDocument();
            $encoder->downloadResult();
        } catch (Exception $e) {
            echo "Error: " . $e->getMessage() . "\n";
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Décrypter PDF" %}}

Décrypter un document PDF est crucial lorsque l'accès à son contenu est restreint en raison du cryptage. Cela permet aux utilisateurs autorisés de reprendre le contrôle total du fichier, permettant l'édition, la visualisation et l'extraction de contenu. Ce processus est particulièrement important dans les flux de travail où des documents sécurisés doivent être accessibles de manière programmatique ou intégrés dans des systèmes plus vastes.
En utilisant des outils comme Aspose.PDF Cloud, le décryptage peut être effectué facilement et en toute sécurité avec le bon mot de passe propriétaire ou utilisateur. Cela garantit que les informations sensibles restent protégées tout en permettant une flexibilité pour ceux qui ont besoin d'un accès légitime.
En fin de compte, le décryptage d'un PDF permet une gestion fluide des documents et renforce l'importance de pratiques de sécurité documentaire fortes mais gérables.
Décryptez les documents PDF avec [Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/).

**Avec notre bibliothèque PHP, vous pouvez :**

+ Ajouter l'en-tête et le pied de page d'un document PDF au format texte ou image.
+ Ajouter des tables et des tampons (texte ou image) aux documents PDF.
+ Joindre plusieurs documents PDF à un fichier existant.
+ Travailler avec les pièces jointes, annotations et champs de formulaire des PDF.
+ Appliquer le cryptage ou le décryptage aux documents PDF et définir un mot de passe.
+ Supprimer tous les tampons et tables d'une page ou d'un document PDF entier.
+ Supprimer un tampon ou une table spécifique du document PDF par son ID.
+ Remplacer une ou plusieurs instances de texte sur une page PDF ou dans l'ensemble du document.
+ Support étendu pour la conversion des documents PDF vers divers autres formats de fichiers.
+ Extraire divers éléments des fichiers PDF et optimiser les documents PDF.
+ Vous pouvez essayer nos [applications gratuites](https://products.aspose.app/pdf/family/) pour tester la fonctionnalité en ligne.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Ressources d'apprentissage" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Documentation" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Code Source" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-php" >}}
{{< blocks/products/pf/slr-element name="Références API" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Support Produit" tabId="support" >}}
{{< blocks/products/pf/slr-element name="Support Gratuit" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="Support Payant" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="Blog" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Pourquoi Aspose.PDF Cloud pour PHP ?" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="Liste des Clients" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="Sécurité" href="https://company.aspose.cloud/legal/security" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< /blocks/products/pf/support-learning-resources >}}

{{< blocks/products/pf/offers-section pfName="Aspose.PDF" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/curl/" imgSrc="/sdk/aspose_pdf-for-curl.svg" platform="cURL" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/net/" imgSrc="/sdk/aspose_pdf-for-net.svg" platform=".NET" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/java/" imgSrc="/sdk/aspose_pdf-for-java.svg" platform="Java" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/php/" imgSrc="/sdk/aspose_pdf-for-php.svg" platform="PHP" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/android/" imgSrc="/sdk/aspose_pdf-for-android.svg" platform="Android" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/python/" imgSrc="/sdk/aspose_pdf-for-python.svg" platform="Python" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/ruby/" imgSrc="/sdk/aspose_pdf-for-ruby.svg" platform="Ruby" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/nodejs/" imgSrc="/sdk/aspose_pdf-for-node.svg" platform="Node.js" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/swift/" imgSrc="/sdk/aspose_pdf-for-swift.svg" platform="Swift" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/go/" imgSrc="/sdk/aspose_pdf-for-go.svg" platform="Go" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/aws/" imgSrc="/sdk/aspose_pdf-for-go.svg" platform="AWS" >}}

{{< /blocks/products/pf/offers-section >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
