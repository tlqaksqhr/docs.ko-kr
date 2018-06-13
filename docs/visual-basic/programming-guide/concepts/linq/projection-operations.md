---
title: 프로젝션 작업 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: b8d38e6d-21cf-4619-8dbb-94476f4badc7
ms.openlocfilehash: f4d1f7531ee69ebdbfb4ccd283f9f5dcb2f000af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647646"
---
# <a name="projection-operations-visual-basic"></a><span data-ttu-id="472a6-102">프로젝션 작업 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="472a6-102">Projection Operations (Visual Basic)</span></span>
<span data-ttu-id="472a6-103">프로젝션은 주로 이후에 사용할 속성으로만 구성된 새 양식으로 개체를 변환하는 작업을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="472a6-103">Projection refers to the operation of transforming an object into a new form that often consists only of those properties that will be subsequently used.</span></span> <span data-ttu-id="472a6-104">프로젝션을 사용하면 각 개체를 기반으로 만들어지는 새 형식을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="472a6-104">By using projection, you can construct a new type that is built from each object.</span></span> <span data-ttu-id="472a6-105">속성을 프로젝션하고 속성에서 수학 함수를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="472a6-105">You can project a property and perform a mathematical function on it.</span></span> <span data-ttu-id="472a6-106">원래 개체를 변경하지 않고 프로젝션할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="472a6-106">You can also project the original object without changing it.</span></span>  
  
 <span data-ttu-id="472a6-107">다음 섹션에는 프로젝션을 수행하는 표준 쿼리 연산자 메서드가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="472a6-107">The standard query operator methods that perform projection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="472a6-108">메서드</span><span class="sxs-lookup"><span data-stu-id="472a6-108">Methods</span></span>  
  
|<span data-ttu-id="472a6-109">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="472a6-109">Method Name</span></span>|<span data-ttu-id="472a6-110">설명</span><span class="sxs-lookup"><span data-stu-id="472a6-110">Description</span></span>|<span data-ttu-id="472a6-111">Visual Basic 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="472a6-111">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="472a6-112">추가 정보</span><span class="sxs-lookup"><span data-stu-id="472a6-112">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="472a6-113">선택</span><span class="sxs-lookup"><span data-stu-id="472a6-113">Select</span></span>|<span data-ttu-id="472a6-114">변환 함수를 기반으로 하는 값을 프로젝션합니다.</span><span class="sxs-lookup"><span data-stu-id="472a6-114">Projects values that are based on a transform function.</span></span>|`Select`|<xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="472a6-115">SelectMany</span><span class="sxs-lookup"><span data-stu-id="472a6-115">SelectMany</span></span>|<span data-ttu-id="472a6-116">변환 함수를 기반으로 하는 값의 시퀀스를 프로젝션한 다음 하나의 시퀀스로 평면화합니다.</span><span class="sxs-lookup"><span data-stu-id="472a6-116">Projects sequences of values that are based on a transform function and then flattens them into one sequence.</span></span>|<span data-ttu-id="472a6-117">여러 `From` 절 사용</span><span class="sxs-lookup"><span data-stu-id="472a6-117">Use multiple `From` clauses</span></span>|<xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SelectMany%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="472a6-118">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="472a6-118">Query Expression Syntax Examples</span></span>  
  
### <a name="select"></a><span data-ttu-id="472a6-119">선택</span><span class="sxs-lookup"><span data-stu-id="472a6-119">Select</span></span>  
 <span data-ttu-id="472a6-120">다음 예제에서는 `Select` 절을 사용하여 문자열 목록의 각 문자열에서 첫 글자를 프로젝션합니다.</span><span class="sxs-lookup"><span data-stu-id="472a6-120">The following example uses the `Select` clause to project the first letter from each string in a list of strings.</span></span>  
  
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
  
### <a name="selectmany"></a><span data-ttu-id="472a6-121">SelectMany</span><span class="sxs-lookup"><span data-stu-id="472a6-121">SelectMany</span></span>  
 <span data-ttu-id="472a6-122">다음 예제에서는 여러 `From` 절 문자열의 목록에서 각 문자열에서 각 단어를 프로젝션 합니다.</span><span class="sxs-lookup"><span data-stu-id="472a6-122">The following example uses multiple `From` clauses to project each word from each string in a list of strings.</span></span>  
  
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
  
