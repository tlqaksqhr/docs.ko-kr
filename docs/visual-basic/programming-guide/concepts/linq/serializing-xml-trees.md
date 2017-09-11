---
title: "XML 트리 (Visual Basic)를 직렬화 하는 작업 | Microsoft 문서"
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
ms.assetid: 2c340695-a726-4030-85be-6975d8a149cf
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
ms.openlocfilehash: a63e875b1c1391ec1bb2b0ae64be9f9cff28d87d
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="serializing-xml-trees-visual-basic"></a><span data-ttu-id="7f241-102">XML 트리 (Visual Basic)를 직렬화 하는 작업</span><span class="sxs-lookup"><span data-stu-id="7f241-102">Serializing XML Trees (Visual Basic)</span></span>
<span data-ttu-id="7f241-103">XML 트리를 serialize하는 것은 XML 트리에서 XML을 생성하는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="7f241-103">Serializing an XML tree means generating XML from the XML tree.</span></span> <span data-ttu-id="7f241-104">구체적 구현 하는 파일에는 serialize 할 수는 <xref:System.IO.TextWriter>클래스 또는 <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> 의 구체적인 구현을</xref:System.IO.TextWriter></span><span class="sxs-lookup"><span data-stu-id="7f241-104">You can serialize to a file, to a concrete implementation of the <xref:System.IO.TextWriter> class, or to a concrete implementation of an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="7f241-105">serialization의 다양한 측면을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f241-105">You can control various aspects of serialization.</span></span> <span data-ttu-id="7f241-106">예를 들어, serialize된 XML을 들여쓸지 여부와 XML 선언을 쓸지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f241-106">For example, you can control whether to indent the serialized XML, and whether to write an XML declaration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7f241-107">단원 내용</span><span class="sxs-lookup"><span data-stu-id="7f241-107">In This Section</span></span>  
  
|<span data-ttu-id="7f241-108">항목</span><span class="sxs-lookup"><span data-stu-id="7f241-108">Topic</span></span>|<span data-ttu-id="7f241-109">설명</span><span class="sxs-lookup"><span data-stu-id="7f241-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="7f241-110">serialize할 때 공백 유지</span><span class="sxs-lookup"><span data-stu-id="7f241-110">Preserving White Space While Serializing</span></span>](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md)|<span data-ttu-id="7f241-111">XML 트리를 serialize할 때 공백 동작을 제어하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7f241-111">Describes how to control white space behavior when you serialize XML trees.</span></span>|  
|[<span data-ttu-id="7f241-112">XML 선언 (Visual Basic)으로 직렬화 하는 작업</span><span class="sxs-lookup"><span data-stu-id="7f241-112">Serializing with an XML Declaration (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-with-an-xml-declaration.md)|<span data-ttu-id="7f241-113">XML 선언이 포함된 XML 트리를 serialize하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7f241-113">Describes how to serialize an XML tree that includes an XML declaration.</span></span>|  
|[<span data-ttu-id="7f241-114">Files, TextWriters 및 XmlWriters로 serialization</span><span class="sxs-lookup"><span data-stu-id="7f241-114">Serializing to Files, TextWriters, and XmlWriters</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-to-files-textwriters-and-xmlwriters.md)|<span data-ttu-id="7f241-115">문서를 serialize 하는 방법에 설명 된 <xref:System.IO.File>, <xref:System.IO.TextWriter>, 또는 <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.IO.TextWriter> </xref:System.IO.File></span><span class="sxs-lookup"><span data-stu-id="7f241-115">Describes how to serialize a document to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="7f241-116">XmlReader (XSLT 호출)로 직렬화 하는 작업 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f241-116">Serializing to an XmlReader (Invoking XSLT) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-to-an-xmlreader-invoking-xslt.md)|<span data-ttu-id="7f241-117">만드는 방법에 설명 된 <xref:System.Xml.XmlReader>다른 모듈에서 XML 트리의 내용을 읽을 수 있도록 합니다.</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="7f241-117">Describes how to create a <xref:System.Xml.XmlReader> that enables another module to read the contents of an XML tree.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7f241-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7f241-118">See Also</span></span>  
 [<span data-ttu-id="7f241-119">프로그래밍 가이드 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f241-119">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
