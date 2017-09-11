---
title: "로드 또는 XML2 구문 분석할 때 공백 유지 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: ef6518e0-2c8d-462c-8b92-a16e9dc737ad
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a2872c1e2354c0a0bd106f7fb945542ce37e7774
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="preserving-white-space-while-loading-or-parsing-xml"></a><span data-ttu-id="7c37a-102">XML을 로드 또는 구문 분석할 때 공백 유지</span><span class="sxs-lookup"><span data-stu-id="7c37a-102">Preserving White Space while Loading or Parsing XML</span></span>
<span data-ttu-id="7c37a-103">이 항목에서는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]의 공백 동작을 제어하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7c37a-103">This topic describes how to control the white space behavior of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span>  
  
 <span data-ttu-id="7c37a-104">일반적인 시나리오는 들여쓴 XML을 읽고 공백 텍스트 노드 없이 메모리 내 XML 트리를 만든 다음(공백을 유지하지 않음) XML에 대한 작업을 수행하고 들여쓰기를 사용하여 XML을 저장하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7c37a-104">A common scenario is to read indented XML, create an in-memory XML tree without any white space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="7c37a-105">서식이 있는 XML을 serialize하는 경우 XML 트리의 유효 공백만 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c37a-105">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="7c37a-106">이것이 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]의 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="7c37a-106">This is the default behavior for [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span>  
  
 <span data-ttu-id="7c37a-107">다른 일반적인 시나리오는 이미 의도적으로 들여쓴 XML을 읽고 수정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7c37a-107">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="7c37a-108">이 들여쓰기를 변경하려고 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c37a-108">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="7c37a-109">[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]에서는 XML을 로드하거나 구문 분석할 때 공백을 유지하고 XML을 serialize할 때 서식을 해제하는 경우 이렇게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c37a-109">To do this in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], you preserve white space when you load or parse the XML and disable formatting when you serialize the XML.</span></span>  
  
 <span data-ttu-id="7c37a-110">이 항목에서는 XML 트리를 채우는 메서드의 공백 동작에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7c37a-110">This topic describes the white space behavior of methods that populate XML trees.</span></span> <span data-ttu-id="7c37a-111">XML 트리를 serialize 할 때 공백을 제어 하는 방법에 대 한 정보를 참조 하십시오. [유지 공백 동안 직렬화](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7c37a-111">For information about controlling white space when you serialize XML trees, see [Preserving White Space While Serializing](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md).</span></span>  
  
## <a name="behavior-of-methods-that-populate-xml-trees"></a><span data-ttu-id="7c37a-112">XML 트리를 채우는 메서드의 동작</span><span class="sxs-lookup"><span data-stu-id="7c37a-112">Behavior of Methods that Populate XML Trees</span></span>  
 <span data-ttu-id="7c37a-113">다음 메서드는 <xref:System.Xml.Linq.XElement>및 <xref:System.Xml.Linq.XDocument>클래스는 XML 트리를 채웁니다.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="7c37a-113">The following methods in the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> classes populate an XML tree.</span></span> <span data-ttu-id="7c37a-114">파일에서 XML 트리를 채울 수는 <xref:System.IO.TextReader>, <xref:System.Xml.XmlReader>, 또는 문자열:</xref:System.Xml.XmlReader> </xref:System.IO.TextReader></span><span class="sxs-lookup"><span data-stu-id="7c37a-114">You can populate an XML tree from a file, a <xref:System.IO.TextReader>, an <xref:System.Xml.XmlReader>, or a string:</span></span>  
  
-   <span data-ttu-id="7c37a-115"><xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7c37a-115"><xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="7c37a-116"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7c37a-116"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="7c37a-117"><xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7c37a-117"><xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="7c37a-118"><xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7c37a-118"><xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></span></span>  
  
 <span data-ttu-id="7c37a-119">메서드를 사용 하지 않는 경우 <xref:System.Xml.Linq.LoadOptions>를 인수로 메서드에 불필요 한 공백을 유지 하지 것입니다.</xref:System.Xml.Linq.LoadOptions></span><span class="sxs-lookup"><span data-stu-id="7c37a-119">If the method does not take <xref:System.Xml.Linq.LoadOptions> as an argument, the method will not preserve insignificant white space.</span></span>  
  
 <span data-ttu-id="7c37a-120">대부분의 경우, 메서드가 사용 <xref:System.Xml.Linq.LoadOptions>를 인수로 하면 선택적으로 유지할 수 무효 공백이 XML 트리의 텍스트 노드로.</xref:System.Xml.Linq.LoadOptions></span><span class="sxs-lookup"><span data-stu-id="7c37a-120">In most cases, if the method takes <xref:System.Xml.Linq.LoadOptions> as an argument, you can optionally preserve insignificant white space as text nodes in the XML tree.</span></span> <span data-ttu-id="7c37a-121">그러나 메서드는 XML을 로드 하는 경우는 <xref:System.Xml.XmlReader>, 그런 다음 <xref:System.Xml.XmlReader>여부 공백이 유지할지 여부를 결정 합니다.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="7c37a-121">However, if the method is loading the XML from an <xref:System.Xml.XmlReader>, then the <xref:System.Xml.XmlReader> determines whether white space will be preserved or not.</span></span> <span data-ttu-id="7c37a-122">설정 <xref:System.Xml.Linq.LoadOptions>아무런 효과가 없습니다.</xref:System.Xml.Linq.LoadOptions></span><span class="sxs-lookup"><span data-stu-id="7c37a-122">Setting <xref:System.Xml.Linq.LoadOptions> will have no effect.</span></span>  
  
 <span data-ttu-id="7c37a-123">이러한 메서드를 통해 공백이 유지 됩니다 무효 공백이 삽입 됩니다 XML 트리에 <xref:System.Xml.Linq.XText>노드.</xref:System.Xml.Linq.XText></span><span class="sxs-lookup"><span data-stu-id="7c37a-123">With these methods, if white space is preserved, insignificant white space is inserted into the XML tree as <xref:System.Xml.Linq.XText> nodes.</span></span> <span data-ttu-id="7c37a-124">공백이 유지되지 않으면 텍스트 노드가 삽입되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c37a-124">If white space is not preserved, text nodes are not inserted.</span></span>  
  
 <span data-ttu-id="7c37a-125"><xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> 를 사용 하 여 XML 트리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c37a-125">You can create an XML tree by using an <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="7c37a-126">기록 되는 노드는 <xref:System.Xml.XmlWriter>트리에 채워집니다.</xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="7c37a-126">Nodes that are written to the <xref:System.Xml.XmlWriter> are populated in the tree.</span></span> <span data-ttu-id="7c37a-127">그러나 이 메서드를 사용하여 XML 트리를 빌드하면 노드가 공백인지 여부나 유효한지 여부에 관계없이 모든 노드가 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c37a-127">However, when you build an XML tree using this method, all nodes are preserved, regardless of whether the node is white space or not, or whether the white space is significant or not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c37a-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c37a-128">See Also</span></span>  
 [<span data-ttu-id="7c37a-129">(Visual Basic) XML 구문 분석</span><span class="sxs-lookup"><span data-stu-id="7c37a-129">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
