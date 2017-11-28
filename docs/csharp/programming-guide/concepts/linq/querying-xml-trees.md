---
title: "XML 트리 쿼리(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 0913d81b-541a-4fd4-9cbf-7ec89fd817ea
caps.latest.revision: "4"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 66028510b57981879412a1c2a161652adde340bd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="querying-xml-trees-c"></a><span data-ttu-id="51f29-102">XML 트리 쿼리(C#)</span><span class="sxs-lookup"><span data-stu-id="51f29-102">Querying XML Trees (C#)</span></span>
<span data-ttu-id="51f29-103">이 단원에서는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 쿼리의 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="51f29-103">This section provides examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>  
  
 <span data-ttu-id="51f29-104">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 쓰기에 대한 자세한 내용은 [C#에서 LINQ 시작](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51f29-104">For more information about writing [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, see [Getting Started with LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md).</span></span>  
  
 <span data-ttu-id="51f29-105">XML 트리를 인스턴스화한 후에는 쿼리를 작성하는 것이 트리에서 데이터를 추출하는 가장 효과적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="51f29-105">After you have instantiated an XML tree, writing queries is the most effective way to extract data from the tree.</span></span> <span data-ttu-id="51f29-106">또한 함수 생성과 함께 쿼리를 수행하여 원래 문서와 모양이 다른 XML 문서를 새로 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51f29-106">Also, querying combined with functional construction enables you to generate a new XML document that has a different shape from the original document.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="51f29-107">단원 내용</span><span class="sxs-lookup"><span data-stu-id="51f29-107">In This Section</span></span>  
  
|<span data-ttu-id="51f29-108">항목</span><span class="sxs-lookup"><span data-stu-id="51f29-108">Topic</span></span>|<span data-ttu-id="51f29-109">설명</span><span class="sxs-lookup"><span data-stu-id="51f29-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="51f29-110">기본 쿼리(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="51f29-110">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)|<span data-ttu-id="51f29-111">XML 트리를 쿼리하는 일반적인 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="51f29-111">Provides common examples of querying XML trees.</span></span>|  
|[<span data-ttu-id="51f29-112">프로젝션 및 변환(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="51f29-112">Projections and Transformations (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)|<span data-ttu-id="51f29-113">XML 트리에서 프로젝션하고 XML 트리를 변환하는 일반적인 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="51f29-113">Provides common examples of projecting from and transforming XML trees.</span></span>|  
|[<span data-ttu-id="51f29-114">고급 쿼리 기술(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="51f29-114">Advanced Query Techniques (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)|<span data-ttu-id="51f29-115">고급 시나리오에 유용한 쿼리 기법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="51f29-115">Provides query techniques that are useful in more advanced scenarios.</span></span>|  
|[<span data-ttu-id="51f29-116">XPath 사용자를 위한 LINQ to XML(C#)</span><span class="sxs-lookup"><span data-stu-id="51f29-116">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)|<span data-ttu-id="51f29-117">다양한 XPath 식과 각 XPath 식에 해당하는 동일한 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="51f29-117">Presents a number of XPath expressions and their [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] equivalents.</span></span>|  
|[<span data-ttu-id="51f29-118">XML의 순수 함수 변환(C#)</span><span class="sxs-lookup"><span data-stu-id="51f29-118">Pure Functional Transformations of XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)|<span data-ttu-id="51f29-119">함수형 프로그래밍의 스타일로 쿼리를 작성하는 방법에 대한 간단한 자습서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="51f29-119">Presents a small tutorial on writing queries in the style of functional programming.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="51f29-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="51f29-120">See Also</span></span>  
 [<span data-ttu-id="51f29-121">프로그래밍 가이드(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="51f29-121">Programming Guide (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)  
 [<span data-ttu-id="51f29-122">C#에서 LINQ 시작</span><span class="sxs-lookup"><span data-stu-id="51f29-122">Getting Started with LINQ in C#</span></span>](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
