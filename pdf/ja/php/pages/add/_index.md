---
title: Cloud PHP SDKを使用してPDFにページを追加
url: php/pages/add/
description: Aspose.PDF Cloud SDKを使用して、PHPでPDFドキュメントに新しいページを追加します。コンテンツを動的に挿入します。
lastmod: 2025-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="PHP SDKでPDFにページを追加" h2="Cloud PHP SDKを使用してPDFドキュメントにページを追加します。" logoImageSrc="/sdk/aspose_pdf-for-php.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for PHP" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for PHP" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="/sdk/aspose_pdf-for-php.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/php/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="https://reference.aspose.cloud/pdf/" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="Cloud PHP SDKを使用してPDFにページを追加する方法" %}}

PDFにページを追加するために、我々は使用します
[Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/)
このCloud SDKは、PHPプログラマーがPHPプログラミング言語を使用してクラウドベースのPDF作成、注釈、編集、および変換アプリを開発するのを支援します。簡単に[Aspose for Cloud](https://dashboard.aspose.cloud/#/apps)でアカウントを作成し、アプリケーション情報を取得します。App SIDとキーを取得したら、Aspose.PDF Cloud PHP SDKを利用する準備が整います。

{{% blocks/products/pf/agp/code-block title="パッケージマネージャーコンソールコマンド" offSpacer="true" %}}

```bash
     
    composer install

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Cloud PHPを使用してPDFにページを追加する手順" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloudの開発者は、数行のコードで簡単にPDFにページをロードして追加できます。

{{% /blocks/products/pf/agp/text %}}

1. PDFドキュメントをアップロード
1. ドキュメントに新しいページを追加
1. 更新されたPDFをダウンロード
1. 安定性のためにエラーハンドリングを実装

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="PHPを使用してPDFにページを追加" offSpacer="" %}}

```php

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

    public function uploadDocument() {
        $fileNamePath = $this->configParams['LOCAL_FOLDER'] . $this->configParams['PDF_DOCUMENT_NAME'];
        $pdfFileData = file_get_contents($fileNamePath);
        $this->pdfApi->uploadFile($this->configParams['PDF_DOCUMENT_NAME'], $pdfFileData);
    }

    public function downloadResult() {
        $changedPdfData = $this->pdfApi->downloadFile($this->configParams['PDF_DOCUMENT_NAME']);
        $filePath = $this->configParams['LOCAL_FOLDER'] . $this->configParams['LOCAL_RESULT_DOCUMENT_NAME'];
        file_put_contents($filePath, $changedPdfData);
        echo "Downloaded: " . $filePath . "\n";
    }

    public function appendPage() {
        $resultPages = $this->pdfApi->putAddNewPage($this->configParams['PDF_DOCUMENT_NAME']);
        if ($resultPages->getCode() == 200) {
            $newPage = end($resultPages->getPages()->getList('list'));
            echo "Appended page:";
            var_dump($newPage);
        } else {
            echo "Unexpected error: can't get pages!!!\n";
        }
    }

    function main() {
        global $configParams;
        $pdfPages = new PdfPages($configParams);
        try {
            $pdfPages->uploadDocument();
            $pdfPages->appendPage();
            $pdfPages->downloadResult();
        } catch (Exception $e) {
            echo "Error: " . $e->getMessage() . "\n";
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="PDFのページを操作する" %}}

PDFドキュメントにページを追加することは、ドキュメントの機能、組織、包括性を向上させるための一般的な作業です。しばしば、付録、参考資料、または元のドキュメント作成時には利用できなかった更新データなどの追加コンテンツを含める必要があります。新しいページを追加することで、この補足情報をシームレスに統合し、ドキュメントが最新かつ包括的であることを保証します。PDFにページを追加することは、コンテンツと構造を強化し、コンプライアンスを確保し、コラボレーションを促進する多様なニーズに対応する汎用的な実践です。特定の要件を理解し、適切なツールを使用することで、ユーザーはさまざまな目的に合わせてPDFドキュメントを効果的に管理および修正できます。
[Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/)を使用してPDFドキュメントにページを追加します。

**私たちのPHPライブラリを使用すると、以下が可能です：**

+ PDFドキュメントのヘッダー＆フッターをテキストまたは画像形式で追加します。
+ PDFドキュメントにテーブル＆スタンプ（テキストまたは画像）を追加します。
+ 複数のPDFドキュメントを既存のファイルに追加します。
+ PDFの添付ファイル、注釈、フォームフィールドを操作します。
+ PDFドキュメントに暗号化または復号化を適用し、パスワードを設定します。
+ ページまたは全体のPDFドキュメントからすべてのスタンプ＆テーブルを削除します。
+ IDで特定のスタンプまたはテーブルをPDFドキュメントから削除します。
+ PDFページまたはドキュメント全体から単一または複数のテキストインスタンスを置換します。
+ PDFドキュメントをさまざまな他のファイル形式に変換するための広範なサポート。
+ PDFファイルのさまざまな要素を抽出し、PDFドキュメントを最適化します。
+ [無料アプリ](https://products.aspose.app/pdf/family)を試して、オンラインで機能をテストできます。

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="学習リソース" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="ドキュメント" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="ソースコード" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-php" >}}
{{< blocks/products/pf/slr-element name="APIリファレンス" href="https://reference.aspose.cloud/pdf/" >}}
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
