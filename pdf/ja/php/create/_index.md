---
title: クラウド PHP SDK を使用して PDF を作成
url: php/create/
description: Aspose.PDF Cloud は PDF ドキュメントを作成できます。PHP ソースコードを確認して PDF ファイルを作成してください。
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="PHP SDK で PDF を作成" h2="クラウド PHP SDK を使用して PDF ドキュメントを作成" logoImageSrc="/sdk/aspose_pdf-for-php.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for PHP" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for PHP" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="/sdk/aspose_pdf-for-php.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/php/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="https://reference.aspose.cloud/pdf/" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="クラウド PHP SDK を通じて PDF を作成する方法" %}}

PDF を作成するには、
[Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/)
このクラウド SDK は PHP プログラマーが Aspose.PDF REST API を通じてクラウドベースの PDF 作成、注釈、編集、変換アプリを開発するのを支援します。[Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) でアカウントを作成し、アプリケーション情報を取得してください。App SID とキーを取得したら、Aspose.PDF Cloud PHP SDK を利用する準備が整います。

{{% blocks/products/pf/agp/code-block title="パッケージマネージャーコンソールコマンド" offSpacer="true" %}}

```bash
     
    composer install

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="クラウド PHP を通じて PDF を作成する手順" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud 開発者は、ほんの数行のコードで簡単に PDF を読み込み、作成できます。

{{% /blocks/products/pf/agp/text %}}

1. PDF ドキュメントをアップロード
1. 設定パラメーターを定義
1. PdfPageChanges クラスを定義
1. createPdfDocument() を呼び出して PDF を生成

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="PHP を使用して PDF を作成" offSpacer="" %}}

```php

    require __DIR__.'\..\..\vendor\autoload.php';

    use Aspose\PDF\Configuration;
    use Aspose\PDF\Api\PdfApi;

    // Загрузка JSON с учетными данными
    $credentials = json_decode(file_get_contents(__DIR__ . '/../../../Credentials/credentials.json'), true);

    $configParams = [
        "LOCAL_FOLDER" => "C:\\Samples\\",
        "TEMP_FOLDER" => "TempPdfCloud",
        "LOCAL_RESULT_DOCUMENT_NAME" => "output_sample.pdf",
        "PAGE_WIDTH" => 590,
        "PAGE_HEIGHT" => 894,
        "PAGES_COUNT" => 5,
    ];

    class PdfPageChanges
    {
        private $pdfApi;
        private $configParams;

        private function _create_rest_api() {
            $credentials = json_decode(file_get_contents("../../../../Credentials/credentials.json"), true);

            $configAuth = new Configuration();
            $configAuth->setAppKey($credentials['key']);
            $configAuth->setAppSid($credentials['id']);

            $this->pdfApi = new PdfApi(null, $configAuth);
        }

        public function __construct($config) {
            $this->configParams = $config;
            $this->_create_rest_api();
        }

        public function downloadResult()
        {
            $fileName = $this->configParams["TEMP_FOLDER"] . DIRECTORY_SEPARATOR . $this->configParams["LOCAL_RESULT_DOCUMENT_NAME"];
            $changedPdfData = $this->pdfApi->downloadFile($fileName);
            $filePath = $this->configParams["LOCAL_FOLDER"] . DIRECTORY_SEPARATOR . $this->configParams["LOCAL_RESULT_DOCUMENT_NAME"];
            file_put_contents($filePath, $changedPdfData->getBody());
            echo "Downloaded: " . $filePath . PHP_EOL;
        }

        public function createPdfDocument()
        {
            $pdfConfig = new \Aspose\PDF\Model\DocumentConfig();
            $pdfConfig->setPagesCount($this->configParams["PAGES_COUNT"]);

            $displayProps = new \Aspose\PDF\Model\DisplayProperties();
            $displayProps->setCenterWindow(true);
            $displayProps->setHideMenuBar(true);
            $displayProps->setDirection(\Aspose\PDF\Model\Direction::L2_R);
            $displayProps->setDisplayDocTitle(true);
            $displayProps->setHideToolBar(true);
            $displayProps->setHideWindowUI(true);
            $displayProps->setNonFullScreenPageMode(\Aspose\PDF\Model\PageMode::USE_THUMBS);
            $displayProps->setPageLayout(\Aspose\PDF\Model\PageLayout::TWO_PAGE_LEFT);
            $displayProps->setPageMode(\Aspose\PDF\Model\PageMode::USE_THUMBS);
            $pdfConfig->setDisplayProperties($displayProps);

            $docProps = new \Aspose\PDF\Model\DocumentProperties();
            $docProp = new \Aspose\PDF\Model\DocumentProperty();
            $docProp->setBuiltIn(false);
            $docProp->setName("prop1");
            $docProp->setValue("Val1");
            $docProps->setList([$docProp]);
            $pdfConfig->setDocumentProperties($docProps);

            $defaultPageConfig = new \Aspose\PDF\Model\DefaultPageConfig();
            $defaultPageConfig->setWidth($this->configParams["PAGE_WIDTH"]);
            $defaultPageConfig->setHeight($this->configParams["PAGE_HEIGHT"]);
            $pdfConfig->setDefaultPageConfig($defaultPageConfig);

            $response = $this->pdfApi->postCreateDocument(
                $this->configParams["LOCAL_RESULT_DOCUMENT_NAME"],
                $pdfConfig,
                null,
                $this->configParams["TEMP_FOLDER"]
            );

            echo "Document #" . $this->configParams["LOCAL_RESULT_DOCUMENT_NAME"] . " created." . PHP_EOL;
            return $response;
        }
    }

    try {
        $pdfManager = new PdfPageChanges($pdfApi, $configParams);
        $pdfManager->createPdfDocument();
        $pdfManager->downloadResult();
    } catch (Exception $e) {
        echo "Error: " . $e->getMessage() . PHP_EOL;
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="私たちの PHP ライブラリを使用してできること：" %}}

[Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/) で PDF ドキュメントを作成。

+ PDF ドキュメントのヘッダーとフッターをテキストまたは画像形式で追加。
+ テーブルとスタンプ（テキストまたは画像）を PDF ドキュメントに追加。
+ 複数の PDF ドキュメントを既存のファイルに追加。
+ PDF の添付ファイル、注釈、フォームフィールドを操作。
+ PDF ドキュメントに暗号化または復号化を適用し、パスワードを設定。
+ ページまたは PDF ドキュメント全体からすべてのスタンプとテーブルを削除。
+ PDF ドキュメントから特定のスタンプまたはテーブルを ID で削除。
+ PDF ページまたはドキュメント全体から単一または複数のテキストインスタンスを置換。
+ PDF ドキュメントをさまざまな他のファイル形式に変換するための広範なサポート。
+ PDF ファイルのさまざまな要素を抽出し、PDF ドキュメントを最適化。
+ 機能をオンラインでテストするための[無料アプリ](https://products.aspose.app/pdf/family)をお試しください。

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="学習リソース" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="ドキュメント" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="ソースコード" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-php" >}}
{{< blocks/products/pf/slr-element name="API リファレンス" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="製品サポート" tabId="support" >}}
{{< blocks/products/pf/slr-element name="無料サポート" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="有料サポート" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="ブログ" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="なぜAspose.PDF Cloud for PHPなのか？" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="顧客リスト" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="セキュリティ" href="https://company.aspose.cloud/legal/security" >}}
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
