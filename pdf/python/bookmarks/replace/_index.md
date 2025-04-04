---
title: Replace Bookmarks in PDF via Cloud Python SDK 
url: /python/bookmarks/replace/
description: Aspose.PDF Cloud allows you to replace a Bookmarks in PDF Document. Check the Python source code to replace a Bookmarks in PDF file.
lastmod: "2024-10-19"
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Replace Bookmarks in PDF document via Cloud Python SDK" h2="API for working with Bookmarks in PDF documents using Cloud Python SDK." logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="How to Replace Bookmarks in PDF via Cloud Python SDK " %}}

To replace Bookmarks from PDF, we'll use [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/). This Cloud SDK assists Python programmers in developing cloud-based PDF creator, annotator, editor, and converter apps using Python programming language via Aspose.PDF REST API. Simply create an account at [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) and get your application information. Once you have the App SID & key, you are ready to give the Aspose.PDF Cloud Python SDK. If the python package is hosted on Github, you can install directly from Github:

{{% blocks/products/pf/agp/code-block title="Installation from Github" offSpacer="true" %}}

```bash

     
    pip install git+https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python.git


```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/code-block title="Package Manager Console Command" offSpacer="true" %}}

```bash
     
    pip install asposepdfcloud

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Steps to replace Bookmarks in PDF via Python" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud developers can easily load & replace Bookmarks from PDF in just a few lines of code.

{{% /blocks/products/pf/agp/text %}}

1. Install [Python SDK](https://pypi.org/project/asposepdfcloud/)
1. Upload a PDF document to the Aspose Cloud server
1. Download the processed PDF document from the Aspose Cloud server
1. Replace bookmark in PDF document

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/feature-section-col title="System Requirements" %}}

{{% blocks/products/pf/agp/text %}}

It is easy to get started with Aspose.PDF Cloud Python SDK and there is nothing to install. Simply create an account at Aspose for Cloud and get your application information. Once you have the App SID & key, you are ready to give the Aspose.PDF Cloud Python SDK.

+ Python 2.7 and 3.4+

{{% /blocks/products/pf/agp/text %}}

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Replace Bookmarks from PDF using Python" offSpacer="" %}}

```python

    import shutil
    import json
    import logging
    from pathlib import Path
    from asposepdfcloud import ApiClient, PdfApi, Bookmark, BookmarksResponse, BookmarkResponse

    class Config:
        """Configuration parameters."""
        CREDENTIALS_FILE = Path(r"C:\\Projects\\ASPOSE\\Pdf.Cloud\\Credentials\\credentials.json")
        LOCAL_FOLDER = Path(r"C:\\Samples")
        PDF_DOCUMENT_NAME = "sample.pdf"
        LOCAL_RESULT_DOCUMENT_NAME = "output_sample.pdf"
        NEW_BOOKMARK_TITLE = "• Increased performance." #"• Productivity improvement"
        BOOKMARK_PATH = "/5"
        NEW_BOOKMARK_PAGE_NUMBER = 3

    # Configure logging
    logging.basicConfig(level=logging.INFO, format="%(asctime)s - %(levelname)s - %(message)s")

    class PdfBookmarks:
        """Class for managing PDF bookmarkss using Aspose PDF Cloud API."""

        def __init__(self, credentials_file: Path = Config.CREDENTIALS_FILE):
            self.pdf_api = None
            self._init_api(credentials_file)

        def _init_api(self, credentials_file: Path):
            """Initialize the API client."""
            try:
                with credentials_file.open("r", encoding="utf-8") as file:
                    credentials = json.load(file)
                    api_key, app_id = credentials.get("key"), credentials.get("id")
                    if not api_key or not app_id:
                        raise ValueError("Error: Missing API keys in the credentials file.")
                    self.pdf_api = PdfApi(ApiClient(api_key, app_id))
            except (FileNotFoundError, json.JSONDecodeError, ValueError) as e:
                logging.error(f"Failed to load credentials: {e}")

        def upload_document(self):
            """Upload a PDF document to the Aspose Cloud server."""
            if self.pdf_api:
                file_path = Config.LOCAL_FOLDER / Config.PDF_DOCUMENT_NAME
                try:
                    self.pdf_api.upload_file(Config.PDF_DOCUMENT_NAME, str(file_path))
                    logging.info(f"File {Config.PDF_DOCUMENT_NAME} uploaded successfully.")
                except Exception as e:
                    logging.error(f"Failed to upload file: {e}")

        def download_result(self):
            """Download the processed PDF document from the Aspose Cloud server."""
            if self.pdf_api:
                try:
                    temp_file = self.pdf_api.download_file(Config.PDF_DOCUMENT_NAME)
                    local_path = Config.LOCAL_FOLDER / Config.LOCAL_RESULT_DOCUMENT_NAME
                    shutil.move(temp_file, str(local_path))
                    logging.info(f"download_result(): File successfully downloaded: {local_path}")
                except Exception as e:
                    logging.error(f"download_result(): Failed to download file: {e}")

        def show_bookmarks_array(self, bookmarks, prefix):
            for item in bookmarks.list:
                logging.info(f"{prefix} => level: '{item.level}' - action: '{item.action}' - title: '{item.title}'")
                if item.bookmarks and item.bookmarks.list and item.bookmarks.list.length > 0:
                    self.show_bookmarks_array(bookmarks=item.bookmarks, prefix=prefix)

        def get_all_bookmarks(self):
            """Get all bookmarks for a specific PDF document."""    
            if self.pdf_api:
                try:
                    response : BookmarksResponse = self.pdf_api.get_document_bookmarks( Config.PDF_DOCUMENT_NAME)
                    if response.code == 200:
                        self.show_bookmarks_array(response.bookmarks, "All")
                    else:
                        logging.error(f"Failed to get bookmarks for the document. Response code: {response.code}")
                except Exception as e:
                    logging.error(f"Error while retrieving bookmarks array: {e}")

        def get_bookmark(self):
            """Get bookmark for a specific PDF document using bookmark path."""    
            if self.pdf_api:
                try:
                    response : BookmarkResponse = self.pdf_api.get_bookmark( Config.PDF_DOCUMENT_NAME, Config.BOOKMARK_PATH)
                    if response.code == 200:
                        logging.info(f"Found bookmark => level: '{response.bookmark.level}' - action: '{response.bookmark.action}' - title: '{response.bookmark.title}'")
                        return response.bookmark
                    else:
                        logging.error(f"Failed to find bookmark for the document. Response code: {response.code}")
                        return None
                except Exception as e:
                    logging.error(f"Error while find bookmark: {e}")

        def replace_bookmark(self):
            if self.pdf_api:
                _bookmark: BookmarkResponse = self.get_bookmark()

                if not _bookmark:
                    return

                _bookmark.title = Config.NEW_BOOKMARK_TITLE

                response: BookmarkResponse = self.pdf_api.put_bookmark(
                    Config.PDF_DOCUMENT_NAME,
                    Config.BOOKMARK_PATH,
                    bookmark=_bookmark,
                )

                if response.code == 200:
                    print("Bookmark replaced successfully.")
                else:
                    print("Failed to replace Bookmark.")


    if __name__ == "__main__":
        pdf_bookmarks = PdfBookmarks()
        pdf_bookmarks.upload_document()
        pdf_bookmarks.get_all_bookmarks()
        pdf_bookmarks.replace_bookmark()
        pdf_bookmarks.download_result()
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="With our Python library you can:" %}}

