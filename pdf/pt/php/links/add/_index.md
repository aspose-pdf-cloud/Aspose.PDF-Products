---
title: Adicionar Links a PDF via Cloud PHP SDK
url: php/links/add/
description: Adicione hyperlinks a documentos PDF usando PHP e o Aspose.PDF Cloud SDK. Torne o conteúdo interativo.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Adicionar Links a PDF no PHP SDK" h2="Adicionar Links em documentos PDF usando Cloud PHP SDK." logoImageSrc="/sdk/aspose_pdf-for-php.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="para PHP" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK para PHP" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="/sdk/aspose_pdf-for-php.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/php/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="https://reference.aspose.cloud/pdf/" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="Como adicionar Links a PDF via Cloud PHP SDK" %}}

Para adicionar Links ao PDF, usaremos
[Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/)
Este Cloud SDK auxilia programadores PHP no desenvolvimento de aplicativos criadores, anotadores, editores e conversores de PDF baseados em nuvem, usando a linguagem de programação PHP via Aspose.PDF REST API. Simplesmente crie uma conta no [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) e obtenha suas informações de aplicativo. Uma vez que você tenha o App SID & chave, estará pronto para usar o Aspose.PDF Cloud PHP SDK.

{{% blocks/products/pf/agp/code-block title="Comando do Console do Gerenciador de Pacotes" offSpacer="true" %}}

```bash
     
    composer install

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Passos para adicionar Links a PDF via Cloud PHP" %}}

{{% blocks/products/pf/agp/text %}}

Desenvolvedores do Aspose.PDF Cloud podem facilmente carregar & adicionar Links a PDF em apenas algumas linhas de código.

{{% /blocks/products/pf/agp/text %}}

1. Carregar um Documento PDF
1. Baixar o PDF Processado
1. Anexar um hyperlink clicável a uma página PDF

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Adicionar Links a PDF usando PHP" offSpacer="" %}}

```php

    private function _create_rest_api() {
        $credentials = json_decode(file_get_contents("./Credentials/credentials.json"), true);

        $configAuth = new Configuration();
        $configAuth->setAppKey($credentials['key']);
        $configAuth->setAppSid($credentials['id']);

        $this->pdfApi = new PdfApi(null, $configAuth);
     }

    public function __construct($config) {
        $this->configParams = $config;
        $this->_create_rest_api();
    }

    public function uploadDocument() {
        $pdfFilePath = $this->configParams['LOCAL_FOLDER'] . $this->configParams['PDF_DOCUMENT_NAME'];
        $pdfFileData = file_get_contents($pdfFilePath);
        $this->pdfApi->uploadFile($this->configParams['PDF_DOCUMENT_NAME'], $pdfFileData);
    }

    public function downloadResult() {
        $changedPdfData = $this->pdfApi->downloadFile($this->configParams['PDF_DOCUMENT_NAME']);
        $filePath = $this->configParams['LOCAL_FOLDER'] . $this->configParams['LOCAL_RESULT_DOCUMENT_NAME'];
        file_put_contents($filePath, $changedPdfData);
        echo "Downloaded: " . $filePath . "\n";
    }

    public function appendLinkOnPage() {
        $linkColor = new Color(['a' => 255, 'r' => 0, 'g' => 255, 'b' => 0]);

        $linkRectangle = new Rectangle();
        $linkRectangle->setLLX($this->configParams['LINK_POS_LLX']);
        $linkRectangle->setLLY($this->configParams['LINK_POS_LLY']);
        $linkRectangle->setURX($this->configParams['LINK_POS_URX']);
        $linkRectangle->setURY($this->configParams['LINK_POS_URY']);

        $linkItem = new Link(['rel' => "self"]);

        $newLink = new LinkAnnotation();
        $newLink->setLinks([$linkItem]);
        $newLink->setActionType(LinkActionType::GO_TO_URI_ACTION);
        $newLink->setAction($this->configParams['NEW_LINK_ACTION']);
        $newLink->setHighlighting(LinkHighlightingMode::INVERT);
        $newLink->setColor($linkColor);
        $newLink->setRect($linkRectangle);

        $addResponse = $this->pdfApi->postPageLinkAnnotations($this->configParams['PDF_DOCUMENT_NAME'], $this->configParams['PAGE_NUMBER'], [$newLink]);

        if ($addResponse->getCode() == 200) {
            echo "Append link successful!\n";
            return true;
        }
    }

function main() {
    global $configParams;

    try {
        $pdfLinks = new PdfLinks($configParams);
        $pdfLinks->uploadDocument();
        $pdfLinks->appendLinkOnPage();
        $pdfLinks->downloadResult();
    } catch (\Exception $e) {
        echo "Error: " . $e->getMessage() . "\n";
    }
}
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Trabalhar com Links em PDF" %}}

Adicionar links a um PDF melhora a usabilidade, interatividade e acessibilidade. Seja para navegação, marketing ou referências cruzadas, hyperlinks melhoram a eficácia do documento, tornando mais fácil para os usuários encontrarem conteúdo relevante e agirem.
Adicione os links aos documentos PDF com [Aspose.PDF Cloud PHP SDK](https://products.aspose.cloud/pdf/php/).

**Com nossa biblioteca PHP você pode:**

+ Adicionar cabeçalho & rodapé do documento PDF em formato de texto ou imagem.
+ Adicionar tabelas & carimbos (texto ou imagem) a documentos PDF.
+ Anexar múltiplos documentos PDF a um arquivo existente.
+ Trabalhar com anexos, anotações & campos de formulário em PDF.
+ Aplicar criptografia ou descriptografia a documentos PDF & definir uma senha.
+ Excluir todos os carimbos & tabelas de uma página ou de todo o documento PDF.
+ Excluir um carimbo ou tabela específico do documento PDF pelo seu ID.
+ Substituir uma ou múltiplas instâncias de texto em uma página PDF ou em todo o documento.
+ Suporte extensivo para converter documentos PDF para vários outros formatos de arquivo.
+ Extrair vários elementos de arquivos PDF & otimizar documentos PDF.
+ Você pode experimentar nosso [App gratuito](https://products.aspose.app/pdf/family) para testar a funcionalidade online.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Recursos de Aprendizado" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Documentação" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Código Fonte" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-php" >}}
{{< blocks/products/pf/slr-element name="Referências da API" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Suporte ao Produto" tabId="support" >}}
{{< blocks/products/pf/slr-element name="Suporte Gratuito" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="Suporte Pago" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="Blog" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Por que Aspose.PDF Cloud para PHP?" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="Lista de Clientes" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="Segurança" href="https://company.aspose.cloud/legal/security" >}}
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
