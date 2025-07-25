---
title: Hapus Teks dari PDF melalui Cloud Node.js SDK
url: nodejs/text/remove/
description: Hapus elemen teks tertentu dari PDF dengan Node.js menggunakan Aspose.PDF Cloud SDK.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Hapus Teks dari PDF dalam Node.js SDK" h2="Hapus Teks dari Dokumen PDF menggunakan Cloud Node.js SDK." logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Cara menghapus Teks dari PDF melalui Node.js SDK" %}}

Untuk menghapus teks dari PDF, kita akan menggunakan
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). SDK Cloud ini membantu programmer Node.js dalam mengembangkan aplikasi pembuat, anotator, editor, dan konverter PDF berbasis cloud menggunakan bahasa pemrograman Node.js melalui Aspose.PDF REST API. Cukup buat akun di [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) dan dapatkan informasi aplikasi Anda. Setelah Anda memiliki App SID & kunci, Anda siap menggunakan Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="Perintah Konsol Manajer Paket" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Langkah-langkah untuk menghapus Teks menggunakan Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Pengembang Aspose.PDF Cloud dapat dengan mudah memuat & menghapus Teks dari PDF hanya dalam beberapa baris kode.

{{% /blocks/products/pf/agp/text %}}

1. Muat Rahasia Aplikasi dan Kunci Anda dari file JSON atau atur kredensial dengan cara lain
1. Buat objek untuk terhubung ke Cloud API
1. Unggah file dokumen Anda
1. Lakukan penghapusan teks menggunakan fungsi pdfApi.postDocumentTextReplace
1. Unduh hasilnya jika diperlukan

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Hapus Teks dari PDF menggunakan Node.js" offSpacer="" %}}

```js

    async function () {
        const pdfApi = new PdfApi(credentials.id, credentials.key);
        try {
            const fileBuffer = await fs.readFile(LOCAL_FILE_NAME);
            await pdfApi.uploadFile(STORAGE_FILENAME, fileBuffer);
            const textReplaceList =
            {
                textReplaces:
                    [
                        { oldValue: "text", newValue: "" },
                        { oldValue: "1", newValue: "" }
                    ]
            }
            const result = await pdfApi.postDocumentTextReplace(STORAGE_FILENAME, textReplaceList);
            console.log("Status:", result.body.status);
            const downloadRes = await pdfApi.downloadFile(STORAGE_FILENAME);
            await fs.writeFile(RESULT_FILENAME, downloadRes.body);
        }
        catch (error) {
            console.error(error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Dengan alat Node.js kami Anda bisa:" %}}

+ Tambahkan header & footer dokumen PDF dalam format teks atau gambar.
+ Tambahkan tabel & cap (teks atau gambar) ke dokumen PDF.
+ Tambahkan beberapa dokumen PDF ke file yang sudah ada.
+ Bekerja dengan lampiran, anotasi, & bidang formulir PDF.
+ Terapkan enkripsi atau dekripsi pada dokumen PDF & atur kata sandi.
+ Hapus semua cap & tabel dari halaman atau seluruh dokumen PDF.
+ Hapus cap atau tabel tertentu dari dokumen PDF berdasarkan ID-nya.
+ Ganti satu atau beberapa instance teks pada halaman PDF atau dari seluruh dokumen.
+ Dukungan luas untuk mengonversi dokumen PDF ke berbagai format file lainnya.
+ Ekstrak berbagai elemen dari file PDF & optimalkan dokumen PDF.
+ Anda bisa mencoba [Aplikasi gratis kami](https://products.aspose.app/pdf/redaction) untuk mengganti teks di file PDF secara online dan menguji fungsionalitasnya.

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



