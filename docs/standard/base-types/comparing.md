---
title: "문자열 비교"
description: "문자열 비교"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 920ee5e8-3d61-4941-b5af-fc50eaee427c
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 47ee37886fa2662a89730e9d52ee04987e37da2f
ms.contentlocale: ko-kr
ms.lasthandoff: 03/02/2017

---

# <a name="comparing-strings"></a><span data-ttu-id="4a4f9-104">문자열 비교</span><span class="sxs-lookup"><span data-stu-id="4a4f9-104">Comparing strings</span></span>

<span data-ttu-id="4a4f9-105">.NET에서는 문자열의 값을 비교하는 여러 가지 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-105">.NET provides several methods to compare the values of strings.</span></span> <span data-ttu-id="4a4f9-106">다음 표에서는 값 비교 메서드를 나열하고 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-106">The following table lists and describes the value-comparison methods.</span></span>

<span data-ttu-id="4a4f9-107">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="4a4f9-107">Method name</span></span> | <span data-ttu-id="4a4f9-108">기능</span><span class="sxs-lookup"><span data-stu-id="4a4f9-108">Use</span></span>
----------- | ---
<span data-ttu-id="4a4f9-109">[String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32))</span><span class="sxs-lookup"><span data-stu-id="4a4f9-109">[String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32))</span></span> | <span data-ttu-id="4a4f9-110">두 문자열의 값을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-110">Compares the values of two strings.</span></span> <span data-ttu-id="4a4f9-111">정수 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-111">Returns an integer value.</span></span>
<span data-ttu-id="4a4f9-112">[String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32))</span><span class="sxs-lookup"><span data-stu-id="4a4f9-112">[String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32))</span></span> | <span data-ttu-id="4a4f9-113">로컬 문화권에 관계없이 두 문자열을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-113">Compares two strings without regard to local culture.</span></span> <span data-ttu-id="4a4f9-114">정수 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-114">Returns an integer value.</span></span>
<span data-ttu-id="4a4f9-115">[String.CompareTo](xref:System.String.CompareTo(System.String))</span><span class="sxs-lookup"><span data-stu-id="4a4f9-115">[String.CompareTo](xref:System.String.CompareTo(System.String))</span></span> | <span data-ttu-id="4a4f9-116">현재 문자열 개체를 다른 문자열과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-116">Compares the current string object to another string.</span></span> <span data-ttu-id="4a4f9-117">정수 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-117">Returns an integer value.</span></span>
<span data-ttu-id="4a4f9-118">[String.StartsWith](xref:System.String.StartsWith(System.String))</span><span class="sxs-lookup"><span data-stu-id="4a4f9-118">[String.StartsWith](xref:System.String.StartsWith(System.String))</span></span> | <span data-ttu-id="4a4f9-119">문자열이 전달된 문자열로 시작하는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-119">Determines whether a string begins with the string passed.</span></span> <span data-ttu-id="4a4f9-120">부울 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-120">Returns a Boolean value.</span></span>
<span data-ttu-id="4a4f9-121">[String.EndsWith](xref:System.String.CompareTo(System.String))</span><span class="sxs-lookup"><span data-stu-id="4a4f9-121">[String.EndsWith](xref:System.String.CompareTo(System.String))</span></span> | <span data-ttu-id="4a4f9-122">문자열이 전달된 문자열로 끝나는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-122">Determines whether a string ends with the string passed.</span></span> <span data-ttu-id="4a4f9-123">부울 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-123">Returns a Boolean value.</span></span>
<span data-ttu-id="4a4f9-124">[String.Equals](xref:System.String.CompareTo(System.String))</span><span class="sxs-lookup"><span data-stu-id="4a4f9-124">[String.Equals](xref:System.String.CompareTo(System.String))</span></span> | <span data-ttu-id="4a4f9-125">두 문자열이 같은지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-125">Determines whether two strings are the same.</span></span> <span data-ttu-id="4a4f9-126">부울 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-126">Returns a Boolean value.</span></span>
<span data-ttu-id="4a4f9-127">[String.IndexOf](xref:System.String.IndexOf(System.Char))</span><span class="sxs-lookup"><span data-stu-id="4a4f9-127">[String.IndexOf](xref:System.String.IndexOf(System.Char))</span></span> | <span data-ttu-id="4a4f9-128">검사 중인 문자열의 처음부터 시작하여 문자 또는 문자열의 인덱스 위치를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-128">Returns the index position of a character or string, starting from the beginning of the string you are examining.</span></span> <span data-ttu-id="4a4f9-129">정수 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-129">Returns an integer value.</span></span>
<span data-ttu-id="4a4f9-130">[String.LastIndexOf](xref:System.String.LastIndexOf(System.Char))</span><span class="sxs-lookup"><span data-stu-id="4a4f9-130">[String.LastIndexOf](xref:System.String.LastIndexOf(System.Char))</span></span> | <span data-ttu-id="4a4f9-131">검사 중인 문자열의 끝부터 시작하여 문자 또는 문자열의 인덱스 위치를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-131">Returns the index position of a character or string, starting from the end of the string you are examining.</span></span> <span data-ttu-id="4a4f9-132">정수 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-132">Returns an integer value.</span></span>

