---
title: Разделение одного PDF-документа | PHP
description: Разделите большие PDF-документы на более мелкие части, используя PHP и Aspose.PDF Cloud SDK.
weight: 40
url: php/split/
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Разделение PDF в PHP SDK" h2="Разделяйте PDF-файлы в PHP Cloud API без использования любого ПО, такого как Adobe PDF." logoImageSrc="/sdk/aspose_pdf-for-php.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="для PHP" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK для PHP" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="/sdk/aspose_pdf-for-php.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/php/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="https://reference.aspose.cloud/pdf/" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="Как разделить PDF-файлы с использованием Cloud API для PHP " %}}

**Зачем мне нужно разделять PDF-документы?** Разделение PDF с помощью PHP может быть необходимо при управлении и организации больших документов или работе в среде обработки данных. Иногда большому документу требуется только отдельный раздел или набор страниц. Разделение PDF позволяет выделить и извлечь соответствующие страницы без остальной части документа.

Кроме того, отправка или обмен всеми PDF может быть неэффективным, особенно если документ большой и содержит больше информации, чем необходимо. При разделении PDF вам нужно только отделить соответствующие страницы, что ускоряет процесс и экономит пропускную способность.

Разделение PDF на более мелкие части может уменьшить размер файла, что полезно, когда у вас возникают проблемы с хранением или загрузкой документов на системы с ограничениями по размеру.

{{% blocks/products/pf/agp/code-block title="Команда консоли диспетчера пакетов" offSpacer="true" %}}

```bash
     
    composer install

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Шаги для разделения PDF через Cloud PHP SDK" %}}

{{% blocks/products/pf/agp/text %}}

Базовое программное разделение PDF с помощью
[Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/)
API можно выполнить всего за несколько строк кода.

{{% /blocks/products/pf/agp/text %}}

1. Установите [PHP SDK](https://pypi.org/project/asposepdfcloud/).
1. Перейдите на [Панель управления Aspose Cloud](https://dashboard.aspose.cloud/).
1. Создайте новую [учетную запись](https://docs.aspose.cloud/display/storagecloud/Creating+and+Managing+Account) для доступа ко всем приложениям и услугам или войдите в свою учетную запись.
1. Нажмите на Приложения в левом меню, чтобы получить Идентификатор клиента и Секрет клиента.
1. Ознакомьтесь с [Руководством разработчика](https://docs.aspose.cloud/pdf/split-pdf-files/), чтобы разделить PDF в PHP.
1. Ознакомьтесь с нашим [репозиторием на GitHub](https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-php) для полного списка API вместе с рабочими примерами.
1. Ознакомьтесь с [страницей справочника API](https://reference.aspose.cloud/pdf/#/Document) для описания параметров API.

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/feature-section-col title="Системные требования" %}}

{{% blocks/products/pf/agp/text %}}

Начать работу с Aspose.PDF Cloud PHP SDK легко, и ничего не нужно устанавливать. Просто создайте учетную запись в Aspose for Cloud и получите информацию о вашем приложении. Как только у вас будут SID и ключ приложения, вы готовы использовать Aspose.PDF Cloud PHP SDK.

+ PHP 7.4 и выше.

{{% /blocks/products/pf/agp/text %}}

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Разделение одного PDF-файла с использованием PHP" offSpacer="" %}}

```php

<?php

    require_once 'vendor/autoload.php';

    use Aspose\Pdf\Configuration;
    use Aspose\Pdf\Api\PdfApi;
    use Aspose\Pdf\Model\SplitResult;

    function splitSingle()
    {
        // Load credentials from JSON file
        $credentials = json_decode(file_get_contents('credentials.json'), true);
        $appSid = $credentials['id'];
        $appKey = $credentials['key'];

        // Initialize the PDF API
        $config = new Configuration();
        $config->setAppSid($appSid);
        $config->setAppKey($appKey);
        $pdfApi = new PdfApi($config);

        // Define local and storage file names
        $localFileName = 'input.pdf';
        $storageFileName = 'uploaded_input.pdf';

        try {
            // Upload the PDF file to Aspose Cloud Storage
            $pdfApi->uploadFile($storageFileName, fopen($localFileName, 'r'));

            // Split the PDF document
            $splitResult = $pdfApi->splitDocument($storageFileName);

            // Check if the split operation was successful
            if ($splitResult->getCode() === 200) {
                echo "Split operation successful.\n";

                // Download each split document
                $documents = $splitResult->getResult()->getDocuments();
                foreach ($documents as $index => $document) {
                    $fileName = "page" . ($index + 1) . ".pdf";
                    $fileContent = $pdfApi->downloadFile($document->getHref());
                    file_put_contents($fileName, $fileContent);
                    echo "Downloaded: $fileName\n";
                }
            } else {
                echo "Error: " . $splitResult->getStatus() . "\n";
            }
        } catch (Exception $e) {
            echo 'Exception: ',  $e->getMessage(), "\n";
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="С нашей библиотекой PHP вы можете:" %}}

+ Добавлять заголовок и нижний колонтитул документа PDF в текстовом или графическом формате.
+ Добавлять таблицы и штампы (текст или изображение) в документы PDF.
+ Добавлять несколько PDF-документов к существующему файлу.
+ Работать с вложениями, аннотациями и полями форм PDF.
+ Применять шифрование или дешифрование к документам PDF и устанавливать пароль.
+ Удалять все штампы и таблицы со страницы или из всего документа PDF.
+ Удалять конкретный штамп или таблицу из документа PDF по его ID.
+ Заменять одну или несколько копий текста на странице PDF или в целом документе.
+ Широкая поддержка конвертации документов PDF в различные другие форматы файлов.
+ Извлекать различные элементы из файлов PDF и оптимизировать документы PDF.
+ Вы можете попробовать наше [бесплатное приложение](https://products.aspose.app/pdf/split-pdf) для разделения PDF-файлов онлайн и тестирования функциональности.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Учебные ресурсы" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Документация" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Исходный код" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-php" >}}
{{< blocks/products/pf/slr-element name="Справочники API" href="https://reference.aspose.cloud/pdf/" >}}
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
