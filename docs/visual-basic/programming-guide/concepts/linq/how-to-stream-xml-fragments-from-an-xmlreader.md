---
title: "방법: XmlReader (Visual Basic)에서 XML 조각을 스트림 | Microsoft 문서"
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
ms.assetid: f67ce598-4a12-4dcb-9a07-24deca02a111
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c9c60bb4730ef6569390f76f63c40a2cbd1c9524
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-visual-basic"></a><span data-ttu-id="da471-102">방법: XmlReader (Visual Basic)에서 XML 조각 스트리밍</span><span class="sxs-lookup"><span data-stu-id="da471-102">How to: Stream XML Fragments from an XmlReader (Visual Basic)</span></span>
<span data-ttu-id="da471-103">큰 XML 파일을 처리해야 하는 경우 전체 XML 트리를 메모리에 로드하는 것이 가능하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da471-103">When you have to process large XML files, it might not be feasible to load the whole XML tree into memory.</span></span> <span data-ttu-id="da471-104">이 항목에서는 <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> 를 사용 하 여 조각을 스트림 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da471-104">This topic shows how to stream fragments using an <xref:System.Xml.XmlReader>.</span></span>  
  
 <span data-ttu-id="da471-105">사용 하는 가장 효과적인 방법 중 하나는 <xref:System.Xml.XmlReader>읽을 <xref:System.Xml.Linq.XElement>개체 사용자 지정 축 메서드를 직접 작성 하는 것입니다.</xref:System.Xml.Linq.XElement> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="da471-105">One of the most effective ways to use an <xref:System.Xml.XmlReader> to read <xref:System.Xml.Linq.XElement> objects is to write your own custom axis method.</span></span> <span data-ttu-id="da471-106">축 메서드는 일반적으로 컬렉션을 반환와 같은 <xref:System.Collections.Generic.IEnumerable%601>의 <xref:System.Xml.Linq.XElement>이 항목의 예제에서와 같이.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="da471-106">An axis method typically returns a collection such as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, as shown in the example in this topic.</span></span> <span data-ttu-id="da471-107">사용자 지정 축 메서드를 호출 하 여 XML 조각을 만든 후에 <xref:System.Xml.Linq.XNode.ReadFrom%2A>메서드를 사용 하 여 컬렉션을 반환 `yield return`.</xref:System.Xml.Linq.XNode.ReadFrom%2A></span><span class="sxs-lookup"><span data-stu-id="da471-107">In the custom axis method, after you create the XML fragment by calling the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method, return the collection using `yield return`.</span></span> <span data-ttu-id="da471-108">이것은 사용자 지정 축 메서드에 지연된 실행 의미를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="da471-108">This provides deferred execution semantics to your custom axis method.</span></span>  
  
 <span data-ttu-id="da471-109">XML 트리를 만들 때는 <xref:System.Xml.XmlReader>개체는 <xref:System.Xml.XmlReader>요소에 배치 되어야 합니다.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="da471-109">When you create an XML tree from an <xref:System.Xml.XmlReader> object, the <xref:System.Xml.XmlReader> must be positioned on an element.</span></span> <span data-ttu-id="da471-110"><xref:System.Xml.Linq.XNode.ReadFrom%2A>메서드는 요소의 닫는 태그를 읽을 때까지 반환 하지 않습니다.</xref:System.Xml.Linq.XNode.ReadFrom%2A></span><span class="sxs-lookup"><span data-stu-id="da471-110">The <xref:System.Xml.Linq.XNode.ReadFrom%2A> method does not return until it has read the close tag of the element.</span></span>  
  
 <span data-ttu-id="da471-111">부분 트리를 만들려는 경우를 인스턴스화할 수 있습니다는 <xref:System.Xml.XmlReader>, 변환 하려는 노드에 판독기를 배치는 <xref:System.Xml.Linq.XElement>트리를 선택한 다음 만들기는 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="da471-111">If you want to create a partial tree, you can instantiate an <xref:System.Xml.XmlReader>, position the reader on the node that you want to convert to an <xref:System.Xml.Linq.XElement> tree, and then create the <xref:System.Xml.Linq.XElement> object.</span></span>  
  
 <span data-ttu-id="da471-112">항목 [하는 방법: 헤더 정보 (Visual Basic)에 액세스할 수 있는 XML 조각 스트림](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md) 좀 더 복잡 한 문서를 스트림 하는 방법에 대 한 예제 및 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="da471-112">The topic [How to: Stream XML Fragments with Access to Header Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md) contains information and an example on how to stream a more complex document.</span></span>  
  
 <span data-ttu-id="da471-113">항목 [하는 방법: 수행 스트리밍 변환의 큰 XML 문서 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-perform-streaming-transform-of-large-xml-documents.md) LINQ to XML 사용 하 여 작은 메모리 사용 공간을 유지 하면서 매우 큰 XML 문서를 변환 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="da471-113">The topic [How to: Perform Streaming Transform of Large XML Documents (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-perform-streaming-transform-of-large-xml-documents.md) contains an example of using LINQ to XML to transform extremely large XML documents while maintaining a small memory footprint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da471-114">예제</span><span class="sxs-lookup"><span data-stu-id="da471-114">Example</span></span>  
 <span data-ttu-id="da471-115">이 예제에서는 사용자 지정 축 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="da471-115">This example creates a custom axis method.</span></span> <span data-ttu-id="da471-116">[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리를 사용하여 이 메서드를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da471-116">You can query it by using a [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query.</span></span> <span data-ttu-id="da471-117">사용자 지정 축 메서드 `StreamRootChildDoc`는 반복되는 `Child` 요소가 있는 문서를 읽도록 특정하게 디자인된 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="da471-117">The custom axis method, `StreamRootChildDoc`, is a method that is designed specifically to read a document that has a repeating `Child` element.</span></span>  
  
<span data-ttu-id="da471-118"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="da471-118"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="da471-119">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="da471-119">This example produces the following output:</span></span>  
  
<span data-ttu-id="da471-120"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="da471-120"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="da471-121">이 예제의 소스 문서는 매우 작습니다.</span><span class="sxs-lookup"><span data-stu-id="da471-121">In this example, the source document is very small.</span></span> <span data-ttu-id="da471-122">`Child` 요소가 수백만 있더라도 이 예제에서는 여전히 작은 메모리 공간만 사용할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="da471-122">However, even if there were millions of `Child` elements, this example would still have a small memory footprint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da471-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da471-123">See Also</span></span>  
 <span data-ttu-id="da471-124">[연습: Visual Basic에서 IEnumerable(Of T) 구현](../../../../visual-basic/programming-guide/language-features/control-flow/walkthrough-implementing-ienumerable-of-t.md) </span><span class="sxs-lookup"><span data-stu-id="da471-124">[Walkthrough: Implementing IEnumerable(Of T) in Visual Basic](../../../../visual-basic/programming-guide/language-features/control-flow/walkthrough-implementing-ienumerable-of-t.md) </span></span>  
<span data-ttu-id="da471-125"> [(Visual Basic) XML 구문 분석](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)</span><span class="sxs-lookup"><span data-stu-id="da471-125"> [Parsing XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)</span></span>
