---
title: Eliminar enlaces de PDF a través de Cloud Node.js SDK
url: nodejs/links/delete/
description: Eliminar hipervínculos de páginas PDF con Aspose.PDF Cloud SDK en Node.js.
lastmod: 2025-02-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Eliminar enlaces de PDF en Node.js SDK" h2="Eliminar enlaces de un documento PDF usando Cloud Node.js SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Cómo eliminar enlaces de PDF a través de Node.js SDK" %}}

Para eliminar enlaces de PDF, utilizaremos
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). Este Cloud SDK ayuda a los programadores de Node.js a desarrollar aplicaciones basadas en la nube para crear, anotar, editar y convertir PDF utilizando el lenguaje de programación Node.js a través de Aspose.PDF REST API. Simplemente cree una cuenta en [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) y obtenga la información de su aplicación. Una vez que tenga el App SID y la clave, estará listo para usar Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="Comando de la consola del gestor de paquetes" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Pasos para eliminar enlaces usando Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Los desarrolladores de Aspose.PDF Cloud pueden cargar y eliminar enlaces de PDF fácilmente en solo unas pocas líneas de código.

{{% /blocks/products/pf/agp/text %}}

1. Crear un objeto para conectar con la API Pdf.Cloud
1. Subir su archivo de documento
1. Eliminar la anotación de enlace requerida del documento utilizando la función deleteLinkAnnotation()
1. Realizar alguna acción después de eliminar con éxito la anotación de enlace del documento
1. Descargar el resultado si es necesario

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Eliminar enlaces de PDF usando Node.js" offSpacer="" %}}

```js

    import credentials from "./credentials.json"  with { type: "json" };    // json-file in this format: { "id": "*****", "key": "*******" }
    import fs from 'node:fs/promises';
    import path from 'node:path';
    import { PdfApi } from "asposepdfcloud";

    const configParams = {
        LOCAL_FOLDER: "C:\\Samples\\",
        PDF_DOCUMENT_NAME: "sample.pdf",
        LOCAL_RESULT_DOCUMENT_NAME: "output_sample.pdf",
        LINK_REMOVE_ID: "GI5UO32UN5KVESKBMN2GS33OHMZTEMJMGUYDQLBTGYYCYNJSGE",
        PAGE_NUMBER: 2,     // Your document page number...
    };

    const pdfApi = new PdfApi(credentials.id, credentials.key);

    const pdfLinks = {
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

        removeLink: async function () {
            const resultDelete = await pdfApi.deleteLinkAnnotation(configParams.PDF_DOCUMENT_NAME, configParams.LINK_REMOVE_ID);

            if (resultDelete.body.code == 200) {
                console.log("Link '" + configParams.LINK_REMOVE_ID + "' was deleted!");
                return ;
            }
            else
                throw new Error("Unexpected error : can't get link !!!");
        }

    }

    async function main() {
        try {
            await pdfLinks.uploadDocument();
            await pdfLinks.removeLink();
            await pdfLinks.downloadResult();
        } catch (error) {
            console.error("Error:", error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Trabajar con enlaces en PDF" %}}

Con el tiempo, los hipervínculos pueden volverse obsoletos o llevar a páginas que ya no existen. Estos enlaces rotos pueden frustrar a los lectores y disminuir la credibilidad del documento. Eliminarlos asegura que el contenido siga siendo preciso y confiable.
Eliminar los enlaces de documentos PDF con [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

**Con nuestra biblioteca de Node.js puedes:**

+ Añadir encabezado y pie de página del documento PDF en formato de texto o imagen.
+ Añadir tablas y sellos (texto o imagen) a documentos PDF.
+ Adjuntar múltiples documentos PDF a un archivo existente.
+ Trabajar con archivos adjuntos, anotaciones y campos de formulario PDF.
+ Aplicar encriptación o desencriptación a documentos PDF y establecer una contraseña.
+ Eliminar todos los sellos y tablas de una página o de todo el documento PDF.
+ Eliminar un sello o tabla específica del documento PDF por su ID.
+ Reemplazar una o múltiples instancias de texto en una página PDF o en todo el documento.
+ Soporte extenso para convertir documentos PDF a varios otros formatos de archivo.
+ Extraer varios elementos de archivos PDF y optimizar documentos PDF.
+ Puedes probar nuestra [App gratuita](https://products.aspose.app/pdf/family) para probar la funcionalidad en línea.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Recursos de aprendizaje" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Documentación" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Código fuente" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-nodejs" >}}
{{< blocks/products/pf/slr-element name="Referencias API" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Soporte de Producto" tabId="support" >}}
{{< blocks/products/pf/slr-element name="Soporte Gratuito" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="Soporte Pagado" href="https://helpdesk.aspose.cloud" >}}
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



