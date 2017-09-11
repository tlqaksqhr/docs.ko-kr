---
title: "프로그래밍 가이드(LINQ to XML)(C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 4b1ffd10-ab81-4a0d-a0ca-e9876478d924
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ed4b0aff72654b9ac0928fae933e34268aede7fe
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="programming-guide-linq-to-xml-c"></a><span data-ttu-id="1de40-102">프로그래밍 가이드(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="1de40-102">Programming Guide (LINQ to XML) (C#)</span></span>
<span data-ttu-id="1de40-103">이 단원에서는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]을 사용한 프로그래밍의 개념과 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1de40-103">This section provides conceptual and how-to information about programming with [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
## <a name="who-should-read-this-documentation"></a><span data-ttu-id="1de40-104">이 설명서를 읽을 대상</span><span class="sxs-lookup"><span data-stu-id="1de40-104">Who Should Read This Documentation</span></span>  
 <span data-ttu-id="1de40-105">이 설명서는 C#과 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]의 기본적인 내용을 알고 있는 개발자를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de40-105">This documentation targets developers who already understand C# and some basic aspects of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>  
  
 <span data-ttu-id="1de40-106">이 설명서의 목표는 모든 개발자가 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]을 쉽게 사용할 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1de40-106">The goal of this documentation is to make [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] easy to use for all kinds of developers.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="1de40-107">을 사용하면 XML을 쉽게 프로그래밍할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1de40-107"> makes XML programming easier.</span></span> <span data-ttu-id="1de40-108">전문 개발자가 아니어도 LINQ to XML을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1de40-108">You do not have to be an expert developer to use it.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="1de40-109">은 제네릭 클래스에 크게 의존하므로</span><span class="sxs-lookup"><span data-stu-id="1de40-109"> relies heavily on generic classes.</span></span> <span data-ttu-id="1de40-110">제네릭 클래스의 사용에 대해 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1de40-110">Therefore, is very important that you understand the use of generic classes.</span></span> <span data-ttu-id="1de40-111">또한 매개 변수가 있는 형식으로 선언된 대리자에 대해 알고 있으면 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1de40-111">Further, it is helpful if you are familiar with delegates that are declared as parameterized types.</span></span> <span data-ttu-id="1de40-112">C# 제네릭 클래스에 대해 잘 모르는 경우에는 [제네릭 클래스](../../../../csharp/programming-guide/generics/generic-classes.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1de40-112">If you are not familiar with C# generic classes, see [Generic Classes](../../../../csharp/programming-guide/generics/generic-classes.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1de40-113">단원 내용</span><span class="sxs-lookup"><span data-stu-id="1de40-113">In This Section</span></span>  
  
