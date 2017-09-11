---
title: "프로젝션 작업 (Visual Basic) | Microsoft 문서"
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
ms.assetid: b8d38e6d-21cf-4619-8dbb-94476f4badc7
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
ms.openlocfilehash: aac5cf69e6c3f4041a4302e8d606ca8dfddbc8a2
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="projection-operations-visual-basic"></a><span data-ttu-id="22b5e-102">프로젝션 작업 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22b5e-102">Projection Operations (Visual Basic)</span></span>
<span data-ttu-id="22b5e-103">프로젝션 종종 나중에 사용 될 속성만 구성 된 새 폼에 개체를 변환 하는 작업을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="22b5e-103">Projection refers to the operation of transforming an object into a new form that often consists only of those properties that will be subsequently used.</span></span> <span data-ttu-id="22b5e-104">프로젝션을 사용하면 각 개체를 기반으로 만들어지는 새 형식을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22b5e-104">By using projection, you can construct a new type that is built from each object.</span></span> <span data-ttu-id="22b5e-105">프로젝트는 속성 수 있으며에 수학 함수를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22b5e-105">You can project a property and perform a mathematical function on it.</span></span> <span data-ttu-id="22b5e-106">또한 변경 하지 않고 원래 개체를 프로젝션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22b5e-106">You can also project the original object without changing it.</span></span>  
  
 <span data-ttu-id="22b5e-107">프로젝션을 수행 하는 표준 쿼리 연산자 메서드는 다음 섹션에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22b5e-107">The standard query operator methods that perform projection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="22b5e-108">메서드</span><span class="sxs-lookup"><span data-stu-id="22b5e-108">Methods</span></span>  
  
|<span data-ttu-id="22b5e-109">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="22b5e-109">Method Name</span></span>|<span data-ttu-id="22b5e-110">설명</span><span class="sxs-lookup"><span data-stu-id="22b5e-110">Description</span></span>|<span data-ttu-id="22b5e-111">Visual Basic 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="22b5e-111">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="22b5e-112">추가 정보</span><span class="sxs-lookup"><span data-stu-id="22b5e-112">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="22b5e-113">선택</span><span class="sxs-lookup"><span data-stu-id="22b5e-113">Select</span></span>|<span data-ttu-id="22b5e-114">변환 함수를 기반으로 하는 프로젝트의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="22b5e-114">Projects values that are based on a transform function.</span></span>|`Select`|<span data-ttu-id="22b5e-115"><xref:System.Linq.Enumerable.Select%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Select%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="22b5e-115"><xref:System.Linq.Enumerable.Select%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="22b5e-116"><xref:System.Linq.Queryable.Select%2A?displayProperty=fullName></xref:System.Linq.Queryable.Select%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="22b5e-116"><xref:System.Linq.Queryable.Select%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="22b5e-117">SelectMany</span><span class="sxs-lookup"><span data-stu-id="22b5e-117">SelectMany</span></span>|<span data-ttu-id="22b5e-118">변환 함수에 기반 하 고 단일 시퀀스로 평면화 하는 값의 시퀀스를 프로젝션 합니다.</span><span class="sxs-lookup"><span data-stu-id="22b5e-118">Projects sequences of values that are based on a transform function and then flattens them into one sequence.</span></span>|<span data-ttu-id="22b5e-119">사용 하 여 `From` 절</span><span class="sxs-lookup"><span data-stu-id="22b5e-119">Use multiple `From` clauses</span></span>|<span data-ttu-id="22b5e-120"><xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=fullName></xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="22b5e-120"><xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="22b5e-121"><xref:System.Linq.Queryable.SelectMany%2A?displayProperty=fullName></xref:System.Linq.Queryable.SelectMany%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="22b5e-121"><xref:System.Linq.Queryable.SelectMany%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="22b5e-122">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="22b5e-122">Query Expression Syntax Examples</span></span>  
  
### <a name="select"></a><span data-ttu-id="22b5e-123">선택</span><span class="sxs-lookup"><span data-stu-id="22b5e-123">Select</span></span>  
 <span data-ttu-id="22b5e-124">다음 예제에서는 `Select` 문자열의 목록에서 각 문자열에서 첫 글자를 프로젝션 하는 절.</span><span class="sxs-lookup"><span data-stu-id="22b5e-124">The following example uses the `Select` clause to project the first letter from each string in a list of strings.</span></span>  
  
```vb  
Dim words = New List(Of String) From {"an", "apple", "a", "day"}  
  
Dim query = From word In words   
            Select word.Substring(0, 1)  
  
Dim sb As New System.Text.StringBuilder()  
For Each letter As String In query  
    sb.AppendLine(letter)  
Next  
  
' Display the output.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' a  
' a  
' a  
' d  
```  
  
### <a name="selectmany"></a><span data-ttu-id="22b5e-125">SelectMany</span><span class="sxs-lookup"><span data-stu-id="22b5e-125">SelectMany</span></span>  
 <span data-ttu-id="22b5e-126">다음 예제에서는 여러 `From` 절 문자열의 목록에서 각 문자열에서 각 단어를 프로젝션 합니다.</span><span class="sxs-lookup"><span data-stu-id="22b5e-126">The following example uses multiple `From` clauses to project each word from each string in a list of strings.</span></span>  
  
