---
title: Извлечение вложений из PDF-документов с помощью Aspose.Pdf Cloud Node.js SDK
url: nodejs/attachments/get/
description: Извлечение вложений PDF с помощью Node.js и Aspose.PDF Cloud SDK. Доступ к встроенному содержимому через API.
lastmod: 2024-10-29
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Извлечение вложений из PDF в Node.js SDK" h2="API для извлечения вложений в PDF-документах с Aspose.PDF Cloud Node.js SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Как извлечь вложения из PDF-документов с помощью Cloud Node.js SDK" %}}

Для работы с вложениями в PDF-документах мы будем использовать
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/)
Этот Cloud SDK помогает программистам Node.js в разработке облачных приложений для создания, аннотирования, редактирования и конвертации PDF с использованием языка программирования Node.js через Aspose.PDF REST API. Откройте
[NPM](https://www.npmjs.com/package/asposepdfcloud)
менеджер пакетов, найдите
Aspose.PDF Cloud,
и установите. Вы также можете использовать следующую команду из консоли менеджера пакетов.

{{% blocks/products/pf/agp/code-block title="Команда консоли менеджера пакетов" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Шаги для извлечения вложений с использованием Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Разработчики Aspose.PDF Cloud Node.js могут легко извлекать, добавлять и заменять вложения в PDF-документах. Для этого разработчикам нужно всего несколько строк кода.

{{% /blocks/products/pf/agp/text %}}

1. Загрузите секрет приложения и ключ из JSON-файла или задайте учетные данные другим способом
1. Создайте объект для подключения к Cloud API
1. Загрузите файл вашего документа
1. Выполните действия по извлечению вложений для PDF-документа
1. Скачайте результат, если это необходимо

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Этот пример кода показывает извлечение вложений PDF-документа с использованием PDF Cloud Node.js SDK" offSpacer="" %}}

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

{{% blocks/products/pf/agp/content h2="Работа с вложениями в PDF через Node.js SDK" %}}

Получение вложений из PDF необходимо для доступа к дополнительному содержимому, повышения эффективности рабочего процесса, обеспечения соответствия и повышения безопасности. Это помогает пользователям извлекать критически важные файлы, автоматизировать обработку документов и оптимизировать управление документами в бизнесе, юриспруденции и технических приложениях.
Получите вложения из PDF-документов с [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

**С нашей библиотекой Node.js вы можете**

+ Добавлять заголовки и колонтитулы PDF-документа в текстовом или графическом формате.
+ Добавлять таблицы и штампы (текстовые или графические) в PDF-документы.
+ Присоединять несколько PDF-документов к существующему файлу.
+ Работать с вложениями PDF, аннотациями и полями форм.
+ Применять шифрование или дешифрование к PDF-документам и устанавливать пароль.
+ Удалять все штампы и таблицы со страницы или всего PDF-документа.
+ Удалять конкретный штамп или таблицу из PDF-документа по их ID.
+ Заменять одно или несколько вхождений текста на странице PDF или во всем документе.
+ Обширная поддержка конвертации PDF-документов в различные другие форматы файлов.
+ Извлекать различные элементы PDF-файлов и оптимизировать PDF-документы.
+ Вы можете попробовать наше [бесплатное приложение](https://products.aspose.app/pdf/xfa) для добавления AcroForms в PDF-файлы онлайн и тестирования функциональности.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
