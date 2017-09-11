---
title: "LINQ to XML Annotations2 | Microsoft 문서"
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
ms.assetid: c3e8b3ff-fceb-4428-b0ca-1ed6f128aac8
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 97f5386630ba687e4401ee0cfb70f7170e273a53
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017


---
# <a name="linq-to-xml-annotations"></a><span data-ttu-id="23068-102">LINQ to XML 주석</span><span class="sxs-lookup"><span data-stu-id="23068-102">LINQ to XML Annotations</span></span>
<span data-ttu-id="23068-103">주석을 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 임의의 형식 중 임의의 개체를 XML 트리의 XML 구성 요소와 연결할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="23068-103">Annotations in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] enable you to associate any arbitrary object of any arbitrary type with any XML component in an XML tree.</span></span>  
  
 <span data-ttu-id="23068-104">와 같은 XML 구성 요소에 주석을 추가 하려면는 <xref:System.Xml.Linq.XElement>또는 <xref:System.Xml.Linq.XAttribute>를 호출 하면는 <xref:System.Xml.Linq.XObject.AddAnnotation%2A>메서드.</xref:System.Xml.Linq.XObject.AddAnnotation%2A> </xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="23068-104">To add an annotation to an XML component, such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>, you call the <xref:System.Xml.Linq.XObject.AddAnnotation%2A> method.</span></span> <span data-ttu-id="23068-105">형식별로 주석을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23068-105">You retrieve annotations by type.</span></span>  
  
 <span data-ttu-id="23068-106">주석은 XML infoset의 일부가 아니므로 serialize되거나 deserialize되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23068-106">Note that annotations are not part of the XML infoset; they are not serialized or deserialized.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="23068-107">메서드</span><span class="sxs-lookup"><span data-stu-id="23068-107">Methods</span></span>  
 <span data-ttu-id="23068-108">주석 작업을 할 때 다음 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23068-108">You can use the following methods when working with annotations:</span></span>  
  
|<span data-ttu-id="23068-109">메서드</span><span class="sxs-lookup"><span data-stu-id="23068-109">Method</span></span>|<span data-ttu-id="23068-110">설명</span><span class="sxs-lookup"><span data-stu-id="23068-110">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="23068-111"><xref:System.Xml.Linq.XObject.AddAnnotation%2A></xref:System.Xml.Linq.XObject.AddAnnotation%2A></span><span class="sxs-lookup"><span data-stu-id="23068-111"><xref:System.Xml.Linq.XObject.AddAnnotation%2A></span></span>|<span data-ttu-id="23068-112">개체를 <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject> 의 주석 목록에 추가</span><span class="sxs-lookup"><span data-stu-id="23068-112">Adds an object to the annotation list of an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<span data-ttu-id="23068-113"><xref:System.Xml.Linq.XObject.Annotation%2A></xref:System.Xml.Linq.XObject.Annotation%2A></span><span class="sxs-lookup"><span data-stu-id="23068-113"><xref:System.Xml.Linq.XObject.Annotation%2A></span></span>|<span data-ttu-id="23068-114"><xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject> 에서 지정 된 형식의 첫 번째 주석 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="23068-114">Gets the first annotation object of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<span data-ttu-id="23068-115"><xref:System.Xml.Linq.XObject.Annotations%2A></xref:System.Xml.Linq.XObject.Annotations%2A></span><span class="sxs-lookup"><span data-stu-id="23068-115"><xref:System.Xml.Linq.XObject.Annotations%2A></span></span>|<span data-ttu-id="23068-116"><xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject> 에 대 한 지정 된 형식의 주석 컬렉션을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="23068-116">Gets a collection of annotations of the specified type for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<span data-ttu-id="23068-117"><xref:System.Xml.Linq.XObject.RemoveAnnotations%2A></xref:System.Xml.Linq.XObject.RemoveAnnotations%2A></span><span class="sxs-lookup"><span data-stu-id="23068-117"><xref:System.Xml.Linq.XObject.RemoveAnnotations%2A></span></span>|<span data-ttu-id="23068-118"><xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject> 에서 지정 된 형식의 주석을 제거합니다</span><span class="sxs-lookup"><span data-stu-id="23068-118">Removes the annotations of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="23068-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23068-119">See Also</span></span>  
 [<span data-ttu-id="23068-120">고급 LINQ to XML 프로그래밍 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23068-120">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