```vb  
Dim phrases = New List(Of String) From {"an apple a day", "the quick brown fox"}  
  
Dim query = From phrase In phrases   
            From word In phrase.Split(" "c)   
            Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In query  
    sb.AppendLine(str)  
Next  
  
' Display the output.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' an  
' apple  
' a  
' day  
' the  
' quick  
' brown  
' fox  
```  
  
## <a name="select-versus-selectmany"></a><span data-ttu-id="22b5e-127">SelectMany와 선택</span><span class="sxs-lookup"><span data-stu-id="22b5e-127">Select versus SelectMany</span></span>  
 <span data-ttu-id="22b5e-128">역할은 모두 `Select()` 및 `SelectMany()` 결과 값 또는 값을 생성 하는 정책 원본 값에서입니다.</span><span class="sxs-lookup"><span data-stu-id="22b5e-128">The work of both `Select()` and `SelectMany()` is to produce a result value (or values) from source values.</span></span> <span data-ttu-id="22b5e-129">`Select()`모든 원본 값에 대해 하나의 결과 값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="22b5e-129">`Select()` produces one result value for every source value.</span></span> <span data-ttu-id="22b5e-130">전체 결과 따라서 소스 컬렉션에 동일한 수의 요소가 들어 있는 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="22b5e-130">The overall result is therefore a collection that has the same number of elements as the source collection.</span></span> <span data-ttu-id="22b5e-131">반면, `SelectMany()` 각 소스 값에서 연결 된 하위 컬렉션을 포함 하는 하나의 전체 결과 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="22b5e-131">In contrast, `SelectMany()` produces a single overall result that contains concatenated sub-collections from each source value.</span></span> <span data-ttu-id="22b5e-132">변환 함수에 인수로 전달 되는 `SelectMany()` 각 소스 값에 대 한 값의 열거 가능한 시퀀스를 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22b5e-132">The transform function that is passed as an argument to `SelectMany()` must return an enumerable sequence of values for each source value.</span></span> <span data-ttu-id="22b5e-133">이러한 열거 가능한 시퀀스를 연결 하 여 `SelectMany()` 하나의 큰 시퀀스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="22b5e-133">These enumerable sequences are then concatenated by `SelectMany()` to create one large sequence.</span></span>  
  
 <span data-ttu-id="22b5e-134">다음 두 그림은 이러한 두 가지 방법의 작업 간의 개념적 차이 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="22b5e-134">The following two illustrations show the conceptual difference between the actions of these two methods.</span></span> <span data-ttu-id="22b5e-135">각각의 경우에서 선택기 (변환) 함수 꽃의 배열을 각 소스 값에서 선택 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="22b5e-135">In each case, assume that the selector (transform) function selects the array of flowers from each source value.</span></span>  
  
 <span data-ttu-id="22b5e-136">이 그림에서는 설명 어떻게 `Select()` 소스 컬렉션에 동일한 수의 요소가 들어 있는 컬렉션을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="22b5e-136">This illustration depicts how `Select()` returns a collection that has the same number of elements as the source collection.</span></span>  
  
 <span data-ttu-id="22b5e-137">![Select ()의 동작에 대 한 개념적 설명](../../../../csharp/programming-guide/concepts/linq/media/selectaction.png "SelectAction")</span><span class="sxs-lookup"><span data-stu-id="22b5e-137">![Conceptual illustration of the action of Select&#40;&#41;](../../../../csharp/programming-guide/concepts/linq/media/selectaction.png "SelectAction")</span></span>  
  
 <span data-ttu-id="22b5e-138">이 그림에서는 설명 어떻게 `SelectMany()` 중간 배열 시퀀스에 있는 각 중간 배열에서 각 값이 포함 된 하나의 최종 결과 값으로 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="22b5e-138">This illustration depicts how `SelectMany()` concatenates the intermediate sequence of arrays into one final result value that contains each value from each intermediate array.</span></span>  
  
 <span data-ttu-id="22b5e-139">![Selectmany ()의 동작을 보여주는 그래픽입니다. ] (../../../../csharp/programming-guide/concepts/linq/media/selectmany.png "SelectMany")</span><span class="sxs-lookup"><span data-stu-id="22b5e-139">![Graphic showing the action of SelectMany&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/selectmany.png "SelectMany")</span></span>  
  
### <a name="code-example"></a><span data-ttu-id="22b5e-140">코드 예제</span><span class="sxs-lookup"><span data-stu-id="22b5e-140">Code Example</span></span>  
 <span data-ttu-id="22b5e-141">동작을 비교 하는 다음 예제에서는 `Select()` 및 `SelectMany()`합니다.</span><span class="sxs-lookup"><span data-stu-id="22b5e-141">The following example compares the behavior of `Select()` and `SelectMany()`.</span></span> <span data-ttu-id="22b5e-142">코드는 소스 컬렉션의 각 꽃 이름 목록에서 처음 두 항목을 수행 하 여 "축 하" 꽃을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="22b5e-142">The code creates a "bouquet" of flowers by taking the first two items from each list of flower names in the source collection.</span></span> <span data-ttu-id="22b5e-143">이 예제에서는 "단일 값" 하는 변환 함수 <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>사용 하 여 값의 컬렉션 자체는.</xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29></span><span class="sxs-lookup"><span data-stu-id="22b5e-143">In this example, the "single value" that the transform function <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> uses is itself a collection of values.</span></span> <span data-ttu-id="22b5e-144">이 위해서는 추가 `For Each` 각 하위 시퀀스의 각 문자열을 열거 하기 위해 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="22b5e-144">This requires the extra `For Each` loop in order to enumerate each string in each sub-sequence.</span></span>  
  
```vb  
Class Bouquet  
    Public Flowers As List(Of String)  
End Class  
  
Sub SelectVsSelectMany()  
    Dim bouquets = New List(Of Bouquet) From {   
        New Bouquet With {.Flowers = New List(Of String)(New String() {"sunflower", "daisy", "daffodil", "larkspur"})},   
        New Bouquet With {.Flowers = New List(Of String)(New String() {"tulip", "rose", "orchid"})},   
        New Bouquet With {.Flowers = New List(Of String)(New String() {"gladiolis", "lily", "snapdragon", "aster", "protea"})},   
        New Bouquet With {.Flowers = New List(Of String)(New String() {"larkspur", "lilac", "iris", "dahlia"})}}  
  
    Dim output As New System.Text.StringBuilder  
  
    ' Select()  
    Dim query1 = bouquets.Select(Function(b) b.Flowers)  
  
    output.AppendLine("Using Select():")  
    For Each flowerList In query1  
        For Each str As String In flowerList  
            output.AppendLine(str)  
        Next  
    Next  
  
    ' SelectMany()  
    Dim query2 = bouquets.SelectMany(Function(b) b.Flowers)  
  
    output.AppendLine(vbCrLf & "Using SelectMany():")  
    For Each str As String In query2  
        output.AppendLine(str)  
    Next  
  
    ' Display the output  
    MsgBox(output.ToString())  
  
    ' This code produces the following output:  
    '  
    ' Using Select():  
    ' sunflower  
    ' daisy  
    ' daffodil  
    ' larkspur  
    ' tulip  
    ' rose  
    ' orchid  
    ' gladiolis  
    ' lily  
    ' snapdragon  
    ' aster  
    ' protea  
    ' larkspur  
    ' lilac  
    ' iris  
    ' dahlia  
  
    ' Using SelectMany()  
    ' sunflower  
    ' daisy  
    ' daffodil  
    ' larkspur  
    ' tulip  
    ' rose  
    ' orchid  
    ' gladiolis  
    ' lily  
    ' snapdragon  
    ' aster  
    ' protea  
    ' larkspur  
    ' lilac  
    ' iris  
    ' dahlia  
  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="22b5e-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="22b5e-145">See Also</span></span>  
 <span data-ttu-id="22b5e-146"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="22b5e-146"><xref:System.Linq></span></span>   
<span data-ttu-id="22b5e-147"> [표준 쿼리 연산자 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="22b5e-147"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="22b5e-148"> [Select 절](../../../../visual-basic/language-reference/queries/select-clause.md) </span><span class="sxs-lookup"><span data-stu-id="22b5e-148"> [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md) </span></span>  
<span data-ttu-id="22b5e-149"> [방법: 조인 사용 하 여 데이터 결합](../../../../visual-basic/programming-guide/language-features/linq/how-to-combine-data-with-linq-by-using-joins.md) </span><span class="sxs-lookup"><span data-stu-id="22b5e-149"> [How to: Combine Data with Joins](../../../../visual-basic/programming-guide/language-features/linq/how-to-combine-data-with-linq-by-using-joins.md) </span></span>  
<span data-ttu-id="22b5e-150"> [방법: 개체 컬렉션 (Visual Basic) (LINQ) 여러 소스에서 채우기](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md) </span><span class="sxs-lookup"><span data-stu-id="22b5e-150"> [How to: Populate Object Collections from Multiple Sources (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md) </span></span>  
<span data-ttu-id="22b5e-151"> [방법: LINQ 쿼리 결과 특정 형식으로 반환](../../../../visual-basic/programming-guide/language-features/linq/how-to-return-a-linq-query-result-as-a-specific-type.md) </span><span class="sxs-lookup"><span data-stu-id="22b5e-151"> [How to: Return a LINQ Query Result as a Specific Type](../../../../visual-basic/programming-guide/language-features/linq/how-to-return-a-linq-query-result-as-a-specific-type.md) </span></span>  
<span data-ttu-id="22b5e-152"> [방법: 그룹 (LINQ) (Visual Basic)를 사용 하 여 파일을 여러 파일로 분할](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)</span><span class="sxs-lookup"><span data-stu-id="22b5e-152"> [How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)</span></span>
