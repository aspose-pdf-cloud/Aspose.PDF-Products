---
title: Ganti Tanda Tangan dalam PDF melalui Cloud PHP SDK
url: php/signature/replace/
description: Aspose.PDF Cloud memungkinkan Anda untuk mengganti tanda tangan dalam Dokumen PDF. Periksa kode sumber PHP untuk mengganti tanda tangan dalam file PDF.
lastmod: 2025-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Ganti Tanda Tangan dalam PDF di PHP SDK" h2="Ganti Tanda Tangan dalam Dokumen PDF menggunakan Cloud PHP SDK" logoImageSrc="/sdk/aspose_pdf-for-php.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="untuk PHP" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK untuk PHP" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="/sdk/aspose_pdf-for-php.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/php/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="https://reference.aspose.cloud/pdf/" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="Cara mengganti Tanda Tangan dalam PDF melalui Cloud PHP SDK" %}}

Untuk mengganti tanda tangan dalam PDF, kita akan menggunakan
[Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/)
Cloud SDK ini membantu pemrogram PHP dalam mengembangkan aplikasi pembuat, anotator, editor, dan konverter PDF berbasis cloud menggunakan bahasa pemrograman PHP melalui Aspose.PDF REST API. Cukup buat akun di [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) dan dapatkan informasi aplikasi Anda. Setelah Anda memiliki App SID & kunci, Anda siap menggunakan Aspose.PDF Cloud PHP SDK.

{{% blocks/products/pf/agp/code-block title="Perintah Konsol Pengelola Paket" offSpacer="true" %}}

