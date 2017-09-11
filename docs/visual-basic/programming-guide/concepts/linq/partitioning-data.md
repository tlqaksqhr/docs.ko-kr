---
title: "(Visual Basic) 데이터 분할 | Microsoft 문서"
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
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
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
ms.openlocfilehash: 9d0df2bc473f48fba4bbb094317166407f7c7ec2
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="partitioning-data-visual-basic"></a><span data-ttu-id="9315d-102">데이터 분할 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9315d-102">Partitioning Data (Visual Basic)</span></span>
<span data-ttu-id="9315d-103">Linq에서 분할은 입력된 시퀀스를 요소를 다시 정렬 한 다음 섹션 중 하나를 반환 하지 않고 두 개의 섹션으로 나눈으로 작동 하는 것을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="9315d-103">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="9315d-104">다음 그림에서는 세 개의 서로 다른 분할 작업 시퀀스에서 문자의 결과 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9315d-104">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="9315d-105">첫 번째 작업 시퀀스에서 처음 세 개의 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9315d-105">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="9315d-106">두 번째 작업에서는 처음 세 개의 요소를 건너뛰고 나머지 요소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9315d-106">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="9315d-107">세 번째 작업 시퀀스에서 처음 두 요소를 생략 하 고 세 개의 요소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9315d-107">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 <span data-ttu-id="9315d-108">![LINQ 분할 작업](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")</span><span class="sxs-lookup"><span data-stu-id="9315d-108">![LINQ Partitioning Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")</span></span>  
  
 <span data-ttu-id="9315d-109">시퀀스를 분할 하는 표준 쿼리 연산자 메서드는 다음 섹션에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9315d-109">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="9315d-110">연산자</span><span class="sxs-lookup"><span data-stu-id="9315d-110">Operators</span></span>  
  
