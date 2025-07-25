---
title: Actualizar Metadatos en Documento PDF a través de Cloud Python SDK
url: python/metadata/update/
description: Actualizar propiedades de metadatos en PDFs usando Python con Aspose.PDF Cloud SDK.
lastmod: 2022-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Actualizar Metadatos en PDF en Python SDK" h2="Actualice todos los Metadatos de un Documento PDF usando Cloud Python SDK." logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="Cómo Actualizar Metadatos de Documento PDF usando Cloud Python SDK " %}}

Para actualizar Metadatos a través de Cloud Python SDK, usaremos
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/)
Este SDK en la nube ayuda a los programadores de Python a desarrollar aplicaciones de creación, anotación, edición y conversión de PDF basadas en la nube utilizando el lenguaje de programación Python a través de Aspose.PDF REST API. Simplemente cree una cuenta en [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) y obtenga la información de su aplicación. Una vez que tenga el App SID y la clave, estará listo para usar Aspose.PDF Cloud Python SDK. Si el paquete de Python está alojado en Github, puede instalarlo directamente desde Github:

{{% blocks/products/pf/agp/code-block title="Instalación desde Github" offSpacer="true" %}}

```bash

     
    pip install git+https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python.git


```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/code-block title="Comando de la Consola del Administrador de Paquetes" offSpacer="true" %}}

```bash
     
    pip install asposepdfcloud

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Pasos para actualizar Metadatos a través de Python SDK" %}}

{{% blocks/products/pf/agp/text %}}

Los desarrolladores de Aspose.PDF Cloud pueden cargar y actualizar metadatos de PDF fácilmente en solo unas pocas líneas de código.

{{% /blocks/products/pf/agp/text %}}

1. Instale [Python SDK](https://pypi.org/project/asposepdfcloud/).
1. Vaya al [Dashboard de Aspose Cloud](https://dashboard.aspose.cloud/).
1. Cree una nueva [Cuenta](https://docs.aspose.cloud/display/storagecloud/Creating+and+Managing+Account) para acceder a todas las aplicaciones y servicios o Inicie sesión en su cuenta.
1. Haga clic en Aplicaciones en el menú de la izquierda para obtener el Id de Cliente y el Secreto de Cliente.
1. Consulte la [Guía del Desarrollador](https://docs.aspose.cloud/pdf/developer-guide/) para actualizar metadatos en PDF a través de Python.
1. Consulte nuestro [repositorio de GitHub](https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python/) para obtener una lista completa de API junto con ejemplos funcionales.
1. Consulte la [página de Referencia de API](https://reference.aspose.cloud/pdf/#/Document) para obtener la descripción de los parámetros de las APIs.

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Este código de muestra muestra cómo actualizar los Metadatos en documentos PDF usando Python" offSpacer="" %}}

```python

    file_name = 'pages.pdf'
    self.uploadFile(file_name)

    date = '2024-10-27T09:59:52+02:00'
    metadata = asposepdfcloud.models.XmpMetadata(properties=[
        # Update user defined property
        asposepdfcloud.models.XmpMetadataProperty(key = "pdf:Producer", value = "Aspose.PDF Cloud", namespace_uri = "http://ns.adobe.com/pdf/1.3/"),
    ])
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Trabajar con Metadatos en PDF" %}}

Trabajar con metadatos en archivos PDF es importante. Los metadatos como el campo de título, autor y tema ayudan a clasificar documentos, facilitando la gestión de grandes colecciones de documentos al proporcionar una visión general rápida del contenido sin abrir los archivos.
Los metadatos también mejoran la búsqueda de archivos al permitirle buscar por palabras clave y atributos. Esto es particularmente valioso en sistemas donde la recuperación rápida de documentos es esencial.

**Con nuestra biblioteca de Python usted puede:**

+ Combinar documentos PDF.
+ Dividir archivos PDF.
+ Convertir PDF a otros formatos, y viceversa.
+ Manipular Anotaciones.
+ Trabajar con Imágenes en PDF, etc.
+ Puede probar nuestra [aplicación gratuita](https://products.aspose.app/pdf/metadata) para actualizar metadatos en archivos PDF en línea y probar la funcionalidad.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