Replace the Bookmarks from PDF documents with [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/).

+ Combine PDF documents.
+ Split PDF Files.
+ Convert PDF to other formats, and vice versa.
+ Manipulate Annotations.
+ Work with Images in PDF, etc.
+ You can try out our [free Apps](https://products.aspose.app/pdf/family/) to test the functionality online.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

<!-- aboutfile Starts -->

{{% blocks/products/pf/agp/content h2="About Aspose.PDF Cloud Python SDK" %}}

A PDF Processing Library to create cross-platform applications with the ability to generate, modify, convert, render, secure and print documents without using Adobe Acrobat. Python PDF API offers compression, table creation, graph & image functions, hyperlinks, stamp and watermarking tasks, extended security controls & custom font handling.

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/about-file-section >}}

{{< blocks/products/pf/agp/demobox sectionTitle="Aspose.PDF No Code Online App" sectionDescription="For testing our functionality visit the [Live Demos website](https://products.aspose.app/pdf/family/). The live demo has the following benefits" >}}

{{< blocks/products/pf/agp/democard icon="fa-cogs" text=" No need to download or setup anything" >}}
{{< blocks/products/pf/agp/democard icon="fa-edit" text=" No need to write any code" >}}
{{< blocks/products/pf/agp/democard icon="fa-file-text" text="Click the button. Your PDF files will be uploaded and will be added." >}}
{{< blocks/products/pf/agp/democard icon="fa-download" text=" Instantly get the download link for the resultant file" >}}

{{< blocks/products/pf/agp/about-file-text fileFormat="PDF" readMoreLink="https://docs.fileformat.com/view/pdf/" >}}
Portable Document Format (PDF) is a type of document created by Adobe back in 1990s. The purpose of this file format was to introduce a standard for representation of documents and other reference material in a format that is independent of application software, hardware as well as Operating System. PDF files can be opened in Adobe Acrobat Reader/Writer as well in most modern browsers like Chrome, Safari, Firefox via extensions/plug-ins. Most of the commercially available software suites also offer conversion of their documents to PDF file format without the requirement of any additional software component. Thus, PDF file format has full capability to contain information like text, images, hyperlinks, form-fields, rich media, digital signatures, attachments, metadata, Geospatial features and 3D objects in it that can become as part of source document.

{{< /blocks/products/pf/agp/about-file-text >}}

{{< /blocks/products/pf/agp/about-file-section >}}

{{< /blocks/products/pf/agp/demobox >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}