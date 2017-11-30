---
title: "문서에 포함된 스타일시트 지시문"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d79fb295-ebc7-438d-ba1b-05be7d534834
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8c5cfcc9f35e4a07e9426a4dd24c1e2f04985f16
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="style-sheet-directives-embedded-in-a-document"></a><span data-ttu-id="cd07a-102">문서에 포함된 스타일시트 지시문</span><span class="sxs-lookup"><span data-stu-id="cd07a-102">Style Sheet Directives Embedded in a Document</span></span>
<span data-ttu-id="cd07a-103">기존 XML에 `<?xml:stylesheet?>`의 스타일시트 지시문이 포함된 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd07a-103">Occasionally, existing XML contains the style sheet directive of `<?xml:stylesheet?>`.</span></span> <span data-ttu-id="cd07a-104">Microsoft Internet Explorer 허용 하는 대신이 `<?xml-stylesheet?>` 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="cd07a-104">Microsoft Internet Explorer accepts this as an alternative to the `<?xml-stylesheet?>` syntax.</span></span> <span data-ttu-id="cd07a-105">다음 데이터와 같이 XML 데이터에 `<?xml:stylesheet?>` 지시문이 있는 경우 이 데이터를 XML DOM(문서 개체 모델)으로 로드하려고 하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd07a-105">When the XML data contains an `<?xml:stylesheet?>` directive, as shown in the following data, attempting to load this data into the XML Document Object Model (DOM) throws an exception.</span></span>  
  
```xml  
<?xml version="1.0" ?>  
<?xml:stylesheet type="text/xsl" href="test2.xsl"?>  
<root>  
    <test>Node 1</test>  
    <test>Node 2</test>  
</root>  
```  
  
 <span data-ttu-id="cd07a-106">이 때문에 발생는 `<?xml:stylesheet?>` 잘못 된 것으로 간주 됩니다 **ProcessingInstruction** dom</span><span class="sxs-lookup"><span data-stu-id="cd07a-106">This occurs because the `<?xml:stylesheet?>` is considered an invalid **ProcessingInstruction** to the DOM.</span></span> <span data-ttu-id="cd07a-107">모든 **ProcessingInstruction**XML 사양의 네임 스페이스에 따라,만 될 수 있습니다-콜론이 없는, 대신 정규화 된 이름 (QNames)입니다.</span><span class="sxs-lookup"><span data-stu-id="cd07a-107">Any **ProcessingInstruction**, according to the Namespaces in XML specification, can only be no-colon names (NCNames), as opposed to qualified names (QNames).</span></span>  
  
 <span data-ttu-id="cd07a-108">XML 사양에서는 같은 효과를 네임 스페이스의 6 단원의 **부하** 및 **LoadXml** 메서드 사양이 문서에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd07a-108">From Section 6 of the Namespaces in XML specification, the effect of having the **Load** and **LoadXml** methods conform to the specification is that in a document:</span></span>  
  
-   <span data-ttu-id="cd07a-109">모든 요소 형식 및 특성 이름에 콜론이 없거나 하나만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd07a-109">All element types and attribute names contain either zero or one colon.</span></span>  
  
-   <span data-ttu-id="cd07a-110">엔터티 이름, ProcessingInstruction 대상 또는 노테이션 이름에 콜론이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd07a-110">No entity names, ProcessingInstruction targets, or notation names contain any colons.</span></span>  
  
 <span data-ttu-id="cd07a-111">`<?xml:stylesheet?>`에는 콜론이 있으므로 두 번째 규칙을 위반한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cd07a-111">With the `<?xml:stylesheet?>` containing a colon, you now violate the rule in the second bullet.</span></span>  
  
 <span data-ttu-id="cd07a-112">www.w3.org/TR/xml-stylesheet에 있는 W3C(World Wide Web 컨소시엄) Associating Style Sheets with XML documents 버전 1.0 권장 사항에 따라 XSLT 스타일시트를 XML 문서에 연결하는 처리 명령은 콜론 대신 대시를 사용한 `<?xml-stylesheet?>`입니다.</span><span class="sxs-lookup"><span data-stu-id="cd07a-112">According to the World Wide Web Consortium (W3C) Associating Style Sheets with XML documents Version 1.0 Recommendation, located at www.w3.org/TR/xml-stylesheet, the processing instruction to associate an XSLT style sheet with an XML document is `<?xml-stylesheet?>`, with a dash replacing the colon.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd07a-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd07a-113">See Also</span></span>  
 [<span data-ttu-id="cd07a-114">XML 문서 개체 모델 (DOM)</span><span class="sxs-lookup"><span data-stu-id="cd07a-114">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
