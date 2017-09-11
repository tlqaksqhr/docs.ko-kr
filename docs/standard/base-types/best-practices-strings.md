---
title: "문자열 사용에 대한 모범 사례"
description: "문자열 사용에 대한 모범 사례"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: b3cefaa4-0a3f-4a96-aba9-1de30fb07c29
ms.translationtype: Human Translation
ms.sourcegitcommit: b828bb1d6c8fb750ad9ef34f8a7a1b7d2574f4c6
ms.openlocfilehash: d5827f8b8ade216a365fd53f9d4547819188fe9b
ms.contentlocale: ko-kr
ms.lasthandoff: 11/15/2016

---

# <a name="best-practices-for-using-strings"></a><span data-ttu-id="e2144-104">문자열 사용에 대한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="e2144-104">Best practices for using strings</span></span>

<span data-ttu-id="e2144-105">.NET에서는 지역화된 응용 프로그램과 전역화된 응용 프로그램을 개발하기 위한 광범위한 지원을 제공하고 문자열 정렬 및 표시와 같은 일반적인 작업을 수행할 때 현재 문화권이나 특정 문화권의 규칙을 쉽게 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-105">.NET provides extensive support for developing localized and globalized applications, and makes it easy to apply the conventions of either the current culture or a specific culture when performing common operations such as sorting and displaying strings.</span></span> <span data-ttu-id="e2144-106">그러나 문자열 정렬 및 비교가 항상 문화권이 구분되는 작업은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-106">But sorting or comparing strings is not always a culture-sensitive operation.</span></span> <span data-ttu-id="e2144-107">예를 들어 응용 프로그램에서 내부적으로 사용되는 문자열은 대기 모든 문화권에서 동일하게 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-107">For example, strings that are used internally by an application typically should be handled identically across all cultures.</span></span> <span data-ttu-id="e2144-108">XML 태그, HTML 태그, 사용자 이름, 파일 경로 및 시스템 개체 이름과 같이 문화권을 구분하지 않는 문자열 데이터가 문화권이 구분되는 것처럼 해석되면 응용 프로그램 코드에는 감지하기 어려운 버그, 성능 저하 및 경우에 따라 보안 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-108">When culturally independent string data, such as XML tags, HTML tags, user names, file paths, and the names of system objects, are interpreted as if they were culture-sensitive, application code can be subject to subtle bugs, poor performance, and, in some cases, security issues.</span></span>

<span data-ttu-id="e2144-109">이 문서에서는 .NET의 문자열 정렬, 비교 및 대/소문자 구분 방법을 살펴보고, 적절한 문자열 처리 방법 선택을 위한 권장 사항을 제공하고, 문자열 처리 방법에 대한 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-109">This article examines the string sorting, comparison, and casing methods in .NET, presents recommendations for selecting an appropriate string-handling method, and provides additional information about string-handling methods.</span></span> <span data-ttu-id="e2144-110">또한 숫자 데이터 및 날짜/시간 데이터와 같은 형식이 지정된 데이터를 표시 및 저장을 위해 처리하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-110">It also examines how formatted data, such as numeric data and date and time data, is handled for display and for storage.</span></span> 

<span data-ttu-id="e2144-111">이 자료에는 다음과 같은 섹션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-111">This article contains the following sections:</span></span>

