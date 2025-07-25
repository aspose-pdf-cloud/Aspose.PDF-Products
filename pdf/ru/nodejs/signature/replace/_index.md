---
title: Замена подписи в PDF через Cloud Node.js SDK
url: nodejs/signature/replace/
description: Aspose.PDF Cloud позволяет заменить подпись в PDF документе. Посмотрите исходный код на Node.js для замены подписи в PDF файле.
lastmod: 2024-11-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Замена подписи в PDF в Node.js SDK" h2="API для работы с подписями в PDF документах с использованием Cloud Node.js SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Как заменить подпись в PDF через Node.js SDK" %}}

Чтобы заменить подпись в PDF, мы будем использовать
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). Этот Cloud SDK помогает программистам на Node.js разрабатывать облачные приложения для создания, аннотирования, редактирования и конвертации PDF, используя язык программирования Node.js через REST API Aspose.PDF. Просто создайте учетную запись на [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) и получите информацию о вашем приложении. Как только у вас будет SID и ключ приложения, вы готовы к использованию Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="Команда консоли диспетчера пакетов" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Шаги по замене подписи в PDF через Cloud Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Разработчики Aspose.PDF Cloud могут легко загрузить и заменить подпись в PDF всего за несколько строк кода.

{{% /blocks/products/pf/agp/text %}}

1. Загрузите PDF документ
1. Создайте и настройте подпись
1. Создайте поле подписи
1. Замените подпись в PDF
1. Скачайте измененный PDF
1. Скачайте обновленный PDF файл из облачного хранилища Aspose PDF Cloud.

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Замена подписи в PDF с использованием Node.js" offSpacer="" %}}

```js

    import credentials from "../../../Credentials/credentials.json"  with { type: "json" };
    import fs from 'node:fs/promises';
    import path from 'node:path';
    import { PdfApi } from "../../src/api/api.js";
    import {Signature} from "../../src/models/signature.js";
    import {SignatureType} from "../../src/models/signatureType.js";
    import {SignatureField} from "../../src/models/signatureField.js";

    const configParams = {
        LOCAL_FOLDER: "C:\\Samples\\",
        PDF_DOCUMENT_NAME: "sample.pdf",
        LOCAL_RESULT_DOCUMENT_NAME: "output_sample.pdf",
        LOCAL_SIGNATURE_PATH: "C:\\Samples\\Signatures\\3",
        SIGNATURE_PFX: "signature.pfx",
        SIGNATURE_FORM_FIELD: 'Signature_1',
        SIGNATURE_PASSWORD: 'Password',
        SIGNATURE_CONTACT: 'Contact',
        SIGNATURE_LOCATION: 'Location',
        SIGNATURE_AUTHORITY: 'Issuer',
        SIGNATURE_DATE: '04/19/2025 12:15:00.000 PM',
        SIGNATURE_RECT:  { lLx: 100, lLy: 100, uRx: 500, uRy: 500 }
    };

    const pdfApi = new PdfApi(credentials.id, credentials.key);

    const pdfSignatures = {
        async uploadFile (folder, fileName) {
            const fileNamePath = path.join(folder, fileName);
            const pdfFileData = await fs.readFile(fileNamePath);
            await pdfApi.uploadFile(fileName, pdfFileData);
            console.log("File '" + fileName + "' successfully uploaded!");
        },

        async uploadDocument () {
            await this.uploadFile(configParams.LOCAL_FOLDER, configParams.PDF_DOCUMENT_NAME);
        },
                        
        async downloadResult () {
            const changedPdfData = await pdfApi.downloadFile(configParams.PDF_DOCUMENT_NAME);
            const filePath = path.join(configParams.LOCAL_FOLDER, configParams.LOCAL_RESULT_DOCUMENT_NAME);
            await fs.writeFile(filePath, changedPdfData.body);
            console.log("Downloaded: " + filePath);
        },

        async replaceSignature () {
            if (pdfApi)
            {  
                
                const signature = new Signature();
                signature.authority = configParams.SIGNATURE_AUTHORITY;
                signature.contact = configParams.SIGNATURE_CONTACT;
                signature.date = configParams.SIGNATURE_DATE;
                signature.formFieldName = configParams.SIGNATURE_FORM_FIELD;
                signature.location = configParams.SIGNATURE_LOCATION;
                signature.password = configParams.SIGNATURE_PASSWORD;
                signature.rectangle = configParams.SIGNATURE_RECT;
                signature.signaturePath = configParams.SIGNATURE_PFX;
                signature.signatureType = SignatureType.PKCS7;
                signature.visible = true;

                const field = new SignatureField();
                field.pageIndex = 1;
                field.signature = signature;
                field.partialName = 'sign1';
                field.rect = configParams.SIGNATURE_RECT;

                const response = await pdfApi.putSignatureField(configParams.PDF_DOCUMENT_NAME, configParams.SIGNATURE_FORM_FIELD, field);

                if (response.body.code == 200)
                    console.log("replaceSignature(): Signature '" + configParams.SIGNATURE_CONTACT + "' successfully replaced in the document.");
                else
                    console.error("replaceSignature(): Failed to replace signature in the document. Response code: " + response.body.code);
            }
        },
    }

    async function main() {
        try {
            await pdfSignatures.uploadFile(configParams.LOCAL_SIGNATURE_PATH, configParams.SIGNATURE_PFX);
            await pdfSignatures.uploadDocument();
            await pdfSignatures.replaceSignature();
            await pdfSignatures.downloadResult();
        } catch (error) {
            console.error("Error:", error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Работа с подписями в PDF" %}}

Замена подписи в PDF необходима, когда оригинальная подпись становится устаревшей, неверной или недействительной. Этот процесс гарантирует, что документ отражает наиболее актуальную и авторизованную информацию. Общие причины замены включают обновление реквизитов подписанта, исправление ошибок в деталях подписи, повторную подпись после изменений в документе или переход на более сильный цифровой сертификат для повышения безопасности и соответствия. Замена подписи помогает поддерживать подлинность, целостность и юридическую силу документа.
Замените подпись в PDF документах с помощью [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

**С нашей библиотекой на Node.js вы можете:**

+ Добавлять заголовки и колонтитулы PDF документа в текстовом или графическом формате.
+ Добавлять таблицы и штампы (текстовые или графические) в PDF документы.
+ Присоединять несколько PDF документов к существующему файлу.
+ Работать с вложениями PDF, аннотациями и полями форм.
+ Применять шифрование или дешифрование к PDF документам и устанавливать пароль.
+ Удалять все штампы и таблицы со страницы или всего PDF документа.
+ Удалять конкретный штамп или таблицу из PDF документа по их ID.
+ Заменять один или несколько экземпляров текста на странице PDF или во всем документе.
+ Поддержка конвертации PDF документов в различные другие форматы файлов.
+ Извлекать различные элементы PDF файлов и оптимизировать PDF документы.
+ Вы можете попробовать наши [бесплатные приложения](https://products.aspose.app/pdf/family/) для тестирования функциональности онлайн.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Учебные ресурсы" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Документация" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Исходный код" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-nodejs" >}}
{{< blocks/products/pf/slr-element name="Справочники API" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Поддержка продукта" tabId="support" >}}
{{< blocks/products/pf/slr-element name="Бесплатная поддержка" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="Платная поддержка" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="Блог" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Почему Aspose.PDF Cloud для Node.js?" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="Список клиентов" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="Безопасность" href="https://company.aspose.cloud/legal/security" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< /blocks/products/pf/support-learning-resources >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}



