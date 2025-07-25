---
title: Cloud PHP SDKを使用したメタデータの追加
url: php/metadata/add/
description: Aspose.PDF Cloud SDKを使用してPHPでPDFファイルにメタデータを追加します。文書にタグを付けて、インデックス作成や検索を向上させます。
lastmod: 2024-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="PHP SDKでPDFにメタデータを追加" h2="Cloud PHP SDKを使用してPDF文書にメタデータを追加します。" logoImageSrc="/sdk/aspose_pdf-for-php.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for PHP" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for PHP" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="/sdk/aspose_pdf-for-php.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/php/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="https://reference.aspose.cloud/pdf/" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="Cloud PHP SDKを使用してメタデータを作成する方法" %}}

メタデータを作成するために、私たちは
[Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/)
このCloud SDKは、PHPプログラマーがAspose.PDF REST APIを介してPHPプログラミング言語を使用してクラウドベースのPDF作成、注釈付け、編集、変換アプリを開発するのに役立ちます。 [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps)でアカウントを作成し、アプリケーション情報を取得してください。App SIDとキーを取得したら、Aspose.PDF Cloud PHP SDKを使用する準備が整います。

{{% blocks/products/pf/agp/code-block title="パッケージマネージャーコンソールコマンド" offSpacer="true" %}}

```bash
     
    composer install

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Cloud PHP SDKを使用してメタデータを作成する手順" %}}

{{% blocks/products/pf/agp/text %}}

プログラムでPDFにメタデータを追加する基本的な方法
[Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/)
APIを使用すると、わずか数行のコードで実行できます。

{{% /blocks/products/pf/agp/text %}}

1. [PHP SDK](https://pypi.org/project/asposepdfcloud/)をインストールします。
1. [Aspose Cloud Dashboard](https://dashboard.aspose.cloud/)にアクセスします。
1. すべてのアプリケーションとサービスにアクセスするために新しい[アカウント](https://docs.aspose.cloud/display/storagecloud/Creating+and+Managing+Account)を作成するか、アカウントにサインインします。
1. 左側のメニューで「アプリケーション」をクリックして、クライアントIDとクライアントシークレットを取得します。
1. PHPでPDFにメタデータを作成するための[開発者ガイド](https://docs.aspose.cloud/pdf/developer-guide/)をチェックしてください。
1. 作業例とともに完全なAPIリストのために、[GitHubリポジトリ](https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-php)をチェックしてください。
1. APIパラメータの説明のために、[APIリファレンスページ](https://reference.aspose.cloud/pdf/#/Document)をチェックしてください。

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/feature-section-col title="システム要件" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud PHP SDKを使い始めるのは簡単で、インストールするものはありません。Aspose for Cloudでアカウントを作成し、アプリケーション情報を取得してください。App SIDとキーを取得したら、Aspose.PDF Cloud PHP SDKを使用する準備が整います。

+ PHP 7.4以降。

{{% /blocks/products/pf/agp/text %}}

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="PHPを使用してPDFにXMPメタデータプロパティを作成する" offSpacer="" %}}

```php

    $name = '4pages.pdf';
    $this->uploadFile($name);

    $date = '2024-10-27T09:59:52+02:00';
    $metadata = new Aspose\PDF\Model\XmpMetadata(array(
        'properties' => array(
            # Add Default property
            new Aspose\PDF\Model\XmpMetadataProperty(array('key' => "BaseURL", 'value' => "http://www.somename.com/path")),
            # Add user defined property
            new Aspose\PDF\Model\XmpMetadataProperty(array('key' => "pdf:Prop", 'value' => "PropValue", 'namespace_uri' => "http://ns.adobe.com/pdf/1.3/")),
        )
    ));
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="PDFでメタデータを操作する" %}}

PDFファイルでメタデータを操作することは重要です。タイトルフィールド、著者、テーマなどのメタデータは文書を分類するのに役立ち、ファイルを開かずにコンテンツの概要をすばやく把握することができるため、大量の文書を管理するのが容易になります。
メタデータは、キーワードや属性で検索を行うことを可能にするため、ファイル検索を改善します。これは、迅速な文書の取得が重要なシステムにおいて特に価値があります。

**私たちのPHPライブラリを使用して、あなたは次のことができます:**

+ PDF文書のヘッダーとフッターをテキストまたは画像形式で追加します。
+ PDF文書にテーブルとスタンプ（テキストまたは画像）を追加します。
+ 複数のPDF文書を既存のファイルに追加します。
+ PDFの添付ファイル、注釈、フォームフィールドを操作します。
+ PDF文書に暗号化または復号化を適用し、パスワードを設定します。
+ ページまたはPDF文書全体からすべてのスタンプとテーブルを削除します。
+ PDF文書から特定のIDのスタンプまたはテーブルを削除します。
+ PDFページまたは文書全体から単一または複数のテキストを置換します。
+ PDF文書をさまざまな他のファイル形式に変換するための広範なサポート。
+ PDFファイルのさまざまな要素を抽出し、PDF文書を最適化します。
+ [無料アプリ](https://products.aspose.app/pdf/metadata)を試して、PDFファイルにメタデータをオンラインで追加し、機能をテストできます。

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
