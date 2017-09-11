---
title: "컬렉션 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: get-started-article
dev_langs:
- VB
ms.assetid: 5f7749f3-aaf2-4319-b63c-bfa72e1e2b7a
caps.latest.revision: 6
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b3c8de3e22075d576f86bcd4eb599946740ebe16
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

---
# <a name="collections-visual-basic"></a><span data-ttu-id="88d1b-102">컬렉션 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88d1b-102">Collections (Visual Basic)</span></span>
<span data-ttu-id="88d1b-103">대부분의 응용 프로그램의 경우 관련 개체의 그룹을 만들고 관리하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-103">For many applications, you want to create and manage groups of related objects.</span></span> <span data-ttu-id="88d1b-104">개체를 그룹화하는 방법에는 개체 배열을 만들거나 개체 컬렉션을 만드는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-104">There are two ways to group objects: by creating arrays of objects, and by creating collections of objects.</span></span>  
  
 <span data-ttu-id="88d1b-105">배열은 고정된 개수의 강력한 형식 개체를 만들고 작업하는 데 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-105">Arrays are most useful for creating and working with a fixed number of strongly-typed objects.</span></span> <span data-ttu-id="88d1b-106">배열에 대 한 정보를 참조 하십시오. [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-106">For information about arrays, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
 <span data-ttu-id="88d1b-107">컬렉션은 개체 그룹에 대해 작업하는 보다 유연한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-107">Collections provide a more flexible way to work with groups of objects.</span></span> <span data-ttu-id="88d1b-108">배열과 달리, 응용 프로그램의 요구가 변경됨에 따라 작업하는 개체 그룹이 동적으로 확장되거나 축소될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-108">Unlike arrays, the group of objects you work with can grow and shrink dynamically as the needs of the application change.</span></span> <span data-ttu-id="88d1b-109">일부 컬렉션의 경우 키를 사용하여 개체를 신속하게 검색할 수 있도록 컬렉션에 추가하는 모든 개체에 키를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-109">For some collections, you can assign a key to any object that you put into the collection so that you can quickly retrieve the object by using the key.</span></span>  
  
 <span data-ttu-id="88d1b-110">컬렉션은 클래스이므로 해당 컬렉션에 요소를 추가하려면 먼저 클래스 인스턴스를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-110">A collection is a class, so you must declare an instance of the class before you can add elements to that collection.</span></span>  
  
 <span data-ttu-id="88d1b-111">하나의 데이터 형식의 요소를 포함 하는 컬렉션, 클래스 중 하나를 사용할 수 있습니다는 <xref:System.Collections.Generic?displayProperty=fullName>네임 스페이스.</xref:System.Collections.Generic?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="88d1b-111">If your collection contains elements of only one data type, you can use one of the classes in the <xref:System.Collections.Generic?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="88d1b-112">제네릭 컬렉션은 다른 데이터 형식을 추가할 수 없도록 형식 안전성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-112">A generic collection enforces type safety so that no other data type can be added to it.</span></span> <span data-ttu-id="88d1b-113">제네릭 컬렉션에서 요소를 검색하는 경우 해당 데이터 형식을 결정하거나 변환할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-113">When you retrieve an element from a generic collection, you do not have to determine its data type or convert it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88d1b-114">이 항목의 예제를 포함 [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 에 대 한 문을 `System.Collections.Generic` 및 `System.Linq` 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-114">For the examples in this topic, include [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statements for the `System.Collections.Generic` and `System.Linq` namespaces.</span></span>  
  
 <span data-ttu-id="88d1b-115">**항목 내용**</span><span class="sxs-lookup"><span data-stu-id="88d1b-115">**In this topic**</span></span>  
  
-   [<span data-ttu-id="88d1b-116">간단한 컬렉션 사용</span><span class="sxs-lookup"><span data-stu-id="88d1b-116">Using a Simple Collection</span></span>](#BKMK_SimpleCollection)  
  
-   [<span data-ttu-id="88d1b-117">컬렉션의 종류</span><span class="sxs-lookup"><span data-stu-id="88d1b-117">Kinds of Collections</span></span>](#BKMK_KindsOfCollections)  
  
    -   [<span data-ttu-id="88d1b-118">System.Collections.Generic 클래스</span><span class="sxs-lookup"><span data-stu-id="88d1b-118">System.Collections.Generic Classes</span></span>](#BKMK_Generic)  
  
    -   [<span data-ttu-id="88d1b-119">System.Collections.Concurrent 클래스</span><span class="sxs-lookup"><span data-stu-id="88d1b-119">System.Collections.Concurrent Classes</span></span>](#BKMK_Concurrent)  
  
    -   [<span data-ttu-id="88d1b-120">System.Collections 클래스</span><span class="sxs-lookup"><span data-stu-id="88d1b-120">System.Collections Classes</span></span>](#BKMK_Collections)  
  
    -   [<span data-ttu-id="88d1b-121">Visual Basic 컬렉션 클래스</span><span class="sxs-lookup"><span data-stu-id="88d1b-121">Visual Basic Collection Class</span></span>](#BKMK_VisualBasic)  
  
-   [<span data-ttu-id="88d1b-122">키/값 쌍의 컬렉션 구현</span><span class="sxs-lookup"><span data-stu-id="88d1b-122">Implementing a Collection of Key/Value Pairs</span></span>](#BKMK_KeyValuePairs)  
  
-   [<span data-ttu-id="88d1b-123">LINQ를 사용 하 여 컬렉션에 액세스 하려면</span><span class="sxs-lookup"><span data-stu-id="88d1b-123">Using LINQ to Access a Collection</span></span>](#BKMK_LINQ)  
  
-   [<span data-ttu-id="88d1b-124">컬렉션 정렬</span><span class="sxs-lookup"><span data-stu-id="88d1b-124">Sorting a Collection</span></span>](#BKMK_Sorting)  
  
-   [<span data-ttu-id="88d1b-125">사용자 지정 컬렉션 정의</span><span class="sxs-lookup"><span data-stu-id="88d1b-125">Defining a Custom Collection</span></span>](#BKMK_CustomCollection)  
  
-   [<span data-ttu-id="88d1b-126">반복기</span><span class="sxs-lookup"><span data-stu-id="88d1b-126">Iterators</span></span>](#BKMK_Iterators)  
  
<a name="BKMK_SimpleCollection"></a>
## <a name="using-a-simple-collection"></a><span data-ttu-id="88d1b-127">간단한 컬렉션 사용</span><span class="sxs-lookup"><span data-stu-id="88d1b-127">Using a Simple Collection</span></span>  
 <span data-ttu-id="88d1b-128">이 섹션의 예제에서는 제네릭 사용 <xref:System.Collections.Generic.List%601>클래스를 통해 강력한 형식의 개체 목록을 사용할 수 있습니다.</xref:System.Collections.Generic.List%601></span><span class="sxs-lookup"><span data-stu-id="88d1b-128">The examples in this section use the generic <xref:System.Collections.Generic.List%601> class, which enables you to work with a strongly typed list of objects.</span></span>  
  
 <span data-ttu-id="88d1b-129">다음 예제에서는 문자열의 목록을 만들고 사용 하 여 문자열을 반복는 [각각에 대해... 다음](../../../visual-basic/language-reference/statements/for-each-next-statement.md) 문입니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-129">The following example creates a list of strings and then iterates through the strings by using a [For Each…Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement.</span></span>  
  
```vb  
' Create a list of strings.  
Dim salmons As New List(Of String)  
salmons.Add("chinook")  
salmons.Add("coho")  
salmons.Add("pink")  
salmons.Add("sockeye")  
  
' Iterate through the list.  
For Each salmon As String In salmons  
    Console.Write(salmon & " ")  
Next  
'Output: chinook coho pink sockeye  
```  
  
 <span data-ttu-id="88d1b-130">컬렉션의 내용을 사전에 확인 하는 경우 사용할 수 있습니다는 *컬렉션 이니셜라이저* 컬렉션을 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-130">If the contents of a collection are known in advance, you can use a *collection initializer* to initialize the collection.</span></span> <span data-ttu-id="88d1b-131">자세한 내용은 참조 [컬렉션 이니셜라이저](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-131">For more information, see [Collection Initializers](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).</span></span>  
  
 <span data-ttu-id="88d1b-132">다음 예제는 컬렉션 이니셜라이저를 사용하여 컬렉션에 요소를 추가한다는 점을 제외하고 이전 예제와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-132">The following example is the same as the previous example, except a collection initializer is used to add elements to the collection.</span></span>  
  
```vb  
' Create a list of strings by using a  
' collection initializer.  
Dim salmons As New List(Of String) From  
    {"chinook", "coho", "pink", "sockeye"}  
  
For Each salmon As String In salmons  
    Console.Write(salmon & " ")  
Next  
'Output: chinook coho pink sockeye  
```  
  
 <span data-ttu-id="88d1b-133">사용할 수는 [에 대 한... 다음](../../../visual-basic/language-reference/statements/for-next-statement.md) 대신 문을 `For Each` 컬렉션을 반복 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-133">You can use a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) statement instead of a `For Each` statement to iterate through a collection.</span></span> <span data-ttu-id="88d1b-134">인덱스 위치에 따라 컬렉션 요소에 액세스하여 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-134">You accomplish this by accessing the collection elements by the index position.</span></span> <span data-ttu-id="88d1b-135">요소의 인덱스는 0부터 시작하고 요소 개수-1에서 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-135">The index of the elements starts at 0 and ends at the element count minus 1.</span></span>  
  
 <span data-ttu-id="88d1b-136">다음 예제에서는 사용 하 여 컬렉션의 요소 반복 `For…Next` 대신 `For Each`합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-136">The following example iterates through the elements of a collection by using `For…Next` instead of `For Each`.</span></span>  
  
```vb  
Dim salmons As New List(Of String) From  
    {"chinook", "coho", "pink", "sockeye"}  
  
For index = 0 To salmons.Count - 1  
    Console.Write(salmons(index) & " ")  
Next  
'Output: chinook coho pink sockeye  
```  
  
 <span data-ttu-id="88d1b-137">다음 예제에서는 제거할 개체를 지정하여 컬렉션에서 요소를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-137">The following example removes an element from the collection by specifying the object to remove.</span></span>  
  
```vb  
' Create a list of strings by using a  
' collection initializer.  
Dim salmons As New List(Of String) From  
    {"chinook", "coho", "pink", "sockeye"}  
  
' Remove an element in the list by specifying  
' the object.  
salmons.Remove("coho")  
  
For Each salmon As String In salmons  
    Console.Write(salmon & " ")  
Next  
'Output: chinook pink sockeye  
```  
  
 <span data-ttu-id="88d1b-138">다음 예제에서는 제네릭 목록에서 요소를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-138">The following example removes elements from a generic list.</span></span> <span data-ttu-id="88d1b-139">대신는 `For Each` 문에서 [에 대 한... 다음](../../../visual-basic/language-reference/statements/for-next-statement.md) 내림차순 반복 문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-139">Instead of a `For Each` statement, a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) statement that iterates in descending order is used.</span></span> <span data-ttu-id="88d1b-140">때문에 이것이 <xref:System.Collections.Generic.List%601.RemoveAt%2A>메서드 낮은 인덱스 값을 제거 된 요소 다음 요소를 사용 하면.</xref:System.Collections.Generic.List%601.RemoveAt%2A></span><span class="sxs-lookup"><span data-stu-id="88d1b-140">This is because the <xref:System.Collections.Generic.List%601.RemoveAt%2A> method causes elements after a removed element to have a lower index value.</span></span>  
  
```vb  
Dim numbers As New List(Of Integer) From  
    {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}  
  
' Remove odd numbers.  
For index As Integer = numbers.Count - 1 To 0 Step -1  
    If numbers(index) Mod 2 = 1 Then  
        ' Remove the element by specifying  
        ' the zero-based index in the list.  
        numbers.RemoveAt(index)  
    End If  
Next  
  
' Iterate through the list.  
' A lambda expression is placed in the ForEach method  
' of the List(T) object.  
numbers.ForEach(  
    Sub(number) Console.Write(number & " "))  
' Output: 0 2 4 6 8  
```  
  
 <span data-ttu-id="88d1b-141"><xref:System.Collections.Generic.List%601>또한 고유한 클래스를 정의할 수 있습니다,</xref:System.Collections.Generic.List%601> 요소 형식에 대 한</span><span class="sxs-lookup"><span data-stu-id="88d1b-141">For the type of elements in the <xref:System.Collections.Generic.List%601>, you can also define your own class.</span></span> <span data-ttu-id="88d1b-142">다음 예제에서는 `Galaxy` 에서 사용 되는 클래스는 <xref:System.Collections.Generic.List%601>코드에서 정의 됩니다.</xref:System.Collections.Generic.List%601></span><span class="sxs-lookup"><span data-stu-id="88d1b-142">In the following example, the `Galaxy` class that is used by the <xref:System.Collections.Generic.List%601> is defined in the code.</span></span>  
  
```vb  
Private Sub IterateThroughList()  
    Dim theGalaxies As New List(Of Galaxy) From  
        {  
            New Galaxy With {.Name = "Tadpole", .MegaLightYears = 400},  
            New Galaxy With {.Name = "Pinwheel", .MegaLightYears = 25},  
            New Galaxy With {.Name = "Milky Way", .MegaLightYears = 0},  
            New Galaxy With {.Name = "Andromeda", .MegaLightYears = 3}  
        }  
  
    For Each theGalaxy In theGalaxies  
        With theGalaxy  
            Console.WriteLine(.Name & "  " & .MegaLightYears)  
        End With  
    Next  
  
    ' Output:  
    '  Tadpole  400  
    '  Pinwheel  25  
    '  Milky Way  0  
    '  Andromeda  3  
End Sub  
  
Public Class Galaxy  
    Public Property Name As String  
    Public Property MegaLightYears As Integer  
End Class  
```  
  
<a name="BKMK_KindsOfCollections"></a>
## <a name="kinds-of-collections"></a><span data-ttu-id="88d1b-143">컬렉션 종류</span><span class="sxs-lookup"><span data-stu-id="88d1b-143">Kinds of Collections</span></span>   
 <span data-ttu-id="88d1b-144">.NET Framework는 많은 일반적인 컬렉션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-144">Many common collections are provided by the .NET Framework.</span></span> <span data-ttu-id="88d1b-145">컬렉션의 각 형식은 특정 목적에 맞게 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-145">Each type of collection is designed for a specific purpose.</span></span>  
  
 <span data-ttu-id="88d1b-146">이 섹션에서는 다음 몇 가지 일반적인 컬렉션 클래스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-146">Some of the common collection classes are described in this section:</span></span>  
  
-   <span data-ttu-id="88d1b-147">@System.Collections.Generic클래스</span><span class="sxs-lookup"><span data-stu-id="88d1b-147">@System.Collections.Generic classes</span></span>  
  
-   <span data-ttu-id="88d1b-148">@System.Collections.Concurrent클래스</span><span class="sxs-lookup"><span data-stu-id="88d1b-148">@System.Collections.Concurrent classes</span></span>  
  
-   <span data-ttu-id="88d1b-149">@System.Collections클래스</span><span class="sxs-lookup"><span data-stu-id="88d1b-149">@System.Collections classes</span></span>  
  
-   <span data-ttu-id="88d1b-150">Visual Basic `Collection` 클래스</span><span class="sxs-lookup"><span data-stu-id="88d1b-150">Visual Basic `Collection` class</span></span>  
  
<a name="BKMK_Generic"></a>
### <a name="systemcollectionsgeneric-classes"></a><span data-ttu-id="88d1b-151">System.Collections.Generic 클래스</span><span class="sxs-lookup"><span data-stu-id="88d1b-151">System.Collections.Generic Classes</span></span>  

 <span data-ttu-id="88d1b-152">클래스 중 하나를 사용 하 여 제네릭 컬렉션을 만들 수는 <xref:System.Collections.Generic>네임 스페이스.</xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="88d1b-152">You can create a generic collection by using one of the classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="88d1b-153">제네릭 컬렉션은 컬렉션의 모든 항목에 동일한 데이터 형식이 있는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-153">A generic collection is useful when every item in the collection has the same data type.</span></span> <span data-ttu-id="88d1b-154">제네릭 컬렉션은 원하는 데이터 형식만 추가할 수 있도록 하여 강력한 형식 지정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-154">A generic collection enforces strong typing by allowing only the desired data type to be added.</span></span>  
  
 <span data-ttu-id="88d1b-155">다음 표에 자주 사용 되는 클래스의 일부는 <xref:System.Collections.Generic?displayProperty=fullName>네임 스페이스:</xref:System.Collections.Generic?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="88d1b-155">The following table lists some of the frequently used classes of the <xref:System.Collections.Generic?displayProperty=fullName> namespace:</span></span>  
  
|<span data-ttu-id="88d1b-156">클래스</span><span class="sxs-lookup"><span data-stu-id="88d1b-156">Class</span></span>|<span data-ttu-id="88d1b-157">설명</span><span class="sxs-lookup"><span data-stu-id="88d1b-157">Description</span></span>|  
|---|---|  
|<span data-ttu-id="88d1b-158"><xref:System.Collections.Generic.Dictionary%602></xref:System.Collections.Generic.Dictionary%602></span><span class="sxs-lookup"><span data-stu-id="88d1b-158"><xref:System.Collections.Generic.Dictionary%602></span></span>|<span data-ttu-id="88d1b-159">키에 따라 구성된 키/값 쌍의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-159">Represents a collection of key/value pairs that are organized based on the key.</span></span>|  
|<span data-ttu-id="88d1b-160"><xref:System.Collections.Generic.List%601></xref:System.Collections.Generic.List%601></span><span class="sxs-lookup"><span data-stu-id="88d1b-160"><xref:System.Collections.Generic.List%601></span></span>|<span data-ttu-id="88d1b-161">인덱스로 액세스할 수 있는 개체 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-161">Represents a list of objects that can be accessed by index.</span></span> <span data-ttu-id="88d1b-162">목록의 검색, 정렬 및 수정에 사용할 수 있는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-162">Provides methods to search, sort, and modify lists.</span></span>|  
|<span data-ttu-id="88d1b-163"><xref:System.Collections.Generic.Queue%601></xref:System.Collections.Generic.Queue%601></span><span class="sxs-lookup"><span data-stu-id="88d1b-163"><xref:System.Collections.Generic.Queue%601></span></span>|<span data-ttu-id="88d1b-164">FIFO(선입선출) 방식의 개체 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-164">Represents a first in, first out (FIFO) collection of objects.</span></span>|  
|<span data-ttu-id="88d1b-165"><xref:System.Collections.Generic.SortedList%602></xref:System.Collections.Generic.SortedList%602></span><span class="sxs-lookup"><span data-stu-id="88d1b-165"><xref:System.Collections.Generic.SortedList%602></span></span>|<span data-ttu-id="88d1b-166">기반으로 연결 된 키에 따라 정렬 된 키/값 쌍의 컬렉션을 나타냅니다 <xref:System.Collections.Generic.IComparer%601>구현 합니다.</xref:System.Collections.Generic.IComparer%601></span><span class="sxs-lookup"><span data-stu-id="88d1b-166">Represents a collection of key/value pairs that are sorted by key based on the associated <xref:System.Collections.Generic.IComparer%601> implementation.</span></span>|  
|<span data-ttu-id="88d1b-167"><xref:System.Collections.Generic.Stack%601></xref:System.Collections.Generic.Stack%601></span><span class="sxs-lookup"><span data-stu-id="88d1b-167"><xref:System.Collections.Generic.Stack%601></span></span>|<span data-ttu-id="88d1b-168">LIFO(후입선출) 방식의 개체 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-168">Represents a last in, first out (LIFO) collection of objects.</span></span>|  
  
 <span data-ttu-id="88d1b-169">자세한 내용은 참조 [일반적으로 사용 되는 한 컬렉션 형식](http://msdn.microsoft.com/library/f5d4c6a4-0d7b-4944-a9fb-3b12d9ebfd55), [Collection 클래스 선택](../../../standard/collections/selecting-a-collection-class.md), 및 <xref:System.Collections.Generic?displayProperty=fullName>.</xref:System.Collections.Generic?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="88d1b-169">For additional information, see [Commonly Used Collection Types](http://msdn.microsoft.com/library/f5d4c6a4-0d7b-4944-a9fb-3b12d9ebfd55), [Selecting a Collection Class](../../../standard/collections/selecting-a-collection-class.md), and <xref:System.Collections.Generic?displayProperty=fullName>.</span></span>  
  
<a name="BKMK_Concurrent"></a>
### <a name="systemcollectionsconcurrent-classes"></a><span data-ttu-id="88d1b-170">System.Collections.Concurrent 클래스</span><span class="sxs-lookup"><span data-stu-id="88d1b-170">System.Collections.Concurrent Classes</span></span>   
 <span data-ttu-id="88d1b-171">.NET Framework 4 이상에서 컬렉션에에서는 <xref:System.Collections.Concurrent>네임 스페이스는 여러 스레드에서 컬렉션 항목에 액세스 하기 위한 효율적이 고 스레드로부터 안전한 작업을 제공 합니다.</xref:System.Collections.Concurrent></span><span class="sxs-lookup"><span data-stu-id="88d1b-171">In the .NET Framework 4 or newer, the collections in the <xref:System.Collections.Concurrent> namespace provide efficient thread-safe operations for accessing collection items from multiple threads.</span></span>  
  
 <span data-ttu-id="88d1b-172">클래스는 <xref:System.Collections.Concurrent>네임 스페이스의 해당 형식 대신 사용 해야는 <xref:System.Collections.Generic?displayProperty=fullName>및 <xref:System.Collections?displayProperty=fullName>여러 스레드는 컬렉션을 동시에 액세스할 때마다 네임 스페이스.</xref:System.Collections?displayProperty=fullName> </xref:System.Collections.Generic?displayProperty=fullName> </xref:System.Collections.Concurrent></span><span class="sxs-lookup"><span data-stu-id="88d1b-172">The classes in the <xref:System.Collections.Concurrent> namespace should be used instead of the corresponding types in the <xref:System.Collections.Generic?displayProperty=fullName> and <xref:System.Collections?displayProperty=fullName> namespaces whenever multiple threads are accessing the collection concurrently.</span></span> <span data-ttu-id="88d1b-173">자세한 내용은 참조 [스레드로부터 안전한 컬렉션](../../../standard/collections/threadsafe/index.md) 및 <xref:System.Collections.Concurrent>.</xref:System.Collections.Concurrent></span><span class="sxs-lookup"><span data-stu-id="88d1b-173">For more information, see [Thread-Safe Collections](../../../standard/collections/threadsafe/index.md) and <xref:System.Collections.Concurrent>.</span></span>  
  
 <span data-ttu-id="88d1b-174">에 포함 된 일부 클래스는 <xref:System.Collections.Concurrent>네임 스페이스는 <xref:System.Collections.Concurrent.BlockingCollection%601>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, 및 <xref:System.Collections.Concurrent.ConcurrentStack%601>.</xref:System.Collections.Concurrent.ConcurrentStack%601> </xref:System.Collections.Concurrent.ConcurrentQueue%601> </xref:System.Collections.Concurrent.ConcurrentDictionary%602> </xref:System.Collections.Concurrent.BlockingCollection%601> </xref:System.Collections.Concurrent></span><span class="sxs-lookup"><span data-stu-id="88d1b-174">Some classes included in the <xref:System.Collections.Concurrent> namespace are <xref:System.Collections.Concurrent.BlockingCollection%601>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, and <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span></span>  
  
<a name="BKMK_Collections"></a>
### <a name="systemcollections-classes"></a><span data-ttu-id="88d1b-175">System.Collections 클래스</span><span class="sxs-lookup"><span data-stu-id="88d1b-175">System.Collections Classes</span></span>    
 <span data-ttu-id="88d1b-176">클래스는 <xref:System.Collections?displayProperty=fullName>특별히 형식화 된 개체로 하지만 형식의 개체로 네임 스페이스 요소를 저장 하지 않는 `Object`.</xref:System.Collections?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="88d1b-176">The classes in the <xref:System.Collections?displayProperty=fullName> namespace do not store elements as specifically typed objects, but as objects of type `Object`.</span></span>  
  
 <span data-ttu-id="88d1b-177">제네릭 컬렉션을 사용 해야 가능 하다 면는 <xref:System.Collections.Generic?displayProperty=fullName>네임 스페이스 또는 <xref:System.Collections.Concurrent>에서 레거시 형식 대신 네임 스페이스는 `System.Collections` 네임 스페이스.</xref:System.Collections.Concurrent> </xref:System.Collections.Generic?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="88d1b-177">Whenever possible, you should use the generic collections in the <xref:System.Collections.Generic?displayProperty=fullName> namespace or the <xref:System.Collections.Concurrent> namespace instead of the legacy types in the `System.Collections` namespace.</span></span>  
  
 <span data-ttu-id="88d1b-178">다음 표에서 일부 자주 사용 되는 클래스에는 `System.Collections` 네임 스페이스:</span><span class="sxs-lookup"><span data-stu-id="88d1b-178">The following table lists some of the frequently used classes in the `System.Collections` namespace:</span></span>  
  
|<span data-ttu-id="88d1b-179">클래스</span><span class="sxs-lookup"><span data-stu-id="88d1b-179">Class</span></span>|<span data-ttu-id="88d1b-180">설명</span><span class="sxs-lookup"><span data-stu-id="88d1b-180">Description</span></span>|  
|---|---|  
|<span data-ttu-id="88d1b-181"><xref:System.Collections.ArrayList></xref:System.Collections.ArrayList></span><span class="sxs-lookup"><span data-stu-id="88d1b-181"><xref:System.Collections.ArrayList></span></span>|<span data-ttu-id="88d1b-182">필요에 따라 크기가 동적으로 증가하는 개체 배열을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-182">Represents an array of objects whose size is dynamically increased as required.</span></span>|  
|<span data-ttu-id="88d1b-183"><xref:System.Collections.Hashtable></xref:System.Collections.Hashtable></span><span class="sxs-lookup"><span data-stu-id="88d1b-183"><xref:System.Collections.Hashtable></span></span>|<span data-ttu-id="88d1b-184">키의 해시 코드에 따라 구성된 키/값 쌍의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-184">Represents a collection of key/value pairs that are organized based on the hash code of the key.</span></span>|  
|<span data-ttu-id="88d1b-185"><xref:System.Collections.Queue></xref:System.Collections.Queue></span><span class="sxs-lookup"><span data-stu-id="88d1b-185"><xref:System.Collections.Queue></span></span>|<span data-ttu-id="88d1b-186">FIFO(선입선출) 방식의 개체 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-186">Represents a first in, first out (FIFO) collection of objects.</span></span>|  
|<span data-ttu-id="88d1b-187"><xref:System.Collections.Stack></xref:System.Collections.Stack></span><span class="sxs-lookup"><span data-stu-id="88d1b-187"><xref:System.Collections.Stack></span></span>|<span data-ttu-id="88d1b-188">LIFO(후입선출) 방식의 개체 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-188">Represents a last in, first out (LIFO) collection of objects.</span></span>|  
  
 <span data-ttu-id="88d1b-189"><xref:System.Collections.Specialized>네임 스페이스는 문자열 컬렉션 및 하이브리드 및 연결 된 목록 사전 등의 특수 한 강력한 형식의 컬렉션 클래스를 제공 합니다.</xref:System.Collections.Specialized></span><span class="sxs-lookup"><span data-stu-id="88d1b-189">The <xref:System.Collections.Specialized> namespace provides specialized and strongly typed collection classes, such as string-only collections and linked-list and hybrid dictionaries.</span></span>  

<a name="BKMK_VisualBasic"></a> 
###  <a name="visual-basic-collection-class"></a><span data-ttu-id="88d1b-190">Visual Basic 컬렉션 클래스</span><span class="sxs-lookup"><span data-stu-id="88d1b-190">Visual Basic Collection Class</span></span>  
 <span data-ttu-id="88d1b-191">Visual Basic에서는 <xref:Microsoft.VisualBasic.Collection>클래스 컬렉션 항목 사용 하 여 숫자 인덱스 또는 액세스를 `String` 키.</xref:Microsoft.VisualBasic.Collection></span><span class="sxs-lookup"><span data-stu-id="88d1b-191">You can use the Visual Basic <xref:Microsoft.VisualBasic.Collection> class to access a collection item by using either a numeric index or a `String` key.</span></span> <span data-ttu-id="88d1b-192">키를 지정하거나 지정하지 않고 컬렉션 개체에 항목을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-192">You can add items to a collection object either with or without specifying a key.</span></span> <span data-ttu-id="88d1b-193">키 없이 항목을 추가하는 경우 숫자 인덱스를 사용해서 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-193">If you add an item without a key, you must use its numeric index to access it.</span></span>  
  
 <span data-ttu-id="88d1b-194">Visual Basic `Collection` 클래스의 모든 요소를 형식으로 저장 `Object`이므로 모든 데이터 형식의 항목을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-194">The Visual Basic `Collection` class stores all its elements as type `Object`, so you can add an item of any data type.</span></span> <span data-ttu-id="88d1b-195">부적절한 데이터 형식이 추가되지 않도록 하는 보호 수단은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-195">There is no safeguard against inappropriate data types being added.</span></span>  
  
 <span data-ttu-id="88d1b-196">Visual Basic을 사용 하는 경우 `Collection` 클래스, 컬렉션의 첫 번째 항목에는 인덱스는 1입니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-196">When you use the Visual Basic `Collection` class, the first item in a collection has an index of 1.</span></span> <span data-ttu-id="88d1b-197">이는 시작 인덱스가 0인 .NET Framework 컬렉션 클래스와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-197">This differs from the .NET Framework collection classes, for which the starting index is 0.</span></span>  
  
 <span data-ttu-id="88d1b-198">제네릭 컬렉션을 사용 해야 가능 하다 면는 <xref:System.Collections.Generic?displayProperty=fullName>네임 스페이스 또는 <xref:System.Collections.Concurrent>네임 스페이스는 Visual Basic 대신 `Collection` 클래스</xref:System.Collections.Concurrent> </xref:System.Collections.Generic?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="88d1b-198">Whenever possible, you should use the generic collections in the <xref:System.Collections.Generic?displayProperty=fullName> namespace or the <xref:System.Collections.Concurrent> namespace instead of the Visual Basic `Collection` class.</span></span>  
  
 <span data-ttu-id="88d1b-199">자세한 내용은 <xref:Microsoft.VisualBasic.Collection>.</xref:Microsoft.VisualBasic.Collection> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="88d1b-199">For more information, see <xref:Microsoft.VisualBasic.Collection>.</span></span>  
  
<a name="BKMK_KeyValuePairs"></a>
## <a name="implementing-a-collection-of-keyvalue-pairs"></a><span data-ttu-id="88d1b-200">키/값 쌍의 컬렉션 구현</span><span class="sxs-lookup"><span data-stu-id="88d1b-200">Implementing a Collection of Key/Value Pairs</span></span>   
 <span data-ttu-id="88d1b-201"><xref:System.Collections.Generic.Dictionary%602>제네릭 컬렉션을 사용 하면 각 요소의 키를 사용 하 여 컬렉션의 요소에 액세스할 수 있습니다.</xref:System.Collections.Generic.Dictionary%602></span><span class="sxs-lookup"><span data-stu-id="88d1b-201">The <xref:System.Collections.Generic.Dictionary%602> generic collection enables you to access to elements in a collection by using the key of each element.</span></span> <span data-ttu-id="88d1b-202">사전에 추가하는 각 항목은 값과 관련 키로 이루어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-202">Each addition to the dictionary consists of a value and its associated key.</span></span> <span data-ttu-id="88d1b-203">한편에 해당 키를 사용 하 여 값을 검색 하는 `Dictionary` 클래스는 해시 테이블로 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-203">Retrieving a value by using its key is fast because the `Dictionary` class is implemented as a hash table.</span></span>  
  
 <span data-ttu-id="88d1b-204">다음 예제에서는 한 `Dictionary` 컬렉션 사용 하 여 사전에서 반복 하 고는 `For Each` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-204">The following example creates a `Dictionary` collection and iterates through the dictionary by using a `For Each` statement.</span></span>  
  
```vb  
Private Sub IterateThroughDictionary()  
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()  
  
    For Each kvp As KeyValuePair(Of String, Element) In elements  
        Dim theElement As Element = kvp.Value  
  
        Console.WriteLine("key: " & kvp.Key)  
        With theElement  
            Console.WriteLine("values: " & .Symbol & " " &  
                .Name & " " & .AtomicNumber)  
        End With  
    Next  
End Sub  
  
Private Function BuildDictionary() As Dictionary(Of String, Element)  
    Dim elements As New Dictionary(Of String, Element)  
  
    AddToDictionary(elements, "K", "Potassium", 19)  
    AddToDictionary(elements, "Ca", "Calcium", 20)  
    AddToDictionary(elements, "Sc", "Scandium", 21)  
    AddToDictionary(elements, "Ti", "Titanium", 22)  
  
    Return elements  
End Function  
  
Private Sub AddToDictionary(ByVal elements As Dictionary(Of String, Element),  
ByVal symbol As String, ByVal name As String, ByVal atomicNumber As Integer)  
    Dim theElement As New Element  
  
    theElement.Symbol = symbol  
    theElement.Name = name  
    theElement.AtomicNumber = atomicNumber  
  
    elements.Add(Key:=theElement.Symbol, value:=theElement)  
End Sub  
  
Public Class Element  
    Public Property Symbol As String  
    Public Property Name As String  
    Public Property AtomicNumber As Integer  
End Class  
```  
  
 <span data-ttu-id="88d1b-205">대신 컬렉션 이니셜라이저를 사용 하 여 작성 하는 `Dictionary` 바꿀 수 컬렉션은 `BuildDictionary` 및 `AddToDictionary` 다음 메서드를 사용 하 여 메서드.</span><span class="sxs-lookup"><span data-stu-id="88d1b-205">To instead use a collection initializer to build the `Dictionary` collection, you can replace the `BuildDictionary` and `AddToDictionary` methods with the following method.</span></span>  
  
```vb  
Private Function BuildDictionary2() As Dictionary(Of String, Element)  
    Return New Dictionary(Of String, Element) From  
        {  
            {"K", New Element With  
                {.Symbol = "K", .Name = "Potassium", .AtomicNumber = 19}},  
            {"Ca", New Element With  
                {.Symbol = "Ca", .Name = "Calcium", .AtomicNumber = 20}},  
            {"Sc", New Element With  
                {.Symbol = "Sc", .Name = "Scandium", .AtomicNumber = 21}},  
            {"Ti", New Element With  
                {.Symbol = "Ti", .Name = "Titanium", .AtomicNumber = 22}}  
        }  
End Function  
```  
  
 <span data-ttu-id="88d1b-206">다음 예제에서는 <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A>메서드 및 <xref:System.Collections.Generic.Dictionary%602.Item%2A>속성 `Dictionary` 신속 하 게 항목을 찾는 키별로.</xref:System.Collections.Generic.Dictionary%602.Item%2A> </xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A></span><span class="sxs-lookup"><span data-stu-id="88d1b-206">The following example uses the <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A> method and the <xref:System.Collections.Generic.Dictionary%602.Item%2A> property of `Dictionary` to quickly find an item by key.</span></span> <span data-ttu-id="88d1b-207">`Item` 속성 항목에 액세스할 수 있습니다는 `elements` 사용 하 여 컬렉션의 `elements(symbol)` Visual basic에서 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-207">The `Item` property enables you to access an item in the `elements` collection by using the `elements(symbol)` code in Visual Basic.</span></span>  
  
```vb  
Private Sub FindInDictionary(ByVal symbol As String)  
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()  
  
    If elements.ContainsKey(symbol) = False Then  
        Console.WriteLine(symbol & " not found")  
    Else  
        Dim theElement = elements(symbol)  
        Console.WriteLine("found: " & theElement.Name)  
    End If  
End Sub  
```  
  
 <span data-ttu-id="88d1b-208">다음 예제에서는 대신 사용 하 여는 <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A>메서드 키에서 항목을 빠르게 찾을.</xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A></span><span class="sxs-lookup"><span data-stu-id="88d1b-208">The following example instead uses the <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> method quickly find an item by key.</span></span>  
  
```vb  
Private Sub FindInDictionary2(ByVal symbol As String)  
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()  
  
    Dim theElement As Element = Nothing  
    If elements.TryGetValue(symbol, theElement) = False Then  
        Console.WriteLine(symbol & " not found")  
    Else  
        Console.WriteLine("found: " & theElement.Name)  
    End If  
End Sub  
```  
  
<a name="BKMK_LINQ"></a> 
##  <a name="using-linq-to-access-a-collection"></a><span data-ttu-id="88d1b-209">LINQ를 사용하여 컬렉션에 액세스</span><span class="sxs-lookup"><span data-stu-id="88d1b-209">Using LINQ to Access a Collection</span></span>  
 <span data-ttu-id="88d1b-210">LINQ(통합 언어 쿼리)를 사용하여 컬렉션에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-210">LINQ (Language-Integrated Query) can be used to access collections.</span></span> <span data-ttu-id="88d1b-211">LINQ 쿼리는 필터링, 정렬 및 그룹화 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-211">LINQ queries provide filtering, ordering, and grouping capabilities.</span></span> <span data-ttu-id="88d1b-212">자세한 내용은 참조 [Visual Basic에서 LINQ 시작](../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-212">For more information, see [Getting Started with LINQ in Visual Basic](../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).</span></span>  
  
 <span data-ttu-id="88d1b-213">제네릭에 대해 LINQ 쿼리를 실행 하는 다음 예제에서는 `List`합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-213">The following example runs a LINQ query against a generic `List`.</span></span> <span data-ttu-id="88d1b-214">LINQ 쿼리는 결과를 포함하는 다른 컬렉션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-214">The LINQ query returns a different collection that contains the results.</span></span>  
  
```vb  
Private Sub ShowLINQ()  
    Dim elements As List(Of Element) = BuildList()  
  
    ' LINQ Query.  
    Dim subset = From theElement In elements  
                  Where theElement.AtomicNumber < 22  
                  Order By theElement.Name  
  
    For Each theElement In subset  
        Console.WriteLine(theElement.Name & " " & theElement.AtomicNumber)  
    Next  
  
    ' Output:  
    '  Calcium 20  
    '  Potassium 19  
    '  Scandium 21  
End Sub  
  
Private Function BuildList() As List(Of Element)  
    Return New List(Of Element) From  
        {  
            {New Element With  
                {.Symbol = "K", .Name = "Potassium", .AtomicNumber = 19}},  
            {New Element With  
                {.Symbol = "Ca", .Name = "Calcium", .AtomicNumber = 20}},  
            {New Element With  
                {.Symbol = "Sc", .Name = "Scandium", .AtomicNumber = 21}},  
            {New Element With  
                {.Symbol = "Ti", .Name = "Titanium", .AtomicNumber = 22}}  
        }  
End Function  
  
Public Class Element  
    Public Property Symbol As String  
    Public Property Name As String  
    Public Property AtomicNumber As Integer  
End Class  
```  
  
 <a name="BKMK_Sorting"></a> 
## <a name="sorting-a-collection"></a><span data-ttu-id="88d1b-215">컬렉션 정렬</span><span class="sxs-lookup"><span data-stu-id="88d1b-215">Sorting a Collection</span></span>  
 <span data-ttu-id="88d1b-216">다음 예제에서는 컬렉션 정렬 절차를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-216">The following example illustrates a procedure for sorting a collection.</span></span> <span data-ttu-id="88d1b-217">인스턴스를 정렬 하는 예제는 `Car` <xref:System.Collections.Generic.List%601>.</xref:System.Collections.Generic.List%601> 에 저장 되어 있는 클래스</span><span class="sxs-lookup"><span data-stu-id="88d1b-217">The example sorts instances of the `Car` class that are stored in a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="88d1b-218">`Car` 클래스가 구현 하는 <xref:System.IComparable%601>인터페이스를 필요로 하는 <xref:System.IComparable%601.CompareTo%2A>메서드를 구현 합니다.</xref:System.IComparable%601.CompareTo%2A> </xref:System.IComparable%601></span><span class="sxs-lookup"><span data-stu-id="88d1b-218">The `Car` class implements the <xref:System.IComparable%601> interface, which requires that the <xref:System.IComparable%601.CompareTo%2A> method be implemented.</span></span>  
  
 <span data-ttu-id="88d1b-219">각 호출에는 <xref:System.IComparable%601.CompareTo%2A>메서드 정렬에 사용 되는 단일 비교를 수행 합니다.</xref:System.IComparable%601.CompareTo%2A></span><span class="sxs-lookup"><span data-stu-id="88d1b-219">Each call to the <xref:System.IComparable%601.CompareTo%2A> method makes a single comparison that is used for sorting.</span></span> <span data-ttu-id="88d1b-220">사용자가 작성 한 코드는 `CompareTo` 메서드를 다른 개체와 현재 개체의 각 비교에 대 한 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-220">User-written code in the `CompareTo` method returns a value for each comparison of the current object with another object.</span></span> <span data-ttu-id="88d1b-221">현재 개체가 다른 개체보다 작으면 반환되는 값이&0;보다 작고, 현재 개체가 다른 개체보다 크면&0;보다 크고, 같으면&0;입니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-221">The value returned is less than zero if the current object is less than the other object, greater than zero if the current object is greater than the other object, and zero if they are equal.</span></span> <span data-ttu-id="88d1b-222">이렇게 하면 보다 큼, 보다 작음 및 같음에 대한 조건을 코드에서 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-222">This enables you to define in code the criteria for greater than, less than, and equal.</span></span>  
  
 <span data-ttu-id="88d1b-223">에 `ListCars` 메서드를는 `cars.Sort()` 문 목록을 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-223">In the `ListCars` method, the `cars.Sort()` statement sorts the list.</span></span> <span data-ttu-id="88d1b-224">이 호출으로는 <xref:System.Collections.Generic.List%601.Sort%2A>의 메서드는 <xref:System.Collections.Generic.List%601>하면는 `CompareTo` 에 대 한 자동으로 호출 될 메서드를는 `Car` 개체에 `List`.</xref:System.Collections.Generic.List%601> </xref:System.Collections.Generic.List%601.Sort%2A></span><span class="sxs-lookup"><span data-stu-id="88d1b-224">This call to the <xref:System.Collections.Generic.List%601.Sort%2A> method of the <xref:System.Collections.Generic.List%601> causes the `CompareTo` method to be called automatically for the `Car` objects in the `List`.</span></span>  
  
```vb  
Public Sub ListCars()  
  
    ' Create some new cars.  
    Dim cars As New List(Of Car) From  
    {  
        New Car With {.Name = "car1", .Color = "blue", .Speed = 20},  
        New Car With {.Name = "car2", .Color = "red", .Speed = 50},  
        New Car With {.Name = "car3", .Color = "green", .Speed = 10},  
        New Car With {.Name = "car4", .Color = "blue", .Speed = 50},  
        New Car With {.Name = "car5", .Color = "blue", .Speed = 30},  
        New Car With {.Name = "car6", .Color = "red", .Speed = 60},  
        New Car With {.Name = "car7", .Color = "green", .Speed = 50}  
    }  
  
    ' Sort the cars by color alphabetically, and then by speed  
    ' in descending order.  
    cars.Sort()  
  
    ' View all of the cars.  
    For Each thisCar As Car In cars  
        Console.Write(thisCar.Color.PadRight(5) & " ")  
        Console.Write(thisCar.Speed.ToString & " ")  
        Console.Write(thisCar.Name)  
        Console.WriteLine()  
    Next  
  
    ' Output:  
    '  blue  50 car4  
    '  blue  30 car5  
    '  blue  20 car1  
    '  green 50 car7  
    '  green 10 car3  
    '  red   60 car6  
    '  red   50 car2  
End Sub  
  
Public Class Car  
    Implements IComparable(Of Car)  
  
    Public Property Name As String  
    Public Property Speed As Integer  
    Public Property Color As String  
  
    Public Function CompareTo(ByVal other As Car) As Integer _  
        Implements System.IComparable(Of Car).CompareTo  
        ' A call to this method makes a single comparison that is  
        ' used for sorting.  
  
        ' Determine the relative order of the objects being compared.  
        ' Sort by color alphabetically, and then by speed in  
        ' descending order.  
  
        ' Compare the colors.  
        Dim compare As Integer  
        compare = String.Compare(Me.Color, other.Color, True)  
  
        ' If the colors are the same, compare the speeds.  
        If compare = 0 Then  
            compare = Me.Speed.CompareTo(other.Speed)  
  
            ' Use descending order for speed.  
            compare = -compare  
        End If  
  
        Return compare  
    End Function  
End Class  
```  
  
<a name="BKMK_CustomCollection"></a> 
## <a name="defining-a-custom-collection"></a><span data-ttu-id="88d1b-225">사용자 지정 컬렉션 정의</span><span class="sxs-lookup"><span data-stu-id="88d1b-225">Defining a Custom Collection</span></span>  
 <span data-ttu-id="88d1b-226">구현 하 여 컬렉션을 정의할 수는 <xref:System.Collections.Generic.IEnumerable%601>또는 <xref:System.Collections.IEnumerable>인터페이스.</xref:System.Collections.IEnumerable> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="88d1b-226">You can define a collection by implementing the <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="88d1b-227">자세한 내용은 참조 [컬렉션을 열거](http://msdn.microsoft.com/en-us/71807ea7-9180-48a6-916f-35a5251d477f)합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-227">For additional information, see [Enumerating a Collection](http://msdn.microsoft.com/en-us/71807ea7-9180-48a6-916f-35a5251d477f).</span></span>  
  
 <span data-ttu-id="88d1b-228">사용자 지정 컬렉션을 정의할 수 있지만 대신에 설명 되어 있는.NET Framework에 포함 된 컬렉션을 사용 하는 것이 바람직합니다 [종류의 컬렉션](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b) 이 항목의 앞부분에 나오는 합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-228">Although you can define a custom collection, it is usually better to instead use the collections that are included in the .NET Framework, which are described in [Kinds of Collections](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b) earlier in this topic.</span></span>  
  
 <span data-ttu-id="88d1b-229">다음 예제에서는 라는 사용자 지정 컬렉션 클래스를 정의 `AllColors`합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-229">The following example defines a custom collection class named `AllColors`.</span></span> <span data-ttu-id="88d1b-230">이 클래스를 구현 하는 <xref:System.Collections.IEnumerable>인터페이스를 필요로 하는 <xref:System.Collections.IEnumerable.GetEnumerator%2A>메서드를 구현 합니다.</xref:System.Collections.IEnumerable.GetEnumerator%2A> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="88d1b-230">This class implements the <xref:System.Collections.IEnumerable> interface, which requires that the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method be implemented.</span></span>  
  
 <span data-ttu-id="88d1b-231">`GetEnumerator` 의 인스턴스를 반환 하는 메서드는 `ColorEnumerator` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-231">The `GetEnumerator` method returns an instance of the `ColorEnumerator` class.</span></span> <span data-ttu-id="88d1b-232">`ColorEnumerator`구현 하는 <xref:System.Collections.IEnumerator>인터페이스를 필요로 하는 <xref:System.Collections.IEnumerator.Current%2A>속성을 <xref:System.Collections.IEnumerator.MoveNext%2A>메서드를 및 <xref:System.Collections.IEnumerator.Reset%2A>메서드를 구현 합니다.</xref:System.Collections.IEnumerator.Reset%2A> </xref:System.Collections.IEnumerator.MoveNext%2A> </xref:System.Collections.IEnumerator.Current%2A> </xref:System.Collections.IEnumerator></span><span class="sxs-lookup"><span data-stu-id="88d1b-232">`ColorEnumerator` implements the <xref:System.Collections.IEnumerator> interface, which requires that the <xref:System.Collections.IEnumerator.Current%2A> property, <xref:System.Collections.IEnumerator.MoveNext%2A> method, and <xref:System.Collections.IEnumerator.Reset%2A> method be implemented.</span></span>  
  
```vb  
Public Sub ListColors()  
    Dim colors As New AllColors()  
  
    For Each theColor As Color In colors  
        Console.Write(theColor.Name & " ")  
    Next  
    Console.WriteLine()  
    ' Output: red blue green  
End Sub  
  
' Collection class.  
Public Class AllColors  
    Implements System.Collections.IEnumerable  
  
    Private _colors() As Color =  
    {  
        New Color With {.Name = "red"},  
        New Color With {.Name = "blue"},  
        New Color With {.Name = "green"}  
    }  
  
    Public Function GetEnumerator() As System.Collections.IEnumerator _  
        Implements System.Collections.IEnumerable.GetEnumerator  
  
        Return New ColorEnumerator(_colors)  
  
        ' Instead of creating a custom enumerator, you could  
        ' use the GetEnumerator of the array.  
        'Return _colors.GetEnumerator  
    End Function  
  
    ' Custom enumerator.  
    Private Class ColorEnumerator  
        Implements System.Collections.IEnumerator  
  
        Private _colors() As Color  
        Private _position As Integer = -1  
  
        Public Sub New(ByVal colors() As Color)  
            _colors = colors  
        End Sub  
  
        Public ReadOnly Property Current() As Object _  
            Implements System.Collections.IEnumerator.Current  
            Get  
                Return _colors(_position)  
            End Get  
        End Property  
  
        Public Function MoveNext() As Boolean _  
            Implements System.Collections.IEnumerator.MoveNext  
            _position += 1  
            Return (_position < _colors.Length)  
        End Function  
  
        Public Sub Reset() Implements System.Collections.IEnumerator.Reset  
            _position = -1  
        End Sub  
    End Class  
End Class  
  
' Element class.  
Public Class Color  
    Public Property Name As String  
End Class  
```  
  
<a name="BKMK_Iterators"></a>
##  <a name="iterators"></a><span data-ttu-id="88d1b-233">반복기</span><span class="sxs-lookup"><span data-stu-id="88d1b-233">Iterators</span></span>  
 <span data-ttu-id="88d1b-234">*반복기* 컬렉션에 대해 사용자 지정 반복을 수행 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-234">An *iterator* is used to perform a custom iteration over a collection.</span></span> <span data-ttu-id="88d1b-235">반복기 메서드 일 수 또는 `get` 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-235">An iterator can be a method or a `get` accessor.</span></span> <span data-ttu-id="88d1b-236">반복기를 사용 하 여는 [생성](../../../visual-basic/language-reference/statements/yield-statement.md) 문을 한 번에 컬렉션의 각 요소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-236">An iterator uses a [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element of the collection one at a time.</span></span>  
  
 <span data-ttu-id="88d1b-237">반복기를 사용 하 여 호출을 [각각에 대해... 다음](../../../visual-basic/language-reference/statements/for-each-next-statement.md) 문입니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-237">You call an iterator by using a [For Each…Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement.</span></span> <span data-ttu-id="88d1b-238">각 반복에서 `For Each` 루프는 반복기를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-238">Each iteration of the `For Each` loop calls the iterator.</span></span> <span data-ttu-id="88d1b-239">경우는 `Yield` 문이 반복기에 도달 하면, 식을 반환 되 고 코드에서 현재 위치는 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-239">When a `Yield` statement is reached in the iterator, an expression is returned, and the current location in code is retained.</span></span> <span data-ttu-id="88d1b-240">다음에 반복기가 호출되면 해당 위치에서 실행이 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-240">Execution is restarted from that location the next time that the iterator is called.</span></span>  
  
 <span data-ttu-id="88d1b-241">자세한 내용은 참조 [반복기 (Visual Basic)](../../../visual-basic/programming-guide/concepts/iterators.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-241">For more information, see [Iterators (Visual Basic)](../../../visual-basic/programming-guide/concepts/iterators.md).</span></span>  
  
 <span data-ttu-id="88d1b-242">다음 예제에서는 반복기 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-242">The following example uses an iterator method.</span></span> <span data-ttu-id="88d1b-243">반복기 메서드가 `Yield` 문 내에 있는 한 [에 대 한... 다음](../../../visual-basic/language-reference/statements/for-next-statement.md) 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="88d1b-243">The iterator method has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="88d1b-244">에 `ListEvenNumbers` 메서드, 각 반복의는 `For Each` 문 본문에서 다음 단계로 진행 하는 반복기 메서드를 호출 만듭니다 `Yield` 문.</span><span class="sxs-lookup"><span data-stu-id="88d1b-244">In the `ListEvenNumbers` method, each iteration of the `For Each` statement body creates a call to the iterator method, which proceeds to the next `Yield` statement.</span></span>  
  
```vb  
Public Sub ListEvenNumbers()  
    For Each number As Integer In EvenSequence(5, 18)  
        Console.Write(number & " ")  
    Next  
    Console.WriteLine()  
    ' Output: 6 8 10 12 14 16 18  
End Sub  
  
Private Iterator Function EvenSequence(  
ByVal firstNumber As Integer, ByVal lastNumber As Integer) _  
As IEnumerable(Of Integer)  
  
' Yield even numbers in the range.  
    For number = firstNumber To lastNumber  
        If number Mod 2 = 0 Then  
            Yield number  
        End If  
    Next  
End Function  
```  
  
## <a name="see-also"></a><span data-ttu-id="88d1b-245">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88d1b-245">See Also</span></span>  
 <span data-ttu-id="88d1b-246">[컬렉션 이니셜라이저](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md) </span><span class="sxs-lookup"><span data-stu-id="88d1b-246">[Collection Initializers](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md) </span></span>  
<span data-ttu-id="88d1b-247"> [프로그래밍 개념 (Visual Basic)](../../../visual-basic/programming-guide/concepts/index.md) </span><span class="sxs-lookup"><span data-stu-id="88d1b-247"> [Programming Concepts (Visual Basic)](../../../visual-basic/programming-guide/concepts/index.md) </span></span>  
<span data-ttu-id="88d1b-248"> [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="88d1b-248"> [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="88d1b-249"> [LINQ to Objects (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span><span class="sxs-lookup"><span data-stu-id="88d1b-249"> [LINQ to Objects (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span></span>  
<span data-ttu-id="88d1b-250"> [PLINQ (병렬 LINQ)](http://msdn.microsoft.com/library/3d4d0cd3-bde4-490b-99e7-f4e41be96455) </span><span class="sxs-lookup"><span data-stu-id="88d1b-250"> [Parallel LINQ (PLINQ)](http://msdn.microsoft.com/library/3d4d0cd3-bde4-490b-99e7-f4e41be96455) </span></span>  
<span data-ttu-id="88d1b-251"> [컬렉션 및 데이터 구조](../../../standard/collections/index.md) </span><span class="sxs-lookup"><span data-stu-id="88d1b-251"> [Collections and Data Structures](../../../standard/collections/index.md) </span></span>  
<span data-ttu-id="88d1b-252"> [컬렉션 만들기 및 조작](http://msdn.microsoft.com/en-us/2065398e-eb1a-4821-9188-75f16e42e069) </span><span class="sxs-lookup"><span data-stu-id="88d1b-252"> [Creating and Manipulating Collections](http://msdn.microsoft.com/en-us/2065398e-eb1a-4821-9188-75f16e42e069) </span></span>  
<span data-ttu-id="88d1b-253"> [Collection 클래스 선택](../../../standard/collections/selecting-a-collection-class.md) </span><span class="sxs-lookup"><span data-stu-id="88d1b-253"> [Selecting a Collection Class](../../../standard/collections/selecting-a-collection-class.md) </span></span>  
<span data-ttu-id="88d1b-254"> [컬렉션 내의 비교와 정렬](../../../standard/collections/comparisons-and-sorts-within-collections.md) </span><span class="sxs-lookup"><span data-stu-id="88d1b-254"> [Comparisons and Sorts Within Collections](../../../standard/collections/comparisons-and-sorts-within-collections.md) </span></span>  
<span data-ttu-id="88d1b-255"> [제네릭 컬렉션 사용 기준](../../../standard/collections/when-to-use-generic-collections.md)</span><span class="sxs-lookup"><span data-stu-id="88d1b-255"> [When to Use Generic Collections](../../../standard/collections/when-to-use-generic-collections.md)</span></span>
