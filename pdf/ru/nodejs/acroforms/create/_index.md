---
title: Создание AcroForm через Cloud Node.js SDK
url: nodejs/acroforms/add/
description: Добавление полей формы в PDF в приложениях Node.js с использованием Aspose.PDF Cloud SDK. Упростите создание интерактивных форм.
lastmod: 2024-11-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Добавление PDF форм в Node.js SDK" h2="Добавление полей формы в PDF документ с использованием Node.js Cloud SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Как создать AcroForm через Node.js SDK" %}}

Чтобы создать AcroForm в PDF, мы будем использовать
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). Этот Cloud SDK помогает программистам Node.js разрабатывать облачные приложения для создания, аннотирования, редактирования и конвертации PDF, используя язык программирования Node.js через Aspose.PDF REST API. Просто создайте учетную запись на [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) и получите информацию о вашем приложении. Как только у вас есть SID и ключ приложения, вы готовы использовать Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="Команда консоли диспетчера пакетов" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Шаги для создания AcroForms через Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Разработчики Aspose.PDF Cloud могут легко загружать и создавать acroforms в PDF всего за несколько строк кода.

{{% /blocks/products/pf/agp/text %}}

1. Загрузите PDF файл в сервис Aspose.PDF Cloud.
1. Создайте новое текстовое поле с необходимыми свойствами
1. Добавьте текстовое поле в PDF файл, хранящийся в сервисе Aspose.PDF Cloud.
1. Скачайте результат, если это необходимо

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Этот пример кода показывает создание AcroForms в PDF документах с использованием Node.js" offSpacer="" %}}

```js

    import credentials from "./credentials.json" with { type: "json" };
    import fs from 'node:fs/promises';
    import { PdfApi } from "asposepdfcloud";
    import { Border } from "asposepdfcloud/src/models/border.js"
    import { TextBoxField } from "asposepdfcloud/src/models/textBoxField.js";
    import { Dash } from "asposepdfcloud/src/models/dash.js";
    import { Rectangle } from "asposepdfcloud/src/models/rectangle.js";
    import { Field } from "asposepdfcloud/src/models/field.js";
    import { FieldType } from "asposepdfcloud/src/models/fieldType.js";
    import { Fields } from "asposepdfcloud/src/models/fields.js";

    async function addFormField () {
        const LOCAL_FILE_NAME = "C:\\Samples\\StudentInfoFormElectronic.pdf";
        const STORAGE_FILE_NAME = "StudentInfoFormElectronic.pdf";

        const pdfApi = new PdfApi(credentials.id, credentials.key);
        try {
            let fileData = await fs.readFile(LOCAL_FILE_NAME);
            let uploadResult = await pdfApi.uploadFile(STORAGE_FILE_NAME, fileData);
            console.log(uploadResult.response.text);
        }
        catch (error) {
            console.error(error.message);
        }

        let textBoxField = new TextBoxField();
        textBoxField.pageIndex = 1;
        textBoxField.partialName = "Email";
        textBoxField.rect = new Rectangle(100, 100, 180, 120);
        textBoxField.value = "aspose-pdf-cloud@example.com";
        let border = new Border();
        border.width = 5;
        border.dash = new Dash(1, 1);
        textBoxField.Border = border;
        try {
            let response = await pdfApi.putTextBoxField(STORAGE_FILE_NAME, "Email", textBoxField);
            console.log(response.body.status);
            const downloadRes = await pdfApi.downloadFile(STORAGE_FILE_NAME)
                        await fs.writeFile(RESULT_FILE_NAME, downloadRes.body);
        } catch (error) {
            console.log(error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Работа с AcroForms через Node.js SDK" %}}

AcroForms позволяет пользователям взаимодействовать непосредственно с PDF, заполняя поля, выбирая опции или нажимая кнопки, делая документ более динамичным. Интерактивные формы обеспечивают эффективный сбор данных, снижая необходимость в ручном вводе данных или внешних инструментах. Это идеально подходит для опросов, регистраций и процессов подачи заявок. Пользователи могут заполнять формы в электронном виде без печати, сканирования или использования других инструментов, экономя время и усилия. Включение AcroForms в документы создает элегантное и современное оформление, отражающее профессионализм и внимание к деталям.
Добавьте AcroForms в PDF документы с помощью [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

**С нашей библиотекой Node.js вы можете**

+ Добавлять заголовки и нижние колонтитулы PDF документа в текстовом или графическом формате.
+ Добавлять таблицы и штампы (текстовые или графические) в PDF документы.
+ Присоединять несколько PDF документов к существующему файлу.
+ Работать с вложениями, аннотациями и полями форм в PDF.
+ Применять шифрование или дешифрование к PDF документам и устанавливать пароль.
+ Удалять все штампы и таблицы со страницы или всего PDF документа.
+ Удалять конкретный штамп или таблицу из PDF документа по его ID.
+ Заменять одиночные или множественные вхождения текста на странице PDF или во всем документе.
+ Обширная поддержка конвертации PDF документов в различные другие форматы файлов.
+ Извлекать различные элементы PDF файлов и оптимизировать PDF документы.
+ Вы можете попробовать наше [бесплатное приложение](https://products.aspose.app/pdf/xfa), чтобы добавить AcroForms в PDF файлы онлайн и протестировать функциональность.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Ресурсы для обучения" tabId="resources" >}}
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



