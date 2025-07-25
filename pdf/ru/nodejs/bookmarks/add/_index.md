---
title: Добавление закладок через облачный SDK Node.js
url: nodejs/bookmarks/add/
description: Добавьте закладки в PDF с помощью Aspose.PDF Cloud SDK для Node.js. Включите навигацию и структуру в документах.
lastmod: 2025-02-20
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Добавьте закладки в PDF в Node.js SDK" h2="Добавление закладок в PDF документ с использованием облачного Node.js SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Как добавить закладки через Node.js SDK" %}}

Чтобы добавить закладки в PDF, мы будем использовать
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). Этот облачный SDK помогает программистам Node.js разрабатывать облачные приложения для создания, аннотирования, редактирования и конвертации PDF, используя язык программирования Node.js через Aspose.PDF REST API. Просто создайте учетную запись на [Aspose для облака](https://dashboard.aspose.cloud/#/apps) и получите информацию о вашем приложении. Как только у вас будет App SID и ключ, вы готовы использовать Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="Команда консоли диспетчера пакетов" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Шаги для добавления закладок через облачный Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Разработчики Aspose.PDF Cloud могут легко добавлять закладки в PDF всего за несколько строк кода.

{{% /blocks/products/pf/agp/text %}}

1. Создайте объект для подключения к API Pdf.Cloud
1. Загрузите файл вашего документа
1. Создайте новые закладки с необходимыми свойствами
1. Добавьте новые закладки в документ, используя функцию postBookmark()
1. Выполните действие после успешного добавления
1. Скачайте результат, если это необходимо

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Этот пример кода показывает добавление закладок в PDF-документы с использованием Node.js" offSpacer="" %}}

```js

    import credentials from "./credentials.json"  with { type: "json" }; // json-file in this format: { "id": "*****", "key": "*******" }
    import fs from 'node:fs/promises';
    import path from 'node:path';
    import { PdfApi } from "asposepdfcloud";
    import { Color } from "asposepdfcloud/src/models/color.js";
    import { Link } from "asposepdfcloud/src/models/link.js";
    import { Bookmark } from "asposepdfcloud/src/models/bookmark.js";
    import { Bookmarks } from "asposepdfcloud/src/models/bookmarks.js";

    const configParams = {
        LOCAL_FOLDER: "C:\\Samples\\",
        PDF_DOCUMENT_NAME: "sample.pdf",
        LOCAL_RESULT_DOCUMENT_NAME: "output_sample.pdf",
        NEW_BOOKMARK_TITLE: "• Productivity improvement",
        PARENT_BOOKMARK_FOR_APPEND: "",     //The parent bookmark path. Specify an empty string when adding a bookmark to the root.
        NEW_BOOKMARK_PAGE_NUMBER: 2,
    };

    const pdfApi = new PdfApi(credentials.id, credentials.key);

    const pdfBookmarks = {
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

        async appendBookmarkLink() {
            const bookmarkLink = new Link({ rel: "self" });
            const bookmarkColor = new Color({ a: 255, r: 0, g: 255, b: 0 });

            const newBookmark = new Bookmark();
            newBookmark.title = configParams.NEW_BOOKMARK_TITLE;
            newBookmark.italic = true;
            newBookmark.bold = false;
            newBookmark.links = [bookmarkLink];
            newBookmark.color = bookmarkColor;
            newBookmark.action = "GoTo";
            newBookmark.level = 1;
            newBookmark.pageDisplayLeft = 83;
            newBookmark.pageDisplayTop = 751;
            newBookmark.pageDisplayZoom = 2;
            newBookmark.pageNumber = configParams.NEW_BOOKMARK_PAGE_NUMBER;

            const response = await pdfApi.postBookmark(configParams.PDF_DOCUMENT_NAME, configParams.PARENT_BOOKMARK_FOR_APPEND, [newBookmark]);
            const { code, bookmarks } = response.body;

            if (code === 200 && bookmarks) {
                const addedBookmark = bookmarks.list[bookmarks.list.length - 1];
                console.log("Appended bookmark: " + addedBookmark.links[0].href + " => " + addedBookmark.title);
                return addedBookmark;
            }
        },
    };

    async function main() {
        try {
            await pdfBookmarks.uploadDocument();
            await pdfBookmarks.appendBookmarkLink();
            await pdfBookmarks.downloadResult();
        } catch (error) {
            console.error("Error:", error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Работа с закладками через Node.js SDK" %}}

Удаление закладок из PDF полезно для поддержания точности документа, оптимизации производительности, повышения безопасности и обеспечения правильного форматирования. Это особенно важно для завершения документов перед их передачей, печатью или архивированием.
Добавьте закладки в PDF-документы с помощью [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

**С нашей библиотекой Node.js вы можете**

+ Добавлять заголовок и нижний колонтитул PDF-документа в текстовом или графическом формате.
+ Добавлять таблицы и штампы (текстовые или графические) в PDF-документы.
+ Присоединять несколько PDF-документов к существующему файлу.
+ Работать с вложениями, аннотациями и полями формы в PDF.
+ Применять шифрование или дешифрование к PDF-документам и устанавливать пароль.
+ Удалять все штампы и таблицы со страницы или всего PDF-документа.
+ Удалять конкретный штамп или таблицу из PDF-документа по его ID.
+ Заменять один или несколько экземпляров текста на странице PDF или во всем документе.
+ Обширная поддержка конвертации PDF-документов в различные другие форматы файлов.
+ Извлекать различные элементы PDF-файлов и оптимизировать PDF-документы.
+ Вы можете попробовать наши [бесплатные приложения](https://products.aspose.app/pdf/family/) для тестирования функциональности онлайн.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Учебные ресурсы" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Документация" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Исходный код" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-nodejs" >}}
{{< blocks/products/pf/slr-element name="Ссылки на API" href="https://reference.aspose.cloud/pdf/" >}}
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