## <a name="select-versus-selectmany"></a><span data-ttu-id="472a6-123">Select 및 SelectMany</span><span class="sxs-lookup"><span data-stu-id="472a6-123">Select versus SelectMany</span></span>  
 <span data-ttu-id="472a6-124">`Select()` 및 `SelectMany()` 둘 다의 작업은 소스 값에서 결과 값을 생성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="472a6-124">The work of both `Select()` and `SelectMany()` is to produce a result value (or values) from source values.</span></span> <span data-ttu-id="472a6-125">`Select()`는 모든 소스 값에 대해 하나의 결과 값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="472a6-125">`Select()` produces one result value for every source value.</span></span> <span data-ttu-id="472a6-126">따라서 전체 결과는 소스 컬렉션과 동일한 개수의 요소가 들어 있는 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="472a6-126">The overall result is therefore a collection that has the same number of elements as the source collection.</span></span> <span data-ttu-id="472a6-127">반면, `SelectMany()`는 각 소스 값에서 연결된 하위 컬렉션을 포함하는 하나의 전체 결과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="472a6-127">In contrast, `SelectMany()` produces a single overall result that contains concatenated sub-collections from each source value.</span></span> <span data-ttu-id="472a6-128">`SelectMany()`에 대한 인수로 전달되는 변환 함수는 각 소스 값에 대해 열거 가능한 값 시퀀스를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="472a6-128">The transform function that is passed as an argument to `SelectMany()` must return an enumerable sequence of values for each source value.</span></span> <span data-ttu-id="472a6-129">이러한 열거 가능한 시퀀스는 `SelectMany()`에 의해 연결되어 하나의 큰 시퀀스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="472a6-129">These enumerable sequences are then concatenated by `SelectMany()` to create one large sequence.</span></span>  
  
 <span data-ttu-id="472a6-130">다음 두 그림은 이러한 두 메서드의 작업 간에 개념적 차이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="472a6-130">The following two illustrations show the conceptual difference between the actions of these two methods.</span></span> <span data-ttu-id="472a6-131">각각의 경우에서 선택기(변환) 함수는 각 소스 값에서 꽃의 배열을 선택한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="472a6-131">In each case, assume that the selector (transform) function selects the array of flowers from each source value.</span></span>  
  
 <span data-ttu-id="472a6-132">이 그림은 `Select()`에서 소스 컬렉션과 동일한 개수의 요소가 들어 있는 컬렉션을 반환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="472a6-132">This illustration depicts how `Select()` returns a collection that has the same number of elements as the source collection.</span></span>  
  
 <span data-ttu-id="472a6-133">![Select&#40;&#41;의 동작에 대한 개념적 설명](../../../../csharp/programming-guide/concepts/linq/media/selectaction.png "SelectAction")</span><span class="sxs-lookup"><span data-stu-id="472a6-133">![Conceptual illustration of the action of Select&#40;&#41;](../../../../csharp/programming-guide/concepts/linq/media/selectaction.png "SelectAction")</span></span>  
  
 <span data-ttu-id="472a6-134">이 그림은 `SelectMany()`에서 배열의 중간 시퀀스를 각 중간 배열의 각 값이 포함된 하나의 최종 결과 값으로 연결하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="472a6-134">This illustration depicts how `SelectMany()` concatenates the intermediate sequence of arrays into one final result value that contains each value from each intermediate array.</span></span>  
  
 <span data-ttu-id="472a6-135">![SelectMany&#40;&#41;의 동작을 보여주는 그래픽](../../../../csharp/programming-guide/concepts/linq/media/selectmany.png "SelectMany")</span><span class="sxs-lookup"><span data-stu-id="472a6-135">![Graphic showing the action of SelectMany&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/selectmany.png "SelectMany")</span></span>  
  
### <a name="code-example"></a><span data-ttu-id="472a6-136">코드 예제</span><span class="sxs-lookup"><span data-stu-id="472a6-136">Code Example</span></span>  
 <span data-ttu-id="472a6-137">다음 예제에서는 `Select()` 및 `SelectMany()`의 동작을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="472a6-137">The following example compares the behavior of `Select()` and `SelectMany()`.</span></span> <span data-ttu-id="472a6-138">코드는 소스 컬렉션의 각 꽃 이름 목록에서 처음 두 항목을 사용하여 꽃 "부케"를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="472a6-138">The code creates a "bouquet" of flowers by taking the first two items from each list of flower names in the source collection.</span></span> <span data-ttu-id="472a6-139">이 예제에서 변환 함수 <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>가 사용하는 “단일 값”은 값 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="472a6-139">In this example, the "single value" that the transform function <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> uses is itself a collection of values.</span></span> <span data-ttu-id="472a6-140">이 경우 각 하위 시퀀스의 각 문자열을 열거하기 위해 `For Each` 루프가 추가로 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="472a6-140">This requires the extra `For Each` loop in order to enumerate each string in each sub-sequence.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="472a6-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="472a6-141">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="472a6-142">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="472a6-142">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="472a6-143">Select 절</span><span class="sxs-lookup"><span data-stu-id="472a6-143">Select Clause</span></span>](../../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="472a6-144">방법: 조인을 사용하여 데이터 결합</span><span class="sxs-lookup"><span data-stu-id="472a6-144">How to: Combine Data with Joins</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-combine-data-with-linq-by-using-joins.md)  
 [<span data-ttu-id="472a6-145">방법: 여러 원본 (LINQ) (Visual Basic)에서 개체 컬렉션 채우기</span><span class="sxs-lookup"><span data-stu-id="472a6-145">How to: Populate Object Collections from Multiple Sources (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)  
 [<span data-ttu-id="472a6-146">방법: LINQ 쿼리 결과를 특정 형식으로 반환</span><span class="sxs-lookup"><span data-stu-id="472a6-146">How to: Return a LINQ Query Result as a Specific Type</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-return-a-linq-query-result-as-a-specific-type.md)  
 [<span data-ttu-id="472a6-147">방법: 한 파일 그룹 (LINQ) (Visual Basic)를 사용 하 여 여러 파일로 분할</span><span class="sxs-lookup"><span data-stu-id="472a6-147">How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
