---
title: Конвертировать CGM в PDF через Cloud Node.js SDK
url: nodejs/conversion/cgm-to-pdf/
description: Конвертируйте векторную графику CGM в PDF с помощью Node.js и Aspose.PDF Cloud SDK. Сохраните точность и макет.
lastmod: 2022-03-17
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Конвертировать CGM в PDF в Node.js SDK" h2="Экспортируйте документы CGM в несколько форматов, включая PDF, с Aspose.PDF Cloud Node.js SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Как конвертировать CGM в PDF с использованием Node.js SDK" %}}

Для конвертации CGM в PDF мы будем использовать
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/)
Этот Cloud SDK помогает Node.js программистам разрабатывать облачные приложения для создания, аннотирования, редактирования и конвертации PDF, используя язык программирования Node.js через Aspose.PDF REST API. Откройте
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

{{% blocks/products/pf/agp/feature-section-col title="Шаги по конвертации CGM в PDF через Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Разработчики Aspose.PDF Cloud Node.js могут легко загрузить и конвертировать файлы CGM в PDF всего несколькими строками кода.

{{% /blocks/products/pf/agp/text %}}

1. Загрузите ваш Секрет и Ключ приложения из JSON файла или установите учетные данные другим способом
1. Создайте объект для подключения к Cloud API
1. Загрузите ваш файл документа
1. Выполните конвертацию с помощью putImageInStorageToPdf
1. Скачайте результат, если это необходимо

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Этот пример кода показывает конвертацию CGM в PDF с использованием Cloud Node.js SDK" offSpacer="" %}}

```js

    const fs = require("fs");
    const credentials = require("./credentials.json");
    const { PdfApi } = require("asposepdfcloud");
    const { ImageTemplatesRequest } = require("asposepdfcloud/src/models/imageTemplatesRequest");
    const { ImageTemplate } = require("asposepdfcloud/src/models/imageTemplate");
    const { ImageSrcType } = require("asposepdfcloud/src/models/imageSrcType");

    // Load your Application Secret and Key from the JSON file or set credentials in another way
    async function convertCGMtoPDF() {
        const localImageFileName = "C:\\Samples\\sample.cgm";
        const storageImageFileName = "sample.cgm";
        const pdfApi = new PdfApi(credentials.id, credentials.key);

        try {
            let fileData = await fs.readFile(localImageFileName);
            let uploadResult = await pdfApi.uploadFile(storageImageFileName, fileData);
            console.log(uploadResult.response.text);
        }
        catch (error) {
            console.error(error.response.text);
        }
        s
        let imageTemplateList = [];
        let imageTemplate = new ImageTemplate();
        imageTemplate.imagePath = storageImageFileName;
        imageTemplate.imageSrcType = ImageSrcType.Common;
        imageTemplateList.push(imageTemplate);

        let imageTemplatesRequest = new ImageTemplatesRequest()
        imageTemplatesRequest.IsOCR = false;
        imageTemplatesRequest.imagesList = imageTemplateList;

        try {
            let convertResult = await pdfApi.putImageInStorageToPdf("sample-cgm-to-pdf.pdf", imageTemplatesRequest);
            console.log(convertResult.response.text);
            const buffer = await pdfApi.downloadFile(STORAGE_FILENAME);
        } catch (error) {
            console.error(error.response.text);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< blocks/products/pf/agp/other-supported-section title="Другие поддерживаемые конверсии" subTitle="Вы также можете конвертировать MD в множество других форматов файлов, включая некоторые из перечисленных ниже." >}}

{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/bmp-to-pdf/" name="BMP В PDF" description="Изображение Bitmap" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/cgm-to-pdf/" name="CGM В PDF" description="Бинарный формат Microsoft Word" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/emf-to-pdf/" name="EMF В PDF" description="Документ Office 2007+ Words" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/epub-to-pdf/" name="EPUB В PDF" description="Формат Enhanced Metafile" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/gif-to-pdf/" name="GIF В PDF" description="Графический формат обмена" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/html-to-pdf/" name="HTML В PDF" description="Язык разметки гипертекста" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/jpeg-to-pdf/" name="JPEG В PDF" description="Объединенная группа экспертов по фотографии" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/latex-to-pdf/" name="LATEX В PDF" description="Выходной текст LaTeX" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pcl-to-pdf/" name="PCL В PDF" description="Язык управления принтером" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/md-to-pdf/" name="MD В PDF" description="Markdown" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-bmp/" name="PDF В BMP" description="Изображение Bitmap" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-epub/" name="PDF В EPUB" description="Формат электронной книги" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-gif/" name="PDF В GIF" description="Графический формат обмена" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-html/" name="PDF В HTML" description="Язык гипертекстовой разметки" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-jpeg/" name="PDF В JPEG" description="Объединенная группа экспертов по фотографии" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-pdfa/" name="PDF В PDF/A" description="Формат переносимых документов" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-png/" name="PDF В PNG" description="Переносимая сетевая графика" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-pptx/" name="PDF В PPTX" description="Microsoft PowerPoint" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-svg/" name="PDF В SVG" description="Масштабируемая векторная графика" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-tex/" name="PDF В TEX" description="Система компьютерной графики" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-tiff/" name="PDF В TIFF" description="Формат тегированных изображений" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-word/" name="PDF В WORD" description="Бинарный формат Microsoft Word" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-xlsx/" name="PDF В XLSX" description="Файл электронной таблицы Microsoft Excel Open XML Format" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-xps/" name="PDF В XPS" description="XML Спецификации бумаги" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/png-to-pdf/" name="PNG В PDF" description="Переносимая сетевая графика" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/ps-to-pdf/" name="PS В PDF" description="PostScript" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/svg-to-pdf/" name="SVG В PDF" description="Масштабируемая векторная графика" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/text-to-pdf/" name="TEXT В PDF" description="Текстовый документ" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/tiff-to-pdf/" name="TIFF В PDF" description="Формат тегированных изображений" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/xps-to-pdf/" name="XPS В PDF" description="XML Спецификации бумаги" >}}

{{< /blocks/products/pf/agp/other-supported-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
