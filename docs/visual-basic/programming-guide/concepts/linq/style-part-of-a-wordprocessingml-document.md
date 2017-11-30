---
title: "WordprocessingML 문서 2의 스타일 부분"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 292cc094-9483-4192-ac3b-a5dc51fbac12
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d16363f377cc8a41ae8192e753ad70a8062588d6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="style-part-of-a-wordprocessingml-document"></a><span data-ttu-id="e70e5-102">WordprocessingML 문서의 스타일 부분</span><span class="sxs-lookup"><span data-stu-id="e70e5-102">Style Part of a WordprocessingML Document</span></span>
<span data-ttu-id="e70e5-103">이 항목에서는 Office Open XML WordprocessingML 문서의 스타일 부분에 대한 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e70e5-103">This topic shows an example of the style part of the Office Open XML WordprocessingML document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e70e5-104">예제</span><span class="sxs-lookup"><span data-stu-id="e70e5-104">Example</span></span>  
 <span data-ttu-id="e70e5-105">다음 예제는 Office Open XML WordprocessingML 문서의 스타일 부분을 구성하는 XML입니다.</span><span class="sxs-lookup"><span data-stu-id="e70e5-105">The following example is the XML that makes up the style part of an Office Open XML WordprocessingML document.</span></span>  
  
 <span data-ttu-id="e70e5-106">기본 단락 스타일에는 다음과 같은 여는 태그를 가진 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e70e5-106">The default paragraph style has an element with the following opening tag:</span></span>  
  
