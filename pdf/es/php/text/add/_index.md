---
title: Agregar texto a PDF a través de Cloud PHP SDK
url: php/text/add/
description: Inserta nuevo texto en PDFs usando PHP con Aspose.PDF Cloud SDK. Automatiza la creación de contenido de documentos.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Agregar texto a PDF en PHP SDK" h2="Agregar un texto a documentos PDF usando Cloud PHP SDK" h2="Crea tus propias aplicaciones PHP para agregar texto a archivos de documentos PDF usando APIs del lado del servidor." logoImageSrc="/sdk/aspose_pdf-for-php.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for PHP" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for PHP" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="/sdk/aspose_pdf-for-php.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/php/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="https://reference.aspose.cloud/pdf/" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="Cómo agregar texto a PDF a través de Cloud PHP SDK" %}}

El siguiente fragmento de código, por Aspose.PDF, carga un archivo PDF y un archivo de fuente personalizado, define el elemento con el estilo personalizado (color de texto, color de fondo, fuente, rotación, alineación y espaciado), y especifica el rectángulo en el cual el párrafo debe ubicarse en la página. Esto es útil para agregar texto estilizado a una cierta área de la página PDF.
Para agregar texto a PDF, usaremos
[Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/)
Este Cloud SDK ayuda a los programadores de PHP a desarrollar aplicaciones de creador, anotador, editor y convertidor de PDF basadas en la nube usando el lenguaje de programación PHP a través de Aspose.PDF REST API. Simplemente crea una cuenta en [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) y obtén la información de tu aplicación. Una vez que tengas el App SID y la clave, estarás listo para probar el Aspose.PDF Cloud PHP SDK.

{{% blocks/products/pf/agp/code-block title="Comando de la Consola del Administrador de Paquetes" offSpacer="true" %}}

```bash
     
    composer install

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Pasos para agregar texto a PDF a través de Cloud PHP SDK" %}}

{{% blocks/products/pf/agp/text %}}

Los desarrolladores de Aspose.PDF Cloud pueden cargar y agregar texto a PDF fácilmente en solo unas pocas líneas de código.

{{% /blocks/products/pf/agp/text %}}

1. Cargar los archivos PDF necesarios.
1. Definir el área del rectángulo de texto.
1. Configurar los colores del texto y las propiedades del texto.
1. Crear el segmento de texto.
1. Armar la línea de texto y definir las propiedades del párrafo.
1. Agregar el párrafo al PDF.
1. Guardar el PDF actualizado.

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Agregar texto a PDF usando PHP" offSpacer="" %}}

```php

    $name = 'sample.pdf';
    $this->uploadFile($name);
    $fontName = 'Righteous-Regular.ttf';
    $this->uploadFile($fontName);

    $pageNumber = 1;
    $folder = $this->tempFolder;

    $rectangle = new Aspose\PDF\Model\Rectangle();
    $rectangle->setLlx(100);
    $rectangle->setLly(100);
    $rectangle->setUrx(200);
    $rectangle->setUry(200);

    $foregroundColor = new Aspose\PDF\Model\Color();
    $foregroundColor->setA(0x00);
    $foregroundColor->setR(0x00);
    $foregroundColor->setG(0xFF);
    $foregroundColor->setB(0x00);

    $backgroundColor = new Aspose\PDF\Model\Color();
    $backgroundColor->setA(0x00);
    $backgroundColor->setR(0xFF);
    $backgroundColor->setG(0x00);
    $backgroundColor->setB(0x00);

    $textState = new Aspose\PDF\Model\TextState();
    $textState->setFont('Righteous');
    $textState->setFontSize(10);
    $textState->setForegroundColor($foregroundColor);
    $textState->setBackgroundColor($backgroundColor);
    $textState->setFontStyle(Aspose\PDF\Model\FontStyles::REGULAR);
    $textState->setFontFile($this->tempFolder . '/' . $fontName);

    $segment = new Aspose\PDF\Model\Segment();
    $segment->setValue('segment 1');
    $segment->setTextState($textState);

    $textLine = new Aspose\PDF\Model\TextLine();
    $textLine->setHorizontalAlignment(Aspose\PDF\Model\TextHorizontalAlignment::RIGHT);
    $textLine->setSegments([$segment]);

    $paragraph = new Aspose\PDF\Model\Paragraph();
    $paragraph->setRectangle($rectangle);
    $paragraph->setLeftMargin(10);
    $paragraph->setRightMargin(10);
    $paragraph->setTopMargin(20);
    $paragraph->setBottomMargin(20);
    $paragraph->setHorizontalAlignment(Aspose\PDF\Model\TextHorizontalAlignment::FULL_JUSTIFY);
    $paragraph->setLineSpacing(Aspose\PDF\Model\LineSpacing::FONT_SIZE);
    $paragraph->setRotation(10);
    $paragraph->setSubsequentLinesIndent(20);
    $paragraph->setVerticalAlignment(Aspose\PDF\Model\VerticalAlignment::CENTER);
    $paragraph->setWrapMode(Aspose\PDF\Model\WrapMode::BY_WORDS);
    $paragraph->setLines([$textLine]);
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Trabajar con texto en PDF" %}}

El texto puede agregarse dinámicamente para personalizar un PDF para un usuario específico, como añadir su nombre o mensaje personalizado. Esto se utiliza a menudo en materiales de marketing o para informes personalizados. Agregar texto en fuentes, colores y alineaciones específicos puede hacer que ciertas secciones sean más legibles y visualmente atractivas, creando una mejor experiencia de usuario. Las adiciones de texto pueden ayudar a mantener información consistente en diferentes versiones de PDF, evitando ediciones manuales y asegurando que la información clave permanezca en su lugar.
Agrega el texto a documentos PDF con [Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/).

**Con nuestra biblioteca PHP puedes:**

+ Agregar el encabezado y pie de página del documento PDF en formato de texto o imagen.
+ Agregar tablas y sellos (texto o imagen) a documentos PDF.
+ Anexar múltiples documentos PDF a un archivo existente.
+ Trabajar con archivos adjuntos, anotaciones y campos de formulario de PDF.
+ Aplicar cifrado o descifrado a documentos PDF y establecer una contraseña.
+ Eliminar todos los sellos y tablas de una página o de todo el documento PDF.
+ Eliminar un sello o tabla específico del documento PDF por su ID.
+ Reemplazar una o múltiples instancias de texto en una página PDF o de todo el documento.
+ Amplio soporte para convertir documentos PDF a varios otros formatos de archivo.
+ Extraer varios elementos de archivos PDF y optimizar documentos PDF.
+ Puedes probar nuestra [aplicación gratuita](https://products.aspose.app/pdf/editor) para agregar texto a archivos PDF en línea y probar la funcionalidad.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Recursos de aprendizaje" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Documentación" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Código Fuente" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-php" >}}
{{< blocks/products/pf/slr-element name="Referencias de API" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Soporte del Producto" tabId="support" >}}
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
