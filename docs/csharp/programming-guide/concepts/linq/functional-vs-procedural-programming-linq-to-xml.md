---
title: "함수형 프로그래밍과 절차적 프로그래밍 비교(LINQ to XML)(C#)"
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
ms.assetid: fc64e39c-a487-4882-9169-da4de97917d9
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
ms.openlocfilehash: 0920206524f9ff93a6be2acdb230f59c244840f7
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="functional-vs-procedural-programming-linq-to-xml-c"></a><span data-ttu-id="1d679-102">함수형 프로그래밍과 절차적 프로그래밍 비교(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="1d679-102">Functional vs. Procedural Programming (LINQ to XML) (C#)</span></span>
<span data-ttu-id="1d679-103">다양한 유형의 XML 응용 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d679-103">There are various types of XML applications:</span></span>  
  
-   <span data-ttu-id="1d679-104">일부 응용 프로그램에서는 소스 XML 문서를 사용하여 소스 문서와 모양이 다른 새 XML 문서를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1d679-104">Some applications take source XML documents, and produce new XML documents that are in a different shape than the source documents.</span></span>  
  
-   <span data-ttu-id="1d679-105">소스 XML 문서를 사용하여 HTML 또는 CSV 텍스트 파일과 같이 완전히 다른 형태의 결과 문서를 생성하는 응용 프로그램도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d679-105">Some applications take source XML documents, and produce result documents in an entirely different form, such as HTML or CSV text files.</span></span>  
  
-   <span data-ttu-id="1d679-106">어떤 응용 프로그램에서는 소스 XML 문서를 사용하여 데이터베이스에 레코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="1d679-106">Some applications take source XML documents, and insert records into a database.</span></span>  
  
-   <span data-ttu-id="1d679-107">데이터베이스 등의 다른 소스에서 데이터를 가져와서 해당 데이터로 XML 문서를 만드는 응용 프로그램도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d679-107">Some applications take data from another source, such as a database, and create XML documents from it.</span></span>  
  
 <span data-ttu-id="1d679-108">이러한 응용 프로그램이 XML 응용 프로그램의 모든 유형은 아니지만 XML 프로그래머가 구현해야 하는 기능 유형의 대표적인 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1d679-108">These are not all of the types of XML applications, but these are a representative set of the types of functionality that an XML programmer has to implement.</span></span>  
  
 <span data-ttu-id="1d679-109">이러한 유형의 응용 프로그램에는 개발자가 선택할 수 있는 두 가지 대조적인 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d679-109">With all of these types of applications, there are two contrasting approaches that a developer can take:</span></span>  
  
-   <span data-ttu-id="1d679-110">선언적 방법을 사용하는 함수 생성</span><span class="sxs-lookup"><span data-stu-id="1d679-110">Functional construction using a declarative approach.</span></span>  
  
-   <span data-ttu-id="1d679-111">절차적 코드를 사용하는 메모리 내 XML 트리 수정</span><span class="sxs-lookup"><span data-stu-id="1d679-111">In-memory XML tree modification using procedural code.</span></span>  
  
 <span data-ttu-id="1d679-112">LINQ to XML에서는 두 방법을 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1d679-112">LINQ to XML supports both approaches.</span></span>  
  
 <span data-ttu-id="1d679-113">함수 방법을 사용하는 경우 소스 문서를 사용하여 원하는 모양의 완전히 새로운 결과 문서를 생성하는 변환을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="1d679-113">When using the functional approach, you write transformations that take the source documents and generate completely new result documents with the desired shape.</span></span>  
  
 <span data-ttu-id="1d679-114">메모리 내 XML 트리를 수정하는 경우 메모리 내 XML 트리의 노드를 트래버스하고 탐색하여 필요에 따라 노드를 삽입, 삭제 및 수정하는 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="1d679-114">When modifying an XML tree in place, you write code that traverses and navigates through nodes in an in-memory XML tree, inserting, deleting, and modifying nodes as necessary.</span></span>  
  
 <span data-ttu-id="1d679-115">두 방법 중 하나로 LINQ to XML을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d679-115">You can use LINQ to XML with either approach.</span></span> <span data-ttu-id="1d679-116">두 방법은 동일한 클래스를 사용하며 경우에 따라 동일한 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d679-116">You use the same classes, and in some cases the same methods.</span></span> <span data-ttu-id="1d679-117">그러나 두 방법의 구조와 목표는 매우 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1d679-117">However, the structure and goals of the two approaches are very different.</span></span> <span data-ttu-id="1d679-118">예를 들어 상황에 따라 성능이 높고 메모리를 적게 사용하는 방법이 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="1d679-118">For example, in different situations, one or the other approach will often have better performance, and use more or less memory.</span></span> <span data-ttu-id="1d679-119">또한 유지 관리하기가 더 쉬운 코드를 작성하고 생성하는 것이 용이한 방법도 상황에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1d679-119">In addition, one or the other approach will be easier to write and yield more maintainable code.</span></span>  
  
 <span data-ttu-id="1d679-120">두 방법을 대조하는 내용을 보려면 [메모리 내 XML 트리 수정과 함수 생성 비교(LINQ to XML)(C#)](../../../../csharp/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d679-120">To see the two approaches contrasted, see [In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="1d679-121">함수 변환 작성에 대한 자습서는 [XML의 순수 함수 변환(C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d679-121">For a tutorial on writing functional transformations, see [Pure Functional Transformations of XML (C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d679-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d679-122">See Also</span></span>  
 [<span data-ttu-id="1d679-123">LINQ to XML 프로그래밍 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="1d679-123">LINQ to XML Programming Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)

