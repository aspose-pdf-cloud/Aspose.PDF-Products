---
title: Añadir Enlaces a PDF a través de Cloud PHP SDK
url: php/links/add/
description: Añadir hipervínculos a documentos PDF usando PHP y Aspose.PDF Cloud SDK. Hacer contenido interactivo.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Añadir Enlaces a PDF en PHP SDK" h2="Añadir Enlaces en documentos PDF usando Cloud PHP SDK." logoImageSrc="/sdk/aspose_pdf-for-php.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for PHP" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for PHP" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="/sdk/aspose_pdf-for-php.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/php/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="https://reference.aspose.cloud/pdf/" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="Cómo añadir Enlaces a PDF a través de Cloud PHP SDK" %}}

Para añadir Enlaces en PDF, usaremos
[Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/)
Este Cloud SDK ayuda a los programadores PHP a desarrollar aplicaciones basadas en la nube para crear, anotar, editar y convertir PDF usando el lenguaje de programación PHP a través de Aspose.PDF REST API. Simplemente crea una cuenta en [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) y obtén la información de tu aplicación. Una vez que tengas el App SID y la clave, estarás listo para utilizar Aspose.PDF Cloud PHP SDK.

{{% blocks/products/pf/agp/code-block title="Comando de Consola del Administrador de Paquetes" offSpacer="true" %}}

```bash
     
    composer install

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Pasos para añadir Enlaces en PDF a través de Cloud PHP" %}}

{{% blocks/products/pf/agp/text %}}

Los desarrolladores de Aspose.PDF Cloud pueden fácilmente cargar y añadir Enlaces a PDF en solo unas pocas líneas de código.

{{% /blocks/products/pf/agp/text %}}

1. Subir un Documento PDF
1. Descargar el PDF Procesado
1. Añadir un hipervínculo clicable a una página PDF

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Añadir Enlaces a PDF usando PHP" offSpacer="" %}}

```php

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
        $pdfFilePath = $this->configParams['LOCAL_FOLDER'] . $this->configParams['PDF_DOCUMENT_NAME'];
        $pdfFileData = file_get_contents($pdfFilePath);
        $this->pdfApi->uploadFile($this->configParams['PDF_DOCUMENT_NAME'], $pdfFileData);
    }

    public function downloadResult() {
        $changedPdfData = $this->pdfApi->downloadFile($this->configParams['PDF_DOCUMENT_NAME']);
        $filePath = $this->configParams['LOCAL_FOLDER'] . $this->configParams['LOCAL_RESULT_DOCUMENT_NAME'];
        file_put_contents($filePath, $changedPdfData);
        echo "Downloaded: " . $filePath . "\n";
    }

    public function appendLinkOnPage() {
        $linkColor = new Color(['a' => 255, 'r' => 0, 'g' => 255, 'b' => 0]);

        $linkRectangle = new Rectangle();
        $linkRectangle->setLLX($this->configParams['LINK_POS_LLX']);
        $linkRectangle->setLLY($this->configParams['LINK_POS_LLY']);
        $linkRectangle->setURX($this->configParams['LINK_POS_URX']);
        $linkRectangle->setURY($this->configParams['LINK_POS_URY']);

        $linkItem = new Link(['rel' => "self"]);

        $newLink = new LinkAnnotation();
        $newLink->setLinks([$linkItem]);
        $newLink->setActionType(LinkActionType::GO_TO_URI_ACTION);
        $newLink->setAction($this->configParams['NEW_LINK_ACTION']);
        $newLink->setHighlighting(LinkHighlightingMode::INVERT);
        $newLink->setColor($linkColor);
        $newLink->setRect($linkRectangle);

        $addResponse = $this->pdfApi->postPageLinkAnnotations($this->configParams['PDF_DOCUMENT_NAME'], $this->configParams['PAGE_NUMBER'], [$newLink]);

        if ($addResponse->getCode() == 200) {
            echo "Append link successful!\n";
            return true;
        }
    }

function main() {
    global $configParams;

    try {
        $pdfLinks = new PdfLinks($configParams);
        $pdfLinks->uploadDocument();
        $pdfLinks->appendLinkOnPage();
        $pdfLinks->downloadResult();
    } catch (\Exception $e) {
        echo "Error: " . $e->getMessage() . "\n";
    }
}
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Trabajar con Enlaces en PDF" %}}

Añadir enlaces a un PDF mejora la usabilidad, interactividad y accesibilidad. Ya sea para navegación, marketing o referencias cruzadas, los hipervínculos mejoran la efectividad del documento, haciendo más fácil para los usuarios encontrar contenido relevante y tomar acción.
Añadir los enlaces en documentos PDF con [Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/).

**Con nuestra biblioteca PHP puedes:**

+ Añadir el encabezado y pie de página de un documento PDF en formato de texto o imagen.
+ Añadir tablas y sellos (texto o imagen) a documentos PDF.
+ Adjuntar múltiples documentos PDF a un archivo existente.
+ Trabajar con adjuntos, anotaciones y campos de formulario en PDF.
+ Aplicar cifrado o descifrado a documentos PDF y establecer una contraseña.
+ Eliminar todos los sellos y tablas de una página o de todo el documento PDF.
+ Eliminar un sello o tabla específico del documento PDF por su ID.
+ Reemplazar una o múltiples instancias de texto en una página PDF o de todo el documento.
+ Soporte extensivo para convertir documentos PDF a varios otros formatos de archivo.
+ Extraer varios elementos de archivos PDF y optimizar documentos PDF.
+ Puedes probar nuestra [App gratuita](https://products.aspose.app/pdf/family) para probar la funcionalidad en línea.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Recursos de Aprendizaje" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Documentación" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Código Fuente" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-php" >}}
{{< blocks/products/pf/slr-element name="Referencias de API" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Soporte de Producto" tabId="support" >}}
{{< blocks/products/pf/slr-element name="Soporte Gratuito" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="Soporte de Pago" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="Blog" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="¿Por qué Aspose.PDF Cloud para PHP?" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="Lista de Clientes" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="Seguridad" href="https://company.aspose.cloud/legal/security" >}}
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
