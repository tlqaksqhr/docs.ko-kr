---
title: "XML 축 속성 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML axis properties [Visual Basic]
- Visual Basic code, XML
- XML axis [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 7e400e20-5d1e-4d22-a65c-9df79d5c1621
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4dd15670eed316552f2f02e4536122a6a110542d
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="xml-axis-properties-visual-basic"></a><span data-ttu-id="28c64-102">XML 축 속성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="28c64-102">XML Axis Properties (Visual Basic)</span></span>
<span data-ttu-id="28c64-103">이 섹션의 항목에서는 문서에서 XML 축 속성 구문의 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="28c64-103">The topics in this section document the syntax of XML axis properties in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="28c64-104">XML 축 속성을 사용 하면 쉽게 코드에서 직접 XML에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="28c64-104">The XML axis properties make it easy to access XML directly in your code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="28c64-105">단원 내용</span><span class="sxs-lookup"><span data-stu-id="28c64-105">In This Section</span></span>  
  
|<span data-ttu-id="28c64-106">항목</span><span class="sxs-lookup"><span data-stu-id="28c64-106">Topic</span></span>|<span data-ttu-id="28c64-107">설명</span><span class="sxs-lookup"><span data-stu-id="28c64-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="28c64-108">XML Attribute 축 속성</span><span class="sxs-lookup"><span data-stu-id="28c64-108">XML Attribute Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)|<span data-ttu-id="28c64-109">특성에 액세스 하는 방법에 설명 된 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="28c64-109">Describes how to access the attributes of an <xref:System.Xml.Linq.XElement> object.</span></span>|  
|[<span data-ttu-id="28c64-110">XML Child 축 속성</span><span class="sxs-lookup"><span data-stu-id="28c64-110">XML Child Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)|<span data-ttu-id="28c64-111">자식에 액세스 하는 방법에 설명 된 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="28c64-111">Describes how to access the children of an <xref:System.Xml.Linq.XElement> object.</span></span>|  
|[<span data-ttu-id="28c64-112">XML Descendant 축 속성</span><span class="sxs-lookup"><span data-stu-id="28c64-112">XML Descendant Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)|<span data-ttu-id="28c64-113">하위 항목에 액세스 하는 방법에 설명 된 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="28c64-113">Describes how to access the descendants of an <xref:System.Xml.Linq.XElement> object.</span></span>|  
|[<span data-ttu-id="28c64-114">확장명 인덱서 속성</span><span class="sxs-lookup"><span data-stu-id="28c64-114">Extension Indexer Property</span></span>](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)|<span data-ttu-id="28c64-115">컬렉션의 개별 요소에 액세스 하는 방법에 설명 <xref:System.Xml.Linq.XElement>또는 <xref:System.Xml.Linq.XAttribute>개체.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="28c64-115">Describes how to access individual elements in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects.</span></span>|  
|[<span data-ttu-id="28c64-116">XML 값 속성</span><span class="sxs-lookup"><span data-stu-id="28c64-116">XML Value Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)|<span data-ttu-id="28c64-117">컬렉션의 첫 번째 요소 값에 액세스 하는 방법에 설명 <xref:System.Xml.Linq.XElement>또는 <xref:System.Xml.Linq.XAttribute>개체.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="28c64-117">Describes how to access the value of the first element of a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28c64-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="28c64-118">See Also</span></span>  
 [<span data-ttu-id="28c64-119">XML</span><span class="sxs-lookup"><span data-stu-id="28c64-119">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
