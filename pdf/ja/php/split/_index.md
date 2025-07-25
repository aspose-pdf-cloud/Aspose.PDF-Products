---
title: 単一のPDFドキュメントを分割 | PHP
description: PHPおよびAspose.PDF Cloud SDKを使用して、大きなPDFドキュメントを小さな部分に分割します。
weight: 40
url: php/split/
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="PHP SDKでPDFを分割" h2="Adobe PDFのようなソフトウェアを使用せずに、PHP Cloud APIでPDFファイルを分割します。" logoImageSrc="/sdk/aspose_pdf-for-php.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for PHP" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for PHP" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="/sdk/aspose_pdf-for-php.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/php/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="https://reference.aspose.cloud/pdf/" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="Cloud API for PHPを使用してPDFファイルを分割する方法 " %}}

**なぜPDFドキュメントを分割する必要があるのか？** PHPでPDFを分割することは、大きなドキュメントを管理および整理する際や、データ処理環境で作業する際に必要となる場合があります。大きなドキュメントの一部のセクションやページのみが必要な場合があります。PDFの分割により、ドキュメント全体を除去せずに対応するページを強調して抽出できます。

また、特にドキュメントが大きくて必要以上の情報を含んでいる場合、すべてのPDFを送信または共有することは非効率的です。PDFを分割すると、対応するページのみを分離する必要があり、プロセスが高速になり、帯域幅を節約できます。

PDFを小さなセクションに分割することでファイルサイズを小さくでき、ストレージの問題がある場合やサイズ制限のあるシステムにドキュメントをロードする場合に便利です。

{{% blocks/products/pf/agp/code-block title="パッケージマネージャーコンソールコマンド" offSpacer="true" %}}

```bash
     
    composer install

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Cloud PHP SDKを使用したPDF分割の手順" %}}

{{% blocks/products/pf/agp/text %}}

プログラムでPDFを分割する基本的な方法は、
[Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/)
APIを使用して数行のコードで実行できます。

{{% /blocks/products/pf/agp/text %}}

1. [PHP SDK](https://pypi.org/project/asposepdfcloud/)をインストールします。
1. [Aspose Cloud Dashboard](https://dashboard.aspose.cloud/)にアクセスします。
1. すべてのアプリケーションとサービスにアクセスするために新しい[アカウント](https://docs.aspose.cloud/display/storagecloud/Creating+and+Managing+Account)を作成するか、アカウントにサインインします。
1. クライアントIDとクライアントシークレットを取得するために、左メニューのアプリケーションをクリックします。
1. PHPでPDFを分割するための[開発者ガイド](https://docs.aspose.cloud/pdf/split-pdf-files/)を確認します。
1. 完全なAPIリストと動作する例が含まれている[GitHubリポジトリ](https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-php)を確認します。
1. APIのパラメータの説明については、[APIリファレンスページ](https://reference.aspose.cloud/pdf/#/Document)を確認してください。

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/feature-section-col title="システム要件" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud PHP SDKを使用するのは簡単で、インストールするものはありません。Aspose for Cloudでアカウントを作成し、アプリケーション情報を取得するだけです。App SIDとキーを取得したら、Aspose.PDF Cloud PHP SDKを使用する準備が整います。

+ PHP 7.4以降。

{{% /blocks/products/pf/agp/text %}}

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="PHPを使用して単一のPDFファイルを分割" offSpacer="" %}}

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

{{% blocks/products/pf/agp/content h2="PHPライブラリでできること:" %}}

+ PDFドキュメントのヘッダーとフッターをテキストまたは画像形式で追加。
+ PDFドキュメントにテーブルとスタンプ（テキストまたは画像）を追加。
+ 複数のPDFドキュメントを既存のファイルに追加。
+ PDFの添付ファイル、注釈、フォームフィールドを操作。
+ PDFドキュメントに暗号化または復号化を適用し、パスワードを設定。
+ ページまたはPDFドキュメント全体からすべてのスタンプとテーブルを削除。
+ PDFドキュメントからIDで特定のスタンプまたはテーブルを削除。
+ PDFページまたはドキュメント全体から単一または複数のテキストインスタンスを置換。
+ PDFドキュメントをさまざまな他のファイル形式に変換するための幅広いサポート。
+ PDFファイルのさまざまな要素を抽出し、PDFドキュメントを最適化。
+ PDFファイルをオンラインで分割し、機能をテストするための[無料アプリ](https://products.aspose.app/pdf/split-pdf)を試すことができます。

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

{{< blocks/products/pf/slr-tab tabTitle="なぜAspose.PDF Cloud for PHPか?" tabId="success-stories" >}}
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