|<span data-ttu-id="1de40-114">항목</span><span class="sxs-lookup"><span data-stu-id="1de40-114">Topic</span></span>|<span data-ttu-id="1de40-115">설명</span><span class="sxs-lookup"><span data-stu-id="1de40-115">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="1de40-116">LINQ to XML 프로그래밍 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="1de40-116">LINQ to XML Programming Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)|<span data-ttu-id="1de40-117">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 클래스에 대해 간략하게 설명하고 가장 중요한 클래스 중 <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XAttribute> 및 <xref:System.Xml.Linq.XDocument> 클래스에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1de40-117">Provides an overview of the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] classes, and detailed information about three of the most important classes: <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XAttribute>, and <xref:System.Xml.Linq.XDocument>.</span></span>|  
|[<span data-ttu-id="1de40-118">XML 트리 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="1de40-118">Creating XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)|<span data-ttu-id="1de40-119">XML 트리 생성의 개념과 작업에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1de40-119">Provides conceptual and task-based information about creating XML trees.</span></span> <span data-ttu-id="1de40-120">함수 생성을 사용하거나 문자열이나 파일에서 XML 텍스트의 구문을 분석하여 XML 트리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1de40-120">You can create XML trees by using functional construction, or by parsing XML text from a string or a file.</span></span> <span data-ttu-id="1de40-121">또한 <xref:System.Xml.XmlReader>를 사용하여 XML 트리를 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1de40-121">You can also use an <xref:System.Xml.XmlReader> to populate an XML tree.</span></span>|  
|[<span data-ttu-id="1de40-122">XML 네임스페이스 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="1de40-122">Working with XML Namespaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)|<span data-ttu-id="1de40-123">네임스페이스를 사용하는 XML 트리를 만드는 데 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1de40-123">Provides detailed information about creating XML trees that use namespaces.</span></span>|  
|[<span data-ttu-id="1de40-124">XML 트리 serialize(C#)</span><span class="sxs-lookup"><span data-stu-id="1de40-124">Serializing XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)|<span data-ttu-id="1de40-125">XML 트리를 serialize하는 여러 방법에 대해 설명하고 사용할 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1de40-125">Describes multiple approaches to serializing an XML tree, and gives guidance on which approach to use.</span></span>|  
|[<span data-ttu-id="1de40-126">LINQ to XML 축(C#)</span><span class="sxs-lookup"><span data-stu-id="1de40-126">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)|<span data-ttu-id="1de40-127">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 쿼리를 작성하기 전에 이해해야 하는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 축 메서드를 열거하고 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1de40-127">Enumerates and describes the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] axis methods, which you must understand before you can write [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>|  
|[<span data-ttu-id="1de40-128">XML 트리 쿼리(C#)</span><span class="sxs-lookup"><span data-stu-id="1de40-128">Querying XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/querying-xml-trees.md)|<span data-ttu-id="1de40-129">XML 트리를 쿼리하는 일반적인 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1de40-129">Provides common examples of querying XML trees.</span></span>|  
|[<span data-ttu-id="1de40-130">XML 트리 수정(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="1de40-130">Modifying XML Trees (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)|<span data-ttu-id="1de40-131">DOM(문서 개체 모델)과 마찬가지로, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]을 통해서도 메모리 내 XML 트리를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1de40-131">Like the Document Object Model (DOM), [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] enables you to modify an XML tree in place.</span></span>|  
|[<span data-ttu-id="1de40-132">고급 LINQ to XML 프로그래밍(C#)</span><span class="sxs-lookup"><span data-stu-id="1de40-132">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)|<span data-ttu-id="1de40-133">주석, 이벤트, 스트리밍 및 기타 고급 시나리오에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1de40-133">Provides information about annotations, events, streaming, and other advanced scenarios.</span></span>|  
|[<span data-ttu-id="1de40-134">LINQ to XML 보안(C#)</span><span class="sxs-lookup"><span data-stu-id="1de40-134">LINQ to XML Security (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-security.md)|<span data-ttu-id="1de40-135">LINQ to XML과 관련된 보안 문제에 대해 설명하고 보안 노출을 줄이기 위한 몇 가지 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1de40-135">Describes security issues associated with LINQ to XML and provides some guidance for mitigating security exposure.</span></span>|  
|[<span data-ttu-id="1de40-136">샘플 XML 문서(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="1de40-136">Sample XML Documents (LINQ to XML)</span></span>](../../../../csharp/programming-guide/concepts/linq/sample-xml-documents-linq-to-xml.md)|<span data-ttu-id="1de40-137">이 설명서의 많은 예제에서 사용하는 샘플 XML 문서가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1de40-137">Contains the sample XML documents that are used by many examples in this documentation.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1de40-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1de40-138">See Also</span></span>  
 <span data-ttu-id="1de40-139">[시작(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/getting-started-linq-to-xml.md) </span><span class="sxs-lookup"><span data-stu-id="1de40-139">[Getting Started (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/getting-started-linq-to-xml.md) </span></span>  
 [<span data-ttu-id="1de40-140">LINQ to XML(C#)</span><span class="sxs-lookup"><span data-stu-id="1de40-140">LINQ to XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)

