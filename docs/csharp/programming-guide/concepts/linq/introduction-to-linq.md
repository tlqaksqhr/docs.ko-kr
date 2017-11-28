---
title: "LINQ 소개(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 54874feb-55e5-4ca8-a9d6-1c1127fd7fb1
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6fd14840cfffb1a59949251b26c168aada336de9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="introduction-to-linq-c"></a><span data-ttu-id="18665-102">LINQ 소개(C#)</span><span class="sxs-lookup"><span data-stu-id="18665-102">Introduction to LINQ (C#)</span></span>
<span data-ttu-id="18665-103">LINQ(Language-Integrated Query)는 개체 환경과 데이터 환경 간의 간격을 연결하는 .NET Framework 버전 3.5에서 도입된 혁신입니다.</span><span class="sxs-lookup"><span data-stu-id="18665-103">Language-Integrated Query (LINQ) is an innovation introduced in the .NET Framework version 3.5 that bridges the gap between the world of objects and the world of data.</span></span>  
  
 <span data-ttu-id="18665-104">일반적으로 데이터에 대한 쿼리는 컴파일 시간의 형식 검사나 IntelliSense 지원 없이 간단한 문자열로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="18665-104">Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support.</span></span> <span data-ttu-id="18665-105">또한 SQL 데이터베이스, XML 문서, 다양한 웹 서비스 등의 각 데이터 소스 형식에 대해 서로 다른 쿼리 언어를 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18665-105">Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on.</span></span> <span data-ttu-id="18665-106">LINQ를 사용하면 *쿼리*가 C#의 첫 번째 언어 구문이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18665-106">LINQ makes a *query* a first-class language construct in C#.</span></span> <span data-ttu-id="18665-107">언어 키워드 및 친숙한 연산자를 사용하여 강력한 형식의 개체 컬렉션에 대해 쿼리를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="18665-107">You write queries against strongly typed collections of objects by using language keywords and familiar operators.</span></span>  
  
 <span data-ttu-id="18665-108">SQL Server 데이터베이스, XML 문서, ADO.NET 데이터 집합 및 <xref:System.Collections.IEnumerable> 또는 제네릭 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 지원하는 모든 개체 컬렉션에 대해 C#으로 LINQ 쿼리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18665-108">You can write LINQ queries in C# for SQL Server databases, XML documents, ADO.NET Datasets, and any collection of objects that supports <xref:System.Collections.IEnumerable> or the generic <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="18665-109">LINQ는 많은 웹 서비스 및 기타 데이터베이스 구현을 위해 타사에서도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="18665-109">LINQ support is also provided by third parties for many Web services and other database implementations.</span></span>  
  
 <span data-ttu-id="18665-110">LINQ 쿼리는 새 프로젝트에서 사용하거나 기존 프로젝트에서 LINQ가 아닌 쿼리와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18665-110">You can use LINQ queries in new projects, or alongside non-LINQ queries in existing projects.</span></span> <span data-ttu-id="18665-111">프로젝트가 .NET Framework 3.5 이상을 대상으로 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18665-111">The only requirement is that the project target .NET Framework 3.5 or later.</span></span>  
  
 <span data-ttu-id="18665-112">다음 그림에서는 Visual Studio에서 전체 형식 검사 및 IntelliSense를 지원하는 C#과 Visual Basic을 사용하여 SQL Server 데이터베이스에 대해 부분적으로 완성된 LINQ 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="18665-112">The following illustration from Visual Studio shows a partially-completed LINQ query against a SQL Server database in both C# and Visual Basic with full type checking and IntelliSense support.</span></span>  
  
 <span data-ttu-id="18665-113">![Intellisense를 사용한 LINQ 쿼리](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")</span><span class="sxs-lookup"><span data-stu-id="18665-113">![LINQ query with Intellisense](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="18665-114">다음 단계</span><span class="sxs-lookup"><span data-stu-id="18665-114">Next Steps</span></span>  
 <span data-ttu-id="18665-115">LINQ에 대한 자세한 내용을 알아보려면 [C#에서 LINQ 시작](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)의 시작 섹션에서 몇 가지 기본 개념을 익힌 후 관심 있는 LINQ 기술에 대한 설명서를 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="18665-115">To learn more details about LINQ, start by becoming familiar with some basic concepts in the Getting Started section [Getting Started with LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md), and then read the documentation for the LINQ technology in which you are interested:</span></span>  
  
-   <span data-ttu-id="18665-116">SQL Server 데이터베이스: [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)</span><span class="sxs-lookup"><span data-stu-id="18665-116">SQL Server databases: [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)</span></span>  
  
-   <span data-ttu-id="18665-117">XML 문서: [LINQ to XML(C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="18665-117">XML documents: [LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)</span></span>  
  
-   <span data-ttu-id="18665-118">ADO.NET 데이터 집합: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span><span class="sxs-lookup"><span data-stu-id="18665-118">ADO.NET Datasets: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span></span>  
  
-   <span data-ttu-id="18665-119">.NET 컬렉션, 파일, 문자열 등: [LINQ to Objects(C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)</span><span class="sxs-lookup"><span data-stu-id="18665-119">.NET collections, files, strings and so on: [LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18665-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18665-120">See Also</span></span>  
 [<span data-ttu-id="18665-121">LINQ(Language-Integrated Query)(C#)</span><span class="sxs-lookup"><span data-stu-id="18665-121">Language-Integrated Query (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/index.md)
