---
title: Agregar texto en el encabezado de PDF a través de Cloud PHP SDK
url: php/header/text/
description: Inserte texto en el encabezado en archivos PDF de forma programática usando PHP y Aspose.PDF Cloud SDK.
lastmod: 2025-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Agregar texto al encabezado de PDF en PHP SDK" h2="Agregar texto en el encabezado en documentos PDF usando Cloud PHP SDK" logoImageSrc="/sdk/aspose_pdf-for-php.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for PHP" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for PHP" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="/sdk/aspose_pdf-for-php.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/php/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="https://reference.aspose.cloud/pdf/" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="Cómo agregar texto en el encabezado de PDF a través de Cloud PHP SDK" %}}

Para agregar texto en el encabezado de PDF, utilizaremos
[Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/)
Este SDK Cloud ayuda a los programadores PHP a desarrollar aplicaciones de creación, anotación, edición y conversión de PDF basadas en la nube utilizando el lenguaje de programación PHP a través de Aspose.PDF REST API. Simplemente cree una cuenta en [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) y obtenga la información de su aplicación. Una vez que tenga el App SID y la clave, está listo para usar el Aspose.PDF Cloud PHP SDK.

{{% blocks/products/pf/agp/code-block title="Comando de la consola del administrador de paquetes" offSpacer="true" %}}

```bash
     
    composer install

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Pasos para agregar texto en el encabezado a través de Cloud PHP" %}}

{{% blocks/products/pf/agp/text %}}

Los desarrolladores de Aspose.PDF Cloud pueden cargar y agregar fácilmente texto en el encabezado de PDF en solo unas pocas líneas de código.

{{% /blocks/products/pf/agp/text %}}

1. Subir un documento PDF
1. Modificar el PDF agregando un encabezado de texto
1. Descargar el documento actualizado

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Agregar texto en el encabezado de PDF usando PHP" offSpacer="" %}}

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
        $filePath = $this->configParams['LOCAL_FOLDER'] . $this->configParams['PDF_DOCUMENT_NAME'];
        $fileData = file_get_contents($filePath);

        $response = $this->pdfApi->uploadFile($this->configParams['PDF_DOCUMENT_NAME'], $fileData);
        if ($response->getCode() === 200) {
            echo "Uploaded file: {$filePath}\n";
        } else {
            echo 'Failed to upload file.';
        }
    }

    public function downloadResult() {
        $response = $this->pdfApi->downloadFile($this->configParams['PDF_DOCUMENT_NAME']);
        $filePath = $this->configParams['LOCAL_FOLDER'] . $this->configParams['LOCAL_RESULT_DOCUMENT_NAME'];

        if ($response->getCode() === 200) {
            file_put_contents($filePath, $response->getContents());
            echo "Downloaded: $filePath\n";
        } else {
            echo "Failed to download file.";
        }
    }

    public function addTextHeader () {
        $textHeader = new TextHeader(array(
            'background' => true,
            'value' => $this->configParams['HEADER_VALUE'],
            'horizontal_alignment' => \Aspose\PDF\Model\HorizontalAlignment::CENTER,
        ));
        $resultHeader = $this->pdfApi->postDocumentTextFooter($this->configParams['PDF_DOCUMENT_NAME'], $textHeader);

        if ($resultHeader->getCode() === 200) {
            echo 'Successfully appended text footer "' . $this->configParams['HEDAER_VALUE'] .'"';
        }
        else
            throw new Error("Unexpected error : can't append text footer!");
    }

    function main() {
        global $configParams;

        try {
            $pdfHeaderFooter = new PdfHeaderFooter($configParams);
            $pdfHeaderFooter->uploadDocument();
            $pdfHeaderFooter->addTextHeader();
            $pdfHeaderFooter->downloadResult();
        } catch (\Exception $e) {
            echo "Error: " . $e->getMessage() . "\n";
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Trabajar con encabezados en PDF" %}}

Agregar texto al encabezado de un PDF mejora la marca, la navegación, la seguridad y el profesionalismo. Ayuda a organizar documentos, mantener el cumplimiento y asegurar la consistencia, convirtiéndolo en una característica valiosa para documentos comerciales, legales, académicos y técnicos.
Agregue el encabezado en documentos PDF con [Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/).

**Con nuestra biblioteca PHP puedes:**

+ Agregar encabezado y pie de página del documento PDF en formato de texto o imagen.
+ Agregar tablas y sellos (texto o imagen) a documentos PDF.
+ Adjuntar múltiples documentos PDF a un archivo existente.
+ Trabajar con archivos adjuntos PDF, anotaciones y campos de formulario.
+ Aplicar cifrado o descifrado a documentos PDF y establecer una contraseña.
+ Eliminar todos los sellos y tablas de una página o de todo el documento PDF.
+ Eliminar un sello o tabla específica del documento PDF por su ID.
+ Reemplazar una o varias instancias de texto en una página PDF o en todo el documento.
+ Amplio soporte para convertir documentos PDF a varios otros formatos de archivo.
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

{{< blocks/products/pf/slr-tab tabTitle="Soporte del Producto" tabId="support" >}}
{{< blocks/products/pf/slr-element name="Soporte gratuito" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="Soporte de pago" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="Blog" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="¿Por qué Aspose.PDF Cloud para PHP?" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="Lista de clientes" href="https://company.aspose.cloud/customers" >}}
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
