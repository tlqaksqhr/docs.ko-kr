---
title: 문서에 포함된 스타일시트 지시문
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: d79fb295-ebc7-438d-ba1b-05be7d534834
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2fa671304c611db571b160cd1d960b83bf451c9a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="style-sheet-directives-embedded-in-a-document"></a><span data-ttu-id="a1f31-102">문서에 포함된 스타일시트 지시문</span><span class="sxs-lookup"><span data-stu-id="a1f31-102">Style Sheet Directives Embedded in a Document</span></span>
<span data-ttu-id="a1f31-103">기존 XML에 `<?xml:stylesheet?>`의 스타일시트 지시문이 포함된 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1f31-103">Occasionally, existing XML contains the style sheet directive of `<?xml:stylesheet?>`.</span></span> <span data-ttu-id="a1f31-104">Microsoft Internet Explorer에서는 `<?xml-stylesheet?>` 구문 대신 이처럼 포함된 지시문이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1f31-104">Microsoft Internet Explorer accepts this as an alternative to the `<?xml-stylesheet?>` syntax.</span></span> <span data-ttu-id="a1f31-105">다음 데이터와 같이 XML 데이터에 `<?xml:stylesheet?>` 지시문이 있는 경우 이 데이터를 XML DOM(문서 개체 모델)으로 로드하려고 하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1f31-105">When the XML data contains an `<?xml:stylesheet?>` directive, as shown in the following data, attempting to load this data into the XML Document Object Model (DOM) throws an exception.</span></span>  
  
```xml  
<?xml version="1.0" ?>  
<?xml:stylesheet type="text/xsl" href="test2.xsl"?>  
<root>  
    <test>Node 1</test>  
    <test>Node 2</test>  
</root>  
```  
  
 <span data-ttu-id="a1f31-106">이는 `<?xml:stylesheet?>`가 DOM에 대해 유효하지 않은 **ProcessingInstruction**으로 간주되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="a1f31-106">This occurs because the `<?xml:stylesheet?>` is considered an invalid **ProcessingInstruction** to the DOM.</span></span> <span data-ttu-id="a1f31-107">XML 사양의 네임스페이스에 따라 **ProcessingInstruction**은 정규화된 이름(QName)이 아닌 콜론이 없는 이름(NCName)만 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1f31-107">Any **ProcessingInstruction**, according to the Namespaces in XML specification, can only be no-colon names (NCNames), as opposed to qualified names (QNames).</span></span>  
  
 <span data-ttu-id="a1f31-108">XML 사양의 네임스페이스에 대해 다룬 6단원의 내용에 따르면, 이 사양에 따라 **Load** 및 **LoadXml** 메서드를 구현할 경우 문서에 다음과 같은 효과가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a1f31-108">From Section 6 of the Namespaces in XML specification, the effect of having the **Load** and **LoadXml** methods conform to the specification is that in a document:</span></span>  
  
-   <span data-ttu-id="a1f31-109">모든 요소 형식 및 특성 이름에 콜론이 없거나 하나만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1f31-109">All element types and attribute names contain either zero or one colon.</span></span>  
  
-   <span data-ttu-id="a1f31-110">엔터티 이름, ProcessingInstruction 대상 또는 노테이션 이름에 콜론이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1f31-110">No entity names, ProcessingInstruction targets, or notation names contain any colons.</span></span>  
  
 <span data-ttu-id="a1f31-111">`<?xml:stylesheet?>`에는 콜론이 있으므로 두 번째 규칙을 위반한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a1f31-111">With the `<?xml:stylesheet?>` containing a colon, you now violate the rule in the second bullet.</span></span>  
  
 <span data-ttu-id="a1f31-112">www.w3.org/TR/xml-stylesheet에 있는 W3C(World Wide Web 컨소시엄) Associating Style Sheets with XML documents 버전 1.0 권장 사항에 따라 XSLT 스타일시트를 XML 문서에 연결하는 처리 명령은 콜론 대신 대시를 사용한 `<?xml-stylesheet?>`입니다.</span><span class="sxs-lookup"><span data-stu-id="a1f31-112">According to the World Wide Web Consortium (W3C) Associating Style Sheets with XML documents Version 1.0 Recommendation, located at www.w3.org/TR/xml-stylesheet, the processing instruction to associate an XSLT style sheet with an XML document is `<?xml-stylesheet?>`, with a dash replacing the colon.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1f31-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1f31-113">See Also</span></span>  
 [<span data-ttu-id="a1f31-114">XML DOM(문서 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="a1f31-114">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
