---
title: Замена таблиц в PDF через Cloud Python SDK
url: python/table/replace/
description: Заменяйте данные таблиц PDF программно на Python с помощью Aspose.PDF Cloud SDK.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Замена таблицы в PDF в Python SDK" h2="Замена таблиц в документе PDF с использованием Cloud Python SDK." logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="Как заменить таблицы в PDF через Cloud Python SDK" %}}

Чтобы заменить таблицы в PDF, мы будем использовать
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/). Этот Cloud SDK помогает программистам на Python разрабатывать облачные приложения для создания, аннотирования, редактирования и конвертации PDF, используя язык программирования Python через Aspose.PDF REST API. Просто создайте аккаунт на [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) и получите информацию о вашем приложении. Как только у вас будут App SID и ключ, вы готовы использовать Aspose.PDF Cloud Python SDK. Если пакет python размещен на Github, вы можете установить его напрямую с Github:

{{% blocks/products/pf/agp/code-block title="Установка с Github" offSpacer="true" %}}

```bash

     
    pip install git+https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python.git


```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/code-block title="Команда консоли диспетчера пакетов" offSpacer="true" %}}

```bash
     
    pip install asposepdfcloud

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Шаги по замене таблиц в PDF через Python SDK" %}}

{{% blocks/products/pf/agp/text %}}

Разработчики Aspose.PDF Cloud могут легко загружать и заменять таблицы в PDF всего несколькими строками кода.

{{% /blocks/products/pf/agp/text %}}

1. Установите [Python SDK](https://pypi.org/project/asposepdfcloud/)
1. Загрузите PDF документ на сервер Aspose Cloud
1. Скачайте обработанный PDF документ с сервера Aspose Cloud
1. Замените таблицу на странице PDF документа

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Замена таблиц в PDF с использованием Python" offSpacer="" %}}

```python

    import shutil
    import shutil
    import json
    import logging
    from pathlib import Path
    from asposepdfcloud import ApiClient, PdfApi, Table, Row, Cell, FontStyles, GraphInfo, TextRect, TextState, Color, BorderInfo
    # Configure logging
    logging.basicConfig(level=logging.INFO, format="%(asctime)s - %(levelname)s - %(message)s")

    class Config:
        """Configuration parameters."""
        CREDENTIALS_FILE = Path(r"C:\\Projects\\ASPOSE\\Pdf.Cloud\\Credentials\\credentials.json")
        LOCAL_FOLDER = Path(r"C:\Samples")
        PDF_DOCUMENT_NAME = "sample.pdf"
        LOCAL_RESULT_DOCUMENT_NAME = "output_sample.pdf"
        TABLE_ID = "GE5TCOZSGAYCYNRQGUWDINZVFQ3DGMA"

    class PdfTables:
        """ Class for managing PDF tables using Aspose PDF Cloud API. """
        def __init__(self, credentials_file: Path = Config.CREDENTIALS_FILE):
            self.pdf_api = None
            self._init_api(credentials_file)

        def _init_api(self, credentials_file: Path):
            """ Initialize the API client. """
            try:
                with credentials_file.open("r", encoding="utf-8") as file:
                    credentials = json.load(file)
                    api_key, app_id = credentials.get("key"), credentials.get("id")
                    if not api_key or not app_id:
                        raise ValueError("init_api(): Error: Missing API keys in the credentials file.")
                    self.pdf_api = PdfApi(ApiClient(api_key, app_id))
            except (FileNotFoundError, json.JSONDecodeError, ValueError) as e:
                logging.error(f"init_api(): Failed to load credentials: {e}")

        def upload_document(self):
            """ Upload a PDF document to the Aspose Cloud server. """
            if self.pdf_api:
                file_path = Config.LOCAL_FOLDER / Config.PDF_DOCUMENT_NAME
                try:
                    self.pdf_api.upload_file(Config.PDF_DOCUMENT_NAME, str(file_path))
                    logging.info(f"upload_document(): File {Config.PDF_DOCUMENT_NAME} uploaded successfully.")
                except Exception as e:
                    logging.error(f"upload_document(): Failed to upload file: {e}")

        def download_result(self):
            """ Download the processed PDF document from the Aspose Cloud server. """
            if self.pdf_api:
                try:
                    temp_file = self.pdf_api.download_file(Config.PDF_DOCUMENT_NAME)
                    local_path = Config.LOCAL_FOLDER / Config.LOCAL_RESULT_DOCUMENT_NAME
                    shutil.move(temp_file, str(local_path))
                    logging.info(f"download_result(): File successfully downloaded: {local_path}")
                except Exception as e:
                    logging.error(f"download_result(): Failed to download file: {e}")

        def _init_table (self):
            """ Initialize new table """
            num_of_cols = 5
            num_of_rows = 5

            header_text_state = TextState(
                font = "Arial Bold",
                font_size = 11,
                foreground_color = Color( a = 255, r = 255, g = 255, b = 255 ),
                font_style = FontStyles.BOLD,
            )

            common_text_state = TextState (
                font = "Arial Bold",
                font_size = 11,
                foreground_color = Color( a=255, r = 112, g = 112, b = 112 ),
                font_style=FontStyles.REGULAR
            )
        
            col_widths = ""
            for col_index in range(0,num_of_cols):
                col_widths += " 70"

            table_rows = []
    
            border_table_border = GraphInfo(
                color = Color(a = 255, r = 0, g = 255, b = 0 ),
                line_width = 0.5
            )
        
            for row_index in range(0, num_of_rows):
                row_cells = []
        
                for col_index in range(0, num_of_cols):
                    cell = Cell( default_cell_text_state = common_text_state)

                    if row_index == 0:  # header cells
                        cell.background_color = Color(a = 255, r = 128, g = 128, b=128)
                        cell.default_cell_text_state = header_text_state
                    else:
                        cell.background_color = Color(a =255, r =255, g =255, b =255)
                
                    text_rect = TextRect()
                    if row_index == 0:
                        text_rect.text = f"header #{col_index}"
                    else:
                        text_rect.text = f"value '({row_index},{col_index})'"
                    cell.paragraphs = [ text_rect]

                    row_cells.append(cell)

                row = Row(cells=row_cells)

                table_rows.append(row)

            table = Table(left=150,top=250, column_widths=col_widths, rows=table_rows)
            
            table.default_cell_border = BorderInfo(
                top = border_table_border,
                right = border_table_border,
                bottom = border_table_border,
                left = border_table_border,
                rounded_border_radius = 2
            )

            return table
        
        def replace_table (self):
            """ Replace table in the PDF document page. """
            if self.pdf_api:
                try:
                    new_table = self._init_table()

                    resultTabs = self.pdf_api.put_table( Config.PDF_DOCUMENT_NAME, Config.TABLE_ID, new_table)

                    if resultTabs.code == 200:
                        logging.info(f"replace_table(): Table #'{Config.TABLE_ID}' was replaced in the document '{Config.PDF_DOCUMENT_NAME}'.")
                    else:
                        logging.error(f"replace_table(): Failed to replace table in the document '{Config.PDF_DOCUMENT_NAME}'.")
                except Exception as e:
                    logging.error(f"replace_table(): Failed to append table: {e}")


    if __name__ == "__main__":
        pdf_tables = PdfTables()
        pdf_tables.upload_document()
        pdf_tables.replace_table()
        pdf_tables.download_result()
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Работа с таблицами в PDF" %}}

Таблицы предоставляют структурированный формат для систематического представления данных, что облегчает читателям понимание и анализ информации. Они также улучшают визуальную привлекательность документа, добавляя профессионализм и организованность. При работе с числовыми или сравнительными данными таблицы улучшают ясность, группируя связанную информацию в легкодоступный формат. Кроме того, таблицы могут включать в себя данные в реальном времени или динамически генерируемые данные, такие как данные из баз данных или аналитических панелей.
Замените таблицу в документах PDF с [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/).

**С нашей библиотекой для Python вы можете:**

+ Объединять PDF документы.
+ Разделять PDF файлы.
+ Конвертировать PDF в другие форматы и наоборот.
+ Манипулировать аннотациями.
+ Работать с изображениями в PDF и т.д.
+ Вы можете попробовать наше [бесплатное приложение](https://products.aspose.app/pdf/family) для тестирования функциональности онлайн.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
