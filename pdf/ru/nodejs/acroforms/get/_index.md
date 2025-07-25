---
title: Получить поля формы из PDF документа через Cloud Node.js SDK
url: nodejs/acroforms/get/
description: Получите и извлеките значения полей формы из PDF AcroForms, используя Aspose.PDF Cloud SDK для Node.js.
lastmod: 2024-11-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Получить PDF формы в Node.js SDK" h2="Получите все поля формы из PDF документа, используя Node.js Cloud SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Получите AcroForms из PDF документа через Cloud Node.js SDK" %}}

Чтобы получить AcroForms из PDF, мы будем использовать
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). Этот Cloud SDK помогает программистам на Node.js разрабатывать облачные приложения для создания, аннотирования, редактирования и конвертации PDF, используя язык программирования Node.js через Aspose.PDF REST API. Просто создайте учетную запись на [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) и получите информацию о вашем приложении. Как только у вас будет SID приложения и ключ, вы готовы использовать Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="Команда консоли менеджера пакетов" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Шаги для получения AcroForms через Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Разработчики Aspose.PDF Cloud могут легко загружать и получать AcroForms из PDF всего за несколько строк кода.

{{% /blocks/products/pf/agp/text %}}

1. Загрузите PDF файл в сервис Aspose.PDF Cloud.
1. Запишите любые ошибки, которые возникают при загрузке файла.
1. Извлеките поля формы из PDF файла в хранилище Aspose.PDF Cloud.
1. Переберите поля формы и запишите названия и значения полей в консоль.
1. Запишите любые ошибки, которые возникают при извлечении полей
1. Загрузите результат, если это необходимо

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Этот пример кода показывает получение AcroForms из PDF документов, используя Node.js" offSpacer="" %}}

```js

    import credentials from "./credentials.json" with { type: "json" };
    import fs from 'node:fs/promises';
    import { PdfApi } from "asposepdfcloud";
    import { Border } from "asposepdfcloud/src/models/border";
    import { TextBoxField } from "asposepdfcloud/src/models/textBoxField";
    import { Dash } from "asposepdfcloud/src/models/dash";
    import { Rectangle } from "asposepdfcloud/src/models/rectangle";
    import { Field } from "asposepdfcloud/src/models/field";
    import { FieldType } from "asposepdfcloud/src/models/fieldType";
    import { Fields } from "asposepdfcloud/src/models/fields";

    async function getFormFields() {
        const localFileName = "C:\\Samples\\StudentInfoFormElectronic.pdf";
        const storageFileName = "StudentInfoFormElectronic.pdf";

        const pdfApi = new PdfApi(credentials.id, credentials.key);
        try {
            let fileData = await fs.readFile(localFileName);
            let uploadResult = await pdfApi.uploadFile(storageFileName, fileData);
            console.log(uploadResult.response.text);
        }
        catch (error) {
            console.error(error.message);
        }

        try {
            let response = await pdfApi.getFields(storageFileName);
            for (const item of response.body.fields.list) {
                if (item.type == "List") {
                    console.log(`Name: [${item.Name}] Value: [${item.Values.join()}]`);
                }
                else {
                    console.log(`Name: [${item.name}] Value: [${item.values[0]}]`);
                }
            }
        } catch (error) {
            console.error(error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Работа с AcroForms через Node.js SDK" %}}

Извлечение данных AcroForm позволяет эффективно собирать и анализировать информацию, собранную от пользователей, такую как ответы на опросы или анкеты. Извлеченные данные AcroForm могут быть интегрированы в базы данных, электронные таблицы или другие системы для дальнейшей обработки или ведения записей. Извлечение AcroForms помогает в аудите заполненных форм для проверки точности, подлинности или полноты предоставленных данных. Извлечение AcroForms необходимо при передаче форм в другие системы управления документами или для создания резервных копий.
Получите AcroForms из PDF документов с [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

**С нашей библиотекой Node.js вы можете**

+ Добавлять заголовок и нижний колонтитул PDF документа в текстовом или графическом формате.
+ Добавлять таблицы и штампы (текстовые или графические) в PDF документы.
+ Присоединять несколько PDF документов к существующему файлу.
+ Работать с вложениями PDF, аннотациями и полями формы.
+ Применять шифрование или дешифрование к PDF документам и устанавливать пароль.
+ Удалять все штампы и таблицы с страницы или всего PDF документа.
+ Удалять определенный штамп или таблицу из PDF документа по его ID.
+ Заменять одно или несколько вхождений текста на странице PDF или во всем документе.
+ Обширная поддержка конвертации PDF документов в различные другие форматы файлов.
+ Извлекать различные элементы файлов PDF и оптимизировать PDF документы.
+ Вы можете опробовать наше [бесплатное приложение](https://products.aspose.app/pdf/xfa) для получения AcroForms из PDF файлов онлайн и тестирования функциональности.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Учебные ресурсы" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Документация" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Исходный код" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-nodejs" >}}
{{< blocks/products/pf/slr-element name="Справочник API" href="https://reference.aspose.cloud/pdf/" >}}
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