```  
<w:style w:type="paragraph" w:default="1" w:styleId="Normal">  
```  
  
 <span data-ttu-id="e70e5-107">기본 스타일 식별자를 찾기 위해 쿼리를 작성할 때 이 정보를 알고 있어야 쿼리에서 기본 스타일을 가진 단락의 스타일을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e70e5-107">You need to know this information when you write the query to find the default style identifier, so that the query can identify the style of paragraphs that have the default style.</span></span>  
  
 <span data-ttu-id="e70e5-108">이러한 문서는 Microsoft Word에서 생성하는 일반적인 문서와 비교할 때 매우 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="e70e5-108">Note that these documents are very simple when compared to typical documents that Microsoft Word generates.</span></span> <span data-ttu-id="e70e5-109">대부분의 경우 Word에서는 많은 양의 추가 정보, 추가 서식 및 메타데이터를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e70e5-109">In many cases, Word saves a great deal of additional information, additional formatting and metadata.</span></span> <span data-ttu-id="e70e5-110">또한 Word에서는 이 예제의 경우처럼 쉽게 읽을 수 있도록 줄의 서식을 지정하지 않으며 XML은 들여쓰기 없이 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="e70e5-110">Furthermore, Word does not format the lines to be easily readable as in this example; instead, the XML is saved without indentation.</span></span> <span data-ttu-id="e70e5-111">그러나 모든 WordprocessingML 문서는 동일한 기본 XML 모양을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="e70e5-111">However, all WordprocessingML documents share the same basic XML shape.</span></span> <span data-ttu-id="e70e5-112">이 때문에 이 자습서에서 제공하는 쿼리는 더욱 복잡한 문서와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e70e5-112">Because of this, the queries presented in this tutorial will work with more complicated documents.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<w:styles  
    xmlns:r="http://schemas.openxmlformats.org/officeDocument/2006/relationships"  
    xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  <w:docDefaults>  
    <w:rPrDefault>  
      <w:rPr>  
        <w:rFonts  
            w:ascii="Times New Roman"  
            w:eastAsia="Times New Roman"  
            w:hAnsi="Times New Roman"  
            w:cs="Times New Roman" />  
        <w:sz w:val="22" />  
        <w:szCs w:val="22" />  
        <w:lang w:val="en-US" w:eastAsia="en-US" w:bidi="ar-SA" />  
      </w:rPr>  
    </w:rPrDefault>  
    <w:pPrDefault />  
  </w:docDefaults>  
  <w:style w:type="paragraph" w:default="1" w:styleId="Normal">  
    <w:name w:val="Normal" />  
    <w:qFormat />  
    <w:rPr>  
      <w:sz w:val="24" />  
      <w:szCs w:val="24" />  
    </w:rPr>  
  </w:style>  
  <w:style w:type="paragraph" w:styleId="Heading1">  
    <w:name w:val="heading 1" />  
    <w:basedOn w:val="Normal" />  
    <w:next w:val="Normal" />  
    <w:link w:val="Heading1Char" />  
    <w:uiPriority w:val="99" />  
    <w:qFormat />  
    <w:rsid w:val="006027C7" />  
    <w:pPr>  
      <w:keepNext />  
      <w:spacing w:before="240" w:after="60" />  
      <w:outlineLvl w:val="0" />  
    </w:pPr>  
    <w:rPr>  
      <w:rFonts w:ascii="Arial" w:hAnsi="Arial" w:cs="Arial" />  
      <w:b />  
      <w:bCs />  
      <w:kern w:val="32" />  
      <w:sz w:val="32" />  
      <w:szCs w:val="32" />  
    </w:rPr>  
  </w:style>  
  <w:style w:type="character" w:default="1" w:styleId="DefaultParagraphFont">  
    <w:name w:val="Default Paragraph Font" />  
    <w:uiPriority w:val="99" />  
    <w:semiHidden />  
  </w:style>  
  <w:style w:type="table" w:default="1" w:styleId="TableNormal">  
    <w:name w:val="Normal Table" />  
    <w:uiPriority w:val="99" />  
    <w:semiHidden />  
    <w:unhideWhenUsed />  
    <w:qFormat />  
    <w:tblPr>  
      <w:tblInd w:w="0" w:type="dxa" />  
      <w:tblCellMar>  
        <w:top w:w="0" w:type="dxa" />  
        <w:left w:w="108" w:type="dxa" />  
        <w:bottom w:w="0" w:type="dxa" />  
        <w:right w:w="108" w:type="dxa" />  
      </w:tblCellMar>  
    </w:tblPr>  
  </w:style>  
  <w:style w:type="numbering" w:default="1" w:styleId="NoList">  
    <w:name w:val="No List" />  
    <w:uiPriority w:val="99" />  
    <w:semiHidden />  
    <w:unhideWhenUsed />  
  </w:style>  
  <w:style w:type="character" w:customStyle="1" w:styleId="Heading1Char">  
    <w:name w:val="Heading 1 Char" />  
    <w:basedOn w:val="DefaultParagraphFont" />  
    <w:link w:val="Heading1" />  
    <w:uiPriority w:val="9" />  
    <w:rsid w:val="009765E3" />  
    <w:rPr>  
      <w:rFonts  
          w:asciiTheme="majorHAnsi"  
          w:eastAsiaTheme="majorEastAsia"  
          w:hAnsiTheme="majorHAnsi"  
          w:cstheme="majorBidi" />  
      <w:b />  
      <w:bCs />  
      <w:kern w:val="32" />  
      <w:sz w:val="32" />  
      <w:szCs w:val="32" />  
    </w:rPr>  
  </w:style>  
  <w:style w:type="paragraph" w:customStyle="1" w:styleId="Code">  
    <w:name w:val="Code" />  
    <w:aliases w:val="c" />  
    <w:uiPriority w:val="99" />  
    <w:rsid w:val="006027C7" />  
    <w:pPr>  
      <w:spacing w:after="60" w:line="300" w:lineRule="exact" />  
    </w:pPr>  
    <w:rPr>  
      <w:rFonts w:ascii="Courier New" w:hAnsi="Courier New" />  
      <w:noProof />  
      <w:color w:val="000080" />  
      <w:sz w:val="20" />  
      <w:szCs w:val="20" />  
    </w:rPr>  
  </w:style>  
</w:styles>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e70e5-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e70e5-113">See Also</span></span>  
 [<span data-ttu-id="e70e5-114">세부 정보를 Office Open XML WordprocessingML 문서 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e70e5-114">Details of Office Open XML WordprocessingML Documents (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md)