## <a name="compare"></a><span data-ttu-id="4a4f9-133">비교</span><span class="sxs-lookup"><span data-stu-id="4a4f9-133">Compare</span></span>

<span data-ttu-id="4a4f9-134">정적 [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) 메서드는 두 문자열을 비교하는 철저한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-134">The static [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) method provides a thorough way of comparing two strings.</span></span> <span data-ttu-id="4a4f9-135">이 메서드는 문화권을 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-135">This method is culturally aware.</span></span> <span data-ttu-id="4a4f9-136">이 함수를 사용하여 두 문자열 또는 두 문자열의 부분 문자열을 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-136">You can use this function to compare two strings or substrings of two strings.</span></span> <span data-ttu-id="4a4f9-137">또한 대/소문자와 문화권 차이를 반영하거나 무시하는 오버로드가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-137">Additionally, overloads are provided that regard or disregard case and cultural variance.</span></span> <span data-ttu-id="4a4f9-138">다음 표에서는 이 메서드가 반환할 수 있는 세 가지 정수 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-138">The following table shows the three integer values that this method might return.</span></span> 

<span data-ttu-id="4a4f9-139">반환 값</span><span class="sxs-lookup"><span data-stu-id="4a4f9-139">Return value</span></span> | <span data-ttu-id="4a4f9-140">조건</span><span class="sxs-lookup"><span data-stu-id="4a4f9-140">Condition</span></span>
------------ | ---------
<span data-ttu-id="4a4f9-141">음의 정수</span><span class="sxs-lookup"><span data-stu-id="4a4f9-141">A negative integer</span></span> | <span data-ttu-id="4a4f9-142">정렬 순서에서 첫 번째 문자열이 두 번째 문자열 앞에 오거나 첫 번째 문자열이 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-142">The first string precedes the second string in the sort order, or the first string is `null`.</span></span>
<span data-ttu-id="4a4f9-143">0</span><span class="sxs-lookup"><span data-stu-id="4a4f9-143">0</span></span> | <span data-ttu-id="4a4f9-144">첫 번째 문자열과 두 번째 문자열이 같거나 두 문자열이 모두 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-144">The first string and the second string are equal, or both strings are `null`.</span></span>
<span data-ttu-id="4a4f9-145">양의 정수 또는 1</span><span class="sxs-lookup"><span data-stu-id="4a4f9-145">A positive integer, or 1</span></span> | <span data-ttu-id="4a4f9-146">정렬 순서에서 첫 번째 문자열이 두 번째 문자열 뒤에 오거나 두 번째 문자열이 null입니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-146">The first string follows the second string in the sort order, or the second string is null.</span></span>
 
> [!IMPORTANT]
> <span data-ttu-id="4a4f9-147">[String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) 메서드는 주로 문자열의 순서를 지정하거나 정렬할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-147">The [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) method is primarily intended for use when ordering or sorting strings.</span></span> <span data-ttu-id="4a4f9-148">[String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) 메서드를 통해 같은지 여부를 테스트하면 안 됩니다(즉, 한 문자열이 다른 문자열보다 작거나 큰지에 관계없이 반환 값 0을 명시적으로 찾기 위해 사용하면 안 됨).</span><span class="sxs-lookup"><span data-stu-id="4a4f9-148">You should not use the [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) method to test for equality (that is, to explicitly look for a return value of 0 with no regard for whether one string is less than or greater than the other).</span></span> <span data-ttu-id="4a4f9-149">대신, 두 문자열이 같은지를 확인하려면 [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)) 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-149">Instead, to determine whether two strings are equal, use the [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)) method.</span></span>

<span data-ttu-id="4a4f9-150">다음 예제에서는 [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) 메서드를 사용하여 두 문자열의 상대 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-150">The following example uses the [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) method to determine the relative values of two strings.</span></span>

