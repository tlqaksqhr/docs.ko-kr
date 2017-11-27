---
title: "Styles2 사용 된 WordprocessingML 문서"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a9136e4d-c368-4661-8049-7d45c679a236
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ac833daca2e4ba12d61a1ee3c9526b7368baee74
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="wordprocessingml-document-with-styles"></a><span data-ttu-id="88deb-102">스타일이 사용된 WordprocessingML 문서</span><span class="sxs-lookup"><span data-stu-id="88deb-102">WordprocessingML Document with Styles</span></span>
<span data-ttu-id="88deb-103">더 복잡한 WordprocessingML 문서에는 스타일로 서식이 지정된 단락이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88deb-103">More complicated WordprocessingML documents have paragraphs that are formatted with styles.</span></span>  
  
 <span data-ttu-id="88deb-104">WordprocessingML 문서의 구성에 대한 몇 가지 정보를 알아 두면 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="88deb-104">A few notes about the makeup of WordprocessingML documents are helpful.</span></span> <span data-ttu-id="88deb-105">WordprocessingML 문서는 패키지로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="88deb-105">WordprocessingML documents are stored in packages.</span></span> <span data-ttu-id="88deb-106">패키지에는 여러 부분이 있습니다. 부분은 패키지의 컨텍스트에서 사용될 때 명시적 의미를 갖습니다. 부분은 패키지를 구성하기 위해 함께 압축된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="88deb-106">Packages have multiple parts (parts have an explicit meaning when used in the context of packages; essentially, parts are files that are zipped together to comprise a package).</span></span> <span data-ttu-id="88deb-107">문서에 스타일로 서식이 지정된 단락이 포함되어 있으면 스타일이 적용된 단락이 포함된 문서 부분이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88deb-107">If a document contains paragraphs that are formatted with styles, there will be a document part that contains paragraphs that have styles applied to them.</span></span> <span data-ttu-id="88deb-108">또한 문서에 의해 참조되는 스타일이 포함된 스타일 부분도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88deb-108">There will also be a style part that contains the styles that are referred to by the document.</span></span>  
  
 <span data-ttu-id="88deb-109">패키지에 액세스할 때 임의의 경로를 사용하는 대신 부분 간 관계를 통해 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88deb-109">When accessing packages, it is important that you do so through the relationships between parts, rather than using an arbitrary path.</span></span> <span data-ttu-id="88deb-110">이 문제는 WordprocessingML 문서의 내용 조작 자습서의 범위를 벗어나지만 이 자습서에 포함된 예제 프로그램에서는 올바른 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="88deb-110">This issue is beyond the scope of the Manipulating Content in a WordprocessingML Document tutorial, but the example programs that are included in this tutorial demonstrate the correct approach.</span></span>  
  
