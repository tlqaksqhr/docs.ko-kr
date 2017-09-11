---
title: "수량자 작업(C#)"
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
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
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
ms.openlocfilehash: f82df05693dffec64bcbc66cc2c0b9db2a7deb20
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="quantifier-operations-c"></a><span data-ttu-id="8ea46-102">수량자 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="8ea46-102">Quantifier Operations (C#)</span></span>
<span data-ttu-id="8ea46-103">수량자 작업은 시퀀스에서 조건을 충족하는 요소가 일부인지 전체인지를 나타내는 <xref:System.Boolean> 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea46-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="8ea46-104">다음 그림은 두 개의 서로 다른 소스 시퀀스에 대한 두 개의 서로 다른 수량자 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8ea46-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="8ea46-105">첫 번째 작업은 요소 중 하나 이상이 문자 'A'이고 결과가 `true`인지 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="8ea46-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="8ea46-106">두 번째 작업은 모든 요소가 문자 'A'이고 결과가 `true`인지 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="8ea46-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 <span data-ttu-id="8ea46-107">![LINQ 수량자 작업](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span><span class="sxs-lookup"><span data-stu-id="8ea46-107">![LINQ Quantifier Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span></span>  
  
 <span data-ttu-id="8ea46-108">다음 섹션에는 수량자 작업을 수행하는 표준 쿼리 연산자 메서드가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ea46-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8ea46-109">메서드</span><span class="sxs-lookup"><span data-stu-id="8ea46-109">Methods</span></span>  
  
|<span data-ttu-id="8ea46-110">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="8ea46-110">Method Name</span></span>|<span data-ttu-id="8ea46-111">설명</span><span class="sxs-lookup"><span data-stu-id="8ea46-111">Description</span></span>|<span data-ttu-id="8ea46-112">C# 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="8ea46-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="8ea46-113">추가 정보</span><span class="sxs-lookup"><span data-stu-id="8ea46-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="8ea46-114">모두</span><span class="sxs-lookup"><span data-stu-id="8ea46-114">All</span></span>|<span data-ttu-id="8ea46-115">시퀀스의 모든 요소가 조건을 만족하는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea46-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="8ea46-116">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="8ea46-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=fullName>|  
|<span data-ttu-id="8ea46-117">임의의 값</span><span class="sxs-lookup"><span data-stu-id="8ea46-117">Any</span></span>|<span data-ttu-id="8ea46-118">시퀀스의 임의의 요소가 조건을 만족하는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea46-118">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="8ea46-119">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="8ea46-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=fullName>|  
|<span data-ttu-id="8ea46-120">포함</span><span class="sxs-lookup"><span data-stu-id="8ea46-120">Contains</span></span>|<span data-ttu-id="8ea46-121">시퀀스에 지정된 요소가 들어 있는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea46-121">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="8ea46-122">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="8ea46-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=fullName>|  
  
## <a name="see-also"></a><span data-ttu-id="8ea46-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ea46-123">See Also</span></span>  
 <span data-ttu-id="8ea46-124"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="8ea46-124"><xref:System.Linq></span></span>   
 <span data-ttu-id="8ea46-125">[표준 쿼리 연산자 개요(C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="8ea46-125">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 <span data-ttu-id="8ea46-126">[방법: 런타임에 동적으로 조건자 필터 지정](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md) </span><span class="sxs-lookup"><span data-stu-id="8ea46-126">[How to: Dynamically Specify Predicate Filters at Runtime](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md) </span></span>  
 [<span data-ttu-id="8ea46-127">방법: 지정된 단어 집합이 들어 있는 문장 쿼리(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="8ea46-127">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)