```csharp
string string1 = "Hello World!";
Console.WriteLine(String.Compare(string1, "Hello World?"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(String.Compare(string1, "Hello World?"))
```

<span data-ttu-id="4a4f9-151">이 예제에서는 콘솔에 `-1`을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-151">This example displays `-1` to the console.</span></span>

## <a name="compareordinal"></a><span data-ttu-id="4a4f9-152">CompareOrdinal</span><span class="sxs-lookup"><span data-stu-id="4a4f9-152">CompareOrdinal</span></span>

<span data-ttu-id="4a4f9-153">[String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) 메서드는 로컬 문화권을 고려하지 않고 두 문자열 개체를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-153">The [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) method compares two string objects without considering the local culture.</span></span> <span data-ttu-id="4a4f9-154">이 메서드의 반환 값은 앞의 표에서 `Compare` 메서드가 반환하는 값과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-154">The return values of this method are identical to the values returned by the `Compare` method in the previous table.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4a4f9-155">[String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) 메서드는 주로 문자열의 순서를 지정하거나 정렬할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-155">The [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) method is primarily intended for use when ordering or sorting strings.</span></span> <span data-ttu-id="4a4f9-156">[String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) 메서드를 통해 문자열이 같은지를 테스트하면 안 됩니다(즉, 한 문자열이 다른 문자열보다 작거나 큰지에 관계없이 반환 값 0을 명시적으로 찾기 위해 사용하면 안 됨).</span><span class="sxs-lookup"><span data-stu-id="4a4f9-156">You should not use the [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) method to test for equality (that is, to explicitly look for a return value of 0 with no regard for whether one string is less than or greater than the other).</span></span> <span data-ttu-id="4a4f9-157">대신, 두 문자열이 같은지를 확인하려면 [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)) 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-157">Instead, to determine whether two strings are equal, use the [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)) method.</span></span>

<span data-ttu-id="4a4f9-158">다음 예제에서는 `CompareOrdinal` 메서드를 사용하여 두 문자열의 값을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-158">The following example uses the `CompareOrdinal` method to compare the values of two strings.</span></span>

```csharp
string string1 = "Hello World!";
Console.WriteLine(String.CompareOrdinal(string1, "hello world!"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(String.CompareOrdinal(string1, "hello world!"))
```

<span data-ttu-id="4a4f9-159">이 예제에서는 콘솔에 `-32`을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-159">This example displays `-32` to the console.</span></span>

## <a name="compareto"></a><span data-ttu-id="4a4f9-160">CompareTo</span><span class="sxs-lookup"><span data-stu-id="4a4f9-160">CompareTo</span></span>

<span data-ttu-id="4a4f9-161">[String.CompareTo](xref:System.String.CompareTo(System.String)) 메서드는 현재 문자열 개체가 캡슐화하는 문자열을 다른 문자열 또는 개체와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-161">The [String.CompareTo](xref:System.String.CompareTo(System.String)) method compares the string that the current string object encapsulates to another string or object.</span></span> <span data-ttu-id="4a4f9-162">이 메서드의 반환 값은 앞의 표에서 `String.Compare` 메서드가 반환하는 값과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-162">The return values of this method are identical to the values returned by the `String.Compare` method in the previous table.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4a4f9-163">[String.CompareTo](xref:System.String.CompareTo(System.String)) 메서드는 주로 문자열의 순서를 지정하거나 정렬할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-163">The [String.CompareTo](xref:System.String.CompareTo(System.String)) method is primarily intended for use when ordering or sorting strings.</span></span> <span data-ttu-id="4a4f9-164">[String.CompareTo](xref:System.String.CompareTo(System.String)) 메서드를 통해 같은지 여부를 테스트하면 안 됩니다(즉, 한 문자열이 다른 문자열보다 작거나 큰지에 관계없이 반환 값 0을 명시적으로 찾기 위해 사용하면 안 됨).</span><span class="sxs-lookup"><span data-stu-id="4a4f9-164">You should not use the [String.CompareTo](xref:System.String.CompareTo(System.String)) method to test for equality (that is, to explicitly look for a return value of 0 with no regard for whether one string is less than or greater than the other).</span></span> <span data-ttu-id="4a4f9-165">대신, 두 문자열이 같은지를 확인하려면 [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)) 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-165">Instead, to determine whether two strings are equal, use the [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)) method.</span></span>

