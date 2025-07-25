---
title: Обновление полей формы в PDF-документе с помощью облачного .NET SDK
url: net/acroforms/update/
description: Обновляйте существующие полях AcroForm в PDF-файлах с помощью облачного SDK для .NET Aspose.PDF. Быстрое, точное и гибкое управление формами.
lastmod: 2022-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Обновление PDF-форм в .NET SDK" h2="Обновляйте все поля формы из PDF-документа с помощью Aspose.PDF Cloud .NET API" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK для .NET" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-net.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-words-cloud-dotnet" >}}

{{% blocks/products/pf/agp/content h2="Как обновить поля формы в PDF-документе с помощью облачного .NET SDK" %}}

Чтобы обновить AcroForm с помощью облачного .NET SDK, мы будем использовать
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
Этот облачный SDK позволяет вам легко создавать облачные приложения для создания, редактирования и преобразования PDF на C#, ASP.NET или других языках .NET для различных облачных платформ. Откройте
[NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
диспетчер пакетов, найдите
Aspose.PDF Cloud
и установите. Вы также можете использовать следующую команду из консоли диспетчера пакетов.

{{% blocks/products/pf/agp/code-block title="Команда консоли диспетчера пакетов" offSpacer="true" %}}

```powershell

     
    PM> Install-Package Aspose.Pdf-Cloud
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Етапы обновления AcroForms с помощью .NET SDK" %}}

{{% blocks/products/pf/agp/text %}}

Разработчики Aspose.PDF Cloud могут легко загружать и обновлять acroforms в PDF всего несколькими строками кода.

{{% /blocks/products/pf/agp/text %}}

1. Создайте новый объект Configuration с вашим Application Secret и Key
1. Создайте объект для подключения к Cloud API
1. Загрузите ваш документ-файл
1. Выполните обновление
1. Скачайте результат

{{% /blocks/products/pf/agp/feature-section-col %}}



{{% blocks/products/pf/agp/code-block title="Этот пример кода показывает обновление AcroForms в PDF-документах" offSpacer="" %}}

```cs

    public static void UpdateFormFields()
    {
        const string localImageFileName = @"C:\Samples\StudentInfoFormElectronic.pdf";
        const string storageFileName = "StudentInfoFormElectronic.pdf";
        // Get your AppSid and AppSecret from https://dashboard.aspose.cloud (free registration required).            
        var pdfApi = new PdfApi(AppSecret, AppSid);
        var filesOnStorage = pdfApi.GetFilesList("");
        if (filesOnStorage.Value.All(f => f.Name != storageFileName))
        {
            using var file = File.OpenRead(localImageFileName);
            var uploadResult = pdfApi.UploadFile(storageFileName, file);
            Console.WriteLine(uploadResult.Uploaded[0]);
        }
        var fieldList = new List<Field>
        {
            new Field(
                    Name: "First Name",
                    Type: FieldType.Text,
                    Values: ["James"],
                    Rect: new Rectangle(125, 735, 200, 752))
        };

        var fields = new Fields(List: fieldList);

        var response = pdfApi.PutUpdateFields(storageFileName, fields);
        Console.WriteLine(response.Status);
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

