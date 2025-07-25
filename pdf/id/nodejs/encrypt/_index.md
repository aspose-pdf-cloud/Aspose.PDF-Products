---
title: Enkripsi PDF di Node.js SDK
url: nodejs/encrypt/
description: Aspose.PDF Cloud memungkinkan Anda untuk mengenkripsi Dokumen PDF. Periksa kode sumber Node.js untuk mengenkripsi file PDF.
lastmod: 2025-04-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Melindungi PDF dengan Kata Sandi di Node.js SDK" h2="API untuk mengenkripsi dokumen PDF menggunakan Cloud Node.js SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Cara Mengenkripsi PDF melalui Node.js SDK" %}}

Untuk mengenkripsi dokumen PDF, kita akan menggunakan
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). SDK Cloud ini membantu programmer Node.js dalam mengembangkan aplikasi pembuat, anotator, editor, dan konverter PDF berbasis cloud menggunakan bahasa pemrograman Node.js melalui Aspose.PDF REST API. Cukup buat akun di [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) dan dapatkan informasi aplikasi Anda. Setelah Anda memiliki App SID & key, Anda siap untuk menggunakan Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="Perintah Konsol Paket Manajer" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Langkah-langkah untuk mengenkripsi PDF melalui Cloud Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Pengembang Aspose.PDF Cloud dapat dengan mudah memuat & mengenkripsi PDF hanya dalam beberapa baris kode.

{{% /blocks/products/pf/agp/text %}}

1. Baca file PDF lokal.
1. Unggah file PDF ke penyimpanan Aspose.PDF Cloud.
1. Enkripsi di cloud menggunakan enkripsi kuat dan kata sandi.
1. Unduh hasilnya jika diperlukan.

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Mengenkripsi PDF menggunakan Node.js" offSpacer="" %}}

```js

    import credentials from "../../../Credentials/credentials.json"  with { type: "json" };    // json-file in this format: { "id": "*****", "key": "*******" }
    import fs from 'node:fs/promises';
    import path from 'node:path';
    import { PdfApi } from "../../src/api/api.js";
    import { CryptoAlgorithm } from "../../src/models/cryptoAlgorithm.js";

    const configParams = {
        LOCAL_FOLDER: "C:\\Samples\\",
        PDF_DOCUMENT_NAME: "sample.pdf",
        LOCAL_RESULT_DOCUMENT_NAME: "output_sample.pdf",
        ENCRYPT_ALGORITHM: CryptoAlgorithm.AESx256,
        USER_PASSWORD: "User-Password",
        OWNER_PASSWORD: "Owner-Password",
    };

    const pdfApi = new PdfApi(credentials.id, credentials.key);

    const pdfEncoder = {
        async uploadDocument () {
            const fileNamePath = path.join(configParams.LOCAL_FOLDER, configParams.PDF_DOCUMENT_NAME);
            const pdfFileData = await fs.readFile(fileNamePath);
            await pdfApi.uploadFile(configParams.PDF_DOCUMENT_NAME, pdfFileData)
                .then(() => console.log("File: '" + configParams.PDF_DOCUMENT_NAME +"' successfully uploaded."));
        },

        async downloadResult() {
            const changedPdfData = await pdfApi.downloadFile(configParams.PDF_DOCUMENT_NAME);
            const filePath = path.join(configParams.LOCAL_FOLDER, configParams.LOCAL_RESULT_DOCUMENT_NAME);
            await fs.writeFile(filePath, changedPdfData.body);
            console.log("Downloaded: " + filePath);
        },

        async encrypt_document() {
            const user_password_encoded = btoa(configParams.USER_PASSWORD)

            const owner_password_encoded = btoa(configParams.OWNER_PASSWORD)

            const response = await pdfApi.postEncryptDocumentInStorage(configParams.PDF_DOCUMENT_NAME, user_password_encoded, owner_password_encoded, configParams.ENCRYPT_ALGORITHM);
            
            if (response.body.code == 200)
                console.log("encrypt_document(): Document #'" + configParams.PDF_DOCUMENT_NAME + "' successfully encrypted.")
            else
                throw new Error("encrypt_document(): Failed to encrypt document #'" + configParams.PDF_DOCUMENT_NAME + "'. Response code: {" + response.code + "}")
        },
        
    }

    async function main() {
        try {
            await pdfEncoder.uploadDocument();
            await pdfEncoder.encrypt_document();
            await pdfEncoder.downloadResult();
        } catch (error) {
            console.error("Error:", error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Enkripsi PDF" %}}

Mengenkripsi dokumen PDF adalah cara sederhana namun ampuh untuk melindungi konten sensitif, memastikan privasi, dan mempertahankan kontrol atas bagaimana dokumen tersebut digunakan. Apakah Anda berbagi kontrak bisnis, laporan keuangan, atau catatan pribadi, enkripsi membantu melindungi informasi Anda dari akses yang tidak sah, perubahan, atau penyalahgunaan.

Dengan menerapkan enkripsi dan menetapkan izin yang sesuai, Anda meningkatkan keamanan dokumen, memastikan kepatuhan terhadap regulasi industri, dan membangun kepercayaan dengan audiens Anda. Di dunia digital saat ini, enkripsi PDF bukan hanya fitur—ini adalah kebutuhan untuk penanganan data yang bertanggung jawab.
Enkripsi dokumen PDF dengan [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

**Dengan library Node.js kami Anda dapat:**

+ Menambahkan header & footer dokumen PDF dalam format teks atau gambar.
+ Menambahkan tabel & stempel (teks atau gambar) ke dokumen PDF.
+ Menambahkan beberapa dokumen PDF ke file yang sudah ada.
+ Bekerja dengan lampiran PDF, anotasi, & bidang formulir.
+ Terapkan enkripsi atau dekripsi ke dokumen PDF & atur kata sandi.
+ Hapus semua stempel & tabel dari halaman atau seluruh dokumen PDF.
+ Hapus stempel atau tabel tertentu dari dokumen PDF berdasarkan ID-nya.
+ Ganti satu atau beberapa instance teks pada halaman PDF atau dari seluruh dokumen.
+ Dukungan luas untuk mengonversi dokumen PDF ke berbagai format file lainnya.
+ Ekstrak berbagai elemen file PDF & optimalkan dokumen PDF.
+ Anda dapat mencoba [Aplikasi gratis kami](https://products.aspose.app/pdf/family/) untuk menguji fungsionalitasnya secara online.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Sumber Belajar" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Dokumentasi" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Kode Sumber" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-nodejs" >}}
{{< blocks/products/pf/slr-element name="Referensi API" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Dukungan Produk" tabId="support" >}}
{{< blocks/products/pf/slr-element name="Dukungan Gratis" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="Dukungan Berbayar" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="Blog" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Mengapa Aspose.PDF Cloud untuk Node.js?" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="Daftar Pelanggan" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="Keamanan" href="https://company.aspose.cloud/legal/security" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< /blocks/products/pf/support-learning-resources >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}



