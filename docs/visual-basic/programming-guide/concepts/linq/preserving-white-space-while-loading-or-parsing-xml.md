---
title: "로드 또는 XML2 구문 분석할 때 공백 유지"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef6518e0-2c8d-462c-8b92-a16e9dc737ad
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d99cea37bb9817c40a6d3876b72ccdbd84d7e7ba
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="preserving-white-space-while-loading-or-parsing-xml"></a><span data-ttu-id="f0788-102">XML을 로드 또는 구문 분석할 때 공백 유지</span><span class="sxs-lookup"><span data-stu-id="f0788-102">Preserving White Space while Loading or Parsing XML</span></span>
<span data-ttu-id="f0788-103">이 항목에서는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]의 공백 동작을 제어하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f0788-103">This topic describes how to control the white space behavior of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="f0788-104">일반적인 시나리오는 들여쓴 XML을 읽고 공백 텍스트 노드 없이 메모리 내 XML 트리를 만든 다음(공백을 유지하지 않음) XML에 대한 작업을 수행하고 들여쓰기를 사용하여 XML을 저장하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f0788-104">A common scenario is to read indented XML, create an in-memory XML tree without any white space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="f0788-105">서식이 있는 XML을 serialize하는 경우 XML 트리의 유효 공백만 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0788-105">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="f0788-106">이것이 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]의 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="f0788-106">This is the default behavior for [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="f0788-107">다른 일반적인 시나리오는 이미 의도적으로 들여쓴 XML을 읽고 수정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f0788-107">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="f0788-108">이 들여쓰기를 변경하려고 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0788-108">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="f0788-109">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에서는 XML을 로드하거나 구문 분석할 때 공백을 유지하고 XML을 serialize할 때 서식을 해제하는 경우 이렇게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0788-109">To do this in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you preserve white space when you load or parse the XML and disable formatting when you serialize the XML.</span></span>  
  
 <span data-ttu-id="f0788-110">이 항목에서는 XML 트리를 채우는 메서드의 공백 동작에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f0788-110">This topic describes the white space behavior of methods that populate XML trees.</span></span> <span data-ttu-id="f0788-111">XML 트리를 serialize할 때 공백을 제어하는 방법에 대한 자세한 내용은 [serialize할 때 공백 유지](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0788-111">For information about controlling white space when you serialize XML trees, see [Preserving White Space While Serializing](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md).</span></span>  
  
## <a name="behavior-of-methods-that-populate-xml-trees"></a><span data-ttu-id="f0788-112">XML 트리를 채우는 메서드의 동작</span><span class="sxs-lookup"><span data-stu-id="f0788-112">Behavior of Methods that Populate XML Trees</span></span>  
 <span data-ttu-id="f0788-113"><xref:System.Xml.Linq.XElement> 및 <xref:System.Xml.Linq.XDocument> 클래스의 다음 메서드는 XML 트리를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="f0788-113">The following methods in the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> classes populate an XML tree.</span></span> <span data-ttu-id="f0788-114">파일, <xref:System.IO.TextReader>, <xref:System.Xml.XmlReader> 또는 문자열에서 XML 트리를 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0788-114">You can populate an XML tree from a file, a <xref:System.IO.TextReader>, an <xref:System.Xml.XmlReader>, or a string:</span></span>  
  
-   <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="f0788-115">메서드에서 <xref:System.Xml.Linq.LoadOptions>를 인수로 사용하지 않는 경우 무효 공백을 유지하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0788-115">If the method does not take <xref:System.Xml.Linq.LoadOptions> as an argument, the method will not preserve insignificant white space.</span></span>  
  
 <span data-ttu-id="f0788-116">대부분의 경우 메서드에서 <xref:System.Xml.Linq.LoadOptions>를 인수로 사용하면 XML 트리의 텍스트 노드로 무효 공백을 선택적으로 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0788-116">In most cases, if the method takes <xref:System.Xml.Linq.LoadOptions> as an argument, you can optionally preserve insignificant white space as text nodes in the XML tree.</span></span> <span data-ttu-id="f0788-117">그러나 메서드가 <xref:System.Xml.XmlReader>에서 XML을 로드하는 경우에는 <xref:System.Xml.XmlReader>가 공백을 유지할지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0788-117">However, if the method is loading the XML from an <xref:System.Xml.XmlReader>, then the <xref:System.Xml.XmlReader> determines whether white space will be preserved or not.</span></span> <span data-ttu-id="f0788-118"><xref:System.Xml.Linq.LoadOptions.PreserveWhitespace>를 설정해도 아무런 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0788-118">Setting <xref:System.Xml.Linq.LoadOptions.PreserveWhitespace> will have no effect.</span></span>  
  
 <span data-ttu-id="f0788-119">이러한 메서드를 사용하는 경우 공백이 유지되면 무효 공백이 XML 트리에 <xref:System.Xml.Linq.XText> 노드로 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0788-119">With these methods, if white space is preserved, insignificant white space is inserted into the XML tree as <xref:System.Xml.Linq.XText> nodes.</span></span> <span data-ttu-id="f0788-120">공백이 유지되지 않으면 텍스트 노드가 삽입되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0788-120">If white space is not preserved, text nodes are not inserted.</span></span>  
  
 <span data-ttu-id="f0788-121"><xref:System.Xml.XmlWriter>를 사용하여 XML 트리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0788-121">You can create an XML tree by using an <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="f0788-122"><xref:System.Xml.XmlWriter>에 쓴 노드가 트리에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="f0788-122">Nodes that are written to the <xref:System.Xml.XmlWriter> are populated in the tree.</span></span> <span data-ttu-id="f0788-123">그러나 이 메서드를 사용하여 XML 트리를 빌드하면 노드가 공백인지 여부나 유효한지 여부에 관계없이 모든 노드가 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0788-123">However, when you build an XML tree using this method, all nodes are preserved, regardless of whether the node is white space or not, or whether the white space is significant or not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0788-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0788-124">See Also</span></span>  
 [<span data-ttu-id="f0788-125">XML 구문 분석 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0788-125">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