|<span data-ttu-id="9315d-111">연산자 이름</span><span class="sxs-lookup"><span data-stu-id="9315d-111">Operator Name</span></span>|<span data-ttu-id="9315d-112">설명</span><span class="sxs-lookup"><span data-stu-id="9315d-112">Description</span></span>|<span data-ttu-id="9315d-113">Visual Basic 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="9315d-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="9315d-114">추가 정보</span><span class="sxs-lookup"><span data-stu-id="9315d-114">More Information</span></span>|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="9315d-115">Skip</span><span class="sxs-lookup"><span data-stu-id="9315d-115">Skip</span></span>|<span data-ttu-id="9315d-116">시퀀스에서 지정 된 위치까지 요소를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="9315d-116">Skips elements up to a specified position in a sequence.</span></span>|`Skip`|<span data-ttu-id="9315d-117"><xref:System.Linq.Enumerable.Skip%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Skip%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="9315d-117"><xref:System.Linq.Enumerable.Skip%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="9315d-118"><xref:System.Linq.Queryable.Skip%2A?displayProperty=fullName></xref:System.Linq.Queryable.Skip%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="9315d-118"><xref:System.Linq.Queryable.Skip%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="9315d-119">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="9315d-119">SkipWhile</span></span>|<span data-ttu-id="9315d-120">요소가 조건을 만족 하지 않을 때까지 조건자 함수를 기반으로 요소를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="9315d-120">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Skip While`|<span data-ttu-id="9315d-121"><xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=fullName></xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="9315d-121"><xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="9315d-122"><xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=fullName></xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="9315d-122"><xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="9315d-123">Take</span><span class="sxs-lookup"><span data-stu-id="9315d-123">Take</span></span>|<span data-ttu-id="9315d-124">시퀀스에서 지정 된 위치까지 요소를 취합니다.</span><span class="sxs-lookup"><span data-stu-id="9315d-124">Takes elements up to a specified position in a sequence.</span></span>|`Take`|<span data-ttu-id="9315d-125"><xref:System.Linq.Enumerable.Take%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Take%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="9315d-125"><xref:System.Linq.Enumerable.Take%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="9315d-126"><xref:System.Linq.Queryable.Take%2A?displayProperty=fullName></xref:System.Linq.Queryable.Take%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="9315d-126"><xref:System.Linq.Queryable.Take%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="9315d-127">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="9315d-127">TakeWhile</span></span>|<span data-ttu-id="9315d-128">요소가 조건을 만족 하지 않을 때까지 조건자 함수를 기반으로 요소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9315d-128">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Take While`|<span data-ttu-id="9315d-129"><xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=fullName></xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="9315d-129"><xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="9315d-130"><xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=fullName></xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="9315d-130"><xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="9315d-131">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="9315d-131">Query Expression Syntax Examples</span></span>  
  
### <a name="skip"></a><span data-ttu-id="9315d-132">Skip</span><span class="sxs-lookup"><span data-stu-id="9315d-132">Skip</span></span>  
 <span data-ttu-id="9315d-133">다음 코드 예제에서는 `Skip` 절 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 문자열의 배열에서 처음&4; 개의 문자열 배열에서 나머지 문자열을 반환 하기 전에 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9315d-133">The following code example uses the `Skip` clause in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to skip over the first four strings in an array of strings before returning the remaining strings in the array.</span></span>  
  
 <span data-ttu-id="9315d-134">[!code-vb[CsLINQPartitioning #&1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="9315d-134">[!code-vb[CsLINQPartitioning#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_1.vb)]</span></span>  
  
### <a name="skipwhile"></a><span data-ttu-id="9315d-135">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="9315d-135">SkipWhile</span></span>  
 <span data-ttu-id="9315d-136">다음 코드 예제에서는 `Skip While` 절에 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 를 건너 뛰 문자열의 첫 글자는 동안 배열에서 문자열은 "a"입니다.</span><span class="sxs-lookup"><span data-stu-id="9315d-136">The following code example uses the `Skip While` clause in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to skip over the strings in an array while the first letter of the string is "a".</span></span> <span data-ttu-id="9315d-137">배열에서 나머지 문자열이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9315d-137">The remaining strings in the array are returned.</span></span>  
  
 <span data-ttu-id="9315d-138">[!code-vb[CsLINQPartitioning #&2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="9315d-138">[!code-vb[CsLINQPartitioning#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_2.vb)]</span></span>  
  
### <a name="take"></a><span data-ttu-id="9315d-139">Take</span><span class="sxs-lookup"><span data-stu-id="9315d-139">Take</span></span>  
 <span data-ttu-id="9315d-140">다음 코드 예제에서는 `Take` 절 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 문자열의 배열에서 처음 두 개의 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9315d-140">The following code example uses the `Take` clause in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to return the first two strings in an array of strings.</span></span>  
  
 <span data-ttu-id="9315d-141">[!code-vb[CsLINQPartitioning #&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="9315d-141">[!code-vb[CsLINQPartitioning#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_3.vb)]</span></span>  
  
### <a name="takewhile"></a><span data-ttu-id="9315d-142">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="9315d-142">TakeWhile</span></span>  
 <span data-ttu-id="9315d-143">다음 코드 예제에서는 `Take While` 절 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 문자열의 길이&5; 개 이하의 배열에서 문자열을 반환 하려면.</span><span class="sxs-lookup"><span data-stu-id="9315d-143">The following code example uses the `Take While` clause in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to return strings from an array while the length of the string is five or less.</span></span>  
  
 <span data-ttu-id="9315d-144">[!code-vb[CsLINQPartitioning #&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="9315d-144">[!code-vb[CsLINQPartitioning#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_4.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9315d-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9315d-145">See Also</span></span>  
 <span data-ttu-id="9315d-146"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="9315d-146"><xref:System.Linq></span></span>   
<span data-ttu-id="9315d-147"> [표준 쿼리 연산자 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="9315d-147"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="9315d-148"> [Skip 절](../../../../visual-basic/language-reference/queries/skip-clause.md) </span><span class="sxs-lookup"><span data-stu-id="9315d-148"> [Skip Clause](../../../../visual-basic/language-reference/queries/skip-clause.md) </span></span>  
<span data-ttu-id="9315d-149"> [Skip While 절](../../../../visual-basic/language-reference/queries/skip-while-clause.md) </span><span class="sxs-lookup"><span data-stu-id="9315d-149"> [Skip While Clause](../../../../visual-basic/language-reference/queries/skip-while-clause.md) </span></span>  
<span data-ttu-id="9315d-150"> [Take 절](../../../../visual-basic/language-reference/queries/take-clause.md) </span><span class="sxs-lookup"><span data-stu-id="9315d-150"> [Take Clause](../../../../visual-basic/language-reference/queries/take-clause.md) </span></span>  
<span data-ttu-id="9315d-151"> [Take While 절](../../../../visual-basic/language-reference/queries/take-while-clause.md)</span><span class="sxs-lookup"><span data-stu-id="9315d-151"> [Take While Clause](../../../../visual-basic/language-reference/queries/take-while-clause.md)</span></span>
