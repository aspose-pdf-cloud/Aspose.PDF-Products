---
title: Eliminar texto de PDF a través de Cloud Node.js SDK
url: nodejs/text/remove/
description: Elimine elementos de texto específicos de PDFs con Node.js usando Aspose.PDF Cloud SDK.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Eliminar texto de PDF en Node.js SDK" h2="Eliminar texto de un documento PDF usando Cloud Node.js SDK." logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Cómo eliminar texto de PDF a través de Node.js SDK" %}}

Para eliminar texto de PDF, utilizaremos
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). Este Cloud SDK ayuda a los programadores de Node.js a desarrollar aplicaciones de creación, anotación, edición y conversión de PDF basadas en la nube usando el lenguaje de programación Node.js a través de Aspose.PDF REST API. Simplemente cree una cuenta en [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) y obtenga la información de su aplicación. Una vez que tenga el App SID y la clave, está listo para usar el Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="Comando de la consola del gestor de paquetes" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Pasos para eliminar texto usando Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Los desarrolladores de Aspose.PDF Cloud pueden cargar y eliminar fácilmente texto de PDF con solo unas pocas líneas de código.

{{% /blocks/products/pf/agp/text %}}

1. Cargue su Secreto de Aplicación y Clave desde el archivo JSON o configure las credenciales de otra manera
1. Cree un objeto para conectarse a la API Cloud
1. Suba su archivo de documento
1. Realice la eliminación del texto utilizando la función pdfApi.postDocumentTextReplace
1. Descargue el resultado si lo necesita

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Eliminar texto de PDF usando Node.js" offSpacer="" %}}

```js

    async function () {
        const pdfApi = new PdfApi(credentials.id, credentials.key);
        try {
            const fileBuffer = await fs.readFile(LOCAL_FILE_NAME);
            await pdfApi.uploadFile(STORAGE_FILENAME, fileBuffer);
            const textReplaceList =
            {
                textReplaces:
                    [
                        { oldValue: "text", newValue: "" },
                        { oldValue: "1", newValue: "" }
                    ]
            }
            const result = await pdfApi.postDocumentTextReplace(STORAGE_FILENAME, textReplaceList);
            console.log("Status:", result.body.status);
            const downloadRes = await pdfApi.downloadFile(STORAGE_FILENAME);
            await fs.writeFile(RESULT_FILENAME, downloadRes.body);
        }
        catch (error) {
            console.error(error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Con nuestra herramienta de Node.js puedes:" %}}

+ Agregar encabezado y pie de página al documento PDF en formato de texto o imagen.
+ Agregar tablas y sellos (texto o imagen) a documentos PDF.
+ Anexar múltiples documentos PDF a un archivo existente.
+ Trabajar con archivos adjuntos de PDF, anotaciones y campos de formulario.
+ Aplicar cifrado o descifrado a documentos PDF y establecer una contraseña.
+ Eliminar todos los sellos y tablas de una página o de todo el documento PDF.
+ Eliminar un sello o tabla específica del documento PDF por su ID.
+ Reemplazar una o varias instancias de texto en una página PDF o de todo el documento.
+ Amplio soporte para convertir documentos PDF a varios otros formatos de archivo.
+ Extraer varios elementos de archivos PDF y optimizar documentos PDF.
+ Puedes probar nuestra [App gratuita](https://products.aspose.app/pdf/redaction) para reemplazar texto en archivos PDF en línea y probar la funcionalidad.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Recursos de aprendizaje" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Documentación" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Código fuente" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-nodejs" >}}
{{< blocks/products/pf/slr-element name="Referencias de API" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Soporte de producto" tabId="support" >}}
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



