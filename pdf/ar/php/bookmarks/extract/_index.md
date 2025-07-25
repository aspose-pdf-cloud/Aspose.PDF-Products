---
title: استخراج العلامات المرجعية من PDF عبر Cloud PHP SDK
url: php/bookmarks/extract/
description: استخراج العلامات المرجعية من ملفات PDF باستخدام Aspose.PDF Cloud SDK لـ PHP. استرجاع هيكل المستند برمجياً.
lastmod: 2025-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="استخراج العلامات المرجعية من PDF في PHP SDK" h2="API للعمل مع العلامات المرجعية في مستندات PDF باستخدام Cloud PHP SDK." h2="قم ببناء تطبيقات PHP الخاصة بك للحصول على العلامات المرجعية في ملفات PDF باستخدام واجهات برمجة التطبيقات على الخادم." logoImageSrc="/sdk/aspose_pdf-for-php.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for PHP" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for PHP" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="/sdk/aspose_pdf-for-php.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/php/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="https://reference.aspose.cloud/pdf/" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="كيفية الحصول على العلامات المرجعية من PDF عبر Cloud PHP SDK" %}}

لاستخراج العلامات المرجعية من PDF، سنستخدم
[Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/)
يساعد هذا الـ Cloud SDK مبرمجي PHP في تطوير تطبيقات إنشاء وتحرير وتعليق وتحويل ملفات PDF السحابية باستخدام لغة برمجة PHP عبر Aspose.PDF REST API. ببساطة، قم بإنشاء حساب في [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) واحصل على معلومات التطبيق الخاصة بك. بمجرد حصولك على App SID والمفتاح، يمكنك البدء في استخدام Aspose.PDF Cloud PHP SDK.

{{% blocks/products/pf/agp/code-block title="أمر وحدة تحكم مدير الحزم" offSpacer="true" %}}

```bash
     
    composer install

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="خطوات للحصول على العلامات المرجعية من PDF عبر Cloud PHP" %}}

{{% blocks/products/pf/agp/text %}}

يمكن لمطوري Aspose.PDF Cloud بسهولة تحميل والحصول على العلامات المرجعية من PDF في بضعة أسطر من الشيفرة.

{{% /blocks/products/pf/agp/text %}}

1. تحميل مستند PDF
1. استرجاع علامة مرجعية عن طريق المسار
1. تنزيل مستند PDF المعالج

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="استخراج العلامات المرجعية من PDF باستخدام PHP" offSpacer="" %}}

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

    public function uploadDocument() {
        $filePath = $this->configParams['LOCAL_FOLDER'] . $this->configParams['PDF_DOCUMENT_NAME'];
        $fileData = file_get_contents($filePath);

        $response = $this->pdfApi->uploadFile($this->configParams['PDF_DOCUMENT_NAME'], $fileData);
        if ($response->getCode() === 200) {
            echo "Uploaded file: {$this->configParams['PDF_DOCUMENT_NAME']}\n";
        } else {
            echo "Failed to upload file.";
        }
    }

    public function getBookmarkByPath()  {
        $resultBookmark = $this->pdfApi->getBookmarks($this->configParams['PDF_DOCUMENT_NAME'], $this->configParams['BOOKMARK_PATH']);
        if ($resultBookmark->getCode() === 200) 
            echo "Found bookmark title: {$resultBookmark->getBookmark()->getTitle()}";
        else
            echo "Unexpected error : Bookmark not found!";
    }

function main() {
    global $configParams;

    try {
        $pdfBookmarks = new PdfBookmarks($configParams);
        $pdfBookmarks->uploadDocument();
        $pdfBookmarks->getBookmarkByPath();
    } catch (\Exception $e) {
        echo "Error: " . $e->getMessage() . "\n";
    }
}
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="العمل مع العلامات المرجعية في PDF" %}}

استخراج العلامات المرجعية من PDF يحسن من استخدامية المستند، ويقوم بأتمتة معالجة المحتوى، ويعزز من قابلية البحث. هذا مفيد بشكل خاص للشركات والباحثين والمحترفين الذين يتعاملون مع مستندات PDF كبيرة أو منظمة.
استخرج العلامات المرجعية من مستندات PDF باستخدام [Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/).

**مع مكتبة PHP الخاصة بنا يمكنك:**

+ إضافة رأس وتذييل مستند PDF بتنسيق نص أو صورة.
+ إضافة جداول وطوابع (نص أو صورة) إلى مستندات PDF.
+ إلحاق مستندات PDF متعددة بملف موجود.
+ العمل مع مرفقات وتعليقات ونماذج مستندات PDF.
+ تطبيق التشفير أو فك التشفير على مستندات PDF وتعيين كلمة مرور.
+ حذف جميع الطوابع والجداول من صفحة أو من مستند PDF بالكامل.
+ حذف طابع أو جدول محدد من مستند PDF بواسطة معرفه.
+ استبدال حالة واحدة أو متعددة من النص في صفحة PDF أو من المستند بالكامل.
+ دعم واسع لتحويل مستندات PDF إلى تنسيقات ملفات أخرى متنوعة.
+ استخراج عناصر متنوعة من ملفات PDF وجعل مستندات PDF محسنة.
+ يمكنك تجربة [تطبيقنا المجاني](https://products.aspose.app/pdf/family) لاختبار الوظائف عبر الإنترنت.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}
{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="موارد التعلم" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="التوثيق" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="الكود المصدري" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-php" >}}
{{< blocks/products/pf/slr-element name="مراجع API" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="دعم المنتج" tabId="support" >}}
{{< blocks/products/pf/slr-element name="دعم مجاني" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="دعم مدفوع" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="مدونة" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="لماذا Aspose.PDF Cloud لـ PHP؟" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="قائمة العملاء" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="الأمان" href="https://company.aspose.cloud/legal/security" >}}
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

<!-- انتهاء ملف المعلومات -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
