---
title: Установить поля формы PDF-документа через облачный .NET SDK
url: net/acroforms/set/
description: Установите поля AcroForm в PDF-документах с помощью облачного SDK Aspose.PDF для .NET. Легко автоматизируйте создание интерактивных форм.
lastmod: 2022-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Установка PDF-форм в .NET SDK" h2="Создавайте собственные облачные приложения для установки заполняемых документов с помощью серверных API." logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK для .NET" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-net.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-words-cloud-dotnet" >}}

{{% blocks/products/pf/agp/content h2="Как установить поля формы PDF-документа с помощью облачного .NET SDK" %}}

Чтобы установить AcroForm с помощью облачного .NET SDK, мы будем использовать
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
Этот облачный SDK позволяет легко создавать облачные приложения для создания, редактирования и конвертирования PDF-файлов на C#, ASP.NET или других языках .NET для различных облачных платформ. Откройте
[NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
менеджер пакетов, найдите
Aspose.PDF Cloud
и установите. Вы также можете использовать следующую команду из консоли Package Manager.

{{% blocks/products/pf/agp/code-block title="Команда Package Manager Console" offSpacer="true" %}}

```powershell

     
    PM> Install-Package Aspose.Pdf-Cloud
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Шаги по установке AcroForms с помощью .NET SDK" %}}

{{% blocks/products/pf/agp/text %}}

Разработчики Aspose.PDF Cloud могут легко загрузить и установить acroforms в PDF-файл всего за несколько строк кода.

{{% /blocks/products/pf/agp/text %}}

1. Создайте новый объект Configuration с вашим Application Secret и Key
1. Создайте объект для подключения к облачному API
1. Загрузите файл вашего документа
1. Выполните установку
1. Скачайте результат

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/feature-section-col title="Требования системы" %}}

{{% blocks/products/pf/agp/text %}}

Легко начать работу с Aspose.PDF Cloud .NET SDK, и установить ничего не нужно. Просто создайте учетную запись на Aspose для Cloud и задайте информацию о вашем приложении. Как только у вас будет App SID и ключ, вы готовы к использованию Aspose.PDF Cloud .NET SDK.

* .NET Framework 2.0 или новее
* JSON.NET

{{% /blocks/products/pf/agp/text %}}

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Этот пример кода демонстрирует установку AcroForms в PDF-документах" offSpacer="" %}}

```cs

    public static void SetFormField()
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

        var response = pdfApi.PutUpdateField(storageFileName, "First Name", new Field(
            Name: "First Name",
            Type: FieldType.Text,
            Values: ["James"],
            Rect: new Rectangle(125, 735, 200, 752)
        ));
        Console.WriteLine(response.Status);
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

