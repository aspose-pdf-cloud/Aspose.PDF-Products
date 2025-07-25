---
title: Verifikasi Tanda Tangan dalam PDF via Cloud PHP SDK
url: php/signature/verify/
description: Aspose.PDF Cloud memungkinkan Anda untuk memverifikasi tanda tangan dalam Dokumen PDF. Periksa kode sumber PHP untuk memverifikasi tanda tangan dalam file PDF.
lastmod: 2025-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Verifikasi Tanda Tangan dalam PDF di PHP SDK" h2="Verifikasi Tanda Tangan dalam Dokumen PDF menggunakan Cloud PHP SDK" logoImageSrc="/sdk/aspose_pdf-for-php.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for PHP" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for PHP" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="/sdk/aspose_pdf-for-php.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/php/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="https://reference.aspose.cloud/pdf/" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="Cara memverifikasi Tanda Tangan dalam PDF melalui Cloud PHP SDK" %}}

Untuk memverifikasi tanda tangan dalam PDF, kita akan menggunakan
[Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/)
Cloud SDK ini membantu pemrogram PHP dalam mengembangkan aplikasi pembuat, annotator, editor, dan konverter PDF berbasis cloud menggunakan bahasa pemrograman PHP melalui Aspose.PDF REST API. Cukup buat akun di [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) dan dapatkan informasi aplikasi Anda. Setelah Anda memiliki App SID & kunci, Anda siap untuk menggunakan Aspose.PDF Cloud PHP SDK.

{{% blocks/products/pf/agp/code-block title="Perintah Konsol Manajer Paket" offSpacer="true" %}}

```bash
     
    composer install

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Langkah-langkah untuk memverifikasi tanda tangan dalam PDF via Cloud PHP" %}}

{{% blocks/products/pf/agp/text %}}

Pengembang Aspose.PDF Cloud dapat dengan mudah memuat & memverifikasi tanda tangan dalam PDF hanya dalam beberapa baris kode.

{{% /blocks/products/pf/agp/text %}}

1. Unggah Dokumen PDF
1. Memverifikasi tanda tangan dalam dokumen PDF dengan getVerifySignature

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Verifikasi tanda tangan dalam PDF menggunakan PHP" offSpacer="" %}}

```php

    require __DIR__.'\..\..\vendor\autoload.php';

    use Aspose\PDF\Configuration;
    use Aspose\PDF\Api\PdfApi;

    $config = [
        'LOCAL_FOLDER' => "C:\\Samples\\",
        'PDF_DOCUMENT_NAME' => "sample-signed.pdf",
        'SIGNATURE_NAME' => 'sign1',
    ];

    class PdfSignatures {
        private $pdfApi;
        private $config;

        private function _create_rest_api() {
            $credentials = json_decode(file_get_contents("./Credentials/credentials.json"), true);

            $configAuth = new Configuration();
            $configAuth->setAppKey($credentials['key']);
            $configAuth->setAppSid($credentials['id']);

            $this->pdfApi = new PdfApi(null, $configAuth);
        }

        public function __construct($config) {
            $this->config = $config;
            $this->_create_rest_api();
        }

        public function uploadDocument() {
            $filePath = $this->config['LOCAL_FOLDER'] . $this->config['PDF_DOCUMENT_NAME'];
            $fileData = file_get_contents($filePath);

            $this->pdfApi->uploadFile($this->config['PDF_DOCUMENT_NAME'], $fileData);
            echo "File: '{$this->config['PDF_DOCUMENT_NAME']}' successfully uploaded.\n";
        }

        public function verifySignature(): void {
            if ($this->pdfApi) {
                $response = $this->pdfApi->getVerifySignature($this->config['PDF_DOCUMENT_NAME'], $this->config['SIGNATURE_NAME']);
                if ($response->code === 200) {
                    if ($response->valid == TRUE)
                        echo "getSignatureFields(): verifySignature(): Signature is VALID for the '" . $this->config['PDF_DOCUMENT_NAME'] . "' document.";
                    else
                        echo "getSignatureFields(): verifySignature(): Signature is NOT VALID for the '" . $this->config['PDF_DOCUMENT_NAME'] . "' document.";
                }
            }
        }
    }

    try {
        $signatures = new PdfSignatures($pdfApi, $configParams);
        $signatures->uploadDocument();
        $signatures->getSignatureFields();
    } catch (Exception $e) {
        echo "Error: " . $e->getMessage() . "\n";
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Bekerja dengan Tanda Tangan dalam PDF" %}}

Memverifikasi tanda tangan dalam PDF sangat penting untuk memastikan keaslian dan integritas dokumen. Ini mengkonfirmasi bahwa konten tidak diubah sejak ditandatangani dan bahwa tanda tangan dibuat oleh sumber yang terpercaya. Verifikasi tanda tangan sangat penting dalam konteks hukum, keuangan, dan bisnis di mana validitas dokumen digital harus dipastikan untuk mencegah penipuan dan memastikan kepatuhan terhadap peraturan.
Verifikasi Tanda Tangan dalam dokumen PDF dengan [Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/).

**Dengan pustaka PHP kami, Anda dapat:**

+ Menambahkan header & footer dokumen PDF dalam format teks atau gambar.
+ Menambahkan tabel & cap (teks atau gambar) ke dokumen PDF.
+ Menambahkan beberapa dokumen PDF ke file yang sudah ada.
+ Bekerja dengan lampiran PDF, anotasi, & bidang formulir.
+ Menerapkan enkripsi atau dekripsi ke dokumen PDF & mengatur kata sandi.
+ Menghapus semua cap & tabel dari halaman atau seluruh dokumen PDF.
+ Menghapus cap atau tabel tertentu dari dokumen PDF berdasarkan ID-nya.
+ Mengganti satu atau beberapa instance teks pada halaman PDF atau dari seluruh dokumen.
+ Dukungan luas untuk mengonversi dokumen PDF ke berbagai format file lainnya.
+ Mengekstraksi berbagai elemen file PDF & membuat dokumen PDF dioptimalkan.
+ Anda dapat mencoba [Aplikasi gratis kami](https://products.aspose.app/pdf/family) untuk menguji fungsionalitas secara online.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Sumber Daya Pembelajaran" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Dokumentasi" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Kode Sumber" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-php" >}}
{{< blocks/products/pf/slr-element name="Referensi API" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Dukungan Produk" tabId="support" >}}
{{< blocks/products/pf/slr-element name="Dukungan Gratis" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="Dukungan Berbayar" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="Blog" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Mengapa Aspose.PDF Cloud untuk PHP?" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="Daftar Pelanggan" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="Keamanan" href="https://company.aspose.cloud/legal/security" >}}
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

<!-- berkas tentang Berakhir -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