<span data-ttu-id="4a4f9-166">다음 예제에서는 `String.CompareTo` 메서드를 사용하여 `string1` 개체를 `string2` 개체와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-166">The following example uses the `String.CompareTo` method to compare the `string1` object to the `string2` object.</span></span>

```csharp
string string1 = "Hello World";
string string2 = "Hello World!";
int MyInt = string1.CompareTo(string2);
Console.WriteLine( MyInt );
```

```vb
Dim string1 As String = "Hello World"
Dim string2 As String = "Hello World!"
Dim MyInt As Integer = string1.CompareTo(string2)
Console.WriteLine(MyInt)
```

<span data-ttu-id="4a4f9-167">이 예제에서는 콘솔에 `-1`을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-167">This example displays `-1` to the console.</span></span>

## <a name="equals"></a><span data-ttu-id="4a4f9-168">같음</span><span class="sxs-lookup"><span data-stu-id="4a4f9-168">Equals</span></span>

<span data-ttu-id="4a4f9-169">[String.Equals](xref:System.String.CompareTo(System.String)) 메서드는 두 문자열이 같은지 여부를 쉽게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-169">The [String.Equals](xref:System.String.CompareTo(System.String)) method can easily determine if two strings are the same.</span></span> <span data-ttu-id="4a4f9-170">대/소문자 구분 메서드는 `true` 또는 `false` 부울 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-170">This case-sensitive method returns a `true` or `false` Boolean value.</span></span> <span data-ttu-id="4a4f9-171">다음 예제와 같이 기존 클래스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-171">It can be used from an existing class, as illustrated in the next example.</span></span> <span data-ttu-id="4a4f9-172">다음 예제에서는 `Equals` 메서드를 사용하여 문자열 개체에 "Hello World"라는 구가 포함되어 있는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-172">The following example uses the `Equals` method to determine whether a string object contains the phrase "Hello World".</span></span>

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.Equals("Hello World"));
```

```vb
Dim string1 As String = "Hello World"
Console.WriteLine(string1.Equals("Hello World"))
```

<span data-ttu-id="4a4f9-173">이 예제에서는 콘솔에 `true`을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-173">This example displays `true` to the console.</span></span>

<span data-ttu-id="4a4f9-174">이 메서드는 정적 메서드로 사용될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-174">This method can also be used as a static method.</span></span> <span data-ttu-id="4a4f9-175">다음 예제에서는 정적 메서드를 사용하여 두 문자열 개체를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-175">The following example compares two string objects using a static method.</span></span>

```csharp
string string1 = "Hello World";
string string2 = "Hello World";
Console.WriteLine(String.Equals(string1, string2));
```

```vb
Dim string1 As String = "Hello World"
Dim string2 As String = "Hello World"
Console.WriteLine(String.Equals(string1, string2))
```

<span data-ttu-id="4a4f9-176">이 예제에서는 콘솔에 `true`을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-176">This example displays `true` to the console.</span></span>

## <a name="startswith-and-endswith"></a><span data-ttu-id="4a4f9-177">StartsWith 및 EndsWith</span><span class="sxs-lookup"><span data-stu-id="4a4f9-177">StartsWith and EndsWith</span></span>

<span data-ttu-id="4a4f9-178">[String.StartsWith](xref:System.String.StartsWith(System.String)) 메서드를 사용하여 문자열 개체가 다른 문자열을 포함하는 동일한 문자로 시작하는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-178">You can use the [String.StartsWith](xref:System.String.StartsWith(System.String)) method to determine whether a string object begins with the same characters that encompass another string.</span></span> <span data-ttu-id="4a4f9-179">이 대/소문자 구분 메서드는 현재 문자열 개체가 전달된 문자열로 시작하는 경우 `true`를 반환하고, 전달된 문자열로 시작하지 않는 경우 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-179">This case-sensitive method returns `true` if the current string object begins with the passed string and `false` if it does not.</span></span> <span data-ttu-id="4a4f9-180">다음 예제에서는 이 메서드를 사용하여 문자열 개체가 "Hello"로 시작하는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-180">The following example uses this method to determine if a string object begins with "Hello".</span></span>

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.StartsWith("Hello"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.StartsWith("Hello"))
```

<span data-ttu-id="4a4f9-181">이 예제에서는 콘솔에 `true`을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-181">This example displays `true` to the console.</span></span>

