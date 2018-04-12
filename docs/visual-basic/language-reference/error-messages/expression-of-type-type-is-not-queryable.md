---
title: 형식의 식은 &lt;형식&gt; 를 쿼리할 수 없습니다
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3f2b98bf48f0b3965929f9211c2944ff97754f23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="expression-of-type-lttypegt-is-not-queryable"></a><span data-ttu-id="5b912-102">형식의 식은 &lt;형식&gt; 를 쿼리할 수 없습니다</span><span class="sxs-lookup"><span data-stu-id="5b912-102">Expression of type &lt;type&gt; is not queryable</span></span>
<span data-ttu-id="5b912-103">형식의 식은 \<유형 >를 쿼리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b912-103">Expression of type \<type> is not queryable.</span></span> <span data-ttu-id="5b912-104">LINQ 공급자에 대 한 어셈블리 참조 및/또는 네임 스페이스 가져오기 누락 되지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b912-104">Make sure you are not missing an assembly reference and/or namespace import for the LINQ provider.</span></span>  
  
 <span data-ttu-id="5b912-105">쿼리 가능 형식에 정의 된는 <xref:System.Linq>, <xref:System.Data.Linq>, 및 <xref:System.Xml.Linq> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="5b912-105">Queryable types are defined in the <xref:System.Linq>, <xref:System.Data.Linq>, and <xref:System.Xml.Linq> namespaces.</span></span> <span data-ttu-id="5b912-106">LINQ 쿼리를 수행 하려면 이러한 네임 스페이스 중 하나 이상을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b912-106">You must import one or more of these namespaces to perform LINQ queries.</span></span>  
  
 <span data-ttu-id="5b912-107"><xref:System.Linq> 네임 스페이스를 사용 하면 컬렉션 및 배열에 같은 쿼리 개체에 LINQ를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b912-107">The <xref:System.Linq> namespace enables you to query objects such as collections and arrays by using LINQ.</span></span>  
  
 <span data-ttu-id="5b912-108"><xref:System.Data.Linq> 네임 스페이스를 사용 하면 LINQ를 사용 하 여 ADO.NET 데이터 집합 및 SQL Server 데이터베이스를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b912-108">The <xref:System.Data.Linq> namespace enables you to query ADO.NET Datasets and SQL Server databases by using LINQ.</span></span>  
  
 <span data-ttu-id="5b912-109"><xref:System.Xml.Linq> 네임 스페이스를 사용 하면 XML 쿼리를 Visual Basic의 XML 기능을 사용 하 고 LINQ를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b912-109">The <xref:System.Xml.Linq> namespace enables you to query XML by using LINQ and to use XML features in Visual Basic.</span></span>  
  
 <span data-ttu-id="5b912-110">**오류 ID:** BC36593</span><span class="sxs-lookup"><span data-stu-id="5b912-110">**Error ID:** BC36593</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5b912-111">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="5b912-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="5b912-112">추가 `Import` 문에 <xref:System.Linq>, <xref:System.Data.Linq>, 또는 <xref:System.Xml.Linq> 코드 파일에 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="5b912-112">Add an `Import` statement for the <xref:System.Linq>, <xref:System.Data.Linq>, or <xref:System.Xml.Linq> namespace to your code file.</span></span> <span data-ttu-id="5b912-113">사용 하 여 프로젝트에 대 한 네임 스페이스를 가져올 수도 있습니다는 **참조** 프로젝트 디자이너의 페이지 (**My Project**).</span><span class="sxs-lookup"><span data-stu-id="5b912-113">You can also import namespaces for your project by using the **References** page of the Project Designer (**My Project**).</span></span>  
  
2.  <span data-ttu-id="5b912-114">쿼리의 소스는 쿼리 가능 형식으로 확인 된 형식을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b912-114">Ensure that the type that you have identified as the source of your query is a queryable type.</span></span> <span data-ttu-id="5b912-115">구현 하는 형식 즉, <xref:System.Collections.Generic.IEnumerable%601> 또는 <xref:System.Linq.IQueryable%601>합니다.</span><span class="sxs-lookup"><span data-stu-id="5b912-115">That is, a type that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b912-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b912-116">See Also</span></span>  
 <xref:System.Linq>  
 <xref:System.Data.Linq>  
 <xref:System.Xml.Linq>  
 [<span data-ttu-id="5b912-117">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="5b912-117">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="5b912-118">LINQ</span><span class="sxs-lookup"><span data-stu-id="5b912-118">LINQ</span></span>](../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="5b912-119">XML</span><span class="sxs-lookup"><span data-stu-id="5b912-119">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="5b912-120">참조 및 Imports 문</span><span class="sxs-lookup"><span data-stu-id="5b912-120">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [<span data-ttu-id="5b912-121">Imports 문(.NET 네임스페이스 및 형식)</span><span class="sxs-lookup"><span data-stu-id="5b912-121">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="5b912-122">프로젝트 디자이너, 참조 페이지(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b912-122">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
