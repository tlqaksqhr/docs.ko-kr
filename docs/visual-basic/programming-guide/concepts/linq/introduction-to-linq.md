---
title: "LINQ (Visual Basic) 소개 | Microsoft 문서"
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
ms.assetid: c6339c12-9b2d-433e-961c-0d2b7f0091c2
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
ms.openlocfilehash: d2c02daacc2674da31715e5fda027b97e6b7bc97
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="introduction-to-linq-visual-basic"></a><span data-ttu-id="7fa28-102">LINQ (Visual Basic) 소개</span><span class="sxs-lookup"><span data-stu-id="7fa28-102">Introduction to LINQ (Visual Basic)</span></span>
<span data-ttu-id="7fa28-103">언어 통합 쿼리 (LINQ) 혁신적.NET Framework 버전 3.5에에서는 연결 개체와 데이터 간의 차이.</span><span class="sxs-lookup"><span data-stu-id="7fa28-103">Language-Integrated Query (LINQ) is an innovation introduced in the .NET Framework version 3.5 that bridges the gap between the world of objects and the world of data.</span></span>  
  
 <span data-ttu-id="7fa28-104">일반적으로 데이터에 대 한 쿼리는 간단한 문자열 시 형식 검사 없이 컴파일 또는 IntelliSense 지원으로 표현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fa28-104">Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support.</span></span> <span data-ttu-id="7fa28-105">또한 데이터 원본의 각 유형에 서로 다른 쿼리 언어를 배울 필요가: SQL 데이터베이스, XML 문서, 다양 한 웹 서비스 및 등입니다.</span><span class="sxs-lookup"><span data-stu-id="7fa28-105">Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on.</span></span> <span data-ttu-id="7fa28-106">LINQ를 사용 하면 한 *쿼리* Visual Basic의 고급 언어 구문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fa28-106">LINQ makes a *query* a first-class language construct in Visual Basic.</span></span> <span data-ttu-id="7fa28-107">언어 키워드 및 친숙 한 연산자를 사용 하 여 강력한 형식의 컬렉션 개체에 대 한 쿼리를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa28-107">You write queries against strongly typed collections of objects by using language keywords and familiar operators.</span></span>  
  
 <span data-ttu-id="7fa28-108">SQL Server 데이터베이스, XML 문서, ADO.NET 데이터 집합 및 지 원하는 개체의 컬렉션에 대 한 Visual Basic의 LINQ 쿼리를 작성할 수 <xref:System.Collections.IEnumerable>또는 제네릭 <xref:System.Collections.Generic.IEnumerable%601>인터페이스.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="7fa28-108">You can write LINQ queries in Visual Basic for SQL Server databases, XML documents, ADO.NET Datasets, and any collection of objects that supports <xref:System.Collections.IEnumerable> or the generic <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="7fa28-109">LINQ 지원 많은 웹 서비스 및 기타 데이터베이스 구현에 대 한 타사에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fa28-109">LINQ support is also provided by third parties for many Web services and other database implementations.</span></span>  
  
 <span data-ttu-id="7fa28-110">새 프로젝트 또는 기존 프로젝트에서 LINQ가 아닌 쿼리와 함께 LINQ 쿼리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fa28-110">You can use LINQ queries in new projects, or alongside non-LINQ queries in existing projects.</span></span> <span data-ttu-id="7fa28-111">유일한 요구 사항은 프로젝트에서.NET Framework 3.5 이상을 대상으로 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="7fa28-111">The only requirement is that the project target .NET Framework 3.5 or later.</span></span>  
  
 <span data-ttu-id="7fa28-112">Visual Studio에서 다음 그림 전체 형식 검사 및 IntelliSense 지원을 사용 하 여 C# 및 Visual Basic에는 SQL Server 데이터베이스에 대해 부분적으로 완료 LINQ 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7fa28-112">The following illustration from Visual Studio shows a partially-completed LINQ query against a SQL Server database in both C# and Visual Basic with full type checking and IntelliSense support.</span></span>  
  
 <span data-ttu-id="7fa28-113">![Intellisense 사용한 LINQ 쿼리](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")</span><span class="sxs-lookup"><span data-stu-id="7fa28-113">![LINQ query with Intellisense](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7fa28-114">다음 단계</span><span class="sxs-lookup"><span data-stu-id="7fa28-114">Next Steps</span></span>  
 <span data-ttu-id="7fa28-115">LINQ에 대 한 자세한 내용은 알아보려면 시작 하기 섹션의 몇 가지 기본 개념에 익숙해지는 것부터 시작 [Visual Basic에서 LINQ 시작](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md), 관심이 있는 LINQ 기술에 대 한 설명서를 참고 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7fa28-115">To learn more details about LINQ, start by becoming familiar with some basic concepts in the Getting Started section [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md), and then read the documentation for the LINQ technology in which you are interested:</span></span>  
  
-   <span data-ttu-id="7fa28-116">SQL Server 데이터베이스: [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)</span><span class="sxs-lookup"><span data-stu-id="7fa28-116">SQL Server databases: [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)</span></span>  
  
-   <span data-ttu-id="7fa28-117">XML 문서: [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="7fa28-117">XML documents: [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)</span></span>  
  
-   <span data-ttu-id="7fa28-118">ADO.NET 데이터 집합: [LINQ to DataSet](http://msdn.microsoft.com/library/743e3755-3ecb-45a2-8d9b-9ed41f0dcf17)</span><span class="sxs-lookup"><span data-stu-id="7fa28-118">ADO.NET Datasets: [LINQ to DataSet](http://msdn.microsoft.com/library/743e3755-3ecb-45a2-8d9b-9ed41f0dcf17)</span></span>  
  
-   <span data-ttu-id="7fa28-119">.NET 컬렉션, 파일, 문자열 등: [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)</span><span class="sxs-lookup"><span data-stu-id="7fa28-119">.NET collections, files, strings and so on: [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fa28-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7fa28-120">See Also</span></span>  
 [<span data-ttu-id="7fa28-121">언어 통합 쿼리 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7fa28-121">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)
