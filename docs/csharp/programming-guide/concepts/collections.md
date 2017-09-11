---
title: "컬렉션(C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: get-started-article
dev_langs:
- CSharp
ms.assetid: 317d7dc3-8587-4873-8b3e-556f86497939
caps.latest.revision: 6
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 26a90b57350837bd51f222ff716364cb3bb902d5
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="collections-c"></a><span data-ttu-id="ba19c-102">컬렉션(C#)</span><span class="sxs-lookup"><span data-stu-id="ba19c-102">Collections (C#)</span></span>
<span data-ttu-id="ba19c-103">대부분의 응용 프로그램의 경우 관련 개체의 그룹을 만들고 관리하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-103">For many applications, you want to create and manage groups of related objects.</span></span> <span data-ttu-id="ba19c-104">개체를 그룹화하는 방법에는 개체 배열을 만들거나 개체 컬렉션을 만드는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-104">There are two ways to group objects: by creating arrays of objects, and by creating collections of objects.</span></span>  
  
 <span data-ttu-id="ba19c-105">배열은 고정된 개수의 강력한 형식 개체를 만들고 작업하는 데 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-105">Arrays are most useful for creating and working with a fixed number of strongly-typed objects.</span></span> <span data-ttu-id="ba19c-106">배열에 대한 자세한 내용은 [배열](../../../csharp/programming-guide/arrays/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba19c-106">For information about arrays, see [Arrays](../../../csharp/programming-guide/arrays/index.md).</span></span>  
  
 <span data-ttu-id="ba19c-107">컬렉션은 개체 그룹에 대해 작업하는 보다 유연한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-107">Collections provide a more flexible way to work with groups of objects.</span></span> <span data-ttu-id="ba19c-108">배열과 달리, 응용 프로그램의 요구가 변경됨에 따라 작업하는 개체 그룹이 동적으로 확장되거나 축소될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-108">Unlike arrays, the group of objects you work with can grow and shrink dynamically as the needs of the application change.</span></span> <span data-ttu-id="ba19c-109">일부 컬렉션의 경우 키를 사용하여 개체를 신속하게 검색할 수 있도록 컬렉션에 추가하는 모든 개체에 키를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-109">For some collections, you can assign a key to any object that you put into the collection so that you can quickly retrieve the object by using the key.</span></span>  
  
 <span data-ttu-id="ba19c-110">컬렉션은 클래스이므로 해당 컬렉션에 요소를 추가하려면 먼저 클래스 인스턴스를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-110">A collection is a class, so you must declare an instance of the class before you can add elements to that collection.</span></span>  
  
 <span data-ttu-id="ba19c-111">컬렉션에 단일 데이터 형식의 요소만 포함된 경우 <xref:System.Collections.Generic?displayProperty=fullName> 네임스페이스의 클래스 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-111">If your collection contains elements of only one data type, you can use one of the classes in the <xref:System.Collections.Generic?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="ba19c-112">제네릭 컬렉션은 다른 데이터 형식을 추가할 수 없도록 형식 안전성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-112">A generic collection enforces type safety so that no other data type can be added to it.</span></span> <span data-ttu-id="ba19c-113">제네릭 컬렉션에서 요소를 검색하는 경우 해당 데이터 형식을 결정하거나 변환할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-113">When you retrieve an element from a generic collection, you do not have to determine its data type or convert it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba19c-114">이 항목의 예제에서는 `System.Collections.Generic` 및 `System.Linq` 네임스페이스에 대한 [using](../../../csharp/language-reference/keywords/using-directive.md) 지시문을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-114">For the examples in this topic, include [using](../../../csharp/language-reference/keywords/using-directive.md) directives for the `System.Collections.Generic` and `System.Linq` namespaces.</span></span>  
  
 <span data-ttu-id="ba19c-115">**항목 내용**</span><span class="sxs-lookup"><span data-stu-id="ba19c-115">**In this topic**</span></span>  
  
-   [<span data-ttu-id="ba19c-116">간단한 컬렉션 사용</span><span class="sxs-lookup"><span data-stu-id="ba19c-116">Using a Simple Collection</span></span>](#BKMK_SimpleCollection)  
  
-   [<span data-ttu-id="ba19c-117">컬렉션 종류</span><span class="sxs-lookup"><span data-stu-id="ba19c-117">Kinds of Collections</span></span>](#BKMK_KindsOfCollections)  
  
    -   [<span data-ttu-id="ba19c-118">System.Collections.Generic 클래스</span><span class="sxs-lookup"><span data-stu-id="ba19c-118">System.Collections.Generic Classes</span></span>](#BKMK_Generic)  
  
    -   [<span data-ttu-id="ba19c-119">System.Collections.Concurrent 클래스</span><span class="sxs-lookup"><span data-stu-id="ba19c-119">System.Collections.Concurrent Classes</span></span>](#BKMK_Concurrent)  
  
    -   [<span data-ttu-id="ba19c-120">System.Collections 클래스</span><span class="sxs-lookup"><span data-stu-id="ba19c-120">System.Collections Classes</span></span>](#BKMK_Collections)  
  
-   [<span data-ttu-id="ba19c-121">키/값 쌍의 컬렉션 구현</span><span class="sxs-lookup"><span data-stu-id="ba19c-121">Implementing a Collection of Key/Value Pairs</span></span>](#BKMK_KeyValuePairs)  
  
-   [<span data-ttu-id="ba19c-122">LINQ를 사용하여 컬렉션에 액세스</span><span class="sxs-lookup"><span data-stu-id="ba19c-122">Using LINQ to Access a Collection</span></span>](#BKMK_LINQ)  
  
-   [<span data-ttu-id="ba19c-123">컬렉션 정렬</span><span class="sxs-lookup"><span data-stu-id="ba19c-123">Sorting a Collection</span></span>](#BKMK_Sorting)  
  
-   [<span data-ttu-id="ba19c-124">사용자 지정 컬렉션 정의</span><span class="sxs-lookup"><span data-stu-id="ba19c-124">Defining a Custom Collection</span></span>](#BKMK_CustomCollection)  
  
-   [<span data-ttu-id="ba19c-125">반복기</span><span class="sxs-lookup"><span data-stu-id="ba19c-125">Iterators</span></span>](#BKMK_Iterators)  
  
<a name="BKMK_SimpleCollection"></a>
## <a name="using-a-simple-collection"></a><span data-ttu-id="ba19c-126">간단한 컬렉션 사용</span><span class="sxs-lookup"><span data-stu-id="ba19c-126">Using a Simple Collection</span></span>  
 <span data-ttu-id="ba19c-127">이 섹션의 예제에서는 강력한 형식의 개체 목록을 사용할 수 있게 해주는 제네릭 <xref:System.Collections.Generic.List%601> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-127">The examples in this section use the generic <xref:System.Collections.Generic.List%601> class, which enables you to work with a strongly typed list of objects.</span></span>  
  
 <span data-ttu-id="ba19c-128">다음 예제에서는 문자열 목록을 만들고 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 문을 사용하여 문자열을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-128">The following example creates a list of strings and then iterates through the strings by using a or [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement.</span></span>  
  
```csharp  
// Create a list of strings.  
var salmons = new List<string>();  
salmons.Add("chinook");  
salmons.Add("coho");  
salmons.Add("pink");  
salmons.Add("sockeye");  
  
// Iterate through the list.  
foreach (var salmon in salmons)  
{  
    Console.Write(salmon + " ");  
}  
// Output: chinook coho pink sockeye  
```  
  
 <span data-ttu-id="ba19c-129">컬렉션의 내용을 사전에 알고 있는 경우 *컬렉션 이니셜라이저*를 사용하여 컬렉션을 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-129">If the contents of a collection are known in advance, you can use a *collection initializer* to initialize the collection.</span></span> <span data-ttu-id="ba19c-130">자세한 내용은 [개체 및 컬렉션 이니셜라이저](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba19c-130">For more information, see [Object and Collection Initializers](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).</span></span>  
  
 <span data-ttu-id="ba19c-131">다음 예제는 컬렉션 이니셜라이저를 사용하여 컬렉션에 요소를 추가한다는 점을 제외하고 이전 예제와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-131">The following example is the same as the previous example, except a collection initializer is used to add elements to the collection.</span></span>  
  
```csharp  
// Create a list of strings by using a  
// collection initializer.  
var salmons = new List<string> { "chinook", "coho", "pink", "sockeye" };  
  
// Iterate through the list.  
foreach (var salmon in salmons)  
{  
    Console.Write(salmon + " ");  
}  
// Output: chinook coho pink sockeye  
```  
  
 <span data-ttu-id="ba19c-132">`foreach` 문 대신 [for](../../../csharp/language-reference/keywords/for.md) 문을 사용하여 컬렉션을 반복할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-132">You can use a [for](../../../csharp/language-reference/keywords/for.md) statement instead of a `foreach` statement to iterate through a collection.</span></span> <span data-ttu-id="ba19c-133">인덱스 위치에 따라 컬렉션 요소에 액세스하여 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-133">You accomplish this by accessing the collection elements by the index position.</span></span> <span data-ttu-id="ba19c-134">요소의 인덱스는 0부터 시작하고 요소 개수-1에서 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-134">The index of the elements starts at 0 and ends at the element count minus 1.</span></span>  
  
 <span data-ttu-id="ba19c-135">다음 예제에서는 `foreach` 대신 `for`를 사용하여 컬렉션의 요소를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-135">The following example iterates through the elements of a collection by using `for` instead of `foreach`.</span></span>  
  
```csharp  
// Create a list of strings by using a  
// collection initializer.  
var salmons = new List<string> { "chinook", "coho", "pink", "sockeye" };  
  
for (var index = 0; index < salmons.Count; index++)  
{  
    Console.Write(salmons[index] + " ");  
}  
// Output: chinook coho pink sockeye  
```  
  
 <span data-ttu-id="ba19c-136">다음 예제에서는 제거할 개체를 지정하여 컬렉션에서 요소를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-136">The following example removes an element from the collection by specifying the object to remove.</span></span>  
  
```csharp  
// Create a list of strings by using a  
// collection initializer.  
var salmons = new List<string> { "chinook", "coho", "pink", "sockeye" };  
  
// Remove an element from the list by specifying  
// the object.  
salmons.Remove("coho");  
  
// Iterate through the list.  
foreach (var salmon in salmons)  
{  
    Console.Write(salmon + " ");  
}  
// Output: chinook pink sockeye  
```  
  
 <span data-ttu-id="ba19c-137">다음 예제에서는 제네릭 목록에서 요소를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-137">The following example removes elements from a generic list.</span></span> <span data-ttu-id="ba19c-138">`foreach` 문 대신 내림차순으로 반복하는 [for](../../../csharp/language-reference/keywords/for.md) 문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-138">Instead of a `foreach` statement, a [for](../../../csharp/language-reference/keywords/for.md) statement that iterates in descending order is used.</span></span> <span data-ttu-id="ba19c-139">이는 <xref:System.Collections.Generic.List%601.RemoveAt%2A> 메서드로 인해 제거된 요소 뒤의 요소가 더 낮은 인덱스 값을 갖기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-139">This is because the <xref:System.Collections.Generic.List%601.RemoveAt%2A> method causes elements after a removed element to have a lower index value.</span></span>  
  
```csharp  
var numbers = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
  
// Remove odd numbers.  
for (var index = numbers.Count - 1; index >= 0; index--)  
{  
    if (numbers[index] % 2 == 1)  
    {  
        // Remove the element by specifying  
        // the zero-based index in the list.  
        numbers.RemoveAt(index);  
    }  
}  
  
// Iterate through the list.  
// A lambda expression is placed in the ForEach method  
// of the List(T) object.  
numbers.ForEach(  
    number => Console.Write(number + " "));  
// Output: 0 2 4 6 8  
```  
  
 <span data-ttu-id="ba19c-140"><xref:System.Collections.Generic.List%601>의 요소 형식에 대해 고유한 클래스를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-140">For the type of elements in the <xref:System.Collections.Generic.List%601>, you can also define your own class.</span></span> <span data-ttu-id="ba19c-141">다음 예제에서, <xref:System.Collections.Generic.List%601>에서 사용되는 `Galaxy` 클래스는 코드에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-141">In the following example, the `Galaxy` class that is used by the <xref:System.Collections.Generic.List%601> is defined in the code.</span></span>  
  
```csharp  
private static void IterateThroughList()  
{  
    var theGalaxies = new List<Galaxy>  
        {  
            new Galaxy() { Name="Tadpole", MegaLightYears=400},  
            new Galaxy() { Name="Pinwheel", MegaLightYears=25},  
            new Galaxy() { Name="Milky Way", MegaLightYears=0},  
            new Galaxy() { Name="Andromeda", MegaLightYears=3}  
        };  
  
    foreach (Galaxy theGalaxy in theGalaxies)  
    {  
        Console.WriteLine(theGalaxy.Name + "  " + theGalaxy.MegaLightYears);  
    }  
  
    // Output:  
    //  Tadpole  400  
    //  Pinwheel  25  
    //  Milky Way  0  
    //  Andromeda  3  
}  
  
public class Galaxy  
{  
    public string Name { get; set; }  
    public int MegaLightYears { get; set; }  
}  
```  

<a name="BKMK_KindsOfCollections"></a>
## <a name="kinds-of-collections"></a><span data-ttu-id="ba19c-142">컬렉션 종류</span><span class="sxs-lookup"><span data-stu-id="ba19c-142">Kinds of Collections</span></span> 
 <span data-ttu-id="ba19c-143">.NET Framework는 많은 일반적인 컬렉션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-143">Many common collections are provided by the .NET Framework.</span></span> <span data-ttu-id="ba19c-144">컬렉션의 각 형식은 특정 목적에 맞게 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-144">Each type of collection is designed for a specific purpose.</span></span>  
  
 <span data-ttu-id="ba19c-145">이 섹션에서는 다음 몇 가지 일반적인 컬렉션 클래스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-145">Some of the common collection classes are described in this section:</span></span>  
  
-   <span data-ttu-id="ba19c-146">@System.Collections.Generic 클래스</span><span class="sxs-lookup"><span data-stu-id="ba19c-146">@System.Collections.Generic classes</span></span>  
  
-   <span data-ttu-id="ba19c-147">@System.Collections.Concurrent 클래스</span><span class="sxs-lookup"><span data-stu-id="ba19c-147">@System.Collections.Concurrent classes</span></span>  
  
-   <span data-ttu-id="ba19c-148">@System.Collections 클래스</span><span class="sxs-lookup"><span data-stu-id="ba19c-148">@System.Collections classes</span></span>  
  
<a name="BKMK_Generic"></a>
### <a name="systemcollectionsgeneric-classes"></a><span data-ttu-id="ba19c-149">System.Collections.Generic 클래스</span><span class="sxs-lookup"><span data-stu-id="ba19c-149">System.Collections.Generic Classes</span></span>  
 <span data-ttu-id="ba19c-150"><xref:System.Collections.Generic> 네임스페이스의 클래스 중 하나를 사용하여 제네릭 컬렉션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-150">You can create a generic collection by using one of the classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="ba19c-151">제네릭 컬렉션은 컬렉션의 모든 항목에 동일한 데이터 형식이 있는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-151">A generic collection is useful when every item in the collection has the same data type.</span></span> <span data-ttu-id="ba19c-152">제네릭 컬렉션은 원하는 데이터 형식만 추가할 수 있도록 하여 강력한 형식 지정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-152">A generic collection enforces strong typing by allowing only the desired data type to be added.</span></span>  
  
 <span data-ttu-id="ba19c-153">다음 표에서는 자주 사용되는 <xref:System.Collections.Generic?displayProperty=fullName> 네임스페이스 클래스 중 일부를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-153">The following table lists some of the frequently used classes of the <xref:System.Collections.Generic?displayProperty=fullName> namespace:</span></span>  

|<span data-ttu-id="ba19c-154">클래스</span><span class="sxs-lookup"><span data-stu-id="ba19c-154">Class</span></span>|<span data-ttu-id="ba19c-155">설명</span><span class="sxs-lookup"><span data-stu-id="ba19c-155">Description</span></span>| 
|---|---|  
|<xref:System.Collections.Generic.Dictionary%602>|<span data-ttu-id="ba19c-156">키에 따라 구성된 키/값 쌍의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-156">Represents a collection of key/value pairs that are organized based on the key.</span></span>|  
|<xref:System.Collections.Generic.List%601>|<span data-ttu-id="ba19c-157">인덱스로 액세스할 수 있는 개체 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-157">Represents a list of objects that can be accessed by index.</span></span> <span data-ttu-id="ba19c-158">목록의 검색, 정렬 및 수정에 사용할 수 있는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-158">Provides methods to search, sort, and modify lists.</span></span>|  
|<xref:System.Collections.Generic.Queue%601>|<span data-ttu-id="ba19c-159">FIFO(선입선출) 방식의 개체 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-159">Represents a first in, first out (FIFO) collection of objects.</span></span>|  
|<xref:System.Collections.Generic.SortedList%602>|<span data-ttu-id="ba19c-160">연관된 <xref:System.Collections.Generic.IComparer%601> 구현을 기반으로 키에 따라 정렬된 키/값 쌍의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-160">Represents a collection of key/value pairs that are sorted by key based on the associated <xref:System.Collections.Generic.IComparer%601> implementation.</span></span>|  
|<xref:System.Collections.Generic.Stack%601>|<span data-ttu-id="ba19c-161">LIFO(후입선출) 방식의 개체 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-161">Represents a last in, first out (LIFO) collection of objects.</span></span>|  
  
 <span data-ttu-id="ba19c-162">자세한 내용은 [일반적으로 사용되는 컬렉션 형식](../../../standard/collections/commonly-used-collection-types.md), [Collection 클래스 선택](../../../standard/collections/selecting-a-collection-class.md) 및 @System.Collections.Generic을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba19c-162">For additional information, see [Commonly Used Collection Types](../../../standard/collections/commonly-used-collection-types.md), [Selecting a Collection Class](../../../standard/collections/selecting-a-collection-class.md), and @System.Collections.Generic.</span></span>  
  
<a name="BKMK_Concurrent"></a>
### <a name="systemcollectionsconcurrent-classes"></a><span data-ttu-id="ba19c-163">System.Collections.Concurrent 클래스</span><span class="sxs-lookup"><span data-stu-id="ba19c-163">System.Collections.Concurrent Classes</span></span>  
 <span data-ttu-id="ba19c-164">.NET Framework 4 이상에서 <xref:System.Collections.Concurrent> 네임스페이스의 컬렉션은 여러 스레드에서 컬렉션 항목에 액세스하기 위한 효율적이고 스레드로부터 안전한 작업을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-164">In the .NET Framework 4 or newer, the collections in the <xref:System.Collections.Concurrent> namespace provide efficient thread-safe operations for accessing collection items from multiple threads.</span></span>  
  
 <span data-ttu-id="ba19c-165">여러 스레드가 동시에 컬렉션에 액세스할 때마다 <xref:System.Collections.Generic?displayProperty=fullName> 및 <xref:System.Collections?displayProperty=fullName>의 해당 형식 대신 <xref:System.Collections.Concurrent> 네임스페이스의 클래스를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-165">The classes in the <xref:System.Collections.Concurrent> namespace should be used instead of the corresponding types in the <xref:System.Collections.Generic?displayProperty=fullName> and <xref:System.Collections?displayProperty=fullName> namespaces whenever multiple threads are accessing the collection concurrently.</span></span> <span data-ttu-id="ba19c-166">자세한 내용은 [스레드로부터 안전한 컬렉션](../../../standard/collections/thread-safe/index.md) 및 <xref:System.Collections.Concurrent>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba19c-166">For more information, see [Thread-Safe Collections](../../../standard/collections/thread-safe/index.md) and <xref:System.Collections.Concurrent>.</span></span>  
  
 <span data-ttu-id="ba19c-167"><xref:System.Collections.Concurrent> 네임스페이스에 포함된 일부 클래스는 <xref:System.Collections.Concurrent.BlockingCollection%601>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, <xref:System.Collections.Concurrent.ConcurrentQueue%601> 및 <xref:System.Collections.Concurrent.ConcurrentStack%601>입니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-167">Some classes included in the <xref:System.Collections.Concurrent> namespace are <xref:System.Collections.Concurrent.BlockingCollection%601>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, and <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span></span>  
  
<a name="BKMK_Collections"></a>
### <a name="systemcollections-classes"></a><span data-ttu-id="ba19c-168">System.Collections 클래스</span><span class="sxs-lookup"><span data-stu-id="ba19c-168">System.Collections Classes</span></span>  
 <span data-ttu-id="ba19c-169"><xref:System.Collections?displayProperty=fullName> 네임스페이스의 클래스는 구체적 형식의 개체가 아니라 `Object` 형식의 개체로 요소를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-169">The classes in the <xref:System.Collections?displayProperty=fullName> namespace do not store elements as specifically typed objects, but as objects of type `Object`.</span></span>  
  
 <span data-ttu-id="ba19c-170">가능하면 항상 `System.Collections` 네임스페이스의 레거시 형식 대신 <xref:System.Collections.Generic?displayProperty=fullName> 네임스페이스 또는 <xref:System.Collections.Concurrent> 네임스페이스의 제네릭 컬렉션을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-170">Whenever possible, you should use the generic collections in the <xref:System.Collections.Generic?displayProperty=fullName> namespace or the <xref:System.Collections.Concurrent> namespace instead of the legacy types in the `System.Collections` namespace.</span></span>  
  
 <span data-ttu-id="ba19c-171">다음 표에서는 자주 사용되는 `System.Collections` 네임스페이스 클래스 중 일부를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-171">The following table lists some of the frequently used classes in the `System.Collections` namespace:</span></span>  
  
|<span data-ttu-id="ba19c-172">클래스</span><span class="sxs-lookup"><span data-stu-id="ba19c-172">Class</span></span>|<span data-ttu-id="ba19c-173">설명</span><span class="sxs-lookup"><span data-stu-id="ba19c-173">Description</span></span>|  
|---|---|  
|<xref:System.Collections.ArrayList>|<span data-ttu-id="ba19c-174">필요에 따라 크기가 동적으로 증가하는 개체 배열을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-174">Represents an array of objects whose size is dynamically increased as required.</span></span>|  
|<xref:System.Collections.Hashtable>|<span data-ttu-id="ba19c-175">키의 해시 코드에 따라 구성된 키/값 쌍의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-175">Represents a collection of key/value pairs that are organized based on the hash code of the key.</span></span>|  
|<xref:System.Collections.Queue>|<span data-ttu-id="ba19c-176">FIFO(선입선출) 방식의 개체 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-176">Represents a first in, first out (FIFO) collection of objects.</span></span>|  
|<xref:System.Collections.Stack>|<span data-ttu-id="ba19c-177">LIFO(후입선출) 방식의 개체 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-177">Represents a last in, first out (LIFO) collection of objects.</span></span>|  
  
 <span data-ttu-id="ba19c-178"><xref:System.Collections.Specialized> 네임스페이스는 문자열 전용 컬렉션 및 연결된 목록과 하이브리드 사전 등의 특수한 강력한 형식의 컬렉션 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-178">The <xref:System.Collections.Specialized> namespace provides specialized and strongly typed collection classes, such as string-only collections and linked-list and hybrid dictionaries.</span></span>  

<a name="BKMK_KeyValuePairs"></a>
## <a name="implementing-a-collection-of-keyvalue-pairs"></a><span data-ttu-id="ba19c-179">키/값 쌍의 컬렉션 구현</span><span class="sxs-lookup"><span data-stu-id="ba19c-179">Implementing a Collection of Key/Value Pairs</span></span>  
 <span data-ttu-id="ba19c-180"><xref:System.Collections.Generic.Dictionary%602> 제네릭 컬렉션을 사용하면 각 요소의 키를 통해 컬렉션의 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-180">The <xref:System.Collections.Generic.Dictionary%602> generic collection enables you to access to elements in a collection by using the key of each element.</span></span> <span data-ttu-id="ba19c-181">사전에 추가하는 각 항목은 값과 관련 키로 이루어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-181">Each addition to the dictionary consists of a value and its associated key.</span></span> <span data-ttu-id="ba19c-182">`Dictionary` 클래스는 해시 테이블로 구현되므로 해당 키를 사용하여 값을 검색하는 것이 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-182">Retrieving a value by using its key is fast because the `Dictionary` class is implemented as a hash table.</span></span>  
  
 <span data-ttu-id="ba19c-183">다음 예제에서는 `Dictionary` 컬렉션을 만들고 `foreach` 문을 사용하여 사전을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-183">The following example creates a `Dictionary` collection and iterates through the dictionary by using a `foreach` statement.</span></span>  
  
```csharp  
private static void IterateThruDictionary()  
{  
    Dictionary<string, Element> elements = BuildDictionary();  
  
    foreach (KeyValuePair<string, Element> kvp in elements)  
    {  
        Element theElement = kvp.Value;  
  
        Console.WriteLine("key: " + kvp.Key);  
        Console.WriteLine("values: " + theElement.Symbol + " " +  
            theElement.Name + " " + theElement.AtomicNumber);  
    }  
}  
  
private static Dictionary<string, Element> BuildDictionary()  
{  
    var elements = new Dictionary<string, Element>();  
  
    AddToDictionary(elements, "K", "Potassium", 19);  
    AddToDictionary(elements, "Ca", "Calcium", 20);  
    AddToDictionary(elements, "Sc", "Scandium", 21);  
    AddToDictionary(elements, "Ti", "Titanium", 22);  
  
    return elements;  
}  
  
private static void AddToDictionary(Dictionary<string, Element> elements,  
    string symbol, string name, int atomicNumber)  
{  
    Element theElement = new Element();  
  
    theElement.Symbol = symbol;  
    theElement.Name = name;  
    theElement.AtomicNumber = atomicNumber;  
  
    elements.Add(key: theElement.Symbol, value: theElement);  
}  
  
public class Element  
{  
    public string Symbol { get; set; }  
    public string Name { get; set; }  
    public int AtomicNumber { get; set; }  
}  
```  
  
 <span data-ttu-id="ba19c-184">대신 컬렉션 이니셜라이저를 사용하여 `Dictionary` 컬렉션을 빌드하려면 `BuildDictionary` 및 `AddToDictionary` 메서드를 다음 메서드로 바꾸면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-184">To instead use a collection initializer to build the `Dictionary` collection, you can replace the `BuildDictionary` and `AddToDictionary` methods with the following method.</span></span>  
  
```csharp  
private static Dictionary<string, Element> BuildDictionary2()  
{  
    return new Dictionary<string, Element>  
    {  
        {"K",  
            new Element() { Symbol="K", Name="Potassium", AtomicNumber=19}},  
        {"Ca",  
            new Element() { Symbol="Ca", Name="Calcium", AtomicNumber=20}},  
        {"Sc",  
            new Element() { Symbol="Sc", Name="Scandium", AtomicNumber=21}},  
        {"Ti",  
            new Element() { Symbol="Ti", Name="Titanium", AtomicNumber=22}}  
    };  
}  
```  
  
 <span data-ttu-id="ba19c-185">다음 예제에서는 `Dictionary`의 <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A> 메서드 및 <xref:System.Collections.Generic.Dictionary%602.Item%2A> 속성을 사용하여 키를 통해 항목을 신속하게 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-185">The following example uses the <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A> method and the <xref:System.Collections.Generic.Dictionary%602.Item%2A> property of `Dictionary` to quickly find an item by key.</span></span> <span data-ttu-id="ba19c-186">`Item` 속성을 사용하면 C#에서 `elements[symbol]`를 통해 `elements` 컬렉션의 항목에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-186">The `Item` property enables you to access an item in the `elements` collection by using the `elements[symbol]` in C#.</span></span>  
  
```csharp  
private static void FindInDictionary(string symbol)  
{  
    Dictionary<string, Element> elements = BuildDictionary();  
  
    if (elements.ContainsKey(symbol) == false)  
    {  
        Console.WriteLine(symbol + " not found");  
    }  
    else  
    {  
        Element theElement = elements[symbol];  
        Console.WriteLine("found: " + theElement.Name);  
    }  
}  
```  
  
 <span data-ttu-id="ba19c-187">다음 예제에서는 대신 <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> 메서드를 사용하여 키를 통해 항목을 신속하게 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-187">The following example instead uses the <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> method quickly find an item by key.</span></span>  
  
```csharp  
private static void FindInDictionary2(string symbol)  
{  
    Dictionary<string, Element> elements = BuildDictionary();  
  
    Element theElement = null;  
    if (elements.TryGetValue(symbol, out theElement) == false)  
        Console.WriteLine(symbol + " not found");  
    else  
        Console.WriteLine("found: " + theElement.Name);  
}  
```  

<a name="BKMK_LINQ"></a>
## <a name="using-linq-to-access-a-collection"></a><span data-ttu-id="ba19c-188">LINQ를 사용하여 컬렉션에 액세스</span><span class="sxs-lookup"><span data-stu-id="ba19c-188">Using LINQ to Access a Collection</span></span>  
 <span data-ttu-id="ba19c-189">LINQ(통합 언어 쿼리)를 사용하여 컬렉션에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-189">LINQ (Language-Integrated Query) can be used to access collections.</span></span> <span data-ttu-id="ba19c-190">LINQ 쿼리는 필터링, 정렬 및 그룹화 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-190">LINQ queries provide filtering, ordering, and grouping capabilities.</span></span> <span data-ttu-id="ba19c-191">자세한 내용은 [C#에서 LINQ 시작](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba19c-191">For more information, see  [Getting Started with LINQ in C#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md).</span></span>  
  
 <span data-ttu-id="ba19c-192">다음 예제에서는 제네릭 `List`에 대해 LINQ 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-192">The following example runs a LINQ query against a generic `List`.</span></span> <span data-ttu-id="ba19c-193">LINQ 쿼리는 결과를 포함하는 다른 컬렉션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-193">The LINQ query returns a different collection that contains the results.</span></span>  
  
```csharp  
private static void ShowLINQ()  
{  
    List<Element> elements = BuildList();  
  
    // LINQ Query.  
    var subset = from theElement in elements  
                 where theElement.AtomicNumber < 22  
                 orderby theElement.Name  
                 select theElement;  
  
    foreach (Element theElement in subset)  
    {  
        Console.WriteLine(theElement.Name + " " + theElement.AtomicNumber);  
    }  
  
    // Output:  
    //  Calcium 20  
    //  Potassium 19  
    //  Scandium 21  
}  
  
private static List<Element> BuildList()  
{  
    return new List<Element>  
    {  
        { new Element() { Symbol="K", Name="Potassium", AtomicNumber=19}},  
        { new Element() { Symbol="Ca", Name="Calcium", AtomicNumber=20}},  
        { new Element() { Symbol="Sc", Name="Scandium", AtomicNumber=21}},  
        { new Element() { Symbol="Ti", Name="Titanium", AtomicNumber=22}}  
    };  
}  
  
public class Element  
{  
    public string Symbol { get; set; }  
    public string Name { get; set; }  
    public int AtomicNumber { get; set; }  
}  
```  

<a name="BKMK_Sorting"></a>
## <a name="sorting-a-collection"></a><span data-ttu-id="ba19c-194">컬렉션 정렬</span><span class="sxs-lookup"><span data-stu-id="ba19c-194">Sorting a Collection</span></span>  
 <span data-ttu-id="ba19c-195">다음 예제에서는 컬렉션 정렬 절차를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-195">The following example illustrates a procedure for sorting a collection.</span></span> <span data-ttu-id="ba19c-196">예제에서는 <xref:System.Collections.Generic.List%601>에 저장된 `Car` 클래스 인스턴스를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-196">The example sorts instances of the `Car` class that are stored in a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="ba19c-197">`Car` 클래스는 <xref:System.IComparable%601.CompareTo%2A> 메서드가 구현되어야 하는 <xref:System.IComparable%601> 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-197">The `Car` class implements the <xref:System.IComparable%601> interface, which requires that the <xref:System.IComparable%601.CompareTo%2A> method be implemented.</span></span>  
  
 <span data-ttu-id="ba19c-198"><xref:System.IComparable%601.CompareTo%2A> 메서드를 호출할 때마다 정렬에 사용되는 단일 비교가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-198">Each call to the <xref:System.IComparable%601.CompareTo%2A> method makes a single comparison that is used for sorting.</span></span> <span data-ttu-id="ba19c-199">`CompareTo` 메서드의 사용자 작성 코드는 다른 개체와 현재 개체의 각 비교에 대한 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-199">User-written code in the `CompareTo` method returns a value for each comparison of the current object with another object.</span></span> <span data-ttu-id="ba19c-200">현재 개체가 다른 개체보다 작으면 반환되는 값이 0보다 작고, 현재 개체가 다른 개체보다 크면 0보다 크고, 같으면 0입니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-200">The value returned is less than zero if the current object is less than the other object, greater than zero if the current object is greater than the other object, and zero if they are equal.</span></span> <span data-ttu-id="ba19c-201">이렇게 하면 보다 큼, 보다 작음 및 같음에 대한 조건을 코드에서 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-201">This enables you to define in code the criteria for greater than, less than, and equal.</span></span>  
  
 <span data-ttu-id="ba19c-202">`ListCars` 메서드에서 `cars.Sort()` 문은 목록을 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-202">In the `ListCars` method, the `cars.Sort()` statement sorts the list.</span></span> <span data-ttu-id="ba19c-203"><xref:System.Collections.Generic.List%601>의 <xref:System.Collections.Generic.List%601.Sort%2A> 메서드를 호출하면 `List`의 `Car` 개체에 대해 `CompareTo` 메서드가 자동으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-203">This call to the <xref:System.Collections.Generic.List%601.Sort%2A> method of the <xref:System.Collections.Generic.List%601> causes the `CompareTo` method to be called automatically for the `Car` objects in the `List`.</span></span>  
  
```csharp  
private static void ListCars()  
{  
    var cars = new List<Car>  
    {  
        { new Car() { Name = "car1", Color = "blue", Speed = 20}},  
        { new Car() { Name = "car2", Color = "red", Speed = 50}},  
        { new Car() { Name = "car3", Color = "green", Speed = 10}},  
        { new Car() { Name = "car4", Color = "blue", Speed = 50}},  
        { new Car() { Name = "car5", Color = "blue", Speed = 30}},  
        { new Car() { Name = "car6", Color = "red", Speed = 60}},  
        { new Car() { Name = "car7", Color = "green", Speed = 50}}  
    };  
  
    // Sort the cars by color alphabetically, and then by speed  
    // in descending order.  
    cars.Sort();  
  
    // View all of the cars.  
    foreach (Car thisCar in cars)  
    {  
        Console.Write(thisCar.Color.PadRight(5) + " ");  
        Console.Write(thisCar.Speed.ToString() + " ");  
        Console.Write(thisCar.Name);  
        Console.WriteLine();  
    }  
  
    // Output:  
    //  blue  50 car4  
    //  blue  30 car5  
    //  blue  20 car1  
    //  green 50 car7  
    //  green 10 car3  
    //  red   60 car6  
    //  red   50 car2  
}  
  
public class Car : IComparable<Car>  
{  
    public string Name { get; set; }  
    public int Speed { get; set; }  
    public string Color { get; set; }  
  
    public int CompareTo(Car other)  
    {  
        // A call to this method makes a single comparison that is  
        // used for sorting.  
  
        // Determine the relative order of the objects being compared.  
        // Sort by color alphabetically, and then by speed in  
        // descending order.  
  
        // Compare the colors.  
        int compare;  
        compare = String.Compare(this.Color, other.Color, true);  
  
        // If the colors are the same, compare the speeds.  
        if (compare == 0)  
        {  
            compare = this.Speed.CompareTo(other.Speed);  
  
            // Use descending order for speed.  
            compare = -compare;  
        }  
  
        return compare;  
    }  
}  
```  
  
<a name="BKMK_CustomCollection"></a>
## <a name="defining-a-custom-collection"></a><span data-ttu-id="ba19c-204">사용자 지정 컬렉션 정의</span><span class="sxs-lookup"><span data-stu-id="ba19c-204">Defining a Custom Collection</span></span>  
 <span data-ttu-id="ba19c-205"><xref:System.Collections.Generic.IEnumerable%601> 또는 <xref:System.Collections.IEnumerable> 인터페이스를 구현하여 컬렉션을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-205">You can define a collection by implementing the <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="ba19c-206">자세한 내용은 [방법: foreach를 사용하여 컬렉션 클래스 액세스](../../../csharp/programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba19c-206">For additional information, see [How to: Access a Collection Class with foreach](../../../csharp/programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md).</span></span>  
  
 <span data-ttu-id="ba19c-207">사용자 지정 컬렉션을 정의할 수도 있지만, 일반적으로 이 항목의 앞부분에 있는 [컬렉션 종류](#BKMK_KindsOfCollections)에서 설명한 .NET Framework에 포함된 컬렉션을 대신 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-207">Although you can define a custom collection, it is usually better to instead use the collections that are included in the .NET Framework, which are described in [Kinds of Collections](#BKMK_KindsOfCollections) earlier in this topic.</span></span>  
  
 <span data-ttu-id="ba19c-208">다음 예제에서는 `AllColors`라는 사용자 지정 컬렉션 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-208">The following example defines a custom collection class named `AllColors`.</span></span> <span data-ttu-id="ba19c-209">이 클래스는 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 메서드가 구현되어야 하는 <xref:System.Collections.IEnumerable> 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-209">This class implements the <xref:System.Collections.IEnumerable> interface, which requires that the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method be implemented.</span></span>  
  
 <span data-ttu-id="ba19c-210">`GetEnumerator` 메서드는 `ColorEnumerator` 클래스의 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-210">The `GetEnumerator` method returns an instance of the `ColorEnumerator` class.</span></span> <span data-ttu-id="ba19c-211">`ColorEnumerator`는 <xref:System.Collections.IEnumerator.Current%2A> 속성, <xref:System.Collections.IEnumerator.MoveNext%2A> 메서드 및 <xref:System.Collections.IEnumerator.Reset%2A> 메서드가 구현되어야 하는 <xref:System.Collections.IEnumerator> 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-211">`ColorEnumerator` implements the <xref:System.Collections.IEnumerator> interface, which requires that the <xref:System.Collections.IEnumerator.Current%2A> property, <xref:System.Collections.IEnumerator.MoveNext%2A> method, and <xref:System.Collections.IEnumerator.Reset%2A> method be implemented.</span></span>  
  
```csharp  
private static void ListColors()  
{  
    var colors = new AllColors();  
  
    foreach (Color theColor in colors)  
    {  
        Console.Write(theColor.Name + " ");  
    }  
    Console.WriteLine();  
    // Output: red blue green  
}  
  
// Collection class.  
public class AllColors : System.Collections.IEnumerable  
{  
    Color[] _colors =  
    {  
        new Color() { Name = "red" },  
        new Color() { Name = "blue" },  
        new Color() { Name = "green" }  
    };  
  
    public System.Collections.IEnumerator GetEnumerator()  
    {  
        return new ColorEnumerator(_colors);  
  
        // Instead of creating a custom enumerator, you could  
        // use the GetEnumerator of the array.  
        //return _colors.GetEnumerator();  
    }  
  
    // Custom enumerator.  
    private class ColorEnumerator : System.Collections.IEnumerator  
    {  
        private Color[] _colors;  
        private int _position = -1;  
  
        public ColorEnumerator(Color[] colors)  
        {  
            _colors = colors;  
        }  
  
        object System.Collections.IEnumerator.Current  
        {  
            get  
            {  
                return _colors[_position];  
            }  
        }  
  
        bool System.Collections.IEnumerator.MoveNext()  
        {  
            _position++;  
            return (_position < _colors.Length);  
        }  
  
        void System.Collections.IEnumerator.Reset()  
        {  
            _position = -1;  
        }  
    }  
}  
  
// Element class.  
public class Color  
{  
    public string Name { get; set; }  
}  
```  

<a name="BKMK_Iterators"></a> 
##  <a name="iterators"></a><span data-ttu-id="ba19c-212">Iterators</span><span class="sxs-lookup"><span data-stu-id="ba19c-212">Iterators</span></span>  
 <span data-ttu-id="ba19c-213">*반복기*는 컬렉션에 대해 사용자 지정 반복을 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-213">An *iterator* is used to perform a custom iteration over a collection.</span></span> <span data-ttu-id="ba19c-214">반복기는 메서드 또는 `get` 접근자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-214">An iterator can be a method or a `get` accessor.</span></span> <span data-ttu-id="ba19c-215">반복기는 [yield return](../../../csharp/language-reference/keywords/yield.md) 문을 사용하여 한 번에 하나씩 컬렉션의 각 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-215">An iterator uses a [yield return](../../../csharp/language-reference/keywords/yield.md) statement to return each element of the collection one at a time.</span></span>  
  
 <span data-ttu-id="ba19c-216">[foreach](../../../csharp/language-reference/keywords/foreach-in.md) 문을 사용하여 반복기를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-216">You call an iterator by using a [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement.</span></span> <span data-ttu-id="ba19c-217">각각의 `foreach` 루프의 반복이 반복기를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-217">Each iteration of the `foreach` loop calls the iterator.</span></span> <span data-ttu-id="ba19c-218">`yield return` 문이 반복기 메서드에 도달하면 식이 반환되고 코드에서 현재 위치는 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-218">When a `yield return` statement is reached in the iterator, an expression is returned, and the current location in code is retained.</span></span> <span data-ttu-id="ba19c-219">다음에 반복기가 호출되면 해당 위치에서 실행이 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-219">Execution is restarted from that location the next time that the iterator is called.</span></span>  
  
 <span data-ttu-id="ba19c-220">자세한 내용은 [반복기(C#)](../../../csharp/programming-guide/concepts/iterators.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba19c-220">For more information, see [Iterators (C#)](../../../csharp/programming-guide/concepts/iterators.md).</span></span>  
  
 <span data-ttu-id="ba19c-221">다음 예제에서는 반복기 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-221">The following example uses an iterator method.</span></span> <span data-ttu-id="ba19c-222">반복기 메서드는 [for](../../../csharp/language-reference/keywords/for.md) 루프 내부에 있는 `yield return` 문을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-222">The iterator method has a `yield return` statement that is inside a [for](../../../csharp/language-reference/keywords/for.md) loop.</span></span> <span data-ttu-id="ba19c-223">`ListEvenNumbers` 메서드에서 `foreach` 문 본문을 반복할 때마다 다음 `yield return` 문으로 진행하는 반복기 메서드에 대한 호출이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba19c-223">In the `ListEvenNumbers` method, each iteration of the `foreach` statement body creates a call to the iterator method, which proceeds to the next `yield return` statement.</span></span>  
  
```csharp  
private static void ListEvenNumbers()  
{  
    foreach (int number in EvenSequence(5, 18))  
    {  
        Console.Write(number.ToString() + " ");  
    }  
    Console.WriteLine();  
    // Output: 6 8 10 12 14 16 18  
}  
  
private static IEnumerable<int> EvenSequence(  
    int firstNumber, int lastNumber)  
{  
    // Yield even numbers in the range.  
    for (var number = firstNumber; number <= lastNumber; number++)  
    {  
        if (number % 2 == 0)  
        {  
            yield return number;  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba19c-224">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ba19c-224">See Also</span></span>  
 <span data-ttu-id="ba19c-225">[개체 이니셜라이저 및 컬렉션 이니셜라이저](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) </span><span class="sxs-lookup"><span data-stu-id="ba19c-225">[Object and Collection Initializers](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) </span></span>  
 <span data-ttu-id="ba19c-226">[프로그래밍 개념(C#)](../../../csharp/programming-guide/concepts/index.md) </span><span class="sxs-lookup"><span data-stu-id="ba19c-226">[Programming Concepts (C#)](../../../csharp/programming-guide/concepts/index.md) </span></span>  
 <span data-ttu-id="ba19c-227">[Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ba19c-227">[Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
 <span data-ttu-id="ba19c-228">[LINQ to Objects(C#)](../../../csharp/programming-guide/concepts/linq/linq-to-objects.md) </span><span class="sxs-lookup"><span data-stu-id="ba19c-228">[LINQ to Objects (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-objects.md) </span></span>  
 <span data-ttu-id="ba19c-229">[PLINQ(병렬 LINQ)](../../../standard/parallel-programming/parallel-linq-plinq.md) </span><span class="sxs-lookup"><span data-stu-id="ba19c-229">[Parallel LINQ (PLINQ)](../../../standard/parallel-programming/parallel-linq-plinq.md) </span></span>  
 <span data-ttu-id="ba19c-230">[컬렉션 및 데이터 구조](../../../standard/collections/index.md) </span><span class="sxs-lookup"><span data-stu-id="ba19c-230">[Collections and Data Structures](../../../standard/collections/index.md) </span></span>  
 <span data-ttu-id="ba19c-231">[컬렉션 만들기 및 조작](http://msdn.microsoft.com/en-us/2065398e-eb1a-4821-9188-75f16e42e069) </span><span class="sxs-lookup"><span data-stu-id="ba19c-231">[Creating and Manipulating Collections](http://msdn.microsoft.com/en-us/2065398e-eb1a-4821-9188-75f16e42e069) </span></span>  
 <span data-ttu-id="ba19c-232">[Collection 클래스 선택](../../../standard/collections/selecting-a-collection-class.md) </span><span class="sxs-lookup"><span data-stu-id="ba19c-232">[Selecting a Collection Class](../../../standard/collections/selecting-a-collection-class.md) </span></span>  
 <span data-ttu-id="ba19c-233">[컬렉션 내에서 비교 및 정렬](../../../standard/collections/comparisons-and-sorts-within-collections.md) </span><span class="sxs-lookup"><span data-stu-id="ba19c-233">[Comparisons and Sorts Within Collections](../../../standard/collections/comparisons-and-sorts-within-collections.md) </span></span>  
 <span data-ttu-id="ba19c-234">[제네릭 컬렉션 사용 기준](../../../standard/collections/when-to-use-generic-collections.md) </span><span class="sxs-lookup"><span data-stu-id="ba19c-234">[When to Use Generic Collections](../../../standard/collections/when-to-use-generic-collections.md) </span></span>  
 [<span data-ttu-id="ba19c-235">방법: foreach를 사용하여 컬렉션 클래스 액세스</span><span class="sxs-lookup"><span data-stu-id="ba19c-235">How to: Access a Collection Class with foreach</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)

