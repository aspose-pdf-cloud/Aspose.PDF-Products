---
title: Convertir PDF a XLSX mediante Python Cloud SDK
url: python/conversion/pdf-to-xlsx/
description: Exportar datos de PDF a formato Excel (XLSX) usando Python y Aspose.PDF Cloud SDK. Extraer datos estructurados.
lastmod: 2024-10-17
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Convertir PDF a XLSX en Python SDK" h2="Exportar documentos PDF a múltiples formatos, incluyendo XLSX, con Aspose.PDF Cloud Python SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOC" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Python SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" DocsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python" >}}

{{% blocks/products/pf/agp/content h2="Cómo convertir PDF a XLSX usando Python SDK" %}}

Para convertir PDF a XLSX, usaremos
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/)
Este Cloud SDK ayuda a los programadores de Python a desarrollar aplicaciones en la nube para crear, anotar, editar y convertir PDFs usando el lenguaje de programación Python a través de la API REST de Aspose.PDF. Simplemente cree una cuenta en [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) y obtenga la información de su aplicación. Una vez que tenga el App SID y la clave, estará listo para utilizar Aspose.PDF Cloud Python SDK. Si el paquete de Python está alojado en Github, puede instalarlo directamente desde Github:

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

{{% blocks/products/pf/agp/feature-section-col title="Pasos para convertir PDF a XLSX mediante Python" %}}

{{% blocks/products/pf/agp/text %}}

Los desarrolladores de Aspose.PDF Cloud Python pueden cargar y convertir fácilmente archivos PDF a XLSX con solo unas pocas líneas de código.

{{% /blocks/products/pf/agp/text %}}

1. Establecer el nombre del archivo de entrada
1. Establecer el nombre del archivo de salida
1. Crear un diccionario de opciones
1. Llamar al método de la API

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/feature-section-col title="Requisitos del sistema" %}}

{{% blocks/products/pf/agp/text %}}

Es fácil comenzar con Aspose.PDF Cloud Python SDK:

* Python 2.7 y 3.4+

{{% /blocks/products/pf/agp/text %}}

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Este código de muestra muestra la conversión de PDF a XLSX con el SDK de Aspose.PDF Cloud Python" offSpacer="" %}}

```python

    file_name = 'pages.pdf'
    result_file_name = "result.xls"

    opts = {
        "file": test_data_path + file_name
    }

    response = pdf_api.put_pdf_in_request_to_xls(
        temp_folder + '/' + result_file_name, **opts)
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< blocks/products/pf/agp/other-supported-section title="Otras conversiones soportadas" subTitle="También puede convertir PDF a muchos otros formatos de archivo, incluyendo algunos listados a continuación." >}}

{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/python/conversion/pdf-to-word/" name="PDF A WORD" description="Microsoft Word DOC y DOC" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/python/conversion/pdf-to-excel/" name="PDF A EXCEL" description="Microsoft Excel" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/python/conversion/pdf-to-jpeg/" name="PDF A JPEG" description="Imagen JPEG" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/python/conversion/pdf-to-png/" name="PDF A PNG" description="Gráficos de Red Portátiles" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/python/conversion/pdf-to-pptx/" name="PDF A PPTX" description="Formato de presentación Open XML" >}}

{{< /blocks/products/pf/agp/other-supported-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}


