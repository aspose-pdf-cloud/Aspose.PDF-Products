---
title: Конвертируйте PS в PDF через Cloud Node.js SDK
weight: 2710
url: nodejs/conversion/ps-to-pdf/
description: Конвертируйте файлы PostScript (PS) в PDF с использованием Aspose.PDF Cloud SDK для Node.js.
lastmod: 2022-03-17
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Конвертируйте PS в PDF в Node.js SDK" h2="Экспортируйте PS документы в несколько форматов, включая PDF, с Aspose.PDF Cloud Node.js SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Как конвертировать PS в PDF с использованием Node.js SDK" %}}

Чтобы конвертировать PS в PDF, мы будем использовать
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/)
Этот Cloud SDK помогает программистам Node.js разрабатывать облачные приложения для создания, аннотирования, редактирования и конвертации PDF, используя язык программирования Node.js через Aspose.PDF REST API. Откройте
[NPM](https://www.npmjs.com/package/asposepdfcloud)
менеджер пакетов, найдите
Aspose.PDF Cloud,
и установите. Вы также можете использовать следующую команду в консоли менеджера пакетов.

{{% blocks/products/pf/agp/code-block title="Команда в консоли менеджера пакетов" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Шаги для конвертации PS в PDF через Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Разработчики Aspose.PDF Cloud Node.js могут легко загрузить и конвертировать PS файлы в PDF всего в несколько строк кода.

{{% /blocks/products/pf/agp/text %}}

1. Загрузите свой секрет и ключ приложения из JSON файла или задайте учетные данные другим способом
1. Создайте объект для подключения к Cloud API
1. Загрузите файл документа
1. Выполните конвертацию, используя putPsInStorageToPdf
1. Скачайте результат, если это необходимо

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Этот пример кода показывает конвертацию PS в PDF с помощью Cloud Node.js SDK" offSpacer="" %}}

```js

    const fs = require("fs");
    const credentials = require("./credentials.json");
    const { PdfApi } = require("asposepdfcloud");

    // Load your Application Secret and Key from the JSON file or set credentials in another way
    async function convertPStoPDF() {
        const localImageFileName = "C:\\Samples\\sample.ps";
        const storageFileName = "sample.ps";
        const pdfApi = new PdfApi(credentials.id, credentials.key);
        let fileData = await fs.readFile(localImageFileName);
        try {
            let uploadResult = await pdfApi.uploadFile(storageFileName, fileData);
            console.log(uploadResult.response.text);
        }
        catch (error) {
            console.error(error.response.text);
        }

        try {
            let convertResult = await pdfApi.putPsInStorageToPdf("sample-ps-to-pdf.pdf", storageFileName);
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

{{< blocks/products/pf/agp/other-supported-section title="Другие поддерживаемые конверсии" subTitle="Вы также можете конвертировать MD в многие другие форматы файлов, включая несколько перечисленных ниже." >}}

{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/bmp-to-pdf/" name="BMP В PDF" description="Изображение Bitmap" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/cgm-to-pdf/" name="CGM В PDF" description="Бинарный формат Microsoft Word" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/emf-to-pdf/" name="EMF В PDF" description="Документ Office 2007+ Words" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/epub-to-pdf/" name="EPUB В PDF" description="Формат расширенного метафайла" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/gif-to-pdf/" name="GIF В PDF" description="Формат обмена графикой" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/html-to-pdf/" name="HTML В PDF" description="Язык гипертекстовой разметки" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/jpeg-to-pdf/" name="JPEG В PDF" description="Объединенная группа экспертов по фотографии" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/latex-to-pdf/" name="LATEX В PDF" description="Выходной текст LaTeX" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pcl-to-pdf/" name="PCL В PDF" description="Язык принтеров" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/md-to-pdf/" name="MD В PDF" description="Markdown" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-bmp/" name="PDF В BMP" description="Изображение Bitmap" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-epub/" name="PDF В EPUB" description="Формат электронных книг" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-gif/" name="PDF TO GIF" description="Формат обмена графическими изображениями" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-html/" name="PDF TO HTML" description="Язык разметки гипертекста" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-jpeg/" name="PDF TO JPEG" description="Объединенная группа экспертов по фотографии" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-pdfa/" name="PDF TO PDF/A" description="Формат портативных документов" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-png/" name="PDF TO PNG" description="Портативная сетевая графика" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-pptx/" name="PDF TO PPTX" description="Microsoft PowerPoint" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-svg/" name="PDF TO SVG" description="Масштабируемая векторная графика" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-tex/" name="PDF TO TEX" description="Система компьютерной графики" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-tiff/" name="PDF TO TIFF" description="Формат тегированного изображения" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-word/" name="PDF TO WORD" description="Двоичный формат Microsoft Word" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-xlsx/" name="PDF TO XLSX" description="Формат электронной таблицы Microsoft Excel Open XML" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-xps/" name="PDF TO XPS" description="Спецификации XML Paper" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/png-to-pdf/" name="PNG TO PDF" description="Портативная сетевая графика" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/ps-to-pdf/" name="PS TO PDF" description="PostScript" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/svg-to-pdf/" name="SVG TO PDF" description="Масштабируемая векторная графика" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/text-to-pdf/" name="TEXT TO PDF" description="Текстовый документ" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/tiff-to-pdf/" name="TIFF TO PDF" description="Формат тегированного изображения" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/xps-to-pdf/" name="XPS TO PDF" description="Спецификации XML Paper" >}}

{{< /blocks/products/pf/agp/other-supported-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}


