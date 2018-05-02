---
title: LINQ to ADO.NET(포털 페이지)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.topic: article
ms.assetid: 6bd269b4-3509-4688-b672-836008704182
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: af0118ecf6ebe2beecf4037c403b58559b108a8d
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="linq-to-adonet-portal-page"></a><span data-ttu-id="beeb1-102">LINQ to ADO.NET(포털 페이지)</span><span class="sxs-lookup"><span data-stu-id="beeb1-102">LINQ to ADO.NET (Portal Page)</span></span>
[!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)]<span data-ttu-id="beeb1-103">를 사용하면 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] 프로그래밍 모델을 통해 [!INCLUDE[vstecado](~/includes/vstecado-md.md)]의 열거 가능한 개체를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beeb1-103"> enables you to query over any enumerable object in [!INCLUDE[vstecado](~/includes/vstecado-md.md)] by using the [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] programming model.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="beeb1-104">[!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)] 설명서는 .NET Framework SDK의 ADO.NET 섹션인 [LINQ 및 ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beeb1-104">The [!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)] documentation is located in the ADO.NET section of the .NET Framework SDK: [LINQ and ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec).</span></span>  
  
 <span data-ttu-id="beeb1-105">ADO.NET에는 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)], [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)] 및 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]의 세 가지 독립적인 [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)] 기술이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beeb1-105">There are three separate ADO.NET [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] technologies: [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)], [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], and [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)].</span></span> [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)]<span data-ttu-id="beeb1-106">는 다양한 기능을 사용하여 <xref:System.Data.DataSet>에 대해 최적화된 쿼리를 수행하는 데 사용되고, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]은 SQL Server 데이터베이스 스키마를 직접 쿼리하는 데 사용되며, [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)]는 [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)]를 쿼리하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="beeb1-106"> provides richer, optimized querying over the <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] enables you to directly query SQL Server database schemas, and [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)] allows you to query an [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)].</span></span>  
  
## <a name="linq-to-dataset"></a><span data-ttu-id="beeb1-107">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="beeb1-107">LINQ to DataSet</span></span>  
 <span data-ttu-id="beeb1-108"><xref:System.Data.DataSet>는 [!INCLUDE[vstecado](~/includes/vstecado-md.md)]에서 가장 널리 사용되는 구성 요소 중 하나이며, [!INCLUDE[vstecado](~/includes/vstecado-md.md)]의 기반이 되는 연결되지 않은 프로그래밍 모델의 핵심 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="beeb1-108">The <xref:System.Data.DataSet> is one of the most widely used components in [!INCLUDE[vstecado](~/includes/vstecado-md.md)], and is a key element of the disconnected programming model that [!INCLUDE[vstecado](~/includes/vstecado-md.md)] is built on.</span></span> <span data-ttu-id="beeb1-109">그러나 이러한 탁월함에도 불구하고 <xref:System.Data.DataSet>의 쿼리 기능에는 한계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beeb1-109">Despite this prominence, however, the <xref:System.Data.DataSet> has limited query capabilities.</span></span>  
  
 [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)]<span data-ttu-id="beeb1-110">를 사용하면 다른 많은 데이터 소스에 사용할 수 있는 것과 동일한 쿼리 기능만 활용해도 더 풍부한 쿼리 기능을 <xref:System.Data.DataSet>에 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beeb1-110"> enables you to build richer query capabilities into <xref:System.Data.DataSet> by using the same query functionality that is available for many other data sources.</span></span>  
  
 <span data-ttu-id="beeb1-111">자세한 내용은 [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="beeb1-111">For more information, see [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).</span></span>  
  
## <a name="linq-to-sql"></a><span data-ttu-id="beeb1-112">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="beeb1-112">LINQ to SQL</span></span>  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]<span data-ttu-id="beeb1-113">은 관계형 데이터를 개체로 관리하는 데 필요한 런타임 인프라를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="beeb1-113"> provides a run-time infrastructure for managing relational data as objects.</span></span> <span data-ttu-id="beeb1-114">
          [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]에서 관계형 데이터베이스의 데이터 모델은 개발자의 프로그래밍 언어로 표현되는 개체 모델에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="beeb1-114">In [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], the data model of a relational database is mapped to an object model expressed in the programming language of the developer.</span></span> <span data-ttu-id="beeb1-115">응용 프로그램을 실행하면 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]에서 개체 모델의 언어 통합 쿼리를 SQL로 변환하여 실행을 위해 데이터베이스로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="beeb1-115">When you execute the application, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] translates language-integrated queries in the object model into SQL and sends them to the database for execution.</span></span> <span data-ttu-id="beeb1-116">데이터베이스가 결과를 반환하면 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]에서 조작할 수 있는 개체로 다시 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="beeb1-116">When the database returns the results, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] translates them back into objects that you can manipulate.</span></span>  
  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]<span data-ttu-id="beeb1-117">에는 데이터베이스의 저장 프로시저 및 사용자 정의 함수와 개체 모델의 상속을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="beeb1-117"> includes support for stored procedures and user-defined functions in the database, and for inheritance in the object model.</span></span>  
  
 <span data-ttu-id="beeb1-118">자세한 내용은 [LINQ to SQL](../../../../../docs/framework/data/adonet/sql/linq/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="beeb1-118">For more information, see [LINQ to SQL](../../../../../docs/framework/data/adonet/sql/linq/index.md).</span></span>  
  
## <a name="linq-to-entities"></a><span data-ttu-id="beeb1-119">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="beeb1-119">LINQ to Entities</span></span>  
 <span data-ttu-id="beeb1-120">[!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)]을 통해 관계형 데이터는 .NET 환경에서 개체로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="beeb1-120">Through the [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)], relational data is exposed as objects in the .NET environment.</span></span> <span data-ttu-id="beeb1-121">이를 통해 개체 계층은 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 지원을 위한 이상적인 대상이 되므로 개발자는 비즈니스 논리를 개발할 때 사용한 언어로 데이터베이스에 대한 쿼리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beeb1-121">This makes the object layer an ideal target for [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] support, allowing developers to formulate queries against the database from the language used to build the business logic.</span></span> <span data-ttu-id="beeb1-122">이러한 기능은 [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)]로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beeb1-122">This capability is known as [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)].</span></span> <span data-ttu-id="beeb1-123">자세한 내용은 [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="beeb1-123">See [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md) for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beeb1-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="beeb1-124">See Also</span></span>  
 [<span data-ttu-id="beeb1-125">LINQ 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="beeb1-125">LINQ and ADO.NET</span></span>](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec)  
 [<span data-ttu-id="beeb1-126">LINQ(Language-Integrated Query)(C#)</span><span class="sxs-lookup"><span data-stu-id="beeb1-126">Language-Integrated Query (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/index.md)