* [<span data-ttu-id="e2144-112">문자열 사용에 대한 권장 사항</span><span class="sxs-lookup"><span data-stu-id="e2144-112">Recommendations for string usage</span></span>](#recommendations-for-string-usage)

* [<span data-ttu-id="e2144-113">명시적으로 문자열 비교 지정</span><span class="sxs-lookup"><span data-stu-id="e2144-113">Specifying string comparisons explicitly</span></span>](#specifying-string-comparisons-explicitly)

* [<span data-ttu-id="e2144-114">문자열 비교 세부 정보</span><span class="sxs-lookup"><span data-stu-id="e2144-114">The details of string comparison</span></span>](#the-details-of-string-comparison)

* [<span data-ttu-id="e2144-115">메서드 호출을 위한 StringComparison 멤버 선택</span><span class="sxs-lookup"><span data-stu-id="e2144-115">Choosing a StringComparison member for your method call</span></span>](#choosing-a-stringcomparison-member-for-your-method-call)

* [<span data-ttu-id="e2144-116">일반적인 문자열 비교 방법</span><span class="sxs-lookup"><span data-stu-id="e2144-116">Common string comparison methods</span></span>](#common-string-comparison-methods)

* [<span data-ttu-id="e2144-117">문자열 비교를 간접적으로 수행하는 방법</span><span class="sxs-lookup"><span data-stu-id="e2144-117">Methods that perform string comparison indirectly</span></span>](#methods-that-perform-string-comparison-indirectly)

* [<span data-ttu-id="e2144-118">서식이 지정된 데이터 표시 및 유지</span><span class="sxs-lookup"><span data-stu-id="e2144-118">Displaying and persisting formatted data</span></span>](#displaying-and-persisting-formatted-data)

## <a name="recommendations-for-string-usage"></a><span data-ttu-id="e2144-119">문자열 사용에 대한 권장 사항</span><span class="sxs-lookup"><span data-stu-id="e2144-119">Recommendations for string usage</span></span>

<span data-ttu-id="e2144-120">.NET으로 개발하는 경우 문자열을 사용할 때 다음과 같은 간단한 권장 사항을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="e2144-120">When you develop with .NET, follow these simple recommendations when you use strings:</span></span> 

* <span data-ttu-id="e2144-121">문자열 작업에 대한 문자열 비교 규칙을 명시적으로 지정하는 오버로드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-121">Use overloads that explicitly specify the string comparison rules for string operations.</span></span> <span data-ttu-id="e2144-122">일반적으로 이 작업은 [StringComparison](xref:System.StringComparison) 형식 매개 변수가 포함된 메서드 오버로드를 호출하는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-122">Typically, this involves calling a method overload that has a parameter of type [StringComparison](xref:System.StringComparison).</span></span>

* <span data-ttu-id="e2144-123">문화권에 독립적인 문자열 일치를 위한 안전한 기본값으로 [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) 또는 [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase)를 비교에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-123">Use [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) or [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) for comparisons as your safe default for culture-agnostic string matching.</span></span>

* <span data-ttu-id="e2144-124">성능을 향상시키려면 [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) 또는 [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase)를 비교에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-124">Use comparisons with [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) or [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) for better performance.</span></span>

* <span data-ttu-id="e2144-125">사용자에게 출력을 표시하는 경우 [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture)를 기반으로 하는 문자열 작업을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-125">Use string operations that are based on [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture) when you display output to the user.</span></span>

* <span data-ttu-id="e2144-126">비교에 언어적 관련성이 없을 경우(예: 기호) [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture)를 기반으로 하는 문자열 작업 대신 비언어적인 [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) 또는 [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-126">Use the non-linguistic [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) or [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) values instead of string operations based on [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) when the comparison is linguistically irrelevant (symbolic, for example).</span></span>

* <span data-ttu-id="e2144-127">비교할 문자열을 정규화하는 경우 [String.ToLowerInvariant](xref:System.String.ToLowerInvariant) 메서드 대신 [String.ToUpperInvariant](xref:System.String.ToUpperInvariant) 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-127">Use the [String.ToUpperInvariant](xref:System.String.ToUpperInvariant) method instead of the [String.ToLowerInvariant](xref:System.String.ToLowerInvariant) method when you normalize strings for comparison.</span></span>

* <span data-ttu-id="e2144-128">[String](xref:System.String) `Equals` 메서드의 오버로드를 사용하여 두 문자열이 같은지를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-128">Use an overload of the [String](xref:System.String) `Equals` method to test whether two strings are equal.</span></span>

* <span data-ttu-id="e2144-129">[String](xref:System.String) `Compare` 및 [String.CompareTo](xref:System.String.CompareTo(System.String)) 메서드의 오버로드를 사용하여 문자열이 같은지 확인하지 않고 문자열을 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-129">Use an overload of the [String](xref:System.String) `Compare` and [String.CompareTo](xref:System.String.CompareTo(System.String)) methods to sort strings, not to check for equality.</span></span>

* <span data-ttu-id="e2144-130">문화권이 구분되는 형식 지정을 사용하여 사용자 인터페이스에서 숫자 및 날짜와 같이 문자열이 아닌 데이터를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-130">Use culture-sensitive formatting to display non-string data, such as numbers and dates, in a user interface.</span></span> <span data-ttu-id="e2144-131">고정 문화권과 함께 형식 지정을 사용하여 문자열 양식에서 문자열이 아닌 데이터를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-131">Use formatting with the invariant culture to persist non-string data in string form.</span></span>

<span data-ttu-id="e2144-132">문자열을 사용할 때 다음 사례를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="e2144-132">Avoid the following practices when you use strings:</span></span>

* <span data-ttu-id="e2144-133">문자열 작업에 대한 문자열 비교 규칙을 명시적 또는 암시적으로 지정하지 않는 오버로드를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="e2144-133">Do not use overloads that do not explicitly or implicitly specify the string comparison rules for string operations.</span></span> 

* <span data-ttu-id="e2144-134">두 문자열이 같은지를 확인하기 위해 [String](xref:System.String) `Compare` 또는 [String.CompareTo](xref:System.String.CompareTo(System.String)) 메서드의 오버로드 및 반환 값 0 테스트를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="e2144-134">Do not use an overload of the [String](xref:System.String) `Compare` or [String.CompareTo](xref:System.String.CompareTo(System.String)) methods and test for a return value of zero to determine whether two strings are equal.</span></span>

* <span data-ttu-id="e2144-135">문자열 양식에서 숫자 데이터나 날짜 및 시간 데이터를 유지하는 데 문화권이 구분되는 형식 지정을 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="e2144-135">Do not use culture-sensitive formatting to persist numeric data or date and time data in string form.</span></span>

## <a name="specifying-string-comparisons-explicitly"></a><span data-ttu-id="e2144-136">명시적으로 문자열 비교 지정</span><span class="sxs-lookup"><span data-stu-id="e2144-136">Specifying string comparisons explicitly</span></span>

<span data-ttu-id="e2144-137">.NET의 문자열 조작 메서드는 대부분 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-137">Most of the string manipulation methods in .NET are overloaded.</span></span> <span data-ttu-id="e2144-138">일반적으로 오버로드 하나 이상은 기본 설정을 그대로 사용하지만, 다른 오버로드는 기본값을 사용하지 않고 문자열을 비교 및 조작하는 정확한 방법을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-138">Typically, one or more overloads accept default settings, whereas others accept no defaults and instead define the precise way in which strings are to be compared or manipulated.</span></span> <span data-ttu-id="e2144-139">기본값을 사용하지 않는 메서드에는 대부분 문화권 및 사례별로 문자열 비교 규칙을 명시적으로 지정하는 열거형인 [StringComparison](xref:System.StringComparison) 형식의 매개 변수가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-139">Most of the methods that do not rely on defaults include a parameter of type [StringComparison](xref:System.StringComparison), which is an enumeration that explicitly specifies rules for string comparison by culture and case.</span></span> <span data-ttu-id="e2144-140">다음 표에서는 [StringComparison](xref:System.StringComparison) 열거형 멤버에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-140">The following table describes the [StringComparison](xref:System.StringComparison) enumeration members.</span></span> 

<span data-ttu-id="e2144-141">StringComparison 멤버</span><span class="sxs-lookup"><span data-stu-id="e2144-141">StringComparison member</span></span> | <span data-ttu-id="e2144-142">설명</span><span class="sxs-lookup"><span data-stu-id="e2144-142">Description</span></span>
----------------------- | -----------
[<span data-ttu-id="e2144-143">StringComparison.CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="e2144-143">StringComparison.CurrentCulture</span></span>](xref:System.StringComparison.CurrentCulture) | <span data-ttu-id="e2144-144">현재 문화권을 사용하여 대/소문자를 구분하는 비교를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-144">Performs a case-sensitive comparison using the current culture.</span></span>
[<span data-ttu-id="e2144-145">CurrentCultureIgnoreCase</span><span class="sxs-lookup"><span data-stu-id="e2144-145">CurrentCultureIgnoreCase</span></span>](xref:System.StringComparison.CurrentCultureIgnoreCase) | <span data-ttu-id="e2144-146">현재 문화권을 사용하여 대/소문자를 구분하지 않는 비교를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-146">Performs a case-insensitive comparison using the current culture.</span></span>
[<span data-ttu-id="e2144-147">StringComparison.Ordinal</span><span class="sxs-lookup"><span data-stu-id="e2144-147">StringComparison.Ordinal</span></span>](xref:System.StringComparison.Ordinal) | <span data-ttu-id="e2144-148">서수 비교를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-148">Performs an ordinal comparison.</span></span>
[<span data-ttu-id="e2144-149">StringComparison.OrdinalIgnoreCase</span><span class="sxs-lookup"><span data-stu-id="e2144-149">StringComparison.OrdinalIgnoreCase</span></span>](xref:System.StringComparison.OrdinalIgnoreCase) | <span data-ttu-id="e2144-150">대소문자를 구분하지 않는 서수 비교를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-150">Performs a case-insensitive ordinal comparison.</span></span>

<span data-ttu-id="e2144-151">예를 들어 문자 또는 문자열과 일치하는 [String](xref:System.String) 개체의 부분 문자열 인덱스를 반환하는 [String](xref:System.String) `IndexOf` 메서드에는 다음과 같은 오버로드 9개가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-151">For example, the [String](xref:System.String) `IndexOf` method, which returns the index of a substring in a [String](xref:System.String) object that matches either a character or a string, has nine overloads:</span></span>

* <span data-ttu-id="e2144-152">[IndexOf(Char)](xref:System.String.IndexOf(System.Char)), [IndexOf(Char, Int32)](xref:System.String.IndexOf(System.Char,System.Int32)) 및 [IndexOf(Char, Int32, Int32)](xref:System.String.IndexOf(System.Char,System.Int32,System.Int32)) - 기본적으로 문자열에서 문자에 대한 서수 검색(대/소문자 구분 및 문화권을 구분하지 않음)을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-152">[IndexOf(Char)](xref:System.String.IndexOf(System.Char)), [IndexOf(Char, Int32)](xref:System.String.IndexOf(System.Char,System.Int32)), and [IndexOf(Char, Int32, Int32)](xref:System.String.IndexOf(System.Char,System.Int32,System.Int32)), which by default perform an ordinal (case-sensitive and culture-insensitive) search for a character in the string.</span></span>

* <span data-ttu-id="e2144-153">[IndexOf(String)](xref:System.String.IndexOf(System.String)), [IndexOf(String, Int32)](xref:System.String.IndexOf(System.String,System.Int32)) 및 [IndexOf(String, Int32, Int32)](xref:System.String.IndexOf(System.String,System.Int32,System.Int32)) - 기본적으로 문자열에서 부분 문자열에 대한 대/소문자 구분 및 문화권 구분 검색을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-153">[IndexOf(String)](xref:System.String.IndexOf(System.String)), [IndexOf(String, Int32)](xref:System.String.IndexOf(System.String,System.Int32)), and [IndexOf(String, Int32, Int32)](xref:System.String.IndexOf(System.String,System.Int32,System.Int32)), which by default perform a case-sensitive and culture-sensitive search for a substring in the string.</span></span>

* <span data-ttu-id="e2144-154">[IndexOf(String, StringComparison)](xref:System.String.IndexOf(System.String,System.StringComparison)), [IndexOf(String, Int32, StringComparison)](xref:System.String.IndexOf(System.String,System.Int32,System.StringComparison)) 및 [IndexOf(String, Int32, Int32, StringComparison)](xref:System.String.IndexOf(System.String,System.Int32,System.Int32,System.StringComparison)) - 비교 형식을 지정할 수 있는 StringComparison 형식의 매개 변수를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-154">[IndexOf(String, StringComparison)](xref:System.String.IndexOf(System.String,System.StringComparison)), [IndexOf(String, Int32, StringComparison)](xref:System.String.IndexOf(System.String,System.Int32,System.StringComparison)), and [IndexOf(String, Int32, Int32, StringComparison)](xref:System.String.IndexOf(System.String,System.Int32,System.Int32,System.StringComparison)), which include a parameter of type StringComparison that allows the form of the comparison to be specified.</span></span>

<span data-ttu-id="e2144-155">다음 이유로 기본값을 사용하지 않는 오버로드를 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-155">We recommend that you select an overload that does not use default values, for the following reasons:</span></span>

* <span data-ttu-id="e2144-156">기본 매개 변수가 있는 일부 오버로드(문자열 인스턴스에서 [Char](xref:System.Char)를 검색하는 오버로드)는 서수 비교를 수행하지만, 다른 오버로드(문자열 인스턴스에서 문자열을 검색하는 오버로드)는 문화권이 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-156">Some overloads with default parameters (those that search for a [Char](xref:System.Char) in the string instance) perform an ordinal comparison, whereas others (those that search for a string in the string instance) are culture-sensitive.</span></span> <span data-ttu-id="e2144-157">어떤 메서드가 어떤 기본값을 사용하는지 기억하기 어렵고 오버로드를 혼동하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-157">It is difficult to remember which method uses which default value, and easy to confuse the overloads.</span></span>

* <span data-ttu-id="e2144-158">메서드 호출에 대해 기본값을 사용하는 코드의 의도는 분명하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-158">The intent of the code that relies on default values for method calls is not clear.</span></span> <span data-ttu-id="e2144-159">기본값을 사용하는 다음 예제에서는 개발자가 실제로 두 문자열의 서수 또는 언어 비교를 의도했는지 또는 `protocol`과 "http" 간의 대/소문자 차이로 인해 같음 테스트에서 `false`가 반환될 수 있는지를 잘 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-159">In the following example, which relies on defaults, it is difficult to know whether the developer actually intended an ordinal or a linguistic comparison of two strings, or whether a case difference between `protocol` and "http" might cause the test for equality to return `false`.</span></span>

```csharp
string protocol = GetProtocol(url);       
if (String.Equals(protocol, "http", StringComparison.OrdinalIgnoreCase)) {
   // ...Code to handle HTTP protocol.
}
else {
   throw new InvalidOperationException();
}
```

```vb
Dim protocol As String = GetProtocol(url)       
If String.Equals(protocol, "http") Then
  ' ...Code to handle HTTP protocol.
Else
   Throw New InvalidOperationException()
End If
```

<span data-ttu-id="e2144-160">일반적으로 기본값을 사용하지 않는 메서드를 사용하면 코드의 의도가 분명해지므로 이 메서드를 호출하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-160">In general, we recommend that you call a method that does not rely on defaults, because it makes the intent of the code unambiguous.</span></span> <span data-ttu-id="e2144-161">이 메서드를 사용하면 코드를 더 쉽게 읽을 수 있고 더 쉽게 디버그 및 유지 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-161">This, in turn, makes the code more readable and easier to debug and maintain.</span></span> <span data-ttu-id="e2144-162">다음 예제에서는 이전 예제와 관련된 질문을 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-162">The following example addresses the questions raised about the previous example.</span></span> <span data-ttu-id="e2144-163">예제에서는 서수 비교가 사용되고 대/소문자 차이가 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-163">It makes it clear that ordinal comparison is used and that differences in case are ignored.</span></span> 

```csharp
string protocol = GetProtocol(url);       
if (String.Equals(protocol, "http", StringComparison.OrdinalIgnoreCase)) {
   // ...Code to handle HTTP protocol.
}
else {
   throw new InvalidOperationException();
}
```

```vb
Dim protocol As String = GetProtocol(url)       
If String.Equals(protocol, "http", StringComparison.OrdinalIgnoreCase) Then
   ' ...Code to handle HTTP protocol.
Else
   Throw New InvalidOperationException()
End If
```

## <a name="the-details-of-string-comparison"></a><span data-ttu-id="e2144-164">문자열 비교 세부 정보</span><span class="sxs-lookup"><span data-stu-id="e2144-164">The details of string comparison</span></span>

<span data-ttu-id="e2144-165">문자열 비교는 특히 정렬 및 같음 테스트와 같은 다양한 문자열 관련 작업의 핵심입니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-165">String comparison is the heart of many string-related operations, particularly sorting and testing for equality.</span></span> <span data-ttu-id="e2144-166">결정된 순서의 문자열 정렬: 정렬된 문자열 목록에서 "my"가 "string" 앞에 나타나면 "my"가 "string"과 같거나 작은지 비교해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-166">Strings sort in a determined order: If "my" appears before "string" in a sorted list of strings, "my" must compare less than or equal to "string".</span></span> <span data-ttu-id="e2144-167">또한 비교는 암시적으로 같음을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-167">Additionally, comparison implicitly defines equality.</span></span> <span data-ttu-id="e2144-168">비교 작업은 같은 것으로 판단되는 문자열에 대해 0을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-168">The comparison operation returns zero for strings it deems equal.</span></span> <span data-ttu-id="e2144-169">다른 문자열보다 작은 문자열이 없다고 해석하는 것이 적절합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-169">A good interpretation is that neither string is less than the other.</span></span> <span data-ttu-id="e2144-170">문자열과 관련된 대부분 의미 있는 작업에는 다른 문자열과 비교 및 잘 정의된 정렬 작업 실행이라는 두 가지 절차가 둘 다 또는 두 가지 중 하나가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-170">Most meaningful operations involving strings include one or both of these procedures: comparing with another string, and executing a well-defined sort operation.</span></span>

<span data-ttu-id="e2144-171">그러나 두 문자열의 같음 또는 정렬 순서를 평가할 때 하나의 올바른 결과가 생성되지는 않습니다. 결과는 문자열 비교에 사용되는 기준에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-171">However, evaluating two strings for equality or sort order does not yield a single, correct result; the outcome depends on the criteria used to compare the strings.</span></span> <span data-ttu-id="e2144-172">특히 서수 문자열 비교나 현재 문화권이나 고정 문화권(영어를 기준으로 로캘을 구분하지 않는 문화권)의 대/소문자 구분 및 정렬 규칙을 기준으로 한 문자열 비교에서는 다른 결과가 생성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-172">In particular, string comparisons that are ordinal or that are based on the casing and sorting conventions of the current culture or the invariant culture (a locale-agnostic culture based on the English language) may produce different results.</span></span>

### <a name="string-comparisons-that-use-the-current-culture"></a><span data-ttu-id="e2144-173">현재 문화권을 사용하는 문자열 비교</span><span class="sxs-lookup"><span data-stu-id="e2144-173">String comparisons that use the current culture</span></span>

<span data-ttu-id="e2144-174">문자열 비교 시 현재 문화권의 규칙을 사용하는 한 가기 기준이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-174">One criterion involves using the conventions of the current culture when comparing strings.</span></span> <span data-ttu-id="e2144-175">현재 문화권을 기준으로 한 비교에는 스레드의 현재 문화권 또는 로캘이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-175">Comparisons that are based on the current culture use the thread's current culture or locale.</span></span> <span data-ttu-id="e2144-176">데이터가 언어적으로 관련되는 경우와 문화권이 구분되는 사용자 조작을 반영하는 경우에는 항상 현재 문화권을 기준으로 한 비교를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-176">You should always use comparisons that are based on the current culture when data is linguistically relevant, and when it reflects culture-sensitive user interaction.</span></span> 

<span data-ttu-id="e2144-177">그러나 문화권이 변경되면 .NET의 비교 및 대/소문자 지정 동작도 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-177">However, comparison and casing behavior in .NET changes when the culture changes.</span></span> <span data-ttu-id="e2144-178">응용 프로그램이 개발된 컴퓨터와 다른 문화권을 포함하는 컴퓨터에서 응용 프로그램을 실행하거나 실행 스레드가 문화권을 변경할 경우 이 동작이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-178">This happens when an application executes on a computer that has a different culture than the computer on which the application was developed, or when the executing thread changes its culture.</span></span> <span data-ttu-id="e2144-179">이 동작은 의도적이지만 대부분 개발자가 이해하기가 분명하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-179">This behavior is intentional, but it remains non-obvious to many developers.</span></span> <span data-ttu-id="e2144-180">다음 예제에서는 미국 영어("en-US") 및 스웨덴어("sv-SE") 문화권의 정렬 순서 차이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-180">The following example illustrates differences in sort order between the U.S. English ("en-US") and Swedish ("sv-SE") cultures.</span></span> <span data-ttu-id="e2144-181">정렬된 문자열 배열에서 단어 "ångström", "Windows" 및 "Visual Studio"가 다른 위치에 나타남을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-181">Note that the words "ångström", "Windows", and "Visual Studio" appear in different positions in the sorted string arrays.</span></span>

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string[] values= { "able", "ångström", "apple", "Æble", 
                         "Windows", "Visual Studio" };
      Array.Sort(values);
      DisplayArray(values);

      // Change culture to Swedish (Sweden).
      string originalCulture = CultureInfo.CurrentCulture.Name;
      Thread.CurrentThread.CurrentCulture = new CultureInfo("sv-SE");
      Array.Sort(values);
      DisplayArray(values);

      // Restore the original culture.
      Thread.CurrentThread.CurrentCulture = new CultureInfo(originalCulture);
    }

    private static void DisplayArray(string[] values)
    {
      Console.WriteLine("Sorting using the {0} culture:",  
                        CultureInfo.CurrentCulture.Name);
      foreach (string value in values)
         Console.WriteLine("   {0}", value);

      Console.WriteLine();
    }
}
// The example displays the following output:
//       Sorting using the en-US culture:
//          able
//          Æble
//          ångström
//          apple
//          Visual Studio
//          Windows
//       
//       Sorting using the sv-SE culture:
//          able
//          Æble
//          apple
//          Windows
//          Visual Studio
//          ångström
```

```vb
Imports System.Globalization
Imports System.Threading

Module Example
   Public Sub Main()
      Dim values() As String = { "able", "ångström", "apple", _
                                 "Æble", "Windows", "Visual Studio" }
      Array.Sort(values)
      DisplayArray(values)

      ' Change culture to Swedish (Sweden).
      Dim originalCulture As String = CultureInfo.CurrentCulture.Name
      Thread.CurrentThread.CurrentCulture = New CultureInfo("sv-SE")
      Array.Sort(values)
      DisplayArray(values)

      ' Restore the original culture.
      Thread.CurrentThread.CurrentCulture = New CultureInfo(originalCulture)
    End Sub

    Private Sub DisplayArray(values() As String)
      Console.WRiteLine("Sorting using the {0} culture:", _ 
                        CultureInfo.CurrentCulture.Name)
      For Each value As String In values
         Console.WriteLine("   {0}", value)
      Next
      Console.WriteLine()   
    End Sub
End Module
' The example displays the following output:
'       Sorting using the en-US culture:
'          able
'          Æble
'          ångström
'          apple
'          Visual Studio
'          Windows
'       
'       Sorting using the sv-SE culture:
'          able
'          Æble
'          apple
'          Windows
'          Visual Studio
'          ångström
```

<span data-ttu-id="e2144-182">현재 문화권을 사용하는 대/소문자를 구분하지 않는 비교는 스레드의 현재 문화권에 지정된 대/소문자를 무시한다는 점을 제외하고 문화권 구분 비교와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-182">Case-insensitive comparisons that use the current culture are the same as culture-sensitive comparisons, except that they ignore case as dictated by the thread's current culture.</span></span> <span data-ttu-id="e2144-183">이 동작은 정렬 순서에서도 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-183">This behavior may manifest itself in sort orders as well.</span></span> 

<span data-ttu-id="e2144-184">현재 문화권 의미 체계를 사용하는 비교는 다음 메서드의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-184">Comparisons that use current culture semantics are the default for the following methods:</span></span>

* <span data-ttu-id="e2144-185">[StringComparison](xref:System.StringComparison) 매개 변수를 포함하지 않는 [String](xref:System.String) `Compare` 오버로드</span><span class="sxs-lookup"><span data-stu-id="e2144-185">[String](xref:System.String) `Compare` overloads that do not include a [StringComparison](xref:System.StringComparison) parameter.</span></span>

* <span data-ttu-id="e2144-186">[String.CompareTo](xref:System.String.CompareTo(System.String)) 오버로드</span><span class="sxs-lookup"><span data-stu-id="e2144-186">[String.CompareTo](xref:System.String.CompareTo(System.String)) overloads.</span></span>

* <span data-ttu-id="e2144-187">기본 [String.StartsWith(String)](xref:System.String.StartsWith(System.String)) 메서드</span><span class="sxs-lookup"><span data-stu-id="e2144-187">The default [String.StartsWith(String)](xref:System.String.StartsWith(System.String)) method.</span></span> 

* <span data-ttu-id="e2144-188">기본 [String.EndsWith(String)](xref:System.String.EndsWith(System.String)) 메서드</span><span class="sxs-lookup"><span data-stu-id="e2144-188">The default [String.EndsWith(String)](xref:System.String.EndsWith(System.String)) method.</span></span>

* <span data-ttu-id="e2144-189">[String](xref:System.String)을 검색 매개 변수로 사용하고 [StringComparison](xref:System.StringComparison) 매개 변수를 포함하지 않는 [String](xref:System.String) `IndexOf` 오버로드</span><span class="sxs-lookup"><span data-stu-id="e2144-189">[String](xref:System.String) `IndexOf` overloads that accept a [String](xref:System.String) as a search parameter and that do not have a [StringComparison](xref:System.StringComparison) parameter.</span></span>

* <span data-ttu-id="e2144-190">[String](xref:System.String)을 검색 매개 변수로 사용하고 [StringComparison](xref:System.StringComparison) 매개 변수를 포함하지 않는 [String](xref:System.String) `LastIndexOf` 오버로드</span><span class="sxs-lookup"><span data-stu-id="e2144-190">[String](xref:System.String) `LastIndexOf` overloads that accept a [String](xref:System.String) as a search parameter and that do not have a [StringComparison](xref:System.StringComparison) parameter.</span></span>

<span data-ttu-id="e2144-191">어떤 경우든지 메서드 호출의 의도가 분명하게 나타나도록 [StringComparison](xref:System.StringComparison) 매개 변수가 있는 오버로드를 호출하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-191">In any case, we recommend that you call an overload that has a [StringComparison](xref:System.StringComparison) parameter to make the intent of the method call clear.</span></span> 

<span data-ttu-id="e2144-192">비언어적인 문자열 데이터가 언어적으로 해석되거나 특정 문화권의 문자열 데이터가 다른 문화권의 규칙을 통해 해석되면 감지하기 어려운 버그와 감지할 수 있는 버그가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-192">Subtle and not so subtle bugs can emerge when non-linguistic string data is interpreted linguistically, or when string data from a particular culture is interpreted using the conventions of another culture.</span></span> <span data-ttu-id="e2144-193">대표적인 예는 Turkish-I 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-193">The canonical example is the Turkish-I problem.</span></span>

<span data-ttu-id="e2144-194">미국 영어를 포함한 거의 모든 라틴어 알파벳에서 문자 "i"(\u0069)는 문자 "I"(\u0049)의 소문자 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-194">For nearly all Latin alphabets, including U.S. English, the character "i" (\u0069) is the lowercase version of the character "I" (\u0049).</span></span> <span data-ttu-id="e2144-195">이 대/소문자 구분 규칙은 해당 문화권에서 프로그래밍하는 사용자에게 빠르게 기본 규칙이 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-195">This casing rule quickly becomes the default for someone programming in such a culture.</span></span> <span data-ttu-id="e2144-196">그러나 터키어("tr-TR") 알파벳에는 "i"의 대문자 버전인 "점이 있는 I" 문자 "İ"(\u0130)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-196">However, the Turkish ("tr-TR") alphabet includes an "I with a dot" character "İ" (\u0130), which is the capital version of "i".</span></span> <span data-ttu-id="e2144-197">터키어에는 대문자 버전이 "I"인 "점이 없는 i" 문자 , "ı"(\u0131)도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-197">Turkish also includes a lowercase "i without a dot" character, "ı" (\u0131), which capitalizes to "I".</span></span> <span data-ttu-id="e2144-198">이 동작은 아제르바이잔어("az") 문화권에서도 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-198">This behavior occurs in the Azerbaijani ("az") culture as well.</span></span>

<span data-ttu-id="e2144-199">따라서 "i"를 대문자로 변환하거나 "I"를 소문자로 변환하는 방법에 대한 가정이 모든 문화권에서 유효한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-199">Therefore, assumptions made about capitalizing "i" or lowercasing "I" are not valid among all cultures.</span></span> <span data-ttu-id="e2144-200">문자열 비교 루틴에 대해 기본 오버로드를 사용하면 이 오버로드에는 문화권 간의 차이가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-200">If you use the default overloads for string comparison routines, they will be subject to variance between cultures.</span></span> <span data-ttu-id="e2144-201">문자열 "file" 및 "FILE"의 대/소문자를 구분하지 않는 비교를 수행하는 다음 시도와 같이, 비교할 데이터가 비언어적일 경우 기본 오버로드를 사용하면 원하지 않는 결과가 생성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-201">If the data to be compared is non-linguistic, using the default overloads can produce undesirable results, as the following attempt to perform a case-insensitive comparison of the strings "file" and "FILE" illustrates.</span></span>

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string fileUrl = "file";
      Thread.CurrentThread.CurrentCulture = new CultureInfo("en-US");
      Console.WriteLine("Culture = {0}",
                        Thread.CurrentThread.CurrentCulture.DisplayName);
      Console.WriteLine("(file == FILE) = {0}", 
                       fileUrl.StartsWith("FILE", true, null));
      Console.WriteLine();

      Thread.CurrentThread.CurrentCulture = new CultureInfo("tr-TR");
      Console.WriteLine("Culture = {0}",
                        Thread.CurrentThread.CurrentCulture.DisplayName);
      Console.WriteLine("(file == FILE) = {0}", 
                        fileUrl.StartsWith("FILE", true, null));
   }
}
// The example displays the following output:
//       Culture = English (United States)
//       (file == FILE) = True
//       
//       Culture = Turkish (Turkey)
//       (file == FILE) = False
```

```vb
Imports System.Globalization
Imports System.Threading

Module Example
   Public Sub Main()
      Dim fileUrl = "file"
      Thread.CurrentThread.CurrentCulture = New CultureInfo("en-US")
      Console.WriteLine("Culture = {0}", _
                        Thread.CurrentThread.CurrentCulture.DisplayName)
      Console.WriteLine("(file == FILE) = {0}", _ 
                       fileUrl.StartsWith("FILE", True, Nothing))
      Console.WriteLine()

      Thread.CurrentThread.CurrentCulture = New CultureInfo("tr-TR")
      Console.WriteLine("Culture = {0}", _
                        Thread.CurrentThread.CurrentCulture.DisplayName)
      Console.WriteLine("(file == FILE) = {0}", _ 
                        fileUrl.StartsWith("FILE", True, Nothing))
   End Sub
End Module
' The example displays the following output:
'       Culture = English (United States)
'       (file == FILE) = True
'       
'       Culture = Turkish (Turkey)
'       (file == FILE) = False
```

<span data-ttu-id="e2144-202">다음 예제와 같이 보안 관련 설정에서 문화권이 의도치 않게 사용되면 이 비교로 인해 큰 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-202">This comparison could cause significant problems if the culture is inadvertently used in security-sensitive settings, as in the following example.</span></span> <span data-ttu-id="e2144-203">`IsFileURI("file:")`와 같은 메서드 호출은 현재 문화권이 미국 영어이면 `true`를 반환하지만 현재 문화권이 터키어이면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-203">A method call such as `IsFileURI("file:")` returns `true` if the current culture is U.S. English, but `false` if the current culture is Turkish.</span></span> <span data-ttu-id="e2144-204">따라서 터키어 시스템에서는 누군가 "FILE:"으로 시작하는 대/소문자를 구분하지 않는 URI에 대한 액세스를 차단하는 보안 조치를 회피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-204">Thus, on Turkish systems, someone could circumvent security measures that block access to case-insensitive URIs that begin with "FILE:".</span></span>

```csharp
public static bool IsFileURI(String path) 
{
   return path.StartsWith("FILE:", true, null);
}
```

```vb
Public Shared Function IsFileURI(path As String) As Boolean 
   Return path.StartsWith("FILE:", True, Nothing)
End Function
```

<span data-ttu-id="e2144-205">이 경우 "file:"은 비언어적, 문화권을 구분하지 않는 식별자로 해석되므로 코드를 다음 예제와 같이 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-205">In this case, because "file:" is meant to be interpreted as a non-linguistic, culture-insensitive identifier, the code should instead be written as shown in the following example.</span></span>

```csharp
public static bool IsFileURI(string path) 
{
   return path.StartsWith("FILE:", StringComparison.OrdinalIgnoreCase);
}
```

```vb
Public Shared Function IsFileURI(path As String) As Boolean 
    Return path.StartsWith("FILE:", StringComparison.OrdinalIgnoreCase)
End Function
```

## <a name="ordinal-string-operations"></a><span data-ttu-id="e2144-206">서수 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="e2144-206">Ordinal String Operations</span></span>

<span data-ttu-id="e2144-207">메서드 호출에서 [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) 또는 [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) 값을 지정하는 것은 자연어의 특징이 무시되는 비언어적인 비교를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-207">Specifying the [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) or [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) value in a method call signifies a non-linguistic comparison in which the features of natural languages are ignored.</span></span> <span data-ttu-id="e2144-208">이러한 [StringComparison](xref:System.StringComparison) 값을 사용하여 호출되는 메서드는 문화권별로 매개 변수화되는 대/소문자 구분 또는 동일성 테이블이 아닌 단순 바이트 비교를 기반으로 하여 문자열 작업을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-208">Methods that are invoked with these [StringComparison](xref:System.StringComparison) values base string operation decisions on simple byte comparisons instead of casing or equivalence tables that are parameterized by culture.</span></span> <span data-ttu-id="e2144-209">대부분 경우에 이 접근 방법은 의도된 문자열 해석에 가장 적합하지만 코드를 더 빠르고 더 안정적으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-209">In most cases, this approach best fits the intended interpretation of strings while making code faster and more reliable.</span></span> 

<span data-ttu-id="e2144-210">서수 비교는 언어적 해석 없이 각 문자열의 각 바이트가 비교되는 문자열 비교입니다. 예를 들어 "windows"는 "Windows"와 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-210">Ordinal comparisons are string comparisons in which each byte of each string is compared without linguistic interpretation; for example, "windows" does not match "Windows".</span></span> <span data-ttu-id="e2144-211">컨텍스트가 문자열이 정확히 일치해야 함을 나타내거나 보수적인 일치 정책을 요구할 경우 이 비교를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-211">Use this comparison when the context dictates that strings should be matched exactly or demands conservative matching policy.</span></span> <span data-ttu-id="e2144-212">또한 서수 비교는 결과를 결정할 때 언어 규칙을 적용하지 않으므로 가장 빠른 비교 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-212">Additionally, ordinal comparison is the fastest comparison operation because it applies no linguistic rules when determining a result.</span></span>

<span data-ttu-id="e2144-213">.NET의 문자열에는 포함된 null 문자가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-213">Strings in .NET can contain embedded null characters.</span></span> <span data-ttu-id="e2144-214">서수 비교와 문화권 구분 비교(고정 문화권을 사용하는 비교 포함) 간 가장 분명한 차이의 하나는 문자열의 포함된 null 문자 처리와 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-214">One of the clearest differences between ordinal and culture-sensitive comparison (including comparisons that use the invariant culture) concerns the handling of embedded null characters in a string.</span></span> <span data-ttu-id="e2144-215">[String](xref:System.String) `Compare` 및 [String](xref:System.String) `Equals` 메서드를 사용하여 문화권 구분 비교(고정 문화권을 사용하는 비교 포함)를 수행하는 경우에는 이러한 문자가 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-215">These characters are ignored when you use the [String](xref:System.String) `Compare` and [String](xref:System.String) `Equals` methods to perform culture-sensitive comparisons (including comparisons that use the invariant culture).</span></span> <span data-ttu-id="e2144-216">따라서 문화권 구분 비교에서 포함된 null 문자가 들어 있는 문자열은 해당 문자가 들어 있지 않은 문자열과 같은 것으로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-216">As a result, in culture-sensitive comparisons, strings that contain embedded null characters can be considered equal to strings that do not.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="e2144-217">문자열 비교 메서드는 포함된 null 문자를 무시하지만 [String.Contains](xref:System.String.Contains(System.String)), [String.EndsWith](xref:System.String.EndsWith(System.String)), [String.IndexOf](xref:System.String.IndexOf(System.Char)), [String.LastIndexOf](xref:System.String.LastIndexOf(System.String)) 및 [String.StartsWith](xref:System.String.StartsWith(System.String))와 같은 문자열 검색 메서드는 무시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-217">Although string comparison methods disregard embedded null characters, string search methods such as [String.Contains](xref:System.String.Contains(System.String)), [String.EndsWith](xref:System.String.EndsWith(System.String)), [String.IndexOf](xref:System.String.IndexOf(System.Char)), [String.LastIndexOf](xref:System.String.LastIndexOf(System.String)), and [String.StartsWith](xref:System.String.StartsWith(System.String)) do not.</span></span> 

<span data-ttu-id="e2144-218">다음 예제에서는 문자열 "Aa" 및 "A"와 "a" 사이에 여러 포함된 null 문자를 포함하는 비슷한 문자열의 문화권 구분 비교를 수행하고 두 문자열을 어떻게 같은 것으로 간주하는지 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-218">The following example performs a culture-sensitive comparison of the string "Aa" with a similar string that contains several embedded null characters between "A" and "a", and shows how the two strings are considered equal.</span></span> 

```csharp
using System;

public class Example
{
   public static void Main()
   {
      string str1 = "Aa";
      string str2 = "A" + new String('\u0000', 3) + "a";
      Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", 
                        str1, ShowBytes(str1), str2, ShowBytes(str2));
      Console.WriteLine("   With String.Compare:");
      Console.WriteLine("      Current Culture: {0}", 
                        String.Compare(str1, str2, StringComparison.CurrentCulture));
      Console.WriteLine("      Invariant Culture: {0}", 
                        String.Compare(str1, str2, StringComparison.InvariantCulture));

      Console.WriteLine("   With String.Equals:");
      Console.WriteLine("      Current Culture: {0}", 
                        String.Equals(str1, str2, StringComparison.CurrentCulture));
      Console.WriteLine("      Invariant Culture: {0}", 
                        String.Equals(str1, str2, StringComparison.InvariantCulture));
   }

   private static string ShowBytes(string str)
   {
      string hexString = String.Empty;
      for (int ctr = 0; ctr < str.Length; ctr++)
      {
         string result = String.Empty;
         result = Convert.ToInt32(str[ctr]).ToString("X4");
         result = " " + result.Substring(0,2) + " " + result.Substring(2, 2);
         hexString += result;
      }
      return hexString.Trim();
   }
}
// The example displays the following output:
//    Comparing 'Aa' (00 41 00 61) and 'A   a' (00 41 00 00 00 00 00 00 00 61):
//       With String.Compare:
//          Current Culture: 0
//          Invariant Culture: 0
//       With String.Equals:
//          Current Culture: True
//          Invariant Culture: True
```

```vb
Module Example
   Public Sub Main()
      Dim str1 As String = "Aa"
      Dim str2 As String = "A" + New String(Convert.ToChar(0), 3) + "a"
      Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", _
                        str1, ShowBytes(str1), str2, ShowBytes(str2))
      Console.WriteLine("   With String.Compare:")
      Console.WriteLine("      Current Culture: {0}", _
                        String.Compare(str1, str2, StringComparison.CurrentCulture))
      Console.WriteLine("      Invariant Culture: {0}", _
                        String.Compare(str1, str2, StringComparison.InvariantCulture))

      Console.WriteLine("   With String.Equals:")
      Console.WriteLine("      Current Culture: {0}", _
                        String.Equals(str1, str2, StringComparison.CurrentCulture))
      Console.WriteLine("      Invariant Culture: {0}", _
                        String.Equals(str1, str2, StringComparison.InvariantCulture))
   End Sub

   Private Function ShowBytes(str As String) As String
      Dim hexString As String = String.Empty
      For ctr As Integer = 0 To str.Length - 1
         Dim result As String = String.Empty
         result = Convert.ToInt32(str.Chars(ctr)).ToString("X4")
         result = " " + result.Substring(0,2) + " " + result.Substring(2, 2)
         hexString += result
      Next
      Return hexString.Trim()
   End Function
End Module
```

<span data-ttu-id="e2144-219">그러나 다음 예제와 같이 서수 비교를 사용할 경우 문자열을 같은 것으로 간주하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-219">However, the strings are not considered equal when you use ordinal comparison, as the following example shows.</span></span>

```csharp
Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", 
                  str1, ShowBytes(str1), str2, ShowBytes(str2));
Console.WriteLine("   With String.Compare:");
Console.WriteLine("      Ordinal: {0}", 
                  String.Compare(str1, str2, StringComparison.Ordinal));

Console.WriteLine("   With String.Equals:");
Console.WriteLine("      Ordinal: {0}", 
                  String.Equals(str1, str2, StringComparison.Ordinal));
// The example displays the following output:
//    Comparing 'Aa' (00 41 00 61) and 'A   a' (00 41 00 00 00 00 00 00 00 61):
//       With String.Compare:
//          Ordinal: 97
//       With String.Equals:
//          Ordinal: False
```

```vb
Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", _
                  str1, ShowBytes(str1), str2, ShowBytes(str2))
Console.WriteLine("   With String.Compare:")
Console.WriteLine("      Ordinal: {0}", _
                  String.Compare(str1, str2, StringComparison.Ordinal))

Console.WriteLine("   With String.Equals:")
Console.WriteLine("      Ordinal: {0}", _
                  String.Equals(str1, str2, StringComparison.Ordinal))
' The example displays the following output:
'    Comparing 'Aa' (00 41 00 61) and 'A   a' (00 41 00 00 00 00 00 00 00 61):
'       With String.Compare:
'          Ordinal: 97
'       With String.Equals:
'          Ordinal: False
```

<span data-ttu-id="e2144-220">대/소문자를 구분하지 않는 서수 비교는 다음으로 가장 보수적인 접근 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-220">Case-insensitive ordinal comparisons are the next most conservative approach.</span></span> <span data-ttu-id="e2144-221">이들 비교는 대부분 대/소문자 구분을 무시합니다. 예를 들어 "windows"는 "Windows"와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-221">These comparisons ignore most casing; for example, "windows" matches "Windows".</span></span> <span data-ttu-id="e2144-222">ASCII 문자를 처리할 때 이 정책은 사용 가능한 ASCII 대/소문자 구분을 무시한다는 점을 제외하고 [StringComparison.Ordinal](xref:System.StringComparison.Ordinal)과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-222">When dealing with ASCII characters, this policy is equivalent to [StringComparison.Ordinal](xref:System.StringComparison.Ordinal), except that it ignores the usual ASCII casing.</span></span> <span data-ttu-id="e2144-223">따라서 [A, Z](\u0041-\u005A)의 모든 문자는 [a,z](\u0061-\007A)의 해당 문자와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-223">Therefore, any character in [A, Z] (\u0041-\u005A) matches the corresponding character in [a,z] (\u0061-\007A).</span></span> <span data-ttu-id="e2144-224">ASCII 범위를 벗어난 대/소문자 구분에는 고정 문화권 테이블이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-224">Casing outside the ASCII range uses the invariant culture's tables.</span></span> <span data-ttu-id="e2144-225">따라서 다음 비교는</span><span class="sxs-lookup"><span data-stu-id="e2144-225">Therefore, the following comparison:</span></span>

```csharp
String.Compare(strA, strB, StringComparison.OrdinalIgnoreCase);
```

```vb
String.Compare(strA, strB, StringComparison.OrdinalIgnoreCase)
```

<span data-ttu-id="e2144-226">다음 비교와 같지만 더 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-226">is equivalent to (but faster than) this comparison:</span></span> 

```csharp
String.Compare(strA.ToUpperInvariant(), strB.ToUpperInvariant(), 
               StringComparison.Ordinal);
```

```vb
String.Compare(strA.ToUpperInvariant(), strB.ToUpperInvariant(), 
               StringComparison.Ordinal)
```

<span data-ttu-id="e2144-227">이들 비교는 매우 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-227">These comparisons are still very fast.</span></span>

<span data-ttu-id="e2144-228">[StringComparison.Ordinal](xref:System.StringComparison.Ordinal)과 [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase)는 둘 다 이진 값을 직접 사용하며 일치에 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-228">Both [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) and [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) use the binary values directly, and are best suited for matching.</span></span> <span data-ttu-id="e2144-229">사용 중인 비교 설정을 확신할 수 없으면 다음 두 값의 하나를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="e2144-229">When you are not sure about your comparison settings, use one of these two values.</span></span> <span data-ttu-id="e2144-230">그러나 이들 값은 바이트 단위 비교를 수행하므로 영어 사전처럼 언어 정렬 순서별로 정렬하는 것이 아니라 이진 정렬 순서별로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-230">However, because they perform a byte-by-byte comparison, they do not sort by a linguistic sort order (like an English dictionary) but by a binary sort order.</span></span> <span data-ttu-id="e2144-231">사용자에게 표시되는 결과가 대부분 컨텍스트에서 이상하게 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-231">The results may look odd in most contexts if displayed to users.</span></span>

<span data-ttu-id="e2144-232">서수 의미 체계는 [StringComparison](xref:System.StringComparison) 인수(같음 연산자 포함)를 포함하지 않는 [String](xref:System.String) `Equals` 오버로드의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-232">Ordinal semantics are the default for [String](xref:System.String) `Equals` overloads that do not include a [StringComparison](xref:System.StringComparison) argument (including the equality operator).</span></span> <span data-ttu-id="e2144-233">어떤 경우든지 [StringComparison](xref:System.StringComparison) 매개 변수가 있는 오버로드를 호출하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-233">In any case, we recommend that you call an overload that has a [StringComparison](xref:System.StringComparison) parameter.</span></span>

### <a name="string-operations-that-use-the-invariant-culture"></a><span data-ttu-id="e2144-234">고정 문화권을 사용하는 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="e2144-234">String operations that use the invariant culture</span></span>

<span data-ttu-id="e2144-235">고정 문화권을 사용한 비교에는 정적 [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) 속성에서 반환되는 [CompareInfo](xref:System.Globalization.CompareInfo) 속성이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-235">Comparisons with the invariant culture use the [CompareInfo](xref:System.Globalization.CompareInfo) property returned by the static [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) property.</span></span> <span data-ttu-id="e2144-236">이 동작은 모든 시스템에서 동일하며, 범위 밖의 모든 문자를 동일한 고정 문화권으로 간주하는 문자로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-236">This behavior is the same on all systems; it translates any characters outside its range into what it believes are equivalent invariant characters.</span></span> <span data-ttu-id="e2144-237">이 정책은 문화권에 걸쳐 단일 문자열 동작 집합을 유지 관리할 경우 유용하지만 예기치 않은 경과를 제공하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-237">This policy can be useful for maintaining one set of string behavior across cultures, but it often provides unexpected results.</span></span>

<span data-ttu-id="e2144-238">고정 문화권을 사용한 대/소문자를 비교하지 않는 비교에는 비교 정보를 위해 정적 [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) 속성에서 반환되는 정적 [CompareInfo](xref:System.Globalization.CompareInfo) 속성이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-238">Case-insensitive comparisons with the invariant culture use the static [CompareInfo](xref:System.Globalization.CompareInfo) property returned by the static [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) property for comparison information as well.</span></span> <span data-ttu-id="e2144-239">모든 경우에 변환된 문자 간의 차이는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-239">Any case differences among these translated characters are ignored.</span></span>

<span data-ttu-id="e2144-240">[CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) 개체를 사용하면 [String](xref:System.String) `Compare` 메서드가 특정 문자 집합을 동일한 것으로 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-240">The [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) object makes a [String](xref:System.String) `Compare` method interpret certain sets of characters as equivalent.</span></span> <span data-ttu-id="e2144-241">예를 들어 다음 동일성은 고정 문화권에서 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-241">For example, the following equivalence is valid under the invariant culture:</span></span>

<span data-ttu-id="e2144-242">InvariantCulture: a + ̊ = å</span><span class="sxs-lookup"><span data-stu-id="e2144-242">InvariantCulture: a + ̊ = å</span></span>

<span data-ttu-id="e2144-243">Latin Small Letter A 문자 "a"(\u0061)는 Combining Ring Above 문자 "+ " ̊"(\u030a) 옆에 있을 경우 Latin Small Letter A With Ring Above 문자 "å"(\u00e5)로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-243">The latin small lette A character "a" (\u0061), when it is next to the combining ring above character "+ " ̊" (\u030a), is interpreted as the latin small letter A with ring above character "å" (\u00e5).</span></span> <span data-ttu-id="e2144-244">다음 예제와 같이 이 동작은 서수 비교와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-244">As the following example shows, this behavior differs from ordinal comparison.</span></span>

```csharp
string separated = "\u0061\u030a";
string combined = "\u00e5";

Console.WriteLine("Equal sort weight of {0} and {1} using InvariantCulture: {2}",
                  separated, combined, 
                  String.Compare(separated, combined, 
                                 StringComparison.InvariantCulture) == 0);

Console.WriteLine("Equal sort weight of {0} and {1} using Ordinal: {2}",
                  separated, combined,
                  String.Compare(separated, combined, 
                                 StringComparison.Ordinal) == 0);
// The example displays the following output:
//    Equal sort weight of a° and å using InvariantCulture: True
//    Equal sort weight of a° and å using Ordinal: False 
```

```vb
Dim separated As String = ChrW(&h61) + ChrW(&h30a)
Dim combined As String = ChrW(&he5)

Console.WriteLine("Equal sort weight of {0} and {1} using InvariantCulture: {2}", _
                  separated, combined, _
                  String.Compare(separated, combined, _ 
                                 StringComparison.InvariantCulture) = 0)

Console.WriteLine("Equal sort weight of {0} and {1} using Ordinal: {2}", _
                  separated, combined, _
                  String.Compare(separated, combined, _
                                 StringComparison.Ordinal) = 0)
' The example displays the following output:
'    Equal sort weight of a° and å using InvariantCulture: True
'    Equal sort weight of a° and å using Ordinal: False
```

<span data-ttu-id="e2144-245">파일 이름, 쿠키 또는 "å"와 같은 조합이 나타날 수 있는 다른 항목을 해석할 때 서수 비교는 가장 투명하고 적합한 동작을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-245">When interpreting file names, cookies, or anything else where a combination such as "å" can appear, ordinal comparisons still offer the most transparent and fitting behavior.</span></span>

<span data-ttu-id="e2144-246">모든 것을 고려해 보면 고정 문화권에는 비교에 유용할 수 있는 속성이 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-246">On balance, the invariant culture has very few properties that make it useful for comparison.</span></span> <span data-ttu-id="e2144-247">고정 문화권은 완전한 기호 동일성을 보장하지 못하게 하는 언어 관련 방식으로 비교를 수행하지만 모든 문화권에서 표시하기에 적합하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-247">It does comparison in a linguistically relevant manner, which prevents it from guaranteeing full symbolic equivalence, but it is not the choice for display in any culture.</span></span> <span data-ttu-id="e2144-248">예를 들어 표시하기 위한 정렬된 식별자 목록을 포함하는 큰 데이터 파일이 응용 프로그램과 함께 제공될 경우 이 목록에 추가하려면 고정 스타일 정렬을 사용한 삽입이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-248">For example, if a large data file that contains a list of sorted identifiers for display accompanies an application, adding to this list would require an insertion with invariant-style sorting.</span></span>

## <a name="choosing-a-stringcomparison-member-for-your-method-call"></a><span data-ttu-id="e2144-249">메서드 호출을 위한 StringComparison 멤버 선택</span><span class="sxs-lookup"><span data-stu-id="e2144-249">Choosing a StringComparison member for your method call</span></span>

<span data-ttu-id="e2144-250">다음 표에서는 의미 체계 문자열 컨텍스트에서 [StringComparison](xref:System.StringComparison) 열거형 멤버로의 매핑을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-250">The following table outlines the mapping from semantic string context to a [StringComparison](xref:System.StringComparison) enumeration member.</span></span>

<span data-ttu-id="e2144-251">데이터</span><span class="sxs-lookup"><span data-stu-id="e2144-251">Data</span></span> | <span data-ttu-id="e2144-252">동작</span><span class="sxs-lookup"><span data-stu-id="e2144-252">Behavior</span></span> | <span data-ttu-id="e2144-253">해당 System.StringComparison 값</span><span class="sxs-lookup"><span data-stu-id="e2144-253">Corresponding System.StringComparison value</span></span>
---- | -------- | -------------------------------------------
<span data-ttu-id="e2144-254">대/소문자 구분 내부 식별자, 표준의 대/소문자 구분 식별자(예: XML 및 HTTP) 또는 대/소문자 구분 보안 관련 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-254">Case-sensitive internal identifiers, case-sensitive identifiers in standards such as XML and HTTP, or case-sensitive security-related settings.</span></span> | <span data-ttu-id="e2144-255">바이트가 정확히 일치하는 비언어적 식별자.</span><span class="sxs-lookup"><span data-stu-id="e2144-255">A non-linguistic identifier, where bytes match exactly.</span></span> | [<span data-ttu-id="e2144-256">StringComparison.Ordinal</span><span class="sxs-lookup"><span data-stu-id="e2144-256">StringComparison.Ordinal</span></span>](xref:System.StringComparison.Ordinal)
<span data-ttu-id="e2144-257">대/소문자를 구분하지 않는 내부 식별자, 표준의 대/소문자를 구분하지 않는 식별자(예: XML 및 HTTP), 파일 경로, 레지스트리 키 및 값, 환경 변수, 리소스 식별자(예: 핸들 이름) 또는 대/소문자를 구분하지 않는 보안 관련 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-257">Case-insensitive internal identifiers, case-insensitive identifiers in standards such as XML and HTTP, file paths, registry keys and values, environment variables, resource identifiers (for example, handle names), or case-insensitive security-related settings.</span></span> | <span data-ttu-id="e2144-258">대/소문자와 관련이 없는 비언어적 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-258">A non-linguistic identifier, where case is irrelevant.</span></span> | [<span data-ttu-id="e2144-259">StringComparison.OrdinalIgnoreCase</span><span class="sxs-lookup"><span data-stu-id="e2144-259">StringComparison.OrdinalIgnoreCase</span></span>](xref:System.StringComparison.OrdinalIgnoreCase)
<span data-ttu-id="e2144-260">사용자 또는 대부분의 사용자 입력에 표시되는 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-260">Data displayed to the user or most user input.</span></span> | <span data-ttu-id="e2144-261">로컬 언어적 사용자 지정이 필요한 데이터.</span><span class="sxs-lookup"><span data-stu-id="e2144-261">Data that requires local linguistic customs.</span></span> | <span data-ttu-id="e2144-262">[StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture) 또는 [CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase)</span><span class="sxs-lookup"><span data-stu-id="e2144-262">[StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture) or [CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase)</span></span>

## <a name="common-string-comparison-methods"></a><span data-ttu-id="e2144-263">일반적인 문자열 비교 방법</span><span class="sxs-lookup"><span data-stu-id="e2144-263">Common string comparison methods</span></span>

<span data-ttu-id="e2144-264">다음 섹션에서는 문자열 비교에 가장 일반적으로 사용되는 메서드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-264">The following sections describe the methods that are most commonly used for string comparison.</span></span>

### <a name="stringcompare"></a><span data-ttu-id="e2144-265">String.Compare</span><span class="sxs-lookup"><span data-stu-id="e2144-265">String.Compare</span></span>

<span data-ttu-id="e2144-266">기본 해석: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="e2144-266">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="e2144-267">문자열 해석의 가장 중심적인 작업으로, 이들 메서드 호출의 모든 인스턴스를 검사하여 문자열이 현재 문화권에 따라 해석되는지, 아니면 문화권과 관계가 없는지를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-267">As the operation most central to string interpretation, all instances of these method calls should be examined to determine whether strings should be interpreted according to the current culture, or dissociated from the culture (symbolically).</span></span> <span data-ttu-id="e2144-268">일반적으로 이는 후자이고 [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) 비교를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-268">Typically, it is the latter, and a [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) comparison should be used instead.</span></span>

<span data-ttu-id="e2144-269">[CultureInfo.CompareInfo](xref:System.Globalization.CultureInfo.CompareInfo) 속성에서 반환되는 [System.Globalization.CompareInfo](xref:System.Globalization.CompareInfo) 클래스에는 [CompareOptions](xref:System.Globalization.CompareOptions) 플래그 열거형을 통해 다양한 일치 항목 찾기 옵션(서수, 공백 무시, 가나 형식 무시 등)을 제공하는 [Compare](xref:System.Globalization.CompareInfo.Compare(System.String,System.Int32,System.String,System.Int32,System.Globalization.CompareOptions)) 메서드도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-269">The [System.Globalization.CompareInfo](xref:System.Globalization.CompareInfo) class, which is returned by the [CultureInfo.CompareInfo](xref:System.Globalization.CultureInfo.CompareInfo) property, also includes a [Compare](xref:System.Globalization.CompareInfo.Compare(System.String,System.Int32,System.String,System.Int32,System.Globalization.CompareOptions)) method that provides a large number of matching options (ordinal, ignoring white space, ignoring kana type, and so on) by means of the [CompareOptions](xref:System.Globalization.CompareOptions) flag enumeration.</span></span> 

### <a name="stringcompareto"></a><span data-ttu-id="e2144-270">String.CompareTo</span><span class="sxs-lookup"><span data-stu-id="e2144-270">String.CompareTo</span></span>

<span data-ttu-id="e2144-271">기본 해석: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="e2144-271">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="e2144-272">이 메서드는 현재 [StringComparison](xref:System.StringComparison) 형식을 지정하는 오버로드를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-272">This method does not currently offer an overload that specifies a [StringComparison](xref:System.StringComparison) type.</span></span> <span data-ttu-id="e2144-273">일반적으로 이 메서드를 권장되는 [String.Compare(String, String, StringComparison)](xref:System.String.Compare(System.String,System.String,System.StringComparison)) 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-273">It is usually possible to convert this method to the recommended [String.Compare(String, String, StringComparison)](xref:System.String.Compare(System.String,System.String,System.StringComparison)) form.</span></span>

<span data-ttu-id="e2144-274">[IComparable](xref:System.IComparable) 및 [IComparable&lt;T&gt;](xref:System.IComparable%601) 인터페이스를 구현하는 형식이 이 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-274">Types that implement the [IComparable](xref:System.IComparable) and [IComparable&lt;T&gt;](xref:System.IComparable%601) interfaces implement this method.</span></span> <span data-ttu-id="e2144-275">[StringComparison](xref:System.StringComparison) 매개 변수의 옵션이 제공되지 않으므로 사용자는 대체로 구현 형식을 통해 생성자에서 [StringComparer](xref:System.StringComparer)를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-275">Because it does not offer the option of a [StringComparison](xref:System.StringComparison) parameter, implementing types often let the user specify a [StringComparer](xref:System.StringComparer) in their constructor.</span></span> <span data-ttu-id="e2144-276">다음 예제에서는 클래스 생성자에 [StringComparer](xref:System.StringComparer) 매개 변수가 포함된 `FileName` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-276">The following example defines a `FileName` class whose class constructor includes a [StringComparer](xref:System.StringComparer) parameter.</span></span> <span data-ttu-id="e2144-277">그런 다음 `FileName.CompareTo` 메서드에서 이 [StringComparer](xref:System.StringComparer) 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-277">This [StringComparer](xref:System.StringComparer) object is then used in the `FileName.CompareTo` method.</span></span>

```csharp
using System;

public class FileName : IComparable
{
   string fname;
   StringComparer comparer; 

   public FileName(string name, StringComparer comparer)
   {
      if (String.IsNullOrEmpty(name))
         throw new ArgumentNullException("name");

      this.fname = name;

      if (comparer != null)
         this.comparer = comparer;
      else
         this.comparer = StringComparer.OrdinalIgnoreCase;
   }

   public string Name
   {
      get { return fname; }
   }

   public int CompareTo(object obj)
   {
      if (obj == null) return 1;

      if (! (obj is FileName))
         return comparer.Compare(this.fname, obj.ToString());
      else
         return comparer.Compare(this.fname, ((FileName) obj).Name);
   }
}
```

```vb
Public Class FileName : Implements IComparable
   Dim fname As String
   Dim comparer As StringComparer 

   Public Sub New(name As String, comparer As StringComparer)
      If String.IsNullOrEmpty(name) Then
         Throw New ArgumentNullException("name")
      End If

      Me.fname = name

      If comparer IsNot Nothing Then
         Me.comparer = comparer
      Else
         Me.comparer = StringComparer.OrdinalIgnoreCase
      End If      
   End Sub

   Public ReadOnly Property Name As String
      Get
         Return fname
      End Get   
   End Property

   Public Function CompareTo(obj As Object) As Integer _
          Implements IComparable.CompareTo
      If obj Is Nothing Then Return 1

      If Not TypeOf obj Is FileName Then
         obj = obj.ToString()
      Else
         obj = CType(obj, FileName).Name
      End If         
      Return comparer.Compare(Me.fname, obj)
   End Function
End Class
```

### <a name="stringequals"></a><span data-ttu-id="e2144-278">String.Equals</span><span class="sxs-lookup"><span data-stu-id="e2144-278">String.Equals</span></span>

<span data-ttu-id="e2144-279">기본 해석: [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).</span><span class="sxs-lookup"><span data-stu-id="e2144-279">Default interpretation: [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).</span></span>

<span data-ttu-id="e2144-280">[String](xref:System.String) 클래스를 통해 정적 또는 인스턴스 `Equals` 메서드 오버로드를 호출하거나 정적 같음 연산자를 사용하여 같음 여부를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-280">The [String](xref:System.String) class lets you test for equality by calling either the static or instance `Equals` method overloads, or by using the static equality operator.</span></span> <span data-ttu-id="e2144-281">오버로드 및 연산자에는 기본적으로 서수 비교가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-281">The overloads and operator use ordinal comparison by default.</span></span> <span data-ttu-id="e2144-282">그러나 서수 비교를 수행하려는 경우에도 [StringComparison](xref:System.StringComparison) 형식을 명시적으로 지정하는 오버로드를 호출하는 것이 좋습니다. 이렇게 하면 특정 문자열 해석을 위해 코드를 더 쉽게 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-282">However, we still recommend that you call an overload that explicitly specifies the [StringComparison](xref:System.StringComparison) type even if you want to perform an ordinal comparison; this makes it easier to search code for a certain string interpretation.</span></span> 

### <a name="stringtoupper-and-stringtolower"></a><span data-ttu-id="e2144-283">String.ToUpper 및 String.ToLower</span><span class="sxs-lookup"><span data-stu-id="e2144-283">String.ToUpper and String.ToLower</span></span>

<span data-ttu-id="e2144-284">기본 해석: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="e2144-284">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="e2144-285">문자열을 대문자 또는 소문자에 적용하는 방법은 대/소문자와 관계없이 문자열 비교 시 작은 정규화로 사용되므로 이들 메서드를 사용할 때 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-285">You should be careful when you use these methods, because forcing a string to a uppercase or lowercase is often used as a small normalization for comparing strings regardless of case.</span></span> <span data-ttu-id="e2144-286">이들 메서드를 사용할 경우 대/소문자를 구분하지 않는 비교를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-286">If so, consider using a case-insensitive comparison.</span></span> 

<span data-ttu-id="e2144-287">[String.ToUpperInvariant](xref:System.String.ToUpperInvariant) 및 [String.ToLowerInvariant](xref:System.String.ToLowerInvariant) 메서드도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-287">The [String.ToUpperInvariant](xref:System.String.ToUpperInvariant) and [String.ToLowerInvariant](xref:System.String.ToLowerInvariant) methods are also available.</span></span> <span data-ttu-id="e2144-288">[ToUpperInvariant](xref:System.String.ToUpperInvariant)는 대/소문자를 정규화하는 표준 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-288">[ToUpperInvariant](xref:System.String.ToUpperInvariant) is the standard way to normalize case.</span></span> <span data-ttu-id="e2144-289">[StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase)를 사용한 비교의 동작은 두 가지 호출(두 문자열 인수에 대한 [ToUpperInvariant](xref:System.String.ToUpperInvariant) 호출 및 [StringComparison.Ordinal](xref:System.StringComparison.Ordinal)을 사용한 비교 수행)의 컴퍼지션입니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-289">Comparisons made using [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) are behaviorally the composition of two calls: calling [ToUpperInvariant](xref:System.String.ToUpperInvariant) on both string arguments, and doing a comparison using [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).</span></span>

<span data-ttu-id="e2144-290">문화권을 나타내는 [CultureInfo](xref:System.Globalization.CultureInfo) 개체를 메서드에 전달하여 특정 문화권에서 대문자 및 소문자로 변환하는 데도 오버로드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-290">Overloads are also available for converting to uppercase and lowercase in a specific culture, by passing a [CultureInfo](xref:System.Globalization.CultureInfo) object that represents that culture to the method.</span></span>

### <a name="chartoupper-and-chartolower"></a><span data-ttu-id="e2144-291">Char.ToUpper 및 Char.ToLower</span><span class="sxs-lookup"><span data-stu-id="e2144-291">Char.ToUpper and Char.ToLower</span></span>

<span data-ttu-id="e2144-292">기본 해석: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="e2144-292">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="e2144-293">이 메서드는 이전 섹션에서 설명된 [String.ToUpper](xref:System.String.ToUpper) 및 [String.ToLower](xref:System.String.ToLower) 메서드와 비슷하게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-293">These methods work similarly to the [String.ToUpper](xref:System.String.ToUpper) and [String.ToLower](xref:System.String.ToLower) methods described in the previous section.</span></span>

### <a name="stringstartswith-and-stringendswith"></a><span data-ttu-id="e2144-294">String.StartsWith 및 String.EndsWith</span><span class="sxs-lookup"><span data-stu-id="e2144-294">String.StartsWith and String.EndsWith</span></span>

<span data-ttu-id="e2144-295">기본 해석: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="e2144-295">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="e2144-296">기본적으로 이들 메서드는 둘 다 문화권 구분 비교를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-296">By default, both of these methods perform a culture-sensitive comparison.</span></span>

### <a name="stringindexof-and-stringlastindexof"></a><span data-ttu-id="e2144-297">String.IndexOf 및 String.LastIndexOf</span><span class="sxs-lookup"><span data-stu-id="e2144-297">String.IndexOf and String.LastIndexOf</span></span>

<span data-ttu-id="e2144-298">기본 해석: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="e2144-298">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="e2144-299">이들 메서드의 기본 오버로드가 비교를 수행하는 방식에는 일관성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-299">There is a lack of consistency in how the default overloads of these methods perform comparisons.</span></span> <span data-ttu-id="e2144-300">[Char](xref:System.Char) 매개 변수를 포함하는 모든 [String](xref:System.String) `IndexOf` and [String](xref:System.String) `LastIndexOf` 메서드는 서수 비교를 수행하지만, [String](xref:System.String) 매개 변수를 포함하는 기본 [String](xref:System.String) `IndexOf` 및 [String`](xref:System.String) `LastIndexOf\` 메서드는 문화권 구분 비교를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-300">All [String](xref:System.String) `IndexOf` and [String](xref:System.String) `LastIndexOf` methods that include a [Char](xref:System.Char) parameter perform an ordinal comparison, but the default [String](xref:System.String) `IndexOf` and [String`](xref:System.String) `LastIndexOf\` methods that include a [String](xref:System.String) parameter perform a culture-sensitive comparison.</span></span> 

<span data-ttu-id="e2144-301">` `IndexOf` or `LastIndexOf\` 메서드를 호출하고 현재 인스턴스에서 찾을 문자열을 전달할 경우 [StringComparison](xref:System.StringComparison) 형식을 명시적으로 지정하는 오버로드를 호출하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-301">If you call ` `IndexOf` or `LastIndexOf\` method and pass it a string to locate in the current instance, we recommend that you call an overload that explicitly specifies the [StringComparison](xref:System.StringComparison) type.</span></span> <span data-ttu-id="e2144-302">[Char](xref:System.Char) 인수를 포함하는 오버로드에서는 [StringComparison](xref:System.StringComparison) 형식을 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-302">The overloads that include a [Char](xref:System.Char) argument do not allow you to specify a [StringComparison](xref:System.StringComparison) type.</span></span>

## <a name="methods-that-perform-string-comparison-indirectly"></a><span data-ttu-id="e2144-303">문자열 비교를 간접적으로 수행하는 방법</span><span class="sxs-lookup"><span data-stu-id="e2144-303">Methods that perform string comparison indirectly</span></span>

<span data-ttu-id="e2144-304">문자열 비교를 중심 작업으로 포함하는 일부 문자열이 아닌 메서드에는 [StringComparer](xref:System.StringComparer) 형식이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-304">Some non-string methods that have string comparison as a central operation use the [StringComparer](xref:System.StringComparer) type.</span></span> <span data-ttu-id="e2144-305">[StringComparer](xref:System.StringComparer) 클래스에는 해당 `Compare` 메서드가 다음 형식의 문자열 비교를 수행하는 [StringComparer](xref:System.StringComparer) 인스턴스를 반환하는 정적 속성 4개가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-305">The [StringComparer](xref:System.StringComparer) class includes four static properties that return [StringComparer](xref:System.StringComparer) instances whose `Compare` methods perform the following types of string comparisons:</span></span>

* <span data-ttu-id="e2144-306">현재 문화권을 사용한 문화권 구분 문자열 비교.</span><span class="sxs-lookup"><span data-stu-id="e2144-306">Culture-sensitive string comparisons using the current culture.</span></span> <span data-ttu-id="e2144-307">이 [StringComparer](xref:System.StringComparer) 개체는 [StringComparer.CurrentCulture](xref:System.StringComparer.CurrentCulture) 속성에서 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-307">This [StringComparer](xref:System.StringComparer) object is returned by the [StringComparer.CurrentCulture](xref:System.StringComparer.CurrentCulture) property.</span></span>

* <span data-ttu-id="e2144-308">현재 문화권을 사용한 대/소문자를 구분하지 않는 문자열 비교.</span><span class="sxs-lookup"><span data-stu-id="e2144-308">Case-insensitive comparisons using the current culture.</span></span> <span data-ttu-id="e2144-309">이 [StringComparer](xref:System.StringComparer) 개체는 [StringComparer.CurrentCultureIgnoreCase](xref:System.StringComparer.CurrentCultureIgnoreCase) 속성에서 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-309">This [StringComparer](xref:System.StringComparer) object is returned by the [StringComparer.CurrentCultureIgnoreCase](xref:System.StringComparer.CurrentCultureIgnoreCase) property.</span></span>

* <span data-ttu-id="e2144-310">서수 비교.</span><span class="sxs-lookup"><span data-stu-id="e2144-310">Ordinal comparison.</span></span> <span data-ttu-id="e2144-311">이 [StringComparer](xref:System.StringComparer) 개체는 [StringComparer.Ordinal](xref:System.StringComparer.Ordinal) 속성에서 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-311">This [StringComparer](xref:System.StringComparer) object is returned by the [StringComparer.Ordinal](xref:System.StringComparer.Ordinal) property.</span></span> 

* <span data-ttu-id="e2144-312">대소문자를 구분하지 않는 서수 비교.</span><span class="sxs-lookup"><span data-stu-id="e2144-312">Case-insensitive ordinal comparison.</span></span> <span data-ttu-id="e2144-313">이 [StringComparer](xref:System.StringComparer) 개체는 [StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase) 속성에서 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-313">This [StringComparer](xref:System.StringComparer) object is returned by the [StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase) property.</span></span>

### <a name="arraysort-and-arraybinarysearch"></a><span data-ttu-id="e2144-314">Array.Sort 및 Array.BinarySearch</span><span class="sxs-lookup"><span data-stu-id="e2144-314">Array.Sort and Array.BinarySearch</span></span>

<span data-ttu-id="e2144-315">기본 해석: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="e2144-315">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="e2144-316">컬렉션에 데이터를 저장하거나 영구 데이터를 파일이나 데이터베이스에서 컬렉션으로 읽을 때 현재 문화권을 전환하면 컬렉션에서 고정이 무효화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-316">When you store any data in a collection, or read persisted data from a file or database into a collection, switching the current culture can invalidate the invariants in the collection.</span></span> <span data-ttu-id="e2144-317">[Array.BinarySearch](xref:System.Array.BinarySearch(System.Array,System.Object)) 메서드는 검색할 배열의 요소가 이미 정렬되었다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-317">The [Array.BinarySearch](xref:System.Array.BinarySearch(System.Array,System.Object)) method assumes that the elements in the array to be searched are already sorted.</span></span> <span data-ttu-id="e2144-318">배열에서 문자열 요소를 정렬하기 위해 [Array.Sort](xref:System.Array.Sort(System.Array)) 메서드는 [String] `Compare` 메서드를 호출하여 개별 요소의 순서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-318">To sort any string element in the array, the [Array.Sort](xref:System.Array.Sort(System.Array)) method calls the [String] `Compare` method to order individual elements.</span></span> <span data-ttu-id="e2144-319">배열이 정렬된 시간과 콘텐츠가 검색된 시간 사이에 문화권이 변경될 경우 문화권 구분 비교자 사용이 위험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-319">Using a culture-sensitive comparer can be dangerous if the culture changes between the time that the array is sorted and its contents are searched.</span></span> <span data-ttu-id="e2144-320">예를 들어 다음 코드에서 저장 및 검색은 `Thread.CurrentThread.CurrentCulture` 속성을 통해 명시적으로 제공된 비교자에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-320">For example, in the following code, storage and retrieval operate on the comparer that is provided implicitly by the `Thread.CurrentThread.CurrentCulture` property.</span></span> <span data-ttu-id="e2144-321">`StoreNames` 및 `DoesNameExist`에 대한 호출 사이에 문화권이 변경되고 특히 배열 콘텐츠가 두 메서드 호출 사이에 지속되면 이진 검색이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-321">If the culture can change between the calls to `StoreNames` and `DoesNameExist`, and especially if the array contents are persisted somewhere between the two method calls, the binary search may fail.</span></span> 

```csharp
// Incorrect.
string []storedNames;

public void StoreNames(string [] names)
{
   int index = 0;
   storedNames = new string[names.Length];

   foreach (string name in names)
   {
      this.storedNames[index++] = name;
   }

   Array.Sort(names); // Line A.
}

public bool DoesNameExist(string name)
{
   return (Array.BinarySearch(this.storedNames, name) >= 0);  // Line B.
}
```

```vb
' Incorrect.
Dim storedNames() As String

Public Sub StoreNames(names() As String)
   Dim index As Integer = 0
   ReDim storedNames(names.Length - 1)

   For Each name As String In names
      Me.storedNames(index) = name
      index+= 1
   Next

   Array.Sort(names)          ' Line A.
End Sub

Public Function DoesNameExist(name As String) As Boolean
   Return Array.BinarySearch(Me.storedNames, name) >= 0      ' Line B.
End Function
```

<span data-ttu-id="e2144-322">배열을 정렬 및 검색할 때 둘 다 같은 서수(문화권을 구분하지 않는) 비교 메서드를 사용하는 다음 예제에서 권장되는 변형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-322">A recommended variation appears in the following example, which uses the same ordinal (culture-insensitive) comparison method both to sort and to search the array.</span></span> <span data-ttu-id="e2144-323">변경 코드는 두 예제의 `Line A` 및 `Line B` 줄에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-323">The change code is reflected in the lines labeled `Line A` and `Line B` in the two examples.</span></span>

```csharp
// Correct.
string []storedNames;

public void StoreNames(string [] names)
{
   int index = 0;
   storedNames = new string[names.Length];

   foreach (string name in names)
   {
      this.storedNames[index++] = name;
   }

   Array.Sort(names, StringComparer.Ordinal);  // Line A.
}

public bool DoesNameExist(string name)
{
   return (Array.BinarySearch(this.storedNames, name, StringComparer.Ordinal) >= 0);  // Line B.
}
```

```vb
' Correct.
Dim storedNames() As String

Public Sub StoreNames(names() As String)
   Dim index As Integer = 0
   ReDim storedNames(names.Length - 1)

   For Each name As String In names
      Me.storedNames(index) = name
      index+= 1
   Next

   Array.Sort(names, StringComparer.Ordinal)           ' Line A.
End Sub

Public Function DoesNameExist(name As String) As Boolean
   Return Array.BinarySearch(Me.storedNames, name, StringComparer.Ordinal) >= 0      ' Line B.
End Function
```

<span data-ttu-id="e2144-324">이 데이터가 문화권에 걸쳐 지속 및 이동되고 이 데이터를 사용자에게 제공할 때 정렬을 사용할 경우 향상된 사용자 출력을 위해 언어적으로 작동하지만 문화권 변경의 영향을 받지 않는 `StringComparison.InvariantCulture`를 사용하는 것이 좋을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-324">If this data is persisted and moved across cultures, and sorting is used to present this data to the user, you might consider using `StringComparison.InvariantCulture`, which operates linguistically for better user output but is unaffected by changes in culture.</span></span> <span data-ttu-id="e2144-325">다음 예제에서는 두 가지 이전 예제에서 배열 정렬 및 검색에 고정 문화권을 사용하도록 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-325">The following example modifies the two previous examples to use the invariant culture for sorting and searching the array.</span></span>

```csharp
// Correct.
string []storedNames;

public void StoreNames(string [] names)
{
   int index = 0;
   storedNames = new string[names.Length];

   foreach (string name in names)
   {
      this.storedNames[index++] = name;
   }

   Array.Sort(names, StringComparer.InvariantCulture);  // Line A.
}

public bool DoesNameExist(string name)
{
   return (Array.BinarySearch(this.storedNames, name, StringComparer.InvariantCulture) >= 0);  // Line B.
}
```

```vb
' Correct.
Dim storedNames() As String

Public Sub StoreNames(names() As String)
   Dim index As Integer = 0
   ReDim storedNames(names.Length - 1)

   For Each name As String In names
      Me.storedNames(index) = name
      index+= 1
   Next

   Array.Sort(names, StringComparer.InvariantCulture)           ' Line A.
End Sub

Public Function DoesNameExist(name As String) As Boolean
   Return Array.BinarySearch(Me.storedNames, name, StringComparer.InvariantCulture) >= 0      ' Line B.
End Function
```

### <a name="collections-example-hashtable-constructor"></a><span data-ttu-id="e2144-326">컬렉션 예제: 해시 가능한 생성자</span><span class="sxs-lookup"><span data-stu-id="e2144-326">Collections Example: Hashtable Constructor</span></span>

<span data-ttu-id="e2144-327">문자열 비교 방법이 영향을 미치는 작업의 두 번째 예로는 문자열 해시가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-327">Hashing strings provides a second example of an operation that is affected by the way in which strings are compared.</span></span> 

<span data-ttu-id="e2144-328">다음 예제에서는 [StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase) 속성에서 반환되는 [StringComparer](xref:System.StringComparer) 개체를 전달하여 [Hashtable](xref:System.Collections.Hashtable) 개체를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-328">The following example instantiates a [Hashtable](xref:System.Collections.Hashtable) object by passing it the [StringComparer](xref:System.StringComparer) object that is returned by the [StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase) property.</span></span> <span data-ttu-id="e2144-329">[StringComparer](xref:System.StringComparer)에서 파생된 [StringComparer](xref:System.StringComparer) 클래스는 [IEqualityComparer](xref:System.Collections.IEqualityComparer) 인터페이스를 구현하므로 해당 [GetHashCode](xref:System.Collections.IEqualityComparer) 메서드는 해시 테이블에서 문자열의 해시 코드를 계산하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-329">Because a class [StringComparer](xref:System.StringComparer) that is derived from [StringComparer](xref:System.StringComparer) implements the [IEqualityComparer](xref:System.Collections.IEqualityComparer) interface, its [GetHashCode](xref:System.Collections.IEqualityComparer) method is used to compute the hash code of strings in the hash table.</span></span>

```csharp
const int initialTableCapacity = 100;
Hashtable h;

public void PopulateFileTable(string directory)
{
   h = new Hashtable(initialTableCapacity, 
                     StringComparer.OrdinalIgnoreCase);

   foreach (string file in Directory.GetFiles(directory))
         h.Add(file, File.GetCreationTime(file));
}

public void PrintCreationTime(string targetFile)
{
   Object dt = h[targetFile];
   if (dt != null)
   {
      Console.WriteLine("File {0} was created at time {1}.",
         targetFile, 
         (DateTime) dt);
   }
   else
   {
      Console.WriteLine("File {0} does not exist.", targetFile);
   }
}
```

```vb
Const initialTableCapacity As Integer = 100
Dim h As Hashtable

Public Sub PopulateFileTable(dir As String)
   h = New Hashtable(initialTableCapacity, _
                     StringComparer.OrdinalIgnoreCase)

   For Each filename As String In Directory.GetFiles(dir)
      h.Add(filename, File.GetCreationTime(filename))
   Next                        
End Sub

Public Sub PrintCreationTime(targetFile As String)
   Dim dt As Object = h(targetFile)
   If dt IsNot Nothing Then
      Console.WriteLine("File {0} was created at {1}.", _
         targetFile, _
         CDate(dt))
   Else
      Console.WriteLine("File {0} does not exist.", targetFile)
   End If
End Sub  
```

## <a name="displaying-and-persisting-formatted-data"></a><span data-ttu-id="e2144-330">서식이 지정된 데이터 표시 및 유지</span><span class="sxs-lookup"><span data-stu-id="e2144-330">Displaying and persisting formatted data</span></span>

<span data-ttu-id="e2144-331">숫자와 날짜 및 시간과 같은 문자열이 아닌 데이터를 사용자에게 표시할 때 사용자의 문화권 설정을 사용하여 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-331">When you display non-string data such as numbers and dates and times to users, format them by using the user's cultural settings.</span></span> <span data-ttu-id="e2144-332">기본적으로 [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) 메서드와 숫자 형식 및 날짜/시간 형식의 `ToString` 메서드는 형식 지정 작업에 현재 스레드 문화권을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-332">By default, the [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) method and the `ToString` methods of the numeric types and the date and time types use the current thread culture for formatting operations.</span></span> <span data-ttu-id="e2144-333">형식 지정 메서드가 현재 문화권을 사용하도록 명시적으로 지정하려면 [String.Format(IFormatProvider, String, Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) 또는 [DateTime.ToString(IFormatProvider)](xref:System.DateTime.ToString(System.IFormatProvider))와 같은 provider 매개 변수가 있는 형식 지정 메서드의 오버로드를 호출하고 [CultureInfo.CurrentCulture](xref:System.Globalization.CultureInfo.CurrentCulture) 속성을 전달하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-333">To explicitly specify that the formatting method should use the current culture, you can call an overload of a formatting method that has a provider parameter, such as [String.Format(IFormatProvider, String, Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) or [DateTime.ToString(IFormatProvider)](xref:System.DateTime.ToString(System.IFormatProvider)), and pass it the [CultureInfo.CurrentCulture](xref:System.Globalization.CultureInfo.CurrentCulture) property.</span></span> 

<span data-ttu-id="e2144-334">문자열이 아닌 데이터를 이진 데이터 또는 형식이 지정된 데이터로 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-334">You can persist non-string data either as binary data or as formatted data.</span></span> <span data-ttu-id="e2144-335">형식이 지정된 데이터로 저장하는 경우 *provider* 매개 변수를 포함하는 형식 지정 메서드 오버로드를 호출하고 [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) 속성을 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-335">If you choose to save it as formatted data, you should call a formatting method overload that includes a *provider* parameter and pass it the [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) property.</span></span> <span data-ttu-id="e2144-336">고정 문화권은 문화권 및 컴퓨터와 관계없는 형식이 지정된 데이터에 대해 일관된 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-336">The invariant culture provides a consistent format for formatted data that is independent of culture and machine.</span></span> <span data-ttu-id="e2144-337">반대로 고정 문화권이 아닌 문화권을 사용하여 형식이 지정된 영구 데이터에는 많은 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-337">In contrast, persisting data that is formatted by using cultures other than the invariant culture has a number of limitations:</span></span> 

* <span data-ttu-id="e2144-338">다른 문화권이 포함된 시스템에서 데이터를 검색하거나 현재 시스템의 사용자가 현재 문화권을 변경하고 데이터를 검색하려고 하면 데이터를 사용하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-338">The data is likely to be unusable if it is retrieved on a system that has a different culture, or if the user of the current system changes the current culture and tries to retrieve the data.</span></span> 

* <span data-ttu-id="e2144-339">특정 컴퓨터의 문화권 속성은 표준 값과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-339">The properties of a culture on a specific computer can differ from standard values.</span></span> <span data-ttu-id="e2144-340">언제든지 사용자가 문화권 구분 표시 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-340">At any time, a user can customize culture-sensitive display settings.</span></span> <span data-ttu-id="e2144-341">이로 인해 사용자가 문화권 설정을 사용자 지정한 후에는 시스템에 저장된 형식이 지정된 데이터를 읽지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-341">Because of this, formatted data that is saved on a system may not be readable after the user customizes cultural settings.</span></span> <span data-ttu-id="e2144-342">컴퓨터 간에 형식이 지정된 데이터의 이식성은 훨씬 더 제한적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-342">The portability of formatted data across computers is likely to be even more limited.</span></span> 

* <span data-ttu-id="e2144-343">숫자 또는 날짜/시간의 형식 지정을 관리하는 국제, 지역 또는 국가 표준은 시간에 지나면서 변경되고 이러한 변경 내용은 운영 체제 업데이트에 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-343">International, regional, or national standards that govern the formatting of numbers or dates and times change over time, and these changes are incorporated into operating system updates.</span></span> <span data-ttu-id="e2144-344">형식 지정 규칙이 변경될 때 이전 규칙을 사용하여 형식이 지정된 데이터를 읽지 못하게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-344">When formatting conventions change, data that was formatted by using the previous conventions may become unreadable.</span></span> 

<span data-ttu-id="e2144-345">다음 예제에서는 문화권 구분 형식 지정을 사용하여 데이터를 유지함으로 인해 제한된 이식성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-345">The following example illustrates the limited portability that results from using culture-sensitive formatting to persist data.</span></span> <span data-ttu-id="e2144-346">예제에서는 날짜 및 시간 값 배열을 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-346">The example saves an array of date and time values to a file.</span></span> <span data-ttu-id="e2144-347">이들 값은 영어(미국) 문화권의 규칙을 사용하여 형식이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-347">These are formatted by using the conventions of the English (United States) culture.</span></span> <span data-ttu-id="e2144-348">응용 프로그램이 현재 스레드 문화권을 프랑스어(스위스)로 변경하고 나면 현재 문화권의 형식 지정 규칙을 사용하여 저장된 값을 읽으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-348">After the application changes the current thread culture to French (Switzerland), it tries to read the saved values by using the formatting conventions of the current culture.</span></span> <span data-ttu-id="e2144-349">두 데이터 항목을 읽으려는 시도로 인해 [FormatException](xref:System.FormatException) 예외가 throw되고 날짜 배열에는 [MinValue](xref:System.DateTime.MinValue)와 같은 잘못된 두 가지 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-349">The attempt to read two of the data items throws a [FormatException](xref:System.FormatException) exception, and the array of dates now contains two incorrect elements that are equal to [MinValue](xref:System.DateTime.MinValue).</span></span> 

```csharp
using System;
using System.Globalization;
using System.IO;
using System.Text;
using System.Threading;

public class Example
{
   private static string filename = @".\dates.dat";

   public static void Main()
   {
      DateTime[] dates = { new DateTime(1758, 5, 6, 21, 26, 0), 
                           new DateTime(1818, 5, 5, 7, 19, 0), 
                           new DateTime(1870, 4, 22, 23, 54, 0),  
                           new DateTime(1890, 9, 8, 6, 47, 0), 
                           new DateTime(1905, 2, 18, 15, 12, 0) }; 
      // Write the data to a file using the current culture.
      WriteData(dates);
      // Change the current culture.
      Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture("fr-CH");
      // Read the data using the current culture.
      DateTime[] newDates = ReadData();
      foreach (var newDate in newDates)
         Console.WriteLine(newDate.ToString("g"));
   }

   private static void WriteData(DateTime[] dates) 
   {
      StreamWriter sw = new StreamWriter(filename, false, Encoding.UTF8);    
      for (int ctr = 0; ctr < dates.Length; ctr++) {
         sw.Write("{0}", dates[ctr].ToString("g", CultureInfo.CurrentCulture));
         if (ctr < dates.Length - 1) sw.Write("|");   
      }      
      sw.Close();
   }

   private static DateTime[] ReadData() 
   {
      bool exceptionOccurred = false;

      // Read file contents as a single string, then split it.
      StreamReader sr = new StreamReader(filename, Encoding.UTF8);
      string output = sr.ReadToEnd();
      sr.Close();   

      string[] values = output.Split( new char[] { '|' } );
      DateTime[] newDates = new DateTime[values.Length]; 
      for (int ctr = 0; ctr < values.Length; ctr++) {
         try {
            newDates[ctr] = DateTime.Parse(values[ctr], CultureInfo.CurrentCulture);
         }
         catch (FormatException) {
            Console.WriteLine("Failed to parse {0}", values[ctr]);
            exceptionOccurred = true;
         }
      }      
      if (exceptionOccurred) Console.WriteLine();
      return newDates;
   }
}
// The example displays the following output:
//       Failed to parse 4/22/1870 11:54 PM
//       Failed to parse 2/18/1905 3:12 PM
//       
//       05.06.1758 21:26
//       05.05.1818 07:19
//       01.01.0001 00:00
//       09.08.1890 06:47
//       01.01.0001 00:00
//       01.01.0001 00:00
```

```vb
Imports System.Globalization
Imports System.IO
Imports System.Text
Imports System.Threading

Module Example
   Private filename As String = ".\dates.dat"

   Public Sub Main()
      Dim dates() As Date = { #5/6/1758 9:26PM#, #5/5/1818 7:19AM#, _ 
                              #4/22/1870 11:54PM#, #9/8/1890 6:47AM#, _ 
                              #2/18/1905 3:12PM# }
      ' Write the data to a file using the current culture.
      WriteData(dates)
      ' Change the current culture.
      Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture("fr-CH")
      ' Read the data using the current culture.
      Dim newDates() As Date = ReadData()
      For Each newDate In newDates
         Console.WriteLine(newDate.ToString("g"))
      Next
   End Sub

   Private Sub WriteData(dates() As Date)
      Dim sw As New StreamWriter(filename, False, Encoding.Utf8)    
      For ctr As Integer = 0 To dates.Length - 1
         sw.Write("{0}", dates(ctr).ToString("g", CultureInfo.CurrentCulture))
         If ctr < dates.Length - 1 Then sw.Write("|")   
      Next      
      sw.Close()
   End Sub

   Private Function ReadData() As Date()
      Dim exceptionOccurred As Boolean = False

      ' Read file contents as a single string, then split it.
      Dim sr As New StreamReader(filename, Encoding.Utf8)
      Dim output As String = sr.ReadToEnd()
      sr.Close()   

      Dim values() As String = output.Split( {"|"c } )
      Dim newDates(values.Length - 1) As Date 
      For ctr As Integer = 0 To values.Length - 1
         Try
            newDates(ctr) = DateTime.Parse(values(ctr), CultureInfo.CurrentCulture)
         Catch e As FormatException
            Console.WriteLine("Failed to parse {0}", values(ctr))
            exceptionOccurred = True
         End Try
      Next      
      If exceptionOccurred Then Console.WriteLine()
      Return newDates
   End Function
End Module
' The example displays the following output:
'       Failed to parse 4/22/1870 11:54 PM
'       Failed to parse 2/18/1905 3:12 PM
'       
'       05.06.1758 21:26
'       05.05.1818 07:19
'       01.01.0001 00:00
'       09.08.1890 06:47
'       01.01.0001 00:00
'       01.01.0001 00:00
'
```

<span data-ttu-id="e2144-350">그러나 [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) 및 [DateTime.Parse(String, IFormatProvider)](xref:System.DateTime.Parse(System.String,System.IFormatProvider)) 호출에서 [CultureInfo.CurrentCulture](xref:System.Globalization.CultureInfo.CurrentCulture) 속성을 [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture)로 바꾸면 다음 출력과 같이 보관된 날짜 및 시간 데이터가 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2144-350">However, if you replace the [CultureInfo.CurrentCulture](xref:System.Globalization.CultureInfo.CurrentCulture) property with [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) in the calls to [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) and [DateTime.Parse(String, IFormatProvider)](xref:System.DateTime.Parse(System.String,System.IFormatProvider)), the persisted date and time data is successfully restored, as the following output shows.</span></span>

```
// 06.05.1758 21:26
// 05.05.1818 07:19
// 22.04.1870 23:54
// 08.09.1890 06:47
// 18.02.1905 15:12
```

## <a name="see-also"></a><span data-ttu-id="e2144-351">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e2144-351">See also</span></span>

[<span data-ttu-id="e2144-352">문자열 조작</span><span class="sxs-lookup"><span data-stu-id="e2144-352">Manipulating strings</span></span>](manipulating-strings.md)

