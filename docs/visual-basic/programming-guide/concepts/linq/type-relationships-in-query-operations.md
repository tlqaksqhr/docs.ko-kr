---
title: "쿼리 작업의 형식 관계(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variable relationships [LINQ in Visual Basic]
- type information inferred [LINQ in Visual Basic]
- type relationships [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], type relationships
- data sources [LINQ in Visual Basic], type relationships
- LINQ [Visual Basic], type relationships
- inferring type information [LINQ in Visual Basic]
- relationships [LINQ in Visual Basic]
ms.assetid: b5ff4da5-f3fd-4a8e-aaac-1cbf52fa16f6
caps.latest.revision: "34"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1b93188475dd2bb00aea044ff178028eb87e00d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="type-relationships-in-query-operations-visual-basic"></a><span data-ttu-id="81cde-102">쿼리 작업의 형식 관계(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81cde-102">Type Relationships in Query Operations (Visual Basic)</span></span>
<span data-ttu-id="81cde-103">사용 되는 변수 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] 쿼리 작업에는 강력한 형식이 며 서로 호환 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-103">Variables used in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] query operations are strongly typed and must be compatible with each other.</span></span> <span data-ttu-id="81cde-104">강력한 형식 지정 데이터 원본, 쿼리 자체 및 쿼리 실행에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-104">Strong typing is used in the data source, in the query itself, and in the query execution.</span></span> <span data-ttu-id="81cde-105">다음 그림에 설명 하는 데 사용 되는 용어를 식별 한 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-105">The following illustration identifies terms used to describe a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query.</span></span> <span data-ttu-id="81cde-106">쿼리 부분에 대 한 자세한 내용은 참조 [기본 쿼리 작업 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-106">For more information about the parts of a query, see [Basic Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).</span></span>  
  
 <span data-ttu-id="81cde-107">![요소가 강조 표시 된 의사 코드 쿼리 합니다. ] (../../../../visual-basic/programming-guide/concepts/linq/media/sjltyperels.png "SJLtypeRels")</span><span class="sxs-lookup"><span data-stu-id="81cde-107">![Pseudocode query with elements highlighted.](../../../../visual-basic/programming-guide/concepts/linq/media/sjltyperels.png "SJLtypeRels")</span></span>  