<span data-ttu-id="4a4f9-182">[String.EndsWith](xref:System.String.CompareTo(System.String)) 메서드는 전달된 문자열을 현재 문자열 개체의 끝에 있는 문자와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-182">The [String.EndsWith](xref:System.String.CompareTo(System.String)) method compares a passed string to the characters that exist at the end of the current string object.</span></span> <span data-ttu-id="4a4f9-183">역시 부울 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-183">It also returns a Boolean value.</span></span> <span data-ttu-id="4a4f9-184">다음 예제에서는 `EndsWith` 메서드를 사용하여 문자열의 끝을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-184">The following example checks the end of a string using the `EndsWith` method.</span></span>

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.EndsWith("Hello"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.EndsWith("Hello"))
```

<span data-ttu-id="4a4f9-185">이 예제에서는 콘솔에 `false`을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-185">This example displays `false` to the console.</span></span>

## <a name="indexof-and-lastindexof"></a><span data-ttu-id="4a4f9-186">IndexOf 및 LastIndexOf</span><span class="sxs-lookup"><span data-stu-id="4a4f9-186">IndexOf and LastIndexOf</span></span>

<span data-ttu-id="4a4f9-187">[String.IndexOf](xref:System.String.IndexOf(System.Char)) 메서드를 사용하여 문자열 내에서 특정 문자의 첫 번째 발생 위치를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-187">You can use the [String.IndexOf](xref:System.String.IndexOf(System.Char)) method to determine the position of the first occurrence of a particular character within a string.</span></span> <span data-ttu-id="4a4f9-188">이 대/소문자 구분 메서드는 문자열의 시작 부분에서 계산을 시작하고&0;부터 시작하는 인덱스를 사용하여 전달된 문자의 위치를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-188">This case-sensitive method starts counting from the beginning of a string and returns the position of a passed character using a zero-based index.</span></span> <span data-ttu-id="4a4f9-189">문자를 찾을 수 없는 경우 -1 값이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-189">If the character cannot be found, a value of –1 is returned.</span></span>

<span data-ttu-id="4a4f9-190">다음 예제에서는 `IndexOf` 메서드를 사용하여 문자열에서 '`l`' 문자의 첫 번째 발생을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-190">The following example uses the `IndexOf` method to search for the first occurrence of the '`l`' character in a string.</span></span>

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.IndexOf('l'));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.IndexOf("l"))
```

<span data-ttu-id="4a4f9-191">이 예제에서는 콘솔에 `2`을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-191">This example displays `2` to the console.</span></span>

<span data-ttu-id="4a4f9-192">[String.LastIndexOf](xref:System.String.LastIndexOf(System.Char)) 메서드는 문자열 내에서 특정 문자의 마지막 발생 위치를 반환한다는 점을 제외하고 `String.IndexOf` 메서드와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-192">The [String.LastIndexOf](xref:System.String.LastIndexOf(System.Char)) method is similar to the `String.IndexOf` method except that it returns the position of the last occurrence of a particular character within a string.</span></span> <span data-ttu-id="4a4f9-193">대/소문자를 구분하며&0;부터 시작하는 인덱스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-193">It is case-sensitive and uses a zero-based index.</span></span> 

<span data-ttu-id="4a4f9-194">다음 예제에서는 `LastIndexOf` 메서드를 사용하여 문자열에서 '`l`' 문자의 마지막 발생을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-194">The following example uses the `LastIndexOf` method to search for the last occurrence of the '`l`' character in a string.</span></span>

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.LastIndexOf('l'));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.LastIndexOf("l"))
```

<span data-ttu-id="4a4f9-195">이 예제에서는 콘솔에 `9`을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-195">This example displays `9` to the console.</span></span>

<span data-ttu-id="4a4f9-196">두 메서드는 모두 [String.Remove](xref:System.String.Remove(System.Int32)) 메서드와 함께 사용할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-196">Both methods are useful when used in conjunction with the [String.Remove](xref:System.String.Remove(System.Int32)) method.</span></span> <span data-ttu-id="4a4f9-197">문자 또는 해당 문자로 시작하는 단어를 제거하기 위해 `IndexOf` 또는 `LastIndexOf` 메서드 중 하나를 사용하여 문자의 위치를 검색한 다음 해당 위치를 `Remove method` 메서드에 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a4f9-197">You can use either the `IndexOf` or `LastIndexOf` methods to retrieve the position of a character, and then supply that position to the `Remove method` in order to remove a character or a word that begins with that character.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a4f9-198">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a4f9-198">See Also</span></span>

[<span data-ttu-id="4a4f9-199">기본적인 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="4a4f9-199">Basic string operations</span></span>](basic-string-operations.md)













