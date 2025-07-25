---
title: Добавить текст в PDF через облачный PHP SDK
url: php/text/add/
description: Вставляйте новый текст в PDF с использованием PHP и Aspose.PDF Cloud SDK. Автоматизируйте создание контента документов.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Добавить текст в PDF в PHP SDK" h2="Добавить текст в PDF документы с использованием облачного PHP SDK" h2="Создайте свои собственные PHP приложения для добавления текста в файлы PDF документов с использованием серверных API." logoImageSrc="/sdk/aspose_pdf-for-php.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="для PHP" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK для PHP" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="/sdk/aspose_pdf-for-php.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/php/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="https://reference.aspose.cloud/pdf/" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="Как добавить текст в PDF через облачный PHP SDK" %}}

Следующий фрагмент кода от Aspose.PDF загружает PDF и файл кастомного шрифта, определяет элемент с кастомным стилем (цвет текста, цвет фона, шрифт, вращение, выравнивание и интервал) и указывает прямоугольник, в который должен быть помещен параграф на странице. Это полезно для добавления стилизованного текста в определенную область страницы PDF.
Чтобы добавить текст в PDF, мы будем использовать
[Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/)
Этот облачный SDK помогает PHP программистам разрабатывать облачные приложения для создания, аннотирования, редактирования и конвертации PDF с использованием языка программирования PHP через REST API Aspose.PDF. Просто создайте аккаунт на [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) и получите информацию о вашем приложении. Как только у вас будут App SID и ключ, вы готовы использовать Aspose.PDF Cloud PHP SDK.

{{% blocks/products/pf/agp/code-block title="Команда консоли менеджера пакетов" offSpacer="true" %}}

```bash
     
    composer install

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Шаги по добавлению текста в PDF через облачный PHP SDK" %}}

{{% blocks/products/pf/agp/text %}}

Разработчики Aspose.PDF Cloud могут легко загружать и добавлять текст в PDF всего за несколько строк кода.

{{% /blocks/products/pf/agp/text %}}

1. Загрузите необходимые PDF файлы.
1. Определите область прямоугольника текста.
1. Установите цвета текста и настройте свойства текста.
1. Создайте сегмент текста.
1. Соберите текстовую строку и определите свойства параграфа.
1. Добавьте параграф в PDF.
1. Сохраните обновленный PDF.

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Добавление текста в PDF с использованием PHP" offSpacer="" %}}

```php

    $name = 'sample.pdf';
    $this->uploadFile($name);
    $fontName = 'Righteous-Regular.ttf';
    $this->uploadFile($fontName);

    $pageNumber = 1;
    $folder = $this->tempFolder;

    $rectangle = new Aspose\PDF\Model\Rectangle();
    $rectangle->setLlx(100);
    $rectangle->setLly(100);
    $rectangle->setUrx(200);
    $rectangle->setUry(200);

    $foregroundColor = new Aspose\PDF\Model\Color();
    $foregroundColor->setA(0x00);
    $foregroundColor->setR(0x00);
    $foregroundColor->setG(0xFF);
    $foregroundColor->setB(0x00);

    $backgroundColor = new Aspose\PDF\Model\Color();
    $backgroundColor->setA(0x00);
    $backgroundColor->setR(0xFF);
    $backgroundColor->setG(0x00);
    $backgroundColor->setB(0x00);

    $textState = new Aspose\PDF\Model\TextState();
    $textState->setFont('Righteous');
    $textState->setFontSize(10);
    $textState->setForegroundColor($foregroundColor);
    $textState->setBackgroundColor($backgroundColor);
    $textState->setFontStyle(Aspose\PDF\Model\FontStyles::REGULAR);
    $textState->setFontFile($this->tempFolder . '/' . $fontName);

    $segment = new Aspose\PDF\Model\Segment();
    $segment->setValue('segment 1');
    $segment->setTextState($textState);

    $textLine = new Aspose\PDF\Model\TextLine();
    $textLine->setHorizontalAlignment(Aspose\PDF\Model\TextHorizontalAlignment::RIGHT);
    $textLine->setSegments([$segment]);

    $paragraph = new Aspose\PDF\Model\Paragraph();
    $paragraph->setRectangle($rectangle);
    $paragraph->setLeftMargin(10);
    $paragraph->setRightMargin(10);
    $paragraph->setTopMargin(20);
    $paragraph->setBottomMargin(20);
    $paragraph->setHorizontalAlignment(Aspose\PDF\Model\TextHorizontalAlignment::FULL_JUSTIFY);
    $paragraph->setLineSpacing(Aspose\PDF\Model\LineSpacing::FONT_SIZE);
    $paragraph->setRotation(10);
    $paragraph->setSubsequentLinesIndent(20);
    $paragraph->setVerticalAlignment(Aspose\PDF\Model\VerticalAlignment::CENTER);
    $paragraph->setWrapMode(Aspose\PDF\Model\WrapMode::BY_WORDS);
    $paragraph->setLines([$textLine]);
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Работа с текстом в PDF" %}}

Текст может быть динамически добавлен для персонализации PDF документа для конкретного пользователя, например, добавления его имени или персонализированного сообщения. Это часто используется в маркетинговых материалах или для персонализированных отчетов. Добавление текста с использованием определенных шрифтов, цветов и выравнивания может сделать определенные разделы более читаемыми и визуально привлекательными, создавая лучший пользовательский опыт. Добавление текста может помочь поддерживать консистентную информацию в разных версиях PDF, избегая ручных правок и обеспечивая наличие ключевой информации.
Добавьте текст в PDF документы с помощью [Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/).

**С нашей библиотекой PHP вы можете:**

+ Добавить заголовок и нижний колонтитул документа PDF в текстовом или графическом формате.
+ Добавить таблицы и штампы (текстовые или графические) в документы PDF.
+ Добавить несколько документов PDF в существующий файл.
+ Работать с вложениями PDF, аннотациями и полями форм.
+ Применять шифрование или дешифрование к документам PDF и устанавливать пароль.
+ Удалить все штампы и таблицы с страницы или всего документа PDF.
+ Удалить конкретный штамп или таблицу из документа PDF по его ID.
+ Заменить одно или несколько вхождений текста на странице PDF или во всем документе.
+ Широкая поддержка конвертации документов PDF в различные другие форматы файлов.
+ Извлекать различные элементы из файлов PDF и оптимизировать документы PDF.
+ Вы можете попробовать наше [бесплатное приложение](https://products.aspose.app/pdf/editor) для добавления текста в PDF файлы онлайн и тестирования функциональности.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Ресурсы для обучения" tabId="resources" >}}
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
