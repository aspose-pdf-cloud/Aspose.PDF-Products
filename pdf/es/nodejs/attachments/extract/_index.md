---
title: Extraer archivos adjuntos de documentos PDF a través de Aspose.Pdf Cloud Node.js SDK
url: nodejs/attachments/get/
description: Extraer archivos adjuntos de PDF usando Node.js y Aspose.PDF Cloud SDK. Acceda al contenido incrustado a través de API.
lastmod: 2024-10-29
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Extraer Archivos Adjuntos de PDF en Node.js SDK" h2="API para extraer archivos adjuntos en documentos PDF con Aspose.PDF Cloud Node.js SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Cómo extraer archivos adjuntos de documentos PDF usando Cloud Node.js SDK" %}}

Para trabajar con archivos adjuntos en documentos PDF, usaremos
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/)
Este SDK Cloud ayuda a los programadores de Node.js a desarrollar aplicaciones de creación, anotación, edición y conversión de PDF basadas en la nube utilizando el lenguaje de programación Node.js a través de Aspose.PDF REST API. Abra
[NPM](https://www.npmjs.com/package/asposepdfcloud)
gestor de paquetes, busque
Aspose.PDF Cloud,
e instale. También puede usar el siguiente comando desde la Consola del Gestor de Paquetes.

{{% blocks/products/pf/agp/code-block title="Comando de la Consola del Gestor de Paquetes" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Pasos para extraer archivos adjuntos usando Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Los desarrolladores de Aspose.PDF Cloud Node.js pueden fácilmente extraer, agregar y reemplazar archivos adjuntos en documentos PDF. Los desarrolladores solo necesitan unas pocas líneas de código.

{{% /blocks/products/pf/agp/text %}}

1. Cargue su Secreto de Aplicación y Clave desde el archivo JSON o configure las credenciales de otra manera
1. Cree un objeto para conectarse a la API Cloud
1. Suba su archivo de documento
1. Realice las acciones de extracción de archivos adjuntos para el documento PDF
1. Descargue el resultado si es necesario

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Este código de ejemplo muestra cómo extraer archivos adjuntos de documentos PDF usando PDF Cloud Node.js SDK" offSpacer="" %}}

```js

    import credentials from "./credentials.json" with { type: "json" };
    import fs from 'node:fs/promises';
    import path from 'node:path';
    import { PdfApi } from "asposepdfcloud";
    import { AttachmentInfo } from "asposepdfcloud/src/models/attachmentInfo.js";

    async function getAllAttachments() {
        const LOCAL_PATH = "C:\\Samples\\";
        const LOCAL_FILE_NAME = "C:\\Samples\\Attachments\\sample_attachment.pdf";
        const STORAGE_FILE_NAME = "sample_attachment.pdf";
        try {
            const pdfApi = new PdfApi(credentials.id, credentials.key);
            const pdfData = await fs.readFile(LOCAL_FILE_NAME);
            await pdfApi.uploadFile(STORAGE_FILE_NAME, pdfData);

            const result = await pdfApi.getDocumentAttachments(STORAGE_FILE_NAME);

            if (result.body.code === 200 && result.body.attachments) {
                const attachmentList = result.body.attachments.list || [];
                if (!attachmentList.length) {
                    console.error("No attachments found.");
                    return;
                }

                const downloadTasks = attachmentList.map(async (attachment) => {
                    try {
                        const attachmentUrl = attachment.links[0].href;
                        const info = await pdfApi.getDocumentAttachmentByIndex(STORAGE_FILE_NAME, attachmentUrl);
                        const download = await pdfApi.getDownloadDocumentAttachmentByIndex(STORAGE_FILE_NAME, attachmentUrl);
                        await fs.writeFile(path.join(LOCAL_PATH, info.body.attachment.name), download.body);
                    } catch (error) {
                        console.error("Failed to download attachment:", error);
                    }
                });

                await Promise.all(downloadTasks);
            } else {
                console.error("Failed to retrieve attachments. Status:", result.statusCode);
            }
        } catch (error) {
            console.error("Error processing PDF attachments:", error);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Trabajar con Archivos Adjuntos en PDF a través de Node.js SDK" %}}

Obtener archivos adjuntos de un PDF es esencial para acceder a contenido suplementario, mejorar la eficiencia del flujo de trabajo, garantizar el cumplimiento y mejorar la seguridad. Ayuda a los usuarios a recuperar archivos críticos, automatizar el procesamiento de documentos y optimizar la gestión de documentos en aplicaciones empresariales, legales y técnicas.
Obtenga los Archivos Adjuntos de documentos PDF con [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

**Con nuestra biblioteca de Node.js, puede**

+ Agregar encabezado y pie de página de documento PDF en formato de texto o imagen.
+ Agregar tablas y estampas (texto o imagen) a documentos PDF.
+ Adjuntar múltiples documentos PDF a un archivo existente.
+ Trabajar con archivos adjuntos, anotaciones y campos de formulario de PDF.
+ Aplicar cifrado o descifrado a documentos PDF y establecer una contraseña.
+ Eliminar todas las estampas y tablas de una página o de todo el documento PDF.
+ Eliminar una estampa o tabla específica del documento PDF por su ID.
+ Reemplazar una o múltiples instancias de texto en una página PDF o en todo el documento.
+ Amplio soporte para convertir documentos PDF a varios otros formatos de archivo.
+ Extraer varios elementos de archivos PDF y optimizar documentos PDF.
+ Puede probar nuestra [App gratuita](https://products.aspose.app/pdf/xfa) para agregar los AcroForms en archivos PDF en línea y probar la funcionalidad.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
