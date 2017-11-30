---
title: "데이터 분할 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0ea305a67765e1b11ceebbf65c48a685024a41f3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="partitioning-data-visual-basic"></a><span data-ttu-id="4c4af-102">데이터 분할 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4c4af-102">Partitioning Data (Visual Basic)</span></span>
<span data-ttu-id="4c4af-103">LINQ의 분할은 요소를 다시 정렬한 후 섹션 중 하나를 반환하지 않고 입력 시퀀스를 두 개의 섹션으로 나누는 작업을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="4c4af-103">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="4c4af-104">다음 그림은 문자 시퀀스에 대한 세 가지 분할 작업의 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4c4af-104">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="4c4af-105">첫 번째 작업은 시퀀스에서 처음 세 개의 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4c4af-105">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="4c4af-106">두 번째 작업은 처음 세 개의 요소를 건너뛰고 나머지 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4c4af-106">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="4c4af-107">세 번째 작업은 시퀀스에서 처음 두 개의 요소를 건너뛰고 다음 세 개의 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4c4af-107">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 <span data-ttu-id="4c4af-108">![LINQ 분할 작업](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")</span><span class="sxs-lookup"><span data-stu-id="4c4af-108">![LINQ Partitioning Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")</span></span>  
  
 <span data-ttu-id="4c4af-109">시퀀스를 분할하는 표준 쿼리 연산자 메서드가 다음 섹션에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c4af-109">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="4c4af-110">연산자</span><span class="sxs-lookup"><span data-stu-id="4c4af-110">Operators</span></span>  
  
|<span data-ttu-id="4c4af-111">연산자 이름</span><span class="sxs-lookup"><span data-stu-id="4c4af-111">Operator Name</span></span>|<span data-ttu-id="4c4af-112">설명</span><span class="sxs-lookup"><span data-stu-id="4c4af-112">Description</span></span>|<span data-ttu-id="4c4af-113">Visual Basic 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="4c4af-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="4c4af-114">추가 정보</span><span class="sxs-lookup"><span data-stu-id="4c4af-114">More Information</span></span>|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="4c4af-115">Skip</span><span class="sxs-lookup"><span data-stu-id="4c4af-115">Skip</span></span>|<span data-ttu-id="4c4af-116">시퀀스에서 지정한 위치까지 요소를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="4c4af-116">Skips elements up to a specified position in a sequence.</span></span>|`Skip`|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="4c4af-117">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="4c4af-117">SkipWhile</span></span>|<span data-ttu-id="4c4af-118">요소가 조건을 충족하지 않을 때까지 조건자 함수를 기반으로 하여 요소를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="4c4af-118">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Skip While`|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="4c4af-119">Take</span><span class="sxs-lookup"><span data-stu-id="4c4af-119">Take</span></span>|<span data-ttu-id="4c4af-120">시퀀스에서 지정된 위치까지 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4c4af-120">Takes elements up to a specified position in a sequence.</span></span>|`Take`|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="4c4af-121">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="4c4af-121">TakeWhile</span></span>|<span data-ttu-id="4c4af-122">요소가 조건을 충족하지 않을 때까지 조건자 함수를 기반으로 하여 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4c4af-122">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Take While`|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="4c4af-123">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="4c4af-123">Query Expression Syntax Examples</span></span>  
  
### <a name="skip"></a><span data-ttu-id="4c4af-124">Skip</span><span class="sxs-lookup"><span data-stu-id="4c4af-124">Skip</span></span>  
 <span data-ttu-id="4c4af-125">다음 코드 예제에서는 `Skip` 절 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 문자열의 배열에서 처음 4 개의 문자열 배열에서 나머지 문자열을 반환 하기 전에 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c4af-125">The following code example uses the `Skip` clause in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] to skip over the first four strings in an array of strings before returning the remaining strings in the array.</span></span>  
  
 [!code-vb[CsLINQPartitioning#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_1.vb)]  
  
### <a name="skipwhile"></a><span data-ttu-id="4c4af-126">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="4c4af-126">SkipWhile</span></span>  
 <span data-ttu-id="4c4af-127">다음 코드 예제에서는 `Skip While` 절 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 를 건너 뛰 동안는 문자열의 첫 번째 문자 배열에서 문자열은 "a"입니다.</span><span class="sxs-lookup"><span data-stu-id="4c4af-127">The following code example uses the `Skip While` clause in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] to skip over the strings in an array while the first letter of the string is "a".</span></span> <span data-ttu-id="4c4af-128">배열에서 나머지 문자열이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c4af-128">The remaining strings in the array are returned.</span></span>  
  
 [!code-vb[CsLINQPartitioning#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_2.vb)]  
  
### <a name="take"></a><span data-ttu-id="4c4af-129">Take</span><span class="sxs-lookup"><span data-stu-id="4c4af-129">Take</span></span>  
 <span data-ttu-id="4c4af-130">다음 코드 예제에서는 `Take` 절 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 문자열의 배열에서 처음 두 개의 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c4af-130">The following code example uses the `Take` clause in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] to return the first two strings in an array of strings.</span></span>  
  
 [!code-vb[CsLINQPartitioning#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_3.vb)]  
  
### <a name="takewhile"></a><span data-ttu-id="4c4af-131">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="4c4af-131">TakeWhile</span></span>  
 <span data-ttu-id="4c4af-132">다음 코드 예제에서는 `Take While` 절 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 문자열의 길이 5 개 이하의 배열에서 문자열을 반환 하려면.</span><span class="sxs-lookup"><span data-stu-id="4c4af-132">The following code example uses the `Take While` clause in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] to return strings from an array while the length of the string is five or less.</span></span>  
  
 [!code-vb[CsLINQPartitioning#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4c4af-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c4af-133">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="4c4af-134">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4c4af-134">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="4c4af-135">Skip 절</span><span class="sxs-lookup"><span data-stu-id="4c4af-135">Skip Clause</span></span>](../../../../visual-basic/language-reference/queries/skip-clause.md)  
 [<span data-ttu-id="4c4af-136">Skip While 절</span><span class="sxs-lookup"><span data-stu-id="4c4af-136">Skip While Clause</span></span>](../../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [<span data-ttu-id="4c4af-137">Take 절</span><span class="sxs-lookup"><span data-stu-id="4c4af-137">Take Clause</span></span>](../../../../visual-basic/language-reference/queries/take-clause.md)  
 [<span data-ttu-id="4c4af-138">Take While 절</span><span class="sxs-lookup"><span data-stu-id="4c4af-138">Take While Clause</span></span>](../../../../visual-basic/language-reference/queries/take-while-clause.md)
