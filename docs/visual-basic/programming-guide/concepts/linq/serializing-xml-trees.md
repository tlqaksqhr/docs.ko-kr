---
title: "XML 트리 (Visual Basic)를 직렬화 하는 작업"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c340695-a726-4030-85be-6975d8a149cf
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 924c4dace92ed306852cd1d7d2fead8588d03dc4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="serializing-xml-trees-visual-basic"></a><span data-ttu-id="93be2-102">XML 트리 (Visual Basic)를 직렬화 하는 작업</span><span class="sxs-lookup"><span data-stu-id="93be2-102">Serializing XML Trees (Visual Basic)</span></span>
<span data-ttu-id="93be2-103">XML 트리를 serialize하는 것은 XML 트리에서 XML을 생성하는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="93be2-103">Serializing an XML tree means generating XML from the XML tree.</span></span> <span data-ttu-id="93be2-104">파일, <xref:System.IO.TextWriter> 클래스의 구체적 구현 또는 <xref:System.Xml.XmlWriter>의 구체적 구현으로 serialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93be2-104">You can serialize to a file, to a concrete implementation of the <xref:System.IO.TextWriter> class, or to a concrete implementation of an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="93be2-105">serialization의 다양한 측면을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93be2-105">You can control various aspects of serialization.</span></span> <span data-ttu-id="93be2-106">예를 들어, serialize된 XML을 들여쓸지 여부와 XML 선언을 쓸지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93be2-106">For example, you can control whether to indent the serialized XML, and whether to write an XML declaration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="93be2-107">단원 내용</span><span class="sxs-lookup"><span data-stu-id="93be2-107">In This Section</span></span>  
  
|<span data-ttu-id="93be2-108">항목</span><span class="sxs-lookup"><span data-stu-id="93be2-108">Topic</span></span>|<span data-ttu-id="93be2-109">설명</span><span class="sxs-lookup"><span data-stu-id="93be2-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="93be2-110">serialize할 때 공백 유지</span><span class="sxs-lookup"><span data-stu-id="93be2-110">Preserving White Space While Serializing</span></span>](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md)|<span data-ttu-id="93be2-111">XML 트리를 serialize할 때 공백 동작을 제어하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="93be2-111">Describes how to control white space behavior when you serialize XML trees.</span></span>|  
|[<span data-ttu-id="93be2-112">XML 선언 (Visual Basic)으로 직렬화 하는 작업</span><span class="sxs-lookup"><span data-stu-id="93be2-112">Serializing with an XML Declaration (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-with-an-xml-declaration.md)|<span data-ttu-id="93be2-113">XML 선언이 포함된 XML 트리를 serialize하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="93be2-113">Describes how to serialize an XML tree that includes an XML declaration.</span></span>|  
|[<span data-ttu-id="93be2-114">Files, TextWriters 및 XmlWriters로 serialization</span><span class="sxs-lookup"><span data-stu-id="93be2-114">Serializing to Files, TextWriters, and XmlWriters</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-to-files-textwriters-and-xmlwriters.md)|<span data-ttu-id="93be2-115">문서를 <xref:System.IO.File>, <xref:System.IO.TextWriter> 또는 <xref:System.Xml.XmlWriter>로 serialize하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="93be2-115">Describes how to serialize a document to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="93be2-116">XmlReader (XSLT 호출)에 대 한 직렬화 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93be2-116">Serializing to an XmlReader (Invoking XSLT) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-to-an-xmlreader-invoking-xslt.md)|<span data-ttu-id="93be2-117">다른 모듈에서 XML 트리의 내용을 읽을 수 있도록 하는 <xref:System.Xml.XmlReader>를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="93be2-117">Describes how to create a <xref:System.Xml.XmlReader> that enables another module to read the contents of an XML tree.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="93be2-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93be2-118">See Also</span></span>  
 [<span data-ttu-id="93be2-119">프로그래밍 가이드 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93be2-119">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
