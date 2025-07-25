---
title: Hapus Tautan dari PDF melalui Cloud Node.js SDK
url: nodejs/links/delete/
description: Hapus hyperlink dari halaman PDF dengan Aspose.PDF Cloud SDK di Node.js.
lastmod: 2025-02-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Hapus Tautan dari PDF di Node.js SDK" h2="Hapus Tautan dari Dokumen PDF menggunakan Cloud Node.js SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Cara menghapus Tautan dari PDF melalui Node.js SDK" %}}

Untuk menghapus tautan dari PDF, kita akan menggunakan
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). Cloud SDK ini membantu programmer Node.js dalam mengembangkan aplikasi pembuat, anotator, editor, dan konverter PDF berbasis cloud menggunakan bahasa pemrograman Node.js melalui Aspose.PDF REST API. Cukup buat akun di [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) dan dapatkan informasi aplikasi Anda. Setelah Anda memiliki App SID & key, Anda siap menggunakan Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="Perintah Konsol Pengelola Paket" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Langkah-langkah untuk menghapus Tautan menggunakan Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Pengembang Aspose.PDF Cloud dapat dengan mudah memuat & menghapus Tautan dari PDF hanya dengan beberapa baris kode.

{{% /blocks/products/pf/agp/text %}}

1. Buat objek untuk terhubung ke API Pdf.Cloud
1. Unggah file dokumen Anda
1. Hapus Anotasi Tautan yang diperlukan dari dokumen menggunakan fungsi deleteLinkAnnotation()
1. Lakukan beberapa tindakan setelah berhasil menghapus Anotasi Tautan dari dokumen
1. Unduh hasilnya jika diperlukan

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Hapus Tautan dari PDF menggunakan Node.js" offSpacer="" %}}

```js

    import credentials from "./credentials.json"  with { type: "json" };    // json-file in this format: { "id": "*****", "key": "*******" }
    import fs from 'node:fs/promises';
    import path from 'node:path';
    import { PdfApi } from "asposepdfcloud";

    const configParams = {
        LOCAL_FOLDER: "C:\\Samples\\",
        PDF_DOCUMENT_NAME: "sample.pdf",
        LOCAL_RESULT_DOCUMENT_NAME: "output_sample.pdf",
        LINK_REMOVE_ID: "GI5UO32UN5KVESKBMN2GS33OHMZTEMJMGUYDQLBTGYYCYNJSGE",
        PAGE_NUMBER: 2,     // Your document page number...
    };

    const pdfApi = new PdfApi(credentials.id, credentials.key);

    const pdfLinks = {
    async uploadDocument() {
            const pdfFilePath = path.join(configParams.LOCAL_FOLDER, configParams.PDF_DOCUMENT_NAME);
            const pdfFileData = await fs.readFile(pdfFilePath);
            await pdfApi.uploadFile(configParams.PDF_DOCUMENT_NAME, pdfFileData);
        },
        
        async downloadResult() {
            const changedPdfData = await pdfApi.downloadFile(configParams.PDF_DOCUMENT_NAME);
            const filePath = path.join(configParams.LOCAL_FOLDER, configParams.LOCAL_RESULT_DOCUMENT_NAME);
            await fs.writeFile(filePath, changedPdfData.body);
            console.log("Downloaded: " + filePath);
        },

        removeLink: async function () {
            const resultDelete = await pdfApi.deleteLinkAnnotation(configParams.PDF_DOCUMENT_NAME, configParams.LINK_REMOVE_ID);

            if (resultDelete.body.code == 200) {
                console.log("Link '" + configParams.LINK_REMOVE_ID + "' was deleted!");
                return ;
            }
            else
                throw new Error("Unexpected error : can't get link !!!");
        }

    }

    async function main() {
        try {
            await pdfLinks.uploadDocument();
            await pdfLinks.removeLink();
            await pdfLinks.downloadResult();
        } catch (error) {
            console.error("Error:", error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Bekerja dengan Tautan dalam PDF" %}}

Seiring waktu, hyperlink dapat menjadi usang atau mengarah ke halaman yang tidak lagi ada. Tautan rusak semacam itu dapat membuat frustrasi pembaca dan mengurangi kredibilitas dokumen. Menghapus ini memastikan konten tetap akurat dan andal.
Hapus Tautan dari dokumen PDF dengan [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

**Dengan pustaka Node.js kami Anda dapat:**

+ Menambahkan header & footer dokumen PDF dalam format teks atau gambar.
+ Menambahkan tabel & stempel (teks atau gambar) ke dokumen PDF.
+ Menambahkan beberapa dokumen PDF ke file yang sudah ada.
+ Bekerja dengan lampiran PDF, anotasi, & bidang formulir.
+ Menerapkan enkripsi atau dekripsi ke dokumen PDF & menetapkan kata sandi.
+ Hapus semua stempel & tabel dari halaman atau seluruh dokumen PDF.
+ Hapus stempel atau tabel tertentu dari dokumen PDF berdasarkan ID-nya.
+ Ganti satu atau beberapa instance teks pada halaman PDF atau dari seluruh dokumen.
+ Dukungan luas untuk mengonversi dokumen PDF ke berbagai format file lainnya.
+ Ekstrak berbagai elemen file PDF & optimalkan dokumen PDF.
+ Anda dapat mencoba [Aplikasi gratis kami](https://products.aspose.app/pdf/family) untuk menguji fungsionalitas secara online.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Sumber Daya Pembelajaran" tabId="resources" >}}
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



