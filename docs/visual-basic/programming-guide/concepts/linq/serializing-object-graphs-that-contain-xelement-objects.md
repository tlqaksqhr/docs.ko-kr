---
title: "XElement 개체 (Visual Basic)를 포함 하는 개체 그래프를 직렬화 하는 작업 | Microsoft 문서"
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
ms.assetid: c0cc5c92-5ca3-44b1-98dd-371601df721b
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
ms.openlocfilehash: ce026e68aa95e6d02b46f9b985ee9ee3a268efb3
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="serializing-object-graphs-that-contain-xelement-objects-visual-basic"></a><span data-ttu-id="42660-102">XElement 개체 (Visual Basic)를 포함 하는 개체 그래프를 직렬화 하는 작업</span><span class="sxs-lookup"><span data-stu-id="42660-102">Serializing Object Graphs that Contain XElement Objects (Visual Basic)</span></span>
<span data-ttu-id="42660-103">이 항목에서는 <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> 형식의 개체에 대 한 참조가 포함 된 개체 그래프를 직렬화 하는 작업의 기능을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="42660-103">This topic introduces the capability of serializing object graphs that contain references to objects of type <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="42660-104">본사로이 직렬화 할이 유형의 <xref:System.Xml.Linq.XElement>구현 하는 <xref:System.Xml.Serialization.IXmlSerializable>인터페이스.</xref:System.Xml.Serialization.IXmlSerializable> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="42660-104">To facility this type of serializing, <xref:System.Xml.Linq.XElement> implements the <xref:System.Xml.Serialization.IXmlSerializable> interface.</span></span>  
  
 <span data-ttu-id="42660-105">만 <xref:System.Xml.Linq.XElement>클래스는 serialization을 구현 합니다.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="42660-105">Note that only the <xref:System.Xml.Linq.XElement> class implements serialization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="42660-106">단원 내용</span><span class="sxs-lookup"><span data-stu-id="42660-106">In This Section</span></span>  
  
|<span data-ttu-id="42660-107">항목</span><span class="sxs-lookup"><span data-stu-id="42660-107">Topic</span></span>|<span data-ttu-id="42660-108">설명</span><span class="sxs-lookup"><span data-stu-id="42660-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="42660-109">방법: XmlSerializer (Visual Basic)를 사용 하 여 Serialize</span><span class="sxs-lookup"><span data-stu-id="42660-109">How to: Serialize Using XmlSerializer (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)|<span data-ttu-id="42660-110"><xref:System.Xml.Serialization.XmlSerializer>.</xref:System.Xml.Serialization.XmlSerializer> 를 사용 하 여 serialize 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="42660-110">Demonstrates how to serialize using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
|[<span data-ttu-id="42660-111">방법: DataContractSerializer (Visual Basic)를 사용 하 여 Serialize</span><span class="sxs-lookup"><span data-stu-id="42660-111">How to: Serialize Using DataContractSerializer (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-serialize-using-datacontractserializer.md)|<span data-ttu-id="42660-112"><xref:System.Runtime.Serialization.DataContractSerializer>.</xref:System.Runtime.Serialization.DataContractSerializer> 를 사용 하 여 serialize 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="42660-112">Demonstrates how to serialize using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="42660-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="42660-113">See Also</span></span>  
 [<span data-ttu-id="42660-114">고급 LINQ to XML 프로그래밍 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="42660-114">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
