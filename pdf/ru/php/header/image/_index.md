---
title: Добавить изображение в заголовок PDF через Cloud PHP SDK
url: php/header/image/
description: Добавляйте заголовки изображений в PDF-документы с помощью PHP и Aspose.PDF Cloud SDK. Автоматизируйте единообразное брендирование документов.
lastmod: 2025-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Добавить изображение в заголовок PDF в PHP SDK" h2="Добавление изображения в заголовок PDF-документов с использованием Cloud PHP SDK" logoImageSrc="/sdk/aspose_pdf-for-php.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="для PHP" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK для PHP" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="/sdk/aspose_pdf-for-php.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/php/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="https://reference.aspose.cloud/pdf/" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="Как добавить изображение в заголовок PDF через Cloud PHP SDK" %}}

Чтобы добавить изображение в заголовок PDF, мы будем использовать
[Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/)
Этот Cloud SDK помогает PHP-программистам разрабатывать облачные приложения для создания, аннотирования, редактирования и конвертации PDF, используя язык программирования PHP через REST API Aspose.PDF. Просто создайте учетную запись на [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) и получите информацию о вашем приложении. Как только у вас будут SID и ключ приложения, вы готовы использовать Aspose.PDF Cloud PHP SDK.

{{% blocks/products/pf/agp/code-block title="Команда консоли диспетчера пакетов" offSpacer="true" %}}

```bash
     
    composer install

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Шаги для добавления изображения в заголовок через Cloud PHP" %}}

{{% blocks/products/pf/agp/text %}}

Разработчики Aspose.PDF Cloud могут легко загрузить и добавить изображение в заголовок PDF всего за несколько строк кода.

{{% /blocks/products/pf/agp/text %}}

1. Загрузите PDF-документ
1. Измените PDF, добавив к нему изображение в заголовок
1. Скачайте обновленный документ

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Добавить изображение в заголовок PDF с использованием PHP" offSpacer="" %}}

```php

    private function _create_rest_api() {
        $credentials = json_decode(file_get_contents("./Credentials/credentials.json"), true);

        $configAuth = new Configuration();
        $configAuth->setAppKey($credentials['key']);
        $configAuth->setAppSid($credentials['id']);

        $this->pdfApi = new PdfApi(null, $configAuth);
     }

    public function __construct($config) {
        $this->configParams = $config;
        $this->_create_rest_api();
    }

    public function uploadFile($fileName) {
        $filePath = $this->configParams['LOCAL_FOLDER'] . $fileName;
        $fileData = file_get_contents($filePath);

        $response = $this->pdfApi->uploadFile($fileName, $fileData);
        if ($response->getCode() === 200) {
            echo "Uploaded file: {$filePath}\n";
        } else {
            echo 'Failed to upload file.';
        }
    }

    public function uploadDocument() {
        $this->uploadFile($this->configParams['PDF_DOCUMENT_NAME']);
    }

    public function downloadResult() {
        $response = $this->pdfApi->downloadFile($this->configParams['PDF_DOCUMENT_NAME']);
        $filePath = $this->configParams['LOCAL_FOLDER'] . $this->configParams['LOCAL_RESULT_DOCUMENT_NAME'];

        if ($response->getCode() === 200) {
            file_put_contents($filePath, $response->getContents());
            echo "Downloaded: $filePath\n";
        } else {
            echo "Failed to download file.";
        }
    }

    public function addImageHeader () {
        $imageHeader = new ImageHeader(array(
            'background' => true,
            'horizontal_alignment' => \Aspose\PDF\Model\HorizontalAlignment::CENTER,
            'file_name' => $this->configParams['IMAGE_HEADER_FILE'],
            'width' => 24,
            'height' => 24,
        ));
        $resultHeader = $this->pdfApi->postDocumentImageHeader($this->configParams['PDF_DOCUMENT_NAME'], $imageHeader);

        if ($resultHeader->getCode() === 200) {
            echo 'Successfully appended image header ' . $this->configParams['IMAGE_HEADER_FILE'];
        }
        else
            throw new Error("Unexpected error : can't append image header!");
    }

    function main() {
        global $configParams;

        try {
            $pdfHeaderHeader = new PdfHeaderFooter($configParams);
            $pdfHeaderHeader->uploadDocument();
            $pdfHeaderHeader->uploadFile($configParams['IMAGE_HEADER_FILE']);
            $pdfHeaderHeader->addImageHeader();
            $pdfHeaderHeader->downloadResult();
        } catch (\Exception $e) {
            echo "Error: " . $e->getMessage() . "\n";
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Работа с заголовками в PDF" %}}

Добавление изображения в заголовок PDF улучшает брендинг, профессионализм, читаемость и безопасность. Это обеспечивает консистентность в бизнесе, юридических, маркетинговых и технических документах, делая их более визуально привлекательными и функциональными.
Добавьте заголовок в PDF-документы с [Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/).

**С нашей PHP-библиотекой вы можете:**

+ Добавлять заголовок и нижний колонтитул PDF-документа в текстовом или графическом формате.
+ Добавлять таблицы и штампы (текстовые или графические) в PDF-документы.
+ Добавлять несколько PDF-документов к существующему файлу.
+ Работать с вложениями, аннотациями и полями форм в PDF.
+ Применять шифрование или дешифрование к PDF-документам и задавать пароль.
+ Удалять все штампы и таблицы со страницы или всего PDF-документа.
+ Удалять конкретный штамп или таблицу из PDF-документа по его ID.
+ Заменять одно или несколько вхождений текста на странице PDF или во всем документе.
+ Обширная поддержка конвертации PDF-документов в различные другие форматы файлов.
+ Извлекать различные элементы из PDF-файлов и оптимизировать PDF-документы.
+ Вы можете попробовать наше [бесплатное приложение](https://products.aspose.app/pdf/family) для тестирования функциональности онлайн.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Учебные материалы" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Документация" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Исходный код" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-php" >}}
{{< blocks/products/pf/slr-element name="Ссылки на API" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Поддержка продукта" tabId="support" >}}
{{< blocks/products/pf/slr-element name="Бесплатная поддержка" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="Платная поддержка" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="Блог" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Почему Aspose.PDF Cloud для PHP?" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="Список клиентов" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="Безопасность" href="https://company.aspose.cloud/legal/security" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< /blocks/products/pf/support-learning-resources >}}

{{< blocks/products/pf/offers-section pfName="Aspose.PDF" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/curl/" imgSrc="/sdk/aspose_pdf-for-curl.svg" platform="cURL" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/net/" imgSrc="/sdk/aspose_pdf-for-net.svg" platform=".NET" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/java/" imgSrc="/sdk/aspose_pdf-for-java.svg" platform="Java" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/php/" imgSrc="/sdk/aspose_pdf-for-php.svg" platform="PHP" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/android/" imgSrc="/sdk/aspose_pdf-for-android.svg" platform="Android" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/python/" imgSrc="/sdk/aspose_pdf-for-python.svg" platform="Python" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/ruby/" imgSrc="/sdk/aspose_pdf-for-ruby.svg" platform="Ruby" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/nodejs/" imgSrc="/sdk/aspose_pdf-for-node.svg" platform="Node.js" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/swift/" imgSrc="/sdk/aspose_pdf-for-swift.svg" platform="Swift" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/go/" imgSrc="/sdk/aspose_pdf-for-go.svg" platform="Go" >}}

{{< blocks/products/pf/offers-section-item link="/pdf/aws/" imgSrc="/sdk/aspose_pdf-for-go.svg" platform="AWS" >}}

{{< /blocks/products/pf/offers-section >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
