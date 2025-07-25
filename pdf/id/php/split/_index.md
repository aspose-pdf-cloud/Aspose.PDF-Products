---
title: Pisahkan Dokumen PDF Tunggal | PHP
description: Pisahkan dokumen PDF besar menjadi bagian yang lebih kecil menggunakan PHP dan Aspose.PDF Cloud SDK.
weight: 40
url: php/split/
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Pisahkan PDF di PHP SDK" h2="Pisahkan file PDF di PHP Cloud API tanpa menggunakan perangkat lunak seperti Adobe PDF." logoImageSrc="/sdk/aspose_pdf-for-php.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="untuk PHP" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK untuk PHP" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="/sdk/aspose_pdf-for-php.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/php/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="https://reference.aspose.cloud/pdf/" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="Cara Memisahkan File PDF Menggunakan Cloud API untuk PHP " %}}

**Mengapa saya perlu memisahkan dokumen PDF?** Memisahkan PDF dengan PHP bisa diperlukan saat mengelola dan mengorganisir dokumen besar atau bekerja dalam lingkungan pemrosesan data. Terkadang dokumen yang lebih besar hanya memerlukan bagian terpisah atau set halaman tertentu. Pemisahan PDF memungkinkan Anda menyoroti dan mengekstrak halaman-halaman yang sesuai tanpa seluruh dokumen.

Juga, mengirim atau berbagi semua PDF mungkin tidak efisien, terutama jika dokumen besar dan berisi lebih banyak informasi dari yang diperlukan. Saat memisahkan PDF, Anda hanya perlu memisahkan halaman yang sesuai, yang membuat proses lebih cepat dan menghemat bandwidth.

Memisahkan PDF menjadi bagian yang lebih kecil dapat mengurangi ukuran file, yang berguna ketika Anda memiliki masalah penyimpanan atau memuat dokumen ke sistem dengan batasan ukuran.

{{% blocks/products/pf/agp/code-block title="Perintah Konsol Pengelola Paket" offSpacer="true" %}}

```bash
     
    composer install

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Langkah-langkah Memisahkan PDF melalui Cloud PHP SDK" %}}

{{% blocks/products/pf/agp/text %}}

Program dasar memisahkan pdf secara pemrograman dengan
[Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/)
API dapat dilakukan hanya dengan beberapa baris kode.

{{% /blocks/products/pf/agp/text %}}

1. Instal [PHP SDK](https://pypi.org/project/asposepdfcloud/).
1. Kunjungi [Aspose Cloud Dashboard](https://dashboard.aspose.cloud/).
1. Buat [Akun](https://docs.aspose.cloud/display/storagecloud/Creating+and+Managing+Account) baru untuk mengakses semua aplikasi dan layanan atau Masuk ke akun Anda.
1. Klik pada Aplikasi di menu kiri untuk mendapatkan Client Id dan Client Secret.
1. Lihat [Panduan Pengembang](https://docs.aspose.cloud/pdf/split-pdf-files/) untuk memisahkan PDF di PHP.
1. Lihat [repositori GitHub](https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-php) kami untuk daftar API lengkap beserta contoh yang berfungsi.
1. Lihat [halaman Referensi API](https://reference.aspose.cloud/pdf/#/Document) untuk deskripsi parameter API.

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/feature-section-col title="Persyaratan Sistem" %}}

{{% blocks/products/pf/agp/text %}}

Mudah untuk memulai dengan Aspose.PDF Cloud PHP SDK dan tidak ada yang perlu diinstal. Cukup buat akun di Aspose for Cloud dan dapatkan informasi aplikasi Anda. Setelah Anda memiliki App SID & kunci, Anda siap untuk menggunakan Aspose.PDF Cloud PHP SDK.

+ PHP 7.4 dan yang lebih baru.

{{% /blocks/products/pf/agp/text %}}

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Pisahkan File PDF Tunggal menggunakan PHP" offSpacer="" %}}

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

{{% blocks/products/pf/agp/content h2="Dengan pustaka PHP kami, Anda dapat:" %}}

+ Tambahkan header & footer dokumen PDF dalam format teks atau gambar.
+ Tambahkan tabel & stempel (teks atau gambar) ke dokumen PDF.
+ Tambahkan beberapa dokumen PDF ke file yang sudah ada.
+ Bekerja dengan lampiran PDF, anotasi, & bidang formulir.
+ Terapkan enkripsi atau dekripsi ke dokumen PDF & atur kata sandi.
+ Hapus semua stempel & tabel dari halaman atau seluruh dokumen PDF.
+ Hapus stempel atau tabel tertentu dari dokumen PDF berdasarkan ID-nya.
+ Ganti satu atau beberapa instance teks pada halaman PDF atau dari seluruh dokumen.
+ Dukungan luas untuk mengonversi dokumen PDF ke berbagai format file lainnya.
+ Ekstrak berbagai elemen file PDF & optimalkan dokumen PDF.
+ Anda dapat mencoba [Aplikasi gratis](https://products.aspose.app/pdf/split-pdf) kami untuk memisahkan file PDF secara online dan menguji fungsionalitasnya.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Sumber Belajar" tabId="resources" >}}
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
