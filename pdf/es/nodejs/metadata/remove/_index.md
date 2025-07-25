---
title: Eliminar metadatos en documento PDF a través de Cloud Node.js SDK
url: nodejs/metadata/remove/
description: Eliminar metadatos de PDFs para proteger datos usando Aspose.PDF Cloud SDK en Node.js.
lastmod: 2024-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Eliminar metadatos de PDF en Node.js SDK" h2="Eliminar un metadato de un documento PDF usando Cloud Node.js SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Cómo eliminar metadatos a través de Node.js SDK" %}}

Para eliminar metadatos, usaremos
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). Este Cloud SDK ayuda a los programadores de Node.js a desarrollar aplicaciones en la nube para crear, anotar, editar y convertir PDFs usando el lenguaje de programación Node.js a través de Aspose.PDF REST API. Simplemente crea una cuenta en [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) y obtén la información de tu aplicación. Una vez que tengas el App SID y la clave, estarás listo para usar Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="Comando de la Consola del Administrador de Paquetes" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Pasos para eliminar metadatos a través de Cloud Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Los desarrolladores de Aspose.PDF Cloud pueden cargar y eliminar fácilmente metadatos de PDF en solo unas pocas líneas de código.

{{% /blocks/products/pf/agp/text %}}

1. Crear un objeto para conectar con la API de Pdf.Cloud
1. Subir tu archivo de documento
1. Crear una nueva XmpMetadataProperty. Establecer el nombre de la propiedad que deseas eliminar como la clave y `null` como el valor
1. Eliminar metadatos en el documento usando la función postXmpMetadata()
1. Realizar alguna acción después de la adición exitosa
1. Descargar el resultado si es necesario

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Eliminar metadatos de PDF usando Node.js" offSpacer="" %}}

```js

    import credentials from "./credentials.json"  with { type: "json" };
    import fs from 'node:fs/promises';
    import path from 'node:path';
    import { PdfApi } from "asposepdfcloud";
    import { XmpMetadata } from "asposepdfcloud/src/models/xmpMetadata.js";
    import { XmpMetadataProperty } from "asposepdfcloud/src/models/xmpMetadataProperty.js";

    const configParams = {
        LOCAL_FOLDER: "C:\\Samples\\",
        PDF_DOCUMENT_NAME: "sample.pdf",
        LOCAL_RESULT_DOCUMENT_NAME: "output_sample.pdf",
    };

    const pdfApi = new PdfApi(credentials.id, credentials.key);

    const pdfMetadatas = {
        async uploadDocument() {
            const pdfFilePath = path.join(configParams.LOCAL_FOLDER, configParams.PDF_DOCUMENT_NAME);
            const pdfFileData = await fs.readFile(pdfFilePath);
            await pdfApi.uploadFile(configParams.PDF_DOCUMENT_NAME, pdfFileData);
        },
        
        async downloadResult() {
            const changedPdfData = await pdfApi.downloadFile(configParams.PDF_DOCUMENT_NAME);
            const filePath = path.join(configParams.LOCAL_FOLDER, configParams.LOCAL_RESULT_DOCUMENT_NAME);
            await fs.writeFile(filePath, changedPdfData.body);
            console.log("Downloaded: " + filePath);
        },

        async getMetadata () {
            const responseMetadata = await pdfApi.getXmpMetadataJson(configParams.PDF_DOCUMENT_NAME);

            if (responseMetadata.response.status == 200)
            {
                const props = responseMetadata.body.properties;
                props.forEach((prop) =>{
                    console.log(prop.key);
                });
            }
        },

        async deleteMetadata () {
            const prop = new XmpMetadataProperty();
            prop.key = 'dc:creator';
            prop.value = null;        // null value means delete property...
            prop.namespaceUri = 'http://purl.org/dc/elements/1.1/';

            const metadata = new XmpMetadata();
            metadata.properties = [prop];
            
            const response = await pdfApi.postXmpMetadata(configParams.PDF_DOCUMENT_NAME, metadata);

            if (response.body.code == 200) {
                console.log("Delete metadata '" + prop.key + "' successful!");
                return true;
            }
        },
    }

    async function main() {
        try {
            await pdfMetadatas.uploadDocument();
            await pdfMetadatas.getMetadata();
            await pdfMetadatas.deleteMetadata();
            await pdfMetadatas.getMetadata();
            await pdfMetadatas.downloadResult();
        } catch (error) {
            console.error("Error:", error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Trabajar con metadatos en PDF" %}}

Trabajar con metadatos en archivos PDF es importante. Los metadatos como el campo de título, autor y tema ayudan a clasificar documentos, facilitando la gestión de grandes colecciones de documentos al proporcionar una visión general rápida del contenido sin abrir archivos.
Los metadatos también mejoran la búsqueda de archivos al permitir buscar por palabras clave y atributos. Esto es particularmente valioso en sistemas donde la recuperación rápida de documentos es esencial.
Agrega metadatos en documentos PDF con [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

**Con nuestra biblioteca de Node.js puedes:**

+ Agregar encabezado y pie de página del documento PDF en formato de texto o imagen.
+ Agregar tablas y sellos (texto o imagen) a documentos PDF.
+ Adjuntar múltiples documentos PDF a un archivo existente.
+ Trabajar con adjuntos, anotaciones y campos de formulario de PDF.
+ Aplicar cifrado o descifrado a documentos PDF y establecer una contraseña.
+ Eliminar todos los sellos y tablas de una página o de todo el documento PDF.
+ Eliminar un sello o tabla específico del documento PDF por su ID.
+ Reemplazar instancias simples o múltiples de texto en una página de PDF o en todo el documento.
+ Amplio soporte para convertir documentos PDF a varios otros formatos de archivo.
+ Extraer varios elementos de archivos PDF y optimizar documentos PDF.
+ Puedes probar nuestra [App gratuita](https://products.aspose.app/pdf/metadata) para eliminar metadatos de archivos PDF en línea y probar la funcionalidad.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Recursos de aprendizaje" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Documentación" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Código Fuente" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-nodejs" >}}
{{< blocks/products/pf/slr-element name="Referencias API" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Soporte del Producto" tabId="support" >}}
{{< blocks/products/pf/slr-element name="Soporte Gratuito" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="Soporte de Pago" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="Blog" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="¿Por qué Aspose.PDF Cloud para Node.js?" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="Lista de Clientes" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="Seguridad" href="https://company.aspose.cloud/legal/security" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< /blocks/products/pf/support-learning-resources >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}



