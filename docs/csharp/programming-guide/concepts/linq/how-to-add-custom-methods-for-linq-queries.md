---
title: '방법: LINQ 쿼리용 사용자 지정 메서드 추가(C#)'
ms.date: 07/20/2015
ms.assetid: 1a500f60-2e10-49fb-8b2a-d8d08e4817cb
ms.openlocfilehash: cd282b4b8ee4add759070317d9dbc3f78c07abf1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-custom-methods-for-linq-queries-c"></a><span data-ttu-id="6a402-102">방법: LINQ 쿼리용 사용자 지정 메서드 추가(C#)</span><span class="sxs-lookup"><span data-stu-id="6a402-102">How to: Add Custom Methods for LINQ Queries (C#)</span></span>
<span data-ttu-id="6a402-103"><xref:System.Collections.Generic.IEnumerable%601> 인터페이스에 확장 메서드를 추가하여 LINQ 쿼리에 사용할 수 있는 메서드 집합을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-103">You can extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="6a402-104">예를 들어 표준 평균 또는 최대 작업 외에 사용자 지정 집계 메서드를 만들어 값 시퀀스에서 단일 값을 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-104">For example, in addition to the standard average or maximum operations, you can create a custom aggregate method to compute a single value from a sequence of values.</span></span> <span data-ttu-id="6a402-105">값 시퀀스에 대한 특정 데이터 변환 또는 사용자 지정 필터로 작동하고 새 시퀀스를 반환하는 메서드를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-105">You can also create a method that works as a custom filter or a specific data transform for a sequence of values and returns a new sequence.</span></span> <span data-ttu-id="6a402-106">이러한 메서드의 예로는 <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A> 및 <xref:System.Linq.Enumerable.Reverse%2A>가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-106">Examples of such methods are <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A>, and <xref:System.Linq.Enumerable.Reverse%2A>.</span></span>  
  
 <span data-ttu-id="6a402-107"><xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 확장하면 사용자 지정 메서드를 열거 가능한 컬렉션에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-107">When you extend the <xref:System.Collections.Generic.IEnumerable%601> interface, you can apply your custom methods to any enumerable collection.</span></span> <span data-ttu-id="6a402-108">자세한 내용은 [확장 메서드](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6a402-108">For more information, see [Extension Methods](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span></span>  
  
## <a name="adding-an-aggregate-method"></a><span data-ttu-id="6a402-109">집계 메서드 추가</span><span class="sxs-lookup"><span data-stu-id="6a402-109">Adding an Aggregate Method</span></span>  
 <span data-ttu-id="6a402-110">집계 메서드는 값 집합에서 하나의 값을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-110">An aggregate method computes a single value from a set of values.</span></span> <span data-ttu-id="6a402-111">LINQ는 <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A> 및 <xref:System.Linq.Enumerable.Max%2A>를 포함하여 여러 집계 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-111">LINQ provides several aggregate methods, including <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Max%2A>.</span></span> <span data-ttu-id="6a402-112"><xref:System.Collections.Generic.IEnumerable%601> 인터페이스에 확장 메서드를 추가하여 고유한 집계 메서드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-112">You can create your own aggregate method by adding an extension method to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
 <span data-ttu-id="6a402-113">다음 코드 예제에서는 `double` 형식의 숫자 시퀀스에 대한 중앙값을 계산하는 `Median`이라는 확장 메서드를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-113">The following code example shows how to create an extension method called `Median` to compute a median for a sequence of numbers of type `double`.</span></span>  
  
```csharp  
public static class LINQExtension  
{  
    public static double Median(this IEnumerable<double> source)  
    {  
        if (source.Count() == 0)  
        {  
            throw new InvalidOperationException("Cannot compute median for an empty set.");  
        }  
  
        var sortedList = from number in source  
                         orderby number  
                         select number;  
  
        int itemIndex = (int)sortedList.Count() / 2;  
  
        if (sortedList.Count() % 2 == 0)  
        {  
            // Even number of items.  
            return (sortedList.ElementAt(itemIndex) + sortedList.ElementAt(itemIndex - 1)) / 2;  
        }  
        else  
        {  
            // Odd number of items.  
            return sortedList.ElementAt(itemIndex);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="6a402-114"><xref:System.Collections.Generic.IEnumerable%601> 인터페이스에서 다른 집계 메서드를 호출하는 것과 같은 방식으로 열거 가능한 컬렉션에 대해 이 확장 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-114">You call this extension method for any enumerable collection in the same way you call other aggregate methods from the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
 <span data-ttu-id="6a402-115">다음 코드 예제에서는 `double` 형식의 배열에 대해 `Median` 메서드를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-115">The following code example shows how to use the `Median` method for an array of type `double`.</span></span>  
  
```csharp  
double[] numbers1 = { 1.9, 2, 8, 4, 5.7, 6, 7.2, 0 };  
  
var query1 = numbers1.Median();  
  
Console.WriteLine("double: Median = " + query1);  
```  

```csharp  
/*  
 This code produces the following output:  
  
 Double: Median = 4.85  
*/  
```  
  
### <a name="overloading-an-aggregate-method-to-accept-various-types"></a><span data-ttu-id="6a402-116">다양한 형식을 허용하도록 집계 메서드 오버로드</span><span class="sxs-lookup"><span data-stu-id="6a402-116">Overloading an Aggregate Method to Accept Various Types</span></span>  
 <span data-ttu-id="6a402-117">다양한 형식의 시퀀스를 허용하도록 집계 메서드를 오버로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-117">You can overload your aggregate method so that it accepts sequences of various types.</span></span> <span data-ttu-id="6a402-118">표준 접근법은 각 형식에 대한 오버로드를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-118">The standard approach is to create an overload for each type.</span></span> <span data-ttu-id="6a402-119">또 다른 접근법은 제네릭 형식을 사용하고 대리자를 통해 이를 특정 형식으로 변환할 오버로드를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-119">Another approach is to create an overload that will take a generic type and convert it to a specific type by using a delegate.</span></span> <span data-ttu-id="6a402-120">두 가지 접근법을 결합할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-120">You can also combine both approaches.</span></span>  
  
#### <a name="to-create-an-overload-for-each-type"></a><span data-ttu-id="6a402-121">각 형식에 대한 오버로드를 만들려면</span><span class="sxs-lookup"><span data-stu-id="6a402-121">To create an overload for each type</span></span>  
 <span data-ttu-id="6a402-122">지원하려는 각 형식에 대한 특정 오버로드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-122">You can create a specific overload for each type that you want to support.</span></span> <span data-ttu-id="6a402-123">다음 코드 예제에서는 `integer` 형식에 대한 `Median` 메서드의 오버로드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-123">The following code example shows an overload of the `Median` method for the `integer` type.</span></span>  
  
```csharp  
//int overload  
  
public static double Median(this IEnumerable<int> source)  
{  
    return (from num in source select (double)num).Median();  
}  
```   
 <span data-ttu-id="6a402-124">이제 다음 코드와 같이 `integer` 및 `double` 형식에 대한 `Median` 오버로드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-124">You can now call the `Median` overloads for both `integer` and `double` types, as shown in the following code:</span></span>  
  
```csharp  
double[] numbers1 = { 1.9, 2, 8, 4, 5.7, 6, 7.2, 0 };  
  
var query1 = numbers1.Median();  
  
Console.WriteLine("double: Median = " + query1);  
```  
  
```csharp  
int[] numbers2 = { 1, 2, 3, 4, 5 };  
  
var query2 = numbers2.Median();  
  
Console.WriteLine("int: Median = " + query2);  
```  
  
```csharp  
/*  
 This code produces the following output:  
  
 Double: Median = 4.85  
 Integer: Median = 3  
*/  
```  

#### <a name="to-create-a-generic-overload"></a><span data-ttu-id="6a402-125">제네릭 오버로드를 만들려면</span><span class="sxs-lookup"><span data-stu-id="6a402-125">To create a generic overload</span></span>  
 <span data-ttu-id="6a402-126">제네릭 개체의 시퀀스를 허용하는 오버로드를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-126">You can also create an overload that accepts a sequence of generic objects.</span></span> <span data-ttu-id="6a402-127">이 오버로드는 대리자를 매개 변수로 사용하여 제네릭 형식의 개체 시퀀스를 특정 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-127">This overload takes a delegate as a parameter and uses it to convert a sequence of objects of a generic type to a specific type.</span></span>  
  
 <span data-ttu-id="6a402-128">다음 코드에서는 <xref:System.Func%602> 대리자를 매개 변수로 사용하는 `Median` 메서드의 오버로드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-128">The following code shows an overload of the `Median` method that takes the <xref:System.Func%602> delegate as a parameter.</span></span> <span data-ttu-id="6a402-129">이 대리자는 제네릭 형식 T의 개체를 사용하고 `double` 형식의 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-129">This delegate takes an object of generic type T and returns an object of type `double`.</span></span>  
  
```csharp  
// Generic overload.  
  
public static double Median<T>(this IEnumerable<T> numbers,  
                       Func<T, double> selector)  
{  
    return (from num in numbers select selector(num)).Median();  
}  
```  
  
 <span data-ttu-id="6a402-130">이제 임의 형식의 개체 시퀀스에 대해 `Median` 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-130">You can now call the `Median` method for a sequence of objects of any type.</span></span> <span data-ttu-id="6a402-131">형식에 자체 메서드 오버로드가 없으면 대리자 매개 변수를 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-131">If the type does not have its own method overload, you have to pass a delegate parameter.</span></span> <span data-ttu-id="6a402-132">C#에서는 이 목적으로 람다 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-132">In C#, you can use a lambda expression for this purpose.</span></span> <span data-ttu-id="6a402-133">또한 Visual Basic에서만, 메서드 호출 대신 `Aggregate` 또는 `Group By` 절을 사용할 경우 범위 내에 있는 값 또는 식을 이 절에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-133">Also, in Visual Basic only, if you use the `Aggregate` or `Group By` clause instead of the method call, you can pass any value or expression that is in the scope this clause.</span></span>  
  
 <span data-ttu-id="6a402-134">다음 예제 코드에서는 정수 배열 및 문자열 배열에 대해 `Median` 메서드를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-134">The following example code shows how to call the `Median` method for an array of integers and an array of strings.</span></span> <span data-ttu-id="6a402-135">문자열의 경우 배열에서 문자열 길이의 중앙값이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-135">For strings, the median for the lengths of strings in the array is calculated.</span></span> <span data-ttu-id="6a402-136">예제에서는 각 경우에 <xref:System.Func%602> 대리자 매개 변수를 `Median` 메서드에 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-136">The example shows how to pass the <xref:System.Func%602> delegate parameter to the `Median` method for each case.</span></span>  
  
```csharp  
int[] numbers3 = { 1, 2, 3, 4, 5 };  
  
/*   
  You can use the num=>num lambda expression as a parameter for the Median method   
  so that the compiler will implicitly convert its value to double.  
  If there is no implicit conversion, the compiler will display an error message.            
*/  
  
var query3 = numbers3.Median(num => num);  
  
Console.WriteLine("int: Median = " + query3);  
  
string[] numbers4 = { "one", "two", "three", "four", "five" };  
  
// With the generic overload, you can also use numeric properties of objects.  
  
var query4 = numbers4.Median(str => str.Length);  
  
Console.WriteLine("String: Median = " + query4);  
  
/*  
 This code produces the following output:  
  
 Integer: Median = 3  
 String: Median = 4  
*/  
```   
## <a name="adding-a-method-that-returns-a-collection"></a><span data-ttu-id="6a402-137">컬렉션을 반환하는 메서드 추가</span><span class="sxs-lookup"><span data-stu-id="6a402-137">Adding a Method That Returns a Collection</span></span>  
 <span data-ttu-id="6a402-138">값 시퀀스를 반환하는 사용자 지정 쿼리 메서드를 사용하여 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-138">You can extend the <xref:System.Collections.Generic.IEnumerable%601> interface with a custom query method that returns a sequence of values.</span></span> <span data-ttu-id="6a402-139">이 경우 메서드는 <xref:System.Collections.Generic.IEnumerable%601> 형식의 컬렉션을 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-139">In this case, the method must return a collection of type <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="6a402-140">이러한 메서드는 필터 또는 데이터 변환을 값 시퀀스에 적용하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-140">Such methods can be used to apply filters or data transforms to a sequence of values.</span></span>  
  
 <span data-ttu-id="6a402-141">다음 예제에서는 모든 기타 요소를 첫 번째 인수부터 반환하는 `AlternateElements` 확장 메서드를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-141">The following example shows how to create an extension method named `AlternateElements` that returns every other element in a collection, starting from the first element.</span></span>  
  
```csharp  
// Extension method for the IEnumerable<T> interface.   
// The method returns every other element of a sequence.  
  
public static IEnumerable<T> AlternateElements<T>(this IEnumerable<T> source)  
{  
    List<T> list = new List<T>();  
  
    int i = 0;  
  
    foreach (var element in source)  
    {  
        if (i % 2 == 0)  
        {  
            list.Add(element);  
        }  
  
        i++;  
    }  
  
    return list;  
}  
```  
 <span data-ttu-id="6a402-142">다음 코드와 같이 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스에서 다른 메서드를 호출할 때와 같은 방법으로 열거 가능한 모든 컬렉션에 대해 이 확장 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a402-142">You can call this extension method for any enumerable collection just as you would call other methods from the <xref:System.Collections.Generic.IEnumerable%601> interface, as shown in the following code:</span></span>  
  
```csharp  
string[] strings = { "a", "b", "c", "d", "e" };  
  
var query = strings.AlternateElements();  
  
foreach (var element in query)  
{  
    Console.WriteLine(element);  
}  
/*  
 This code produces the following output:  
  
 a  
 c  
 e  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="6a402-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a402-143">See Also</span></span>  
 <xref:System.Collections.Generic.IEnumerable%601>  
 [<span data-ttu-id="6a402-144">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="6a402-144">Extension Methods</span></span>](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
