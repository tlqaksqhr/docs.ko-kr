---
title: "데이터 필터링 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: fa2d3b6c5b81f137ab3a81f9b18707bb2da91f6e
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="filtering-data-visual-basic"></a><span data-ttu-id="6e688-102">데이터 필터링 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e688-102">Filtering Data (Visual Basic)</span></span>
<span data-ttu-id="6e688-103">결과 집합에 지정한 조건을 충족 하는 요소만 포함 되도록 제한 작업에 참조 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e688-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="6e688-104">선택 영역 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e688-104">It is also known as selection.</span></span>  
  
 <span data-ttu-id="6e688-105">다음 그림에는 문자 시퀀스를 필터링 한 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6e688-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="6e688-106">필터링 작업에 대 한 조건자는 문자 'A'이 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e688-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 <span data-ttu-id="6e688-107">![LINQ 필터링 작업](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span><span class="sxs-lookup"><span data-stu-id="6e688-107">![LINQ Filtering Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span></span>  
  
 <span data-ttu-id="6e688-108">선택을 수행 하는 표준 쿼리 연산자 메서드는 다음 섹션에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e688-108">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6e688-109">메서드</span><span class="sxs-lookup"><span data-stu-id="6e688-109">Methods</span></span>  
  
|<span data-ttu-id="6e688-110">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="6e688-110">Method Name</span></span>|<span data-ttu-id="6e688-111">설명</span><span class="sxs-lookup"><span data-stu-id="6e688-111">Description</span></span>|<span data-ttu-id="6e688-112">Visual Basic 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="6e688-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="6e688-113">추가 정보</span><span class="sxs-lookup"><span data-stu-id="6e688-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="6e688-114">OfType</span><span class="sxs-lookup"><span data-stu-id="6e688-114">OfType</span></span>|<span data-ttu-id="6e688-115">지정된 된 형식으로 캐스팅할 수에 따라 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e688-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="6e688-116">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="6e688-116">Not applicable.</span></span>|<span data-ttu-id="6e688-117"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="6e688-117"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="6e688-118"><xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="6e688-118"><xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="6e688-119">Where</span><span class="sxs-lookup"><span data-stu-id="6e688-119">Where</span></span>|<span data-ttu-id="6e688-120">조건자 함수를 기반으로 하는 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e688-120">Selects values that are based on a predicate function.</span></span>|`Where`|<span data-ttu-id="6e688-121"><xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="6e688-121"><xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="6e688-122"><xref:System.Linq.Queryable.Where%2A?displayProperty=fullName></xref:System.Linq.Queryable.Where%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="6e688-122"><xref:System.Linq.Queryable.Where%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="6e688-123">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="6e688-123">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="6e688-124">다음 예제에서는 `Where` 특정 길이의 이러한 문자열 배열에서 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e688-124">The following example uses the `Where` to filter from an array those strings that have a specific length.</span></span>  
  
```vb  
Dim words() As String = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim query = From word In words   
            Where word.Length = 3   
            Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In query  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' the  
' fox  
```  
  
## <a name="see-also"></a><span data-ttu-id="6e688-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e688-125">See Also</span></span>  
 <span data-ttu-id="6e688-126"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="6e688-126"><xref:System.Linq></span></span>   
<span data-ttu-id="6e688-127"> [표준 쿼리 연산자 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="6e688-127"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="6e688-128"> [여기서 절](../../../../visual-basic/language-reference/queries/where-clause.md) </span><span class="sxs-lookup"><span data-stu-id="6e688-128"> [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md) </span></span>  
<span data-ttu-id="6e688-129"> [방법: 쿼리 결과 필터링](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md) </span><span class="sxs-lookup"><span data-stu-id="6e688-129"> [How to: Filter Query Results](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md) </span></span>  
<span data-ttu-id="6e688-130"> [방법: 리플렉션 (LINQ) (Visual Basic) 사용 하 여 어셈블리의 메타 데이터 쿼리](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md) </span><span class="sxs-lookup"><span data-stu-id="6e688-130"> [How to: Query An Assembly's Metadata with Reflection (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md) </span></span>  
<span data-ttu-id="6e688-131"> [방법: 지정 된 특성 또는 이름 (Visual Basic)를 사용 하 여 파일에 대 한 쿼리](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md) </span><span class="sxs-lookup"><span data-stu-id="6e688-131"> [How to: Query for Files with a Specified Attribute or Name (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md) </span></span>  
<span data-ttu-id="6e688-132"> [방법: 데이터 정렬 또는 필터링 텍스트에서 단어 또는 필드 (Visual Basic) (LINQ)](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)</span><span class="sxs-lookup"><span data-stu-id="6e688-132"> [How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)</span></span>