```bash
     
    composer install

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Langkah-langkah untuk mengganti tanda tangan dalam PDF melalui Cloud PHP" %}}

{{% blocks/products/pf/agp/text %}}

Pengembang Aspose.PDF Cloud dapat dengan mudah memuat & mengganti tanda tangan dalam PDF hanya dengan beberapa baris kode.

{{% /blocks/products/pf/agp/text %}}

1. Unggah Dokumen PDF
1. Unduh dokumen PDF dengan tanda tangan yang diterapkan dari penyimpanan cloud Aspose.PDF.
1. Terapkan tanda tangan yang ditentukan ke dokumen PDF.

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Ganti tanda tangan dalam PDF menggunakan PHP" offSpacer="" %}}

```php

    require __DIR__.'\..\..\vendor\autoload.php';

    use Aspose\PDF\Configuration;
    use Aspose\PDF\Api\PdfApi;

    $config = [
        'LOCAL_FOLDER' => "C:\\Samples\\",
        'PDF_DOCUMENT_NAME' => "sample.pdf",
        'LOCAL_RESULT_DOCUMENT_NAME' => "output_sample.pdf",
        'LOCAL_SIGNATURE_PATH' => "C:\\Samples\\Signatures\\3",
        'SIGNATURE_PFX' => "signature.pfx",
        'SIGNATURE_FORM_FIELD' => 'Signature_1',
        'SIGNATURE_PASSWORD' => 'Password',
        'SIGNATURE_CONTACT' => 'Contact',
        'SIGNATURE_LOCATION' => 'Location',
        'SIGNATURE_AUTHORITY' => 'Issuer',
        'SIGNATURE_DATE' => '04/19/2025 12:15:00.000 PM',
        'SIGNATURE_RECT' => new Aspose\PDF\Model\Rectangle(array('llx' => 100, 'lly' => 100, 'urx' => 0, 'ury' => 0))
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

        public function uploadFile($folder, $fileName) {
            $filePath = $folder . DIRECTORY_SEPARATOR . $fileName;
            $data = file_get_contents($filePath);
            $this->pdfApi->uploadFile($fileName, $data);
            echo "File '$fileName' successfully uploaded!\n";
        }

        public function uploadDocument() {
            $this->uploadFile($this->config['LOCAL_FOLDER'], $this->config['PDF_DOCUMENT_NAME']);
        }

        public function downloadResult() {
            $response = $this->pdfApi->downloadFile($this->config['PDF_DOCUMENT_NAME']);
            $filePath = $this->config['LOCAL_FOLDER'] . DIRECTORY_SEPARATOR . $this->config['LOCAL_RESULT_DOCUMENT_NAME'];
            file_put_contents($filePath, $response->body);
            echo "Downloaded: $filePath\n";
        }

        public function replaceSignature() {
            $signature = new \Aspose\PDF\Model\Signature( array(
                'authority'=> $this->config['SIGNATURE_AUTHORITY'],
                'contact' => $this->config['SIGNATURE_CONTACT'],
                'date' => $this->config['SIGNATURE_DATE'],
                'form_field_name' => $this->config['SIGNATURE_FORM_FIELD'],
                'location' => $this->config['SIGNATURE_LOCATION'],
                'password' => $this->config['SIGNATURE_PASSWORD'],
                'rectangle' => $this->config['SIGNATURE_RECT'],
                'signature_path' => $this->config['SIGNATURE_PFX'],
                'signature_type' => \Aspose\PDF\Model\SignatureType::PKCS7,
                'visible' => TRUE )
            );

            $field = new \Aspose\PDF\Model\SignatureField( array(
                'page_index' => 1,
                'signature' => $signature,
                'partial_name' => 'sign1',
                'rect' => $this->config['SIGNATURE_RECT'])
            );

            $response = $this->pdfApi->putSignatureField(
                $this->config['PDF_DOCUMENT_NAME'],
                $this->config['SIGNATURE_FORM_FIELD'],
                $field
            );

            if ($response->code === 200) {
                echo "replaceSignature(): Signature '" . $this->config['SIGNATURE_CONTACT'] . "' successfully replaced.\n";
            } else {
                echo "replaceSignature(): Failed to replace signature. Code: " . $response->code . "\n";
            }
        }
    }

    try {
        $signatures = new PdfSignatures($pdfApi, $configParams);
        $signatures->uploadFile($configParams['LOCAL_SIGNATURE_PATH'], $configParams['SIGNATURE_PFX']);
        $signatures->uploadDocument();
        $signatures->replaceSignature();
        $signatures->downloadResult();
    } catch (Exception $e) {
        echo "Error: " . $e->getMessage() . "\n";
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Bekerja dengan Tanda Tangan dalam PDF" %}}

Mengganti tanda tangan dalam PDF diperlukan ketika tanda tangan asli menjadi usang, salah, atau tidak valid. Proses ini memastikan bahwa dokumen mencerminkan informasi yang paling akurat dan sah. Alasan umum untuk penggantian termasuk memperbarui kredensial penandatangan, memperbaiki kesalahan dalam detail tanda tangan, menandatangani ulang setelah perubahan dokumen, atau beralih ke sertifikat digital yang lebih kuat untuk meningkatkan keamanan dan kepatuhan. Mengganti tanda tangan membantu menjaga keaslian, integritas, dan keabsahan hukum dokumen.
Ganti Tanda Tangan dalam dokumen PDF dengan [Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/).

**Dengan perpustakaan PHP kami Anda dapat:**

+ Tambahkan header & footer dokumen PDF dalam format teks atau gambar.
+ Tambahkan tabel & stempel (teks atau gambar) ke dokumen PDF.
+ Gabungkan beberapa dokumen PDF ke dalam file yang sudah ada.
+ Bekerja dengan lampiran PDF, anotasi, & bidang formulir.
+ Terapkan enkripsi atau dekripsi pada dokumen PDF & atur kata sandi.
+ Hapus semua stempel & tabel dari satu halaman atau seluruh dokumen PDF.
+ Hapus stempel atau tabel tertentu dari dokumen PDF berdasarkan ID-nya.
+ Ganti satu atau beberapa instance teks pada halaman PDF atau dari seluruh dokumen.
+ Dukungan luas untuk mengonversi dokumen PDF ke berbagai format file lainnya.
+ Ekstrak berbagai elemen dari file PDF & optimalkan dokumen PDF.
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

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