## <a name="a-document-that-uses-styles"></a><span data-ttu-id="88deb-111">스타일을 사용하는 문서</span><span class="sxs-lookup"><span data-stu-id="88deb-111">A Document that Uses Styles</span></span>  
 <span data-ttu-id="88deb-112">제공 하는 WordML 예제는 [WordprocessingML 문서의 모양 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/shape-of-wordprocessingml-documents.md) 항목은 매우 단순 합니다.</span><span class="sxs-lookup"><span data-stu-id="88deb-112">The WordML example presented in the [Shape of WordprocessingML Documents (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/shape-of-wordprocessingml-documents.md) topic is a very simple one.</span></span> <span data-ttu-id="88deb-113">다음 문서는 더 복잡합니다. 이 문서에는 스타일로 서식이 지정된 단락이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88deb-113">The following document is more complicated: It has paragraphs that are formatted with styles.</span></span> <span data-ttu-id="88deb-114">Office Open XML 문서를 구성 하는 XML 실행 하는 것을 확인 하는 가장 쉬운 방법은 [예제 해당 출력 Office Open XML 문서 요소 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/example-that-outputs-office-open-xml-document-parts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="88deb-114">The easiest way to see the XML that makes up an Office Open XML document is to run the [Example that Outputs Office Open XML Document Parts (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/example-that-outputs-office-open-xml-document-parts.md).</span></span>  
  
 <span data-ttu-id="88deb-115">다음 문서에서 첫 번째 단락에는 `Heading1` 스타일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88deb-115">In the following document, the first paragraph has the style `Heading1`.</span></span> <span data-ttu-id="88deb-116">기본 스타일이 있는 단락이 많이 있으며</span><span class="sxs-lookup"><span data-stu-id="88deb-116">There are a number of paragraphs that have the default style.</span></span> <span data-ttu-id="88deb-117">`Code` 스타일이 있는 단락도 많이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88deb-117">There are also a number of paragraphs that have the style `Code`.</span></span> <span data-ttu-id="88deb-118">이 문서는 이와 같이 비교적 복잡하기 때문에 LINQ to XML을 사용하여 구문 분석하기가 더 흥미로운 대상입니다.</span><span class="sxs-lookup"><span data-stu-id="88deb-118">Because of this relative complexity, this is a more interesting document to parse with LINQ to XML.</span></span>  
  
 <span data-ttu-id="88deb-119">비기본 스타일이 있는 단락에서 단락 요소에는 `w:pPr`이라는 자식 요소가 있으며 이 자식 요소에는 `w:pStyle`이라는 자식 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88deb-119">In those paragraphs with non-default styles, the paragraph elements have a child element named `w:pPr`, which in turn has a child element `w:pStyle`.</span></span> <span data-ttu-id="88deb-120">이 요소에는 스타일 이름이 포함된 `w:val` 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88deb-120">That element has an attribute, `w:val`, which contains the style name.</span></span> <span data-ttu-id="88deb-121">단락에 기본 스타일이 있으면 단락 요소에 `w:p.Pr` 자식 요소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88deb-121">If the paragraph has the default style, it means that the paragraph element does not have a `w:p.Pr` child element.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<w:document  
    xmlns:ve="http://schemas.openxmlformats.org/markup-compatibility/2006"  
    xmlns:o="urn:schemas-microsoft-com:office:office"  
    xmlns:r="http://schemas.openxmlformats.org/officeDocument/2006/relationships"  
    xmlns:m="http://schemas.openxmlformats.org/officeDocument/2006/math"  
    xmlns:v="urn:schemas-microsoft-com:vml"  
    xmlns:wp="http://schemas.openxmlformats.org/drawingml/2006/wordprocessingDrawing"  
    xmlns:w10="urn:schemas-microsoft-com:office:word"  
    xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
    xmlns:wne="http://schemas.microsoft.com/office/word/2006/wordml">  
  <w:body>  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Heading1" />  
      </w:pPr>  
      <w:r>  
        <w:t>Parsing WordprocessingML with LINQ to XML</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" />  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0">  
      <w:r>  
        <w:t>The following example prints to the console.</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" />  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r>  
        <w:t>using System;</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRPr="00876F34" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r w:rsidRPr="00876F34">  
        <w:t>class Program {</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRPr="00876F34" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r w:rsidRPr="00876F34">  
        <w:t xml:space="preserve">    public static void </w:t>  
      </w:r>  
      <w:smartTag w:uri="urn:schemas-microsoft-com:office:smarttags" w:element="place">  
        <w:r w:rsidRPr="00876F34">  
          <w:t>Main</w:t>  
        </w:r>  
      </w:smartTag>  
      <w:r w:rsidRPr="00876F34">  
        <w:t>(string[] args) {</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRPr="00876F34" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r w:rsidRPr="00876F34">  
        <w:t xml:space="preserve">        Console.WriteLine("Hello World");</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRPr="00876F34" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r w:rsidRPr="00876F34">  
        <w:t xml:space="preserve">    }</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRPr="00876F34" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r w:rsidRPr="00876F34">  
        <w:t>}</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" />  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0">  
      <w:r>  
        <w:t>This example produces the following output:</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" />  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r>  
        <w:t>Hello World</w:t>  
      </w:r>  
    </w:p>  
    <w:sectPr w:rsidR="00A75AE0" w:rsidSect="00A75AE0">  
      <w:pgSz w:w="12240" w:h="15840" />  
      <w:pgMar w:top="1440" w:right="1800" w:bottom="1440" w:left="1800" w:header="720" w:footer="720" w:gutter="0" />  
      <w:cols w:space="720" />  
      <w:docGrid w:linePitch="360" />  
    </w:sectPr>  
  </w:body>  
</w:document>  
```  
  
## <a name="see-also"></a><span data-ttu-id="88deb-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88deb-122">See Also</span></span>  
 [<span data-ttu-id="88deb-123">세부 정보를 Office Open XML WordprocessingML 문서 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88deb-123">Details of Office Open XML WordprocessingML Documents (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md)
