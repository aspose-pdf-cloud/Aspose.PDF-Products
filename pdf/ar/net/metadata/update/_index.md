---
title: تحديث بيانات Dublin Core في مستند PDF عبر Cloud .NET SDK
url: net/metadata/update/
description: تحديث بيانات Dublin Core لبث PDF عبر Cloud SDK للمنتجاتργماغانية الدعم Moreover، تعديلاياامNotes يمكن أن يكون men can الانتظامّ
lastmod: 2022-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="تحديث بيانات Dublin Core في PDF من خلال Cloud .NET SDK" h2="تحديث كل ما يتعلق ببيانات Dublin Core مستند PDF ب Cloud .NET API" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for .NET" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-net.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-words-cloud-dotnet" >}}

{{% blocks/products/pf/agp/content h2="كيفية تحديث بيانات Dublin Core PDF من خلال Cloud .NET SDK" %}}

في سبيل تحديث البيانات عبر Cloud .NET SDK، سنستخدم
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
هذا السحب لكي يتسنى لك:hover nonce easily وثائق PDF التحديث-editor & التحويل التطبيقات في C#،غطاء.NET أو لغات أخرى .NET للأبعاد المختلفة constitutes. 
[NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
manager، بحث عن
Aspose.PDF Cloud
مقابل. يمكنك أيضًا استخدام الأمر التالي من Console Manager.

{{% blocks/products/pf/agp/code-block title="Package Manager Console Command" offSpacer="true" %}}

```powershell

     
    PM> Install-Package Aspose.Pdf-Cloud
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="خطوات تحديث بيانات Dublin Core من خلال .NET SDK" %}}

{{% blocks/products/pf/agp/text %}}

المطورون Aspose.PDF Cloud يمكنهم بسهولة تحميل & تحديث بيانات Dublin Core في PDF في سطور ثنائية كما يمكن عرضامياللهيب.

{{% /blocks/products/pf/agp/text %}}

1. إنشاء غمضة ببيانك Application Secret و Key
1. إنشاء حادث إرساء التعضاء بال Cloud API
1. تحميل الوثيقة معالايها
1. تحديث الخصائص عبر PutSetProperty
1. علاج الخصائص، على غرار طابع حبر الانطباع

{{% /blocks/products/pf/agp/feature-section-col %}}



{{% blocks/products/pf/agp/code-block title="إ Jeux current code ويظهر تحديث البيانات في PDF الوثائق " offSpacer="" %}}

```cs

    public static void UpdateMetadata()
    {
        const string localImageFileName = @"C:\Samples\sample.pdf";
        const string storageFileName = "sample.pdf";


        // Get your AppSid and AppSecret https://dashboard.aspose.cloud (free registration required).
        var pdfApi = new PdfApi(AppSecret, AppSid);

        using var file = File.OpenRead(localImageFileName);
        var uploadResult = pdfApi.UploadFile(storageFileName, file);
        Console.WriteLine(uploadResult.Uploaded[0]);
        var response = pdfApi.GetDocumentProperty(storageFileName, "xmp:ArchiveType");
        if (response.DocumentProperty.Value != null && !response.DocumentProperty.Value.StartsWith("Aspose"))
        {
            var responseSet = pdfApi.PutSetProperty(storageFileName, "xmp:ArchiveType", "Aspose Sample Document");
            Console.WriteLine(responseSet.Status);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

