---
title: "방법: LINQ 쿼리 (Visual Basic)에 대 한 사용자 지정 메서드 추가 | Microsoft 문서"
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
ms.assetid: 099b2e2a-83cd-45c6-aa4d-01b398b5faaf
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 166eb731d41e009c374ba55f929eed302793ecd0
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-add-custom-methods-for-linq-queries-visual-basic"></a><span data-ttu-id="f07bb-102">방법: LINQ 쿼리 (Visual Basic)에 대 한 사용자 지정 메서드 추가</span><span class="sxs-lookup"><span data-stu-id="f07bb-102">How to: Add Custom Methods for LINQ Queries (Visual Basic)</span></span>
<span data-ttu-id="f07bb-103">확장 메서드를 추가 하 여 LINQ 쿼리에 사용할 수 있는 메서드 집합을 확장할 수는 <xref:System.Collections.Generic.IEnumerable%601>인터페이스.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="f07bb-103">You can extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="f07bb-104">예를 들어 표준 평균 또는 최대 작업 외에 값의 시퀀스에서 단일 값을 계산 하는 사용자 지정 집계 메서드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07bb-104">For example, in addition to the standard average or maximum operations, you can create a custom aggregate method to compute a single value from a sequence of values.</span></span> <span data-ttu-id="f07bb-105">사용자 지정 필터 또는 값의 시퀀스에 대 한 특정 데이터 변환을로 작동 하 고 새 시퀀스를 반환 하는 메서드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07bb-105">You can also create a method that works as a custom filter or a specific data transform for a sequence of values and returns a new sequence.</span></span> <span data-ttu-id="f07bb-106">이러한 메서드의 예로 <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A>, 및 <xref:System.Linq.Enumerable.Reverse%2A>.</xref:System.Linq.Enumerable.Reverse%2A> </xref:System.Linq.Enumerable.Skip%2A> </xref:System.Linq.Enumerable.Distinct%2A></span><span class="sxs-lookup"><span data-stu-id="f07bb-106">Examples of such methods are <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A>, and <xref:System.Linq.Enumerable.Reverse%2A>.</span></span>  
  
 <span data-ttu-id="f07bb-107">확장 하는 경우는 <xref:System.Collections.Generic.IEnumerable%601>인터페이스, 열거형 컬렉션에 사용자 지정 메서드를 적용할 수 있습니다.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="f07bb-107">When you extend the <xref:System.Collections.Generic.IEnumerable%601> interface, you can apply your custom methods to any enumerable collection.</span></span> <span data-ttu-id="f07bb-108">자세한 내용은 참조 [확장 메서드](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f07bb-108">For more information, see [Extension Methods](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).</span></span>  
  
## <a name="adding-an-aggregate-method"></a><span data-ttu-id="f07bb-109">집계 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f07bb-109">Adding an Aggregate Method</span></span>  
 <span data-ttu-id="f07bb-110">집계 메서드는 값 집합에서 단일 값을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="f07bb-110">An aggregate method computes a single value from a set of values.</span></span> <span data-ttu-id="f07bb-111">포함 하는 여러 집계 메서드를 제공 하는 LINQ <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A>, 및 <xref:System.Linq.Enumerable.Max%2A>.</xref:System.Linq.Enumerable.Max%2A> </xref:System.Linq.Enumerable.Min%2A> </xref:System.Linq.Enumerable.Average%2A></span><span class="sxs-lookup"><span data-stu-id="f07bb-111">LINQ provides several aggregate methods, including <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Max%2A>.</span></span> <span data-ttu-id="f07bb-112">확장 메서드를 추가 하 여 사용자 고유의 집계 메서드를 만들 수는 <xref:System.Collections.Generic.IEnumerable%601>인터페이스.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="f07bb-112">You can create your own aggregate method by adding an extension method to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
 <span data-ttu-id="f07bb-113">다음 코드 예제에는 확장 메서드를 만드는 방법을 보여 줍니다 `Median` 일련의 숫자 형식에 대 한 중앙값을 계산 하 `double`합니다.</span><span class="sxs-lookup"><span data-stu-id="f07bb-113">The following code example shows how to create an extension method called `Median` to compute a median for a sequence of numbers of type `double`.</span></span>  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module LINQExtension  
  
    ' Extension method for the IEnumerable(of T) interface.   
    ' The method accepts only values of the Double type.  
    <Extension()>   
    Function Median(ByVal source As IEnumerable(Of Double)) As Double  
        If source.Count = 0 Then  
            Throw New InvalidOperationException("Cannot compute median for an empty set.")  
        End If  
  
        Dim sortedSource = From number In source   
                           Order By number  
  
        Dim itemIndex = sortedSource.Count \ 2  
  
        If sortedSource.Count Mod 2 = 0 Then  
            ' Even number of items in list.  
            Return (sortedSource(itemIndex) + sortedSource(itemIndex - 1)) / 2  
        Else  
            ' Odd number of items in list.  
            Return sortedSource(itemIndex)  
        End If  
    End Function  
End Module  
```  
  
 <span data-ttu-id="f07bb-114">다른 집계 메서드를 호출 하면 동일한 방식으로 열거 가능한 컬렉션에 대 한이 확장 메서드를 호출는 <xref:System.Collections.Generic.IEnumerable%601>인터페이스.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="f07bb-114">You call this extension method for any enumerable collection in the same way you call other aggregate methods from the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f07bb-115">Visual Basic에서 사용 하거나 메서드 호출 또는 표준 쿼리 구문에는 `Aggregate` 또는 `Group By` 절.</span><span class="sxs-lookup"><span data-stu-id="f07bb-115">In Visual Basic, you can either use a method call or standard query syntax for the `Aggregate` or `Group By` clause.</span></span> <span data-ttu-id="f07bb-116">자세한 내용은 참조 [Aggregate 절](../../../../visual-basic/language-reference/queries/aggregate-clause.md) 및 [그룹 By 절](../../../../visual-basic/language-reference/queries/group-by-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f07bb-116">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="f07bb-117">다음 코드 예제를 사용 하는 방법을 보여 줍니다는 `Median` 형식의 배열에 대 한 메서드 `double`합니다.</span><span class="sxs-lookup"><span data-stu-id="f07bb-117">The following code example shows how to use the `Median` method for an array of type `double`.</span></span>  
  
<span data-ttu-id="f07bb-118"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="f07bb-118"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
<span data-ttu-id="f07bb-119"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="f07bb-119"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span></span>  
### <a name="overloading-an-aggregate-method-to-accept-various-types"></a><span data-ttu-id="f07bb-120">다양 한 형식에 적용할 집계 메서드를 오버 로드</span><span class="sxs-lookup"><span data-stu-id="f07bb-120">Overloading an Aggregate Method to Accept Various Types</span></span>  
 <span data-ttu-id="f07bb-121">다양 한 형식의 시퀀스를 수락 하 여 집계 메서드를 오버 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07bb-121">You can overload your aggregate method so that it accepts sequences of various types.</span></span> <span data-ttu-id="f07bb-122">각 형식에 대 한 오버 로드를 만들 하는 표준 방법이입니다.</span><span class="sxs-lookup"><span data-stu-id="f07bb-122">The standard approach is to create an overload for each type.</span></span> <span data-ttu-id="f07bb-123">또 다른 방법은 제네릭 형식을 하는 대리자를 사용 하 여 특정 형식으로 변환 하는 오버 로드를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f07bb-123">Another approach is to create an overload that will take a generic type and convert it to a specific type by using a delegate.</span></span> <span data-ttu-id="f07bb-124">두 방법 모두를 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07bb-124">You can also combine both approaches.</span></span>  
  
#### <a name="to-create-an-overload-for-each-type"></a><span data-ttu-id="f07bb-125">각 형식에 대 한 오버 로드를 만들려면</span><span class="sxs-lookup"><span data-stu-id="f07bb-125">To create an overload for each type</span></span>  
 <span data-ttu-id="f07bb-126">지원 하려는 각 형식에 대 한 특정 오버 로드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07bb-126">You can create a specific overload for each type that you want to support.</span></span> <span data-ttu-id="f07bb-127">다음 코드 예제에서는 오버 로드는 `Median` 에 대 한 메서드는 `integer` 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="f07bb-127">The following code example shows an overload of the `Median` method for the `integer` type.</span></span>  
  
<span data-ttu-id="f07bb-128"><CodeContentPlaceHolder>3</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="f07bb-128"><CodeContentPlaceHolder>3</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="f07bb-129">이제 호출할 수는 `Median` 둘 다에 대해 오버 로드 `integer` 및 `double` 형식, 다음 코드에 나와 있는 것 처럼:</span><span class="sxs-lookup"><span data-stu-id="f07bb-129">You can now call the `Median` overloads for both `integer` and `double` types, as shown in the following code:</span></span>  
  
<span data-ttu-id="f07bb-130"><CodeContentPlaceHolder>4</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="f07bb-130"><CodeContentPlaceHolder>4</CodeContentPlaceHolder></span></span>  
<span data-ttu-id="f07bb-131"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="f07bb-131"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span></span>  
<span data-ttu-id="f07bb-132"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="f07bb-132"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span></span>  
#### <a name="to-create-a-generic-overload"></a><span data-ttu-id="f07bb-133">제네릭 오버 로드를 만들려면</span><span class="sxs-lookup"><span data-stu-id="f07bb-133">To create a generic overload</span></span>  
 <span data-ttu-id="f07bb-134">일반 개체의 시퀀스를 받아들이는 오버 로드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07bb-134">You can also create an overload that accepts a sequence of generic objects.</span></span> <span data-ttu-id="f07bb-135">이 오버 로드는 대리자를 매개 변수로 제네릭 형식의 개체 시퀀스의 특정 형식으로 변환 하려면 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f07bb-135">This overload takes a delegate as a parameter and uses it to convert a sequence of objects of a generic type to a specific type.</span></span>  
  
 <span data-ttu-id="f07bb-136">다음 코드에서는 오버 로드는 `Median` 를 받는 메서드에 <xref:System.Func%602>대리자를 매개 변수로.</xref:System.Func%602></span><span class="sxs-lookup"><span data-stu-id="f07bb-136">The following code shows an overload of the `Median` method that takes the <xref:System.Func%602> delegate as a parameter.</span></span> <span data-ttu-id="f07bb-137">이 대리자는 제네릭 형식 T의 개체는 개체를 반환 형식의 `double`합니다.</span><span class="sxs-lookup"><span data-stu-id="f07bb-137">This delegate takes an object of generic type T and returns an object of type `double`.</span></span>  
  
```vb  
' Generic overload.  
  
<Extension()>   
Function Median(Of T)(ByVal source As IEnumerable(Of T),   
                      ByVal selector As Func(Of T, Double)) As Double  
    Return Aggregate num In source Select selector(num) Into med = Median()  
End Function  
```  
  
 <span data-ttu-id="f07bb-138">이제 호출할 수는 `Median` 모든 형식의 개체의 시퀀스에 대 한 메서드.</span><span class="sxs-lookup"><span data-stu-id="f07bb-138">You can now call the `Median` method for a sequence of objects of any type.</span></span> <span data-ttu-id="f07bb-139">형식에 고유한 메서드 오버 로드가 없는 경우는 대리자 매개 변수를 전달 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f07bb-139">If the type does not have its own method overload, you have to pass a delegate parameter.</span></span> <span data-ttu-id="f07bb-140">Visual Basic의 람다 식을이 용도로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07bb-140">In Visual Basic, you can use a lambda expression for this purpose.</span></span> <span data-ttu-id="f07bb-141">또한 사용 하는 경우는 `Aggregate` 또는 `Group By` 메서드를 호출 하는 대신 절 임의의 값 또는이 절은 범위 내에 있는 식을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07bb-141">Also, if you use the `Aggregate` or `Group By` clause instead of the method call, you can pass any value or expression that is in the scope this clause.</span></span>  
  
 <span data-ttu-id="f07bb-142">다음 예제 코드를 호출 하는 방법을 보여 줍니다는 `Median` 정수의 배열 및 문자열의 배열에 대 한 메서드.</span><span class="sxs-lookup"><span data-stu-id="f07bb-142">The following example code shows how to call the `Median` method for an array of integers and an array of strings.</span></span> <span data-ttu-id="f07bb-143">문자열, 배열에 문자열의 길이 대 한 중앙값을 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f07bb-143">For strings, the median for the lengths of strings in the array is calculated.</span></span> <span data-ttu-id="f07bb-144">전달 하는 방법을 보여 주는 예제는는 <xref:System.Func%602>대리자를 매개 변수는 `Median` 각 사례에 대 한 메서드.</xref:System.Func%602></span><span class="sxs-lookup"><span data-stu-id="f07bb-144">The example shows how to pass the <xref:System.Func%602> delegate parameter to the `Median` method for each case.</span></span>  
  
<span data-ttu-id="f07bb-145"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="f07bb-145"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span></span>  
## <a name="adding-a-method-that-returns-a-collection"></a><span data-ttu-id="f07bb-146">컬렉션을 반환 하는 메서드 추가</span><span class="sxs-lookup"><span data-stu-id="f07bb-146">Adding a Method That Returns a Collection</span></span>  
 <span data-ttu-id="f07bb-147">확장할 수는 <xref:System.Collections.Generic.IEnumerable%601>값의 시퀀스를 반환 하는 사용자 지정 쿼리 메서드로 인터페이스.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="f07bb-147">You can extend the <xref:System.Collections.Generic.IEnumerable%601> interface with a custom query method that returns a sequence of values.</span></span> <span data-ttu-id="f07bb-148">메서드 이름 필드에 <xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601> 의 컬렉션을 반환 해야이 경우</span><span class="sxs-lookup"><span data-stu-id="f07bb-148">In this case, the method must return a collection of type <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="f07bb-149">값의 시퀀스에 필터 또는 데이터 변환을 적용 하려면 이러한 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07bb-149">Such methods can be used to apply filters or data transforms to a sequence of values.</span></span>  
  
 <span data-ttu-id="f07bb-150">다음 예제에 라는 확장 메서드를 만드는 방법을 보여 줍니다 `AlternateElements` 첫 번째 요소에서 시작 하 여 컬렉션의 다른 모든 요소를 반환 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="f07bb-150">The following example shows how to create an extension method named `AlternateElements` that returns every other element in a collection, starting from the first element.</span></span>  
  
<span data-ttu-id="f07bb-151"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="f07bb-151"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="f07bb-152">다른 메서드를 호출 하는 것 처럼 모든 열거 가능한 컬렉션에 대 한이 확장 메서드를 호출할 수는 <xref:System.Collections.Generic.IEnumerable%601>인터페이스에 다음 코드에 나와 있는 것 처럼:</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="f07bb-152">You can call this extension method for any enumerable collection just as you would call other methods from the <xref:System.Collections.Generic.IEnumerable%601> interface, as shown in the following code:</span></span>  
  
```vb  
Dim strings() As String = {"a", "b", "c", "d", "e"}  
  
Dim query = strings.AlternateElements()  
  
For Each element In query  
    Console.WriteLine(element)  
Next  
  
' This code produces the following output:  
'  
' a  
' c  
' e  
```  
  
## <a name="see-also"></a><span data-ttu-id="f07bb-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f07bb-153">See Also</span></span>  
 <span data-ttu-id="f07bb-154"><xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="f07bb-154"><xref:System.Collections.Generic.IEnumerable%601></span></span>   
<span data-ttu-id="f07bb-155"> [확장명 메서드](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)</span><span class="sxs-lookup"><span data-stu-id="f07bb-155"> [Extension Methods](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)</span></span>
