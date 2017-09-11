---
title: "대/소문자 바꾸기"
description: "대/소문자 바꾸기"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 646c5afd-8aec-4393-9c00-f68ad2580c68
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 023f40969095627242d3652add853eb999c30c4b
ms.contentlocale: ko-kr
ms.lasthandoff: 03/02/2017

---

# <a name="changing-case"></a><span data-ttu-id="ba6af-104">대/소문자 바꾸기</span><span class="sxs-lookup"><span data-stu-id="ba6af-104">Changing case</span></span>

<span data-ttu-id="ba6af-105">사용자 입력을 수락하는 응용 프로그램을 작성하는 경우 데이터를 입력할 때 사용하는 대/소문자를 확신할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba6af-105">If you write an application that accepts input from a user, you can never be sure what case he or she will use to enter the data.</span></span> <span data-ttu-id="ba6af-106">특히 사용자 인터페이스에 표시하는 경우 문자열의 대/소문자를 일관되게 표시하려는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="ba6af-106">Often, you want strings to be cased consistently, particularly if you are displaying them in the user interface.</span></span> <span data-ttu-id="ba6af-107">다음 표에서는 두 가지 대/소문자 변경 메서드를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ba6af-107">The following table describes two case-changing methods.</span></span>

<span data-ttu-id="ba6af-108">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="ba6af-108">Method name</span></span> | <span data-ttu-id="ba6af-109">기능</span><span class="sxs-lookup"><span data-stu-id="ba6af-109">Use</span></span>
----------- | ---
[<span data-ttu-id="ba6af-110">String.ToUpper</span><span class="sxs-lookup"><span data-stu-id="ba6af-110">String.ToUpper</span></span>](xref:System.String.ToUpper) | <span data-ttu-id="ba6af-111">문자열의 모든 문자를 대문자로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba6af-111">Converts all characters in a string to uppercase.</span></span>
[<span data-ttu-id="ba6af-112">String.ToLower</span><span class="sxs-lookup"><span data-stu-id="ba6af-112">String.ToLower</span></span>](xref:System.String.ToLower) | <span data-ttu-id="ba6af-113">문자열의 모든 문자를 소문자로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba6af-113">Converts all characters in a string to lowercase.</span></span>

> [!WARNING]  
> <span data-ttu-id="ba6af-114">문자열을 비교하거나 같은지 테스트하기 위해 `String.ToUpper` 및 `String.ToLower` 메서드를 사용하여 문자열을 변환하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba6af-114">Note that the `String.ToUpper` and `String.ToLower` methods should not be used to convert strings in order to compare them or test them for equality.</span></span> 

## <a name="comparing-strings-of-mixed-case"></a><span data-ttu-id="ba6af-115">대/소문자가 혼합된 문자열 비교</span><span class="sxs-lookup"><span data-stu-id="ba6af-115">Comparing strings of mixed case</span></span>

<span data-ttu-id="ba6af-116">대/소문자가 혼합된 문자열을 비교하여 같은지 확인하려면 [String](xref:System) `Equals` 메서드의 오버로드 중 하나를 *comparisonType* 매개 변수와 함께 호출하고 *comparisonType* 인수에 대해 [StringComparison.CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase) 또는 [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ba6af-116">To compare strings of mixed case to determine whether they are equal, their, call one of the overloads of the [String](xref:System) `Equals` method with a *comparisonType* parameter, and provide a value of either [StringComparison.CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase) or [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) for the *comparisonType* argument.</span></span> 

<span data-ttu-id="ba6af-117">자세한 내용은 [문자열 사용에 대한 모범 사례](best-practices.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba6af-117">For more information, see [Best Practices for Using Strings](best-practices.md).</span></span> 

## <a name="toupper"></a><span data-ttu-id="ba6af-118">ToUpper</span><span class="sxs-lookup"><span data-stu-id="ba6af-118">ToUpper</span></span>

<span data-ttu-id="ba6af-119">[String.ToUpper](xref:System.String.ToUpper) 메서드는 문자열의 모든 문자를 대문자로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ba6af-119">The [String.ToUpper](xref:System.String.ToUpper) method changes all characters in a string to uppercase.</span></span> <span data-ttu-id="ba6af-120">다음 예제에서는 "Hello World!" 문자열을</span><span class="sxs-lookup"><span data-stu-id="ba6af-120">The following example converts the string "Hello World!"</span></span> <span data-ttu-id="ba6af-121">대/소문자 혼합에서 대문자로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba6af-121">from mixed case to uppercase.</span></span>

```csharp
string properString = "Hello World!";
Console.WriteLine(properString.ToUpper());
// This example displays the following output:
//       HELLO WORLD!
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.ToUpper())
' This example displays the following output:
'       HELLO WORLD!
```

## <a name="tolower"></a><span data-ttu-id="ba6af-122">ToLower</span><span class="sxs-lookup"><span data-stu-id="ba6af-122">ToLower</span></span>

<span data-ttu-id="ba6af-123">[String.ToLower](xref:System.String.ToLower) 메서드는 이전 메서드와 비슷하지만 대신 문자열의 모든 문자를 소문자로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba6af-123">The [String.ToLower](xref:System.String.ToLower) method is similar to the previous method, but instead converts all the characters in a string to lowercase.</span></span> <span data-ttu-id="ba6af-124">다음 예제에서는 "Hello World!" 문자열을</span><span class="sxs-lookup"><span data-stu-id="ba6af-124">The following example converts the string "Hello World!"</span></span> <span data-ttu-id="ba6af-125">소문자로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba6af-125">to lowercase.</span></span>

```csharp
string properString = "Hello World!";
Console.WriteLine(properString.ToLower());
// This example displays the following output:
//       hello world!
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.ToLower())
' This example displays the following output:
'       hello world!
```

## <a name="see-also"></a><span data-ttu-id="ba6af-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ba6af-126">See Also</span></span>

[<span data-ttu-id="ba6af-127">기본적인 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="ba6af-127">Basic string operations</span></span>](basic-string-operations.md)

