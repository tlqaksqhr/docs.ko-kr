---
title: "XML 트리 만들기(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: bccc3e0a-c08c-468e-9d30-e075670fdace
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 23b19593774b5a010b453e3fe755e21386afd015
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="creating-xml-trees-c"></a><span data-ttu-id="5b4f5-102">XML 트리 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="5b4f5-102">Creating XML Trees (C#)</span></span>
<span data-ttu-id="5b4f5-103">가장 일반적인 XML 작업 중 하나는 XML 트리를 생성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5b4f5-103">One of the most common XML tasks is constructing an XML tree.</span></span> <span data-ttu-id="5b4f5-104">이 단원에서는 XML 트리를 만드는 몇 가지 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5b4f5-104">This section describes several ways to create them.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5b4f5-105">단원 내용</span><span class="sxs-lookup"><span data-stu-id="5b4f5-105">In This Section</span></span>  
  
|<span data-ttu-id="5b4f5-106">항목</span><span class="sxs-lookup"><span data-stu-id="5b4f5-106">Topic</span></span>|<span data-ttu-id="5b4f5-107">설명</span><span class="sxs-lookup"><span data-stu-id="5b4f5-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="5b4f5-108">함수 생성(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="5b4f5-108">Functional Construction (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/functional-construction-linq-to-xml.md)|<span data-ttu-id="5b4f5-109">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]의 함수 생성에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5b4f5-109">Provides an overview of functional construction in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span> <span data-ttu-id="5b4f5-110">함수 생성을 통해 단일 문으로 XML 트리를 모두 만들거나 일부만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b4f5-110">Functional construction enables you to create all or part of your XML tree in a single statement.</span></span> <span data-ttu-id="5b4f5-111">또한 XML 트리를 생성할 때 쿼리를 포함하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5b4f5-111">This topic also shows how to embed queries when constructing an XML tree.</span></span>|  
|[<span data-ttu-id="5b4f5-112">C#에서 XML 트리 만들기(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="5b4f5-112">Creating XML Trees in C# (LINQ to XML)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees-linq-to-xml-2.md)|<span data-ttu-id="5b4f5-113">C#에서 트리를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5b4f5-113">Shows how to create trees in C#.</span></span>|  
|[<span data-ttu-id="5b4f5-114">복제와 연결(C#)</span><span class="sxs-lookup"><span data-stu-id="5b4f5-114">Cloning vs. Attaching (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/cloning-vs-attaching.md)|<span data-ttu-id="5b4f5-115">기존 XML 트리의 노드를 추가하는 방법(노드가 복제된 다음 추가됨)과 부모가 없는 노드를 추가하는 방법(노드가 추가되기만 함)의 차이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5b4f5-115">Demonstrates the difference between adding nodes from an existing XML tree (nodes are cloned and then added) and adding nodes with no parent (they are simply attached).</span></span>|  
|[<span data-ttu-id="5b4f5-116">XML 구문 분석(C#)</span><span class="sxs-lookup"><span data-stu-id="5b4f5-116">Parsing XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)|<span data-ttu-id="5b4f5-117">다양한 소스에서 XML의 구문을 분석하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5b4f5-117">Shows how to parse XML from a variety of sources.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="5b4f5-118">은 XML의 구문을 분석하는 데 사용되는 <xref:System.Xml.XmlReader>를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b4f5-118"> is layered on top of <xref:System.Xml.XmlReader>, which is used to parse the XML.</span></span>|  
|[<span data-ttu-id="5b4f5-119">방법: XmlWriter를 사용하여 XML 트리 채우기(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="5b4f5-119">How to: Populate an XML Tree with an XmlWriter (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml.md)|<span data-ttu-id="5b4f5-120"><xref:System.Xml.XmlWriter>를 사용하여 XML 트리를 채우는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5b4f5-120">Shows how to populate an XML tree by using an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="5b4f5-121">방법: XSD를 사용하여 유효성 검사(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="5b4f5-121">How to: Validate Using XSD (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md)|<span data-ttu-id="5b4f5-122">XSD를 사용하여 XML 트리의 유효성을 검사하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5b4f5-122">Shows how to validate an XML tree using XSD.</span></span>|  
|[<span data-ttu-id="5b4f5-123">XElement 및 XDocument 개체의 올바른 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="5b4f5-123">Valid Content of XElement and XDocument Objects</span></span>](../../../../csharp/programming-guide/concepts/linq/valid-content-of-xelement-and-xdocument-objects3.md)|<span data-ttu-id="5b4f5-124">생성자에 전달될 수 있는 유효한 인수에 대해 설명하고 내용을 요소와 문서에 추가하는 데 사용되는 메서드에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5b4f5-124">Describes the valid arguments that can be passed to the constructors and methods that are used to add content to elements and documents.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5b4f5-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b4f5-125">See Also</span></span>  
 [<span data-ttu-id="5b4f5-126">프로그래밍 가이드(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="5b4f5-126">Programming Guide (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