<span data-ttu-id="81cde-108">LINQ 쿼리</span><span class="sxs-lookup"><span data-stu-id="81cde-108">Parts of a LINQ query</span></span>  
  
 <span data-ttu-id="81cde-109">쿼리에서 범위 변수의 종류는 데이터 원본에 있는 요소의 형식과 호환 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-109">The type of the range variable in the query must be compatible with the type of the elements in the data source.</span></span> <span data-ttu-id="81cde-110">쿼리 변수의 형식에 정의 된 시퀀스 요소와 호환 되어야 합니다는 `Select` 절.</span><span class="sxs-lookup"><span data-stu-id="81cde-110">The type of the query variable must be compatible with the sequence element defined in the `Select` clause.</span></span> <span data-ttu-id="81cde-111">마지막으로 시퀀스 요소의 형식과 호환 되어야 합니다에 사용 되는 루프 제어 변수의 형식을 `For Each` 쿼리를 실행 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-111">Finally, the type of the sequence elements also must be compatible with the type of the loop control variable that is used in the `For Each` statement that executes the query.</span></span> <span data-ttu-id="81cde-112">이 강력한 형식 지정 컴파일 시 형식 오류 식별을 용이 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-112">This strong typing facilitates identification of type errors at compile time.</span></span>  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="81cde-113">하면 강력한 형식 지정 편리 함 지역 형식 유추를 구현 하 여 *암시적 형식을*합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-113"> makes strong typing convenient by implementing local type inference, also known as *implicit typing*.</span></span> <span data-ttu-id="81cde-114">기능 이전 예제에서 사용 하 고 전체에서 사용 되는 것을 보게는 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 예제 및 설명서입니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-114">That feature is used in the previous example, and you will see it used throughout the [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] samples and documentation.</span></span> <span data-ttu-id="81cde-115">Visual Basic에서 지역 형식 유추를 그대로 사용 하 여 수행 됩니다는 `Dim` 문을 없이 `As` 절.</span><span class="sxs-lookup"><span data-stu-id="81cde-115">In Visual Basic, local type inference is accomplished simply by using a `Dim` statement without an `As` clause.</span></span> <span data-ttu-id="81cde-116">다음 예에서 `city` 강력한 형식의 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-116">In the following example, `city` is strongly typed as a string.</span></span>  
  
 [!code-vb[VbLINQTypeRels#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_1.vb)]  
  
> [!NOTE]
>  <span data-ttu-id="81cde-117">경우에만 작동 하는 지역 형식 유추 `Option Infer` 로 설정 된 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-117">Local type inference works only when `Option Infer` is set to `On`.</span></span> <span data-ttu-id="81cde-118">자세한 내용은 참조 [Option Infer 문](../../../../visual-basic/language-reference/statements/option-infer-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-118">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>  
  
 <span data-ttu-id="81cde-119">그러나 쿼리에서 지역 형식 유추를 사용 하는 경우에 동일한 유형 관계는 데이터 원본에서 변수, 쿼리 변수 및 쿼리 실행 루프 중입니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-119">However, even if you use local type inference in a query, the same type relationships are present among the variables in the data source, the query variable, and the query execution loop.</span></span> <span data-ttu-id="81cde-120">작성 하는 경우 이러한 형식 관계에 대 한 기본적인 이해를가 하는 것이 유용 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 또는 설명서의 코드 예제와 샘플 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-120">It is useful to have a basic understanding of these type relationships when you are writing [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, or working with the samples and code examples in the documentation.</span></span>  
  
 <span data-ttu-id="81cde-121">데이터 소스에서 반환 된 형식과 일치 하지 않는 범위 변수에 대해 명시적 형식을 지정 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-121">You may need to specify an explicit type for a range variable that does not match the type returned from the data source.</span></span> <span data-ttu-id="81cde-122">범위 변수의 형식을 사용 하 여 지정할 수 있습니다는 `As` 절.</span><span class="sxs-lookup"><span data-stu-id="81cde-122">You can specify the type of the range variable by using an `As` clause.</span></span> <span data-ttu-id="81cde-123">그러나 이렇게 하면 오류로 변환 되 면는 [축소 변환](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) 및 `Option Strict` 로 설정 된 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-123">However, this results in an error if the conversion is a [narrowing conversion](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and `Option Strict` is set to `On`.</span></span> <span data-ttu-id="81cde-124">따라서 데이터 원본에서 검색 된 값에는 변환을 수행 하도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-124">Therefore, we recommend that you perform the conversion on the values retrieved from the data source.</span></span> <span data-ttu-id="81cde-125">사용 하 여 명시적 범위 변수 형식으로 값 데이터 소스에서 변환할 수는 <xref:System.Linq.Enumerable.Cast%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="81cde-125">You can convert the values from the data source to the explicit range variable type by using the <xref:System.Linq.Enumerable.Cast%2A> method.</span></span> <span data-ttu-id="81cde-126">선택한 값으로 캐스팅할 수도 있습니다는 `Select` 절을 명시적 형식으로 범위 변수의 형식과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-126">You can also cast the values selected in the `Select` clause to an explicit type that is different from the type of the range variable.</span></span> <span data-ttu-id="81cde-127">이러한 점은 다음 코드에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-127">These points are illustrated in the following code.</span></span>  
  
 [!code-vb[VbLINQTypeRels#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_2.vb)]  
  
## <a name="queries-that-return-entire-elements-of-the-source-data"></a><span data-ttu-id="81cde-128">원본 데이터의 전체 요소를 반환 하는 쿼리</span><span class="sxs-lookup"><span data-stu-id="81cde-128">Queries That Return Entire Elements of the Source Data</span></span>  
 <span data-ttu-id="81cde-129">다음 예제에서는 한 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 원본 데이터에서 선택 된 요소의 시퀀스를 반환 하는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-129">The following example shows a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query operation that returns a sequence of elements selected from the source data.</span></span> <span data-ttu-id="81cde-130">소스 `names`, 문자열의 배열을 포함 쿼리 결과 M으로 시작 하는 문자열을 포함 하는 연속입니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-130">The source, `names`, contains an array of strings, and the query output is a sequence containing strings that start with the letter M.</span></span>  
  
 [!code-vb[VbLINQTypeRels#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_3.vb)]  
  
 <span data-ttu-id="81cde-131">이 다음 코드와 동일 하지만 훨씬 더 짧게 만들어 더 쉽게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-131">This is equivalent to the following code, but is much shorter and easier to write.</span></span> <span data-ttu-id="81cde-132">쿼리에서 지역 형식 유추에 대 한 의존도 Visual Basic에서 기본 스타일입니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-132">Reliance on local type inference in queries is the preferred style in Visual Basic.</span></span>  
  
 [!code-vb[VbLINQTypeRels#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_4.vb)]  
  
 <span data-ttu-id="81cde-133">유형은 암시적 또는 명시적으로 결정 됩니다 없이의 이전 코드 예제 모두에 다음 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-133">The following relationships exist in both of the previous code examples, whether the types are determined implicitly or explicitly.</span></span>  
  
1.  <span data-ttu-id="81cde-134">데이터 원본에 있는 요소의 형식 `names`, 범위 변수의 형식이 `name`, 쿼리에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-134">The type of the elements in the data source, `names`, is the type of the range variable, `name`, in the query.</span></span>  
  
2.  <span data-ttu-id="81cde-135">현재 선택 된 개체의 형식 `name`, 쿼리 변수의 형식을 결정 `mNames`합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-135">The type of the object that is selected, `name`, determines the type of the query variable, `mNames`.</span></span> <span data-ttu-id="81cde-136">여기 `name` 는 문자열로, 쿼리 변수는 Visual Basic에서 IEnumerable (Of String).</span><span class="sxs-lookup"><span data-stu-id="81cde-136">Here `name` is a string, so the query variable is IEnumerable(Of String) in Visual Basic.</span></span>  
  
3.  <span data-ttu-id="81cde-137">에 정의 된 쿼리 `mNames` 에서 실행 되는 `For Each` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-137">The query defined in `mNames` is executed in the `For Each` loop.</span></span> <span data-ttu-id="81cde-138">루프는 쿼리 실행의 결과 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-138">The loop iterates over the result of executing the query.</span></span> <span data-ttu-id="81cde-139">때문에 `mNames`실행 될 때, 루프 반복 변수 문자열의 시퀀스를 반환 합니다 `nm`, 또한는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-139">Because `mNames`, when it is executed, will return a sequence of strings, the loop iteration variable, `nm`, also is a string.</span></span>  
  
## <a name="queries-that-return-one-field-from-selected-elements"></a><span data-ttu-id="81cde-140">선택한 요소에서 한 필드를 반환 하는 쿼리</span><span class="sxs-lookup"><span data-stu-id="81cde-140">Queries That Return One Field from Selected Elements</span></span>  
 <span data-ttu-id="81cde-141">다음 예제에서는 한 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] 쿼리 데이터 원본에서 선택한 각 요소에의 한 부분을 포함 하는 시퀀스를 반환 하는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-141">The following example shows a [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] query operation that returns a sequence containing only one part of each element selected from the data source.</span></span> <span data-ttu-id="81cde-142">컬렉션을 사용 하는 쿼리 `Customer` 데이터 원본으로 개체를 프로젝트에 해당는 `Name` 결과에 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-142">The query takes a collection of `Customer` objects as its data source and projects only the `Name` property in the result.</span></span> <span data-ttu-id="81cde-143">고객 이름은 문자열 이기 때문에 쿼리 출력으로 문자열의 시퀀스를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-143">Because the customer name is a string, the query produces a sequence of strings as output.</span></span>  
  
```vb  
' Method GetTable returns a table of Customer objects.  
Dim customers = db.GetTable(Of Customer)()  
Dim custNames = From cust In customers   
                Where cust.City = "London"   
                Select cust.Name  
  
For Each custName In custNames  
    Console.WriteLine(custName)  
Next  
```  
  
 <span data-ttu-id="81cde-144">간단한 예제에서와 같이 변수 간 관계는 합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-144">The relationships between variables are like those in the simpler example.</span></span>  
  
1.  <span data-ttu-id="81cde-145">데이터 원본에 있는 요소의 형식 `customers`, 범위 변수의 형식이 `cust`, 쿼리에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-145">The type of the elements in the data source, `customers`, is the type of the range variable, `cust`, in the query.</span></span> <span data-ttu-id="81cde-146">이 예제에서는 형식 `Customer`합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-146">In this example, that type is `Customer`.</span></span>  
  
2.  <span data-ttu-id="81cde-147">`Select` 문에서 반환 된 `Name` 각 속성 `Customer` 개체 전체가 아니라 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-147">The `Select` statement returns the `Name` property of each `Customer` object instead of the whole object.</span></span> <span data-ttu-id="81cde-148">때문에 `Name` 쿼리 변수는 문자열 `custNames`, 다시 됩니다 IEnumerable (Of String)의 `Customer`합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-148">Because `Name` is a string, the query variable, `custNames`, will again be IEnumerable(Of String), not of `Customer`.</span></span>  
  
3.  <span data-ttu-id="81cde-149">때문에 `custNames` 문자열의 시퀀스를 나타내는 `For Each` 루프의 반복 변수 `custName`, 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-149">Because `custNames` represents a sequence of strings, the `For Each` loop's iteration variable, `custName`, must be a string.</span></span>  
  
 <span data-ttu-id="81cde-150">지역 형식 유추, 앞의 예제를 작성 하 고 다음 예제와 같이 이해 하기 번거로운 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-150">Without local type inference, the previous example would be more cumbersome to write and to understand, as the following example shows.</span></span>  
  
```vb  
' Method GetTable returns a table of Customer objects.  
 Dim customers As Table(Of Customer) = db.GetTable(Of Customer)()  
 Dim custNames As IEnumerable(Of String) =  
     From cust As Customer In customers   
     Where cust.City = "London"   
     Select cust.Name  
  
 For Each custName As String In custNames  
     Console.WriteLine(custName)  
 Next  
```  
  
## <a name="queries-that-require-anonymous-types"></a><span data-ttu-id="81cde-151">익명 형식이 필요로 하는 쿼리</span><span class="sxs-lookup"><span data-stu-id="81cde-151">Queries That Require Anonymous Types</span></span>  
 <span data-ttu-id="81cde-152">다음 예제에서는 보다 복잡 한 상황을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-152">The following example shows a more complex situation.</span></span> <span data-ttu-id="81cde-153">이전 예제에서는 모든 변수 형식을 명시적으로 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-153">In the previous example, it was inconvenient to specify types for all the variables explicitly.</span></span> <span data-ttu-id="81cde-154">이 예제에서는 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-154">In this example, it is impossible.</span></span> <span data-ttu-id="81cde-155">전체 선택 하는 대신 `Customer` 데이터 원본 또는 각 요소에서 단일 필드의 요소는 `Select` 원래의 두 속성을 반환 하는 절이 쿼리에 `Customer` 개체: `Name` 및 `City`합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-155">Instead of selecting entire `Customer` elements from the data source, or a single field from each element, the `Select` clause in this query returns two properties of the original `Customer` object: `Name` and `City`.</span></span> <span data-ttu-id="81cde-156">에 대 한 응답에는 `Select` 절 컴파일러 이러한 두 속성을 포함 하는 익명 형식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-156">In response to the `Select` clause, the compiler defines an anonymous type that contains those two properties.</span></span> <span data-ttu-id="81cde-157">실행 결과 `nameCityQuery` 에 `For Each` 루프는 새 익명 형식의 인스턴스 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-157">The result of executing `nameCityQuery` in the `For Each` loop is a collection of instances of the new anonymous type.</span></span> <span data-ttu-id="81cde-158">형식을 지정할 수 없습니다 익명 형식 이름이 없기 때문에 사용할 수 있는, `nameCityQuery` 또는 `custInfo` 명시적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-158">Because the anonymous type has no usable name, you cannot specify the type of `nameCityQuery` or `custInfo` explicitly.</span></span> <span data-ttu-id="81cde-159">즉, 대신 사용할 형식 이름이 있는 익명 형식을 `String` 에서 `IEnumerable(Of String)`합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-159">That is, with an anonymous type, you have no type name to use in place of `String` in `IEnumerable(Of String)`.</span></span> <span data-ttu-id="81cde-160">자세한 내용은 [무명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81cde-160">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
```vb  
' Method GetTable returns a table of Customer objects.  
Dim customers = db.GetTable(Of Customer)()  
Dim nameCityQuery = From cust In customers   
                    Where cust.City = "London"   
                    Select cust.Name, cust.City  
  
For Each custInfo In nameCityQuery  
    Console.WriteLine(custInfo.Name)  
Next  
```  
  
 <span data-ttu-id="81cde-161">이전 예제에서 모든 변수에 대 한 형식을 지정 하려면 가능한 경우에 관계.</span><span class="sxs-lookup"><span data-stu-id="81cde-161">Although it is not possible to specify types for all the variables in the previous example, the relationships remain the same.</span></span>  
  
1.  <span data-ttu-id="81cde-162">데이터 원본에 있는 요소의 형식은 쿼리에서 범위 변수의 형식을 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-162">The type of the elements in the data source is again the type of the range variable in the query.</span></span> <span data-ttu-id="81cde-163">이 예제에서는 `cust` 의 인스턴스가 `Customer`합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-163">In this example, `cust` is an instance of `Customer`.</span></span>  
  
2.  <span data-ttu-id="81cde-164">때문에 `Select` 문은 쿼리 변수 익명 형식을 생성 `nameCityQuery`, 익명 형식으로 암시적으로 형식화 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-164">Because the `Select` statement produces an anonymous type, the query variable, `nameCityQuery`, must be implicitly typed as an anonymous type.</span></span> <span data-ttu-id="81cde-165">익명 형식에 사용할 수 있는 이름은 및 따라서 명시적으로 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-165">An anonymous type has no usable name, and therefore cannot be specified explicitly.</span></span>  
  
3.  <span data-ttu-id="81cde-166">에 반복 변수의 형식은 `For Each` 루프는 2 단계에서 만든 익명 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-166">The type of the iteration variable in the `For Each` loop is the anonymous type created in step 2.</span></span> <span data-ttu-id="81cde-167">형식 이름이 없기 때문에 사용할 수 있는, 루프 반복 변수의 형식은 암시적으로 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81cde-167">Because the type has no usable name, the type of the loop iteration variable must be determined implicitly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81cde-168">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81cde-168">See Also</span></span>  
 [<span data-ttu-id="81cde-169">Visual Basic에서 LINQ 시작</span><span class="sxs-lookup"><span data-stu-id="81cde-169">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [<span data-ttu-id="81cde-170">익명 형식</span><span class="sxs-lookup"><span data-stu-id="81cde-170">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [<span data-ttu-id="81cde-171">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="81cde-171">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="81cde-172">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="81cde-172">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="81cde-173">LINQ</span><span class="sxs-lookup"><span data-stu-id="81cde-173">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="81cde-174">쿼리</span><span class="sxs-lookup"><span data-stu-id="81cde-174">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)
