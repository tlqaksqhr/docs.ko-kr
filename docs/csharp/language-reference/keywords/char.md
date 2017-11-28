---
title: "char(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords: char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
caps.latest.revision: "27"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 41f672e9b12481fa5cce78015e95d2c5245a26db
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="char-c-reference"></a><span data-ttu-id="75e6b-102">char(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="75e6b-102">char (C# Reference)</span></span>
<span data-ttu-id="75e6b-103">`char` 키워드는 .NET Framework에서 유니코드 문자를 표현하는 데 사용하는 <xref:System.Char?displayProperty=nameWithType> 구조체의 인스턴스를 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="75e6b-103">The `char` keyword is used to declare an instance of the <xref:System.Char?displayProperty=nameWithType> structure that the .NET Framework uses to represent a Unicode character.</span></span> <span data-ttu-id="75e6b-104">`Char` 개체의 값은 16비트 숫자(서수) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="75e6b-104">The value of a `Char` object is a 16-bit numeric (ordinal) value.</span></span>  
  
 <span data-ttu-id="75e6b-105">유니코드 문자는 전 세계에서 대부분의 문자 체계를 표현하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="75e6b-105">Unicode characters are used to represent most of the written languages throughout the world.</span></span>  
  
|<span data-ttu-id="75e6b-106">형식</span><span class="sxs-lookup"><span data-stu-id="75e6b-106">Type</span></span>|<span data-ttu-id="75e6b-107">범위</span><span class="sxs-lookup"><span data-stu-id="75e6b-107">Range</span></span>|<span data-ttu-id="75e6b-108">크기</span><span class="sxs-lookup"><span data-stu-id="75e6b-108">Size</span></span>|<span data-ttu-id="75e6b-109">.NET Framework 형식</span><span class="sxs-lookup"><span data-stu-id="75e6b-109">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`char`|<span data-ttu-id="75e6b-110">U+0000~U+FFFF</span><span class="sxs-lookup"><span data-stu-id="75e6b-110">U+0000 to U+FFFF</span></span>|<span data-ttu-id="75e6b-111">유니코드 16비트 문자</span><span class="sxs-lookup"><span data-stu-id="75e6b-111">Unicode 16-bit character</span></span>|<xref:System.Char?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="75e6b-112">리터럴</span><span class="sxs-lookup"><span data-stu-id="75e6b-112">Literals</span></span>  
 <span data-ttu-id="75e6b-113">`char` 형식의 상수는 문자 리터럴, 16진수 이스케이프 시퀀스 또는 유니코드 표현으로 기록될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75e6b-113">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="75e6b-114">정수 문자 코드를 캐스트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75e6b-114">You can also cast the integral character codes.</span></span> <span data-ttu-id="75e6b-115">다음 예제에서 `char` 변수 4개는 동일 문자 `X`를 사용하여 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="75e6b-115">In the following example four `char` variables are initialized with the same character `X`:</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/char_1.cs)]  
  
## <a name="conversions"></a><span data-ttu-id="75e6b-116">변환</span><span class="sxs-lookup"><span data-stu-id="75e6b-116">Conversions</span></span>  
 <span data-ttu-id="75e6b-117">`char`는 [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) 또는 [decimal](../../../csharp/language-reference/keywords/decimal.md)로 암시적으로 변환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75e6b-117">A `char` can be implicitly converted to [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="75e6b-118">그러나 기타 형식에서 `char` 형식으로의 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="75e6b-118">However, there are no implicit conversions from other types to the `char` type.</span></span>  
  
 <span data-ttu-id="75e6b-119"><xref:System.Char?displayProperty=nameWithType> 형식은 `char` 값 작업을 위한 몇 가지 정적 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="75e6b-119">The <xref:System.Char?displayProperty=nameWithType> type provides several static methods for working with `char` values.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="75e6b-120">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="75e6b-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="75e6b-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="75e6b-121">See Also</span></span>  
 <xref:System.Char>  
 [<span data-ttu-id="75e6b-122">C# 참조</span><span class="sxs-lookup"><span data-stu-id="75e6b-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="75e6b-123">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="75e6b-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="75e6b-124">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="75e6b-124">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="75e6b-125">정수 계열 형식 표</span><span class="sxs-lookup"><span data-stu-id="75e6b-125">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="75e6b-126">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="75e6b-126">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="75e6b-127">암시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="75e6b-127">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="75e6b-128">명시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="75e6b-128">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
 [<span data-ttu-id="75e6b-129">Nullable 형식</span><span class="sxs-lookup"><span data-stu-id="75e6b-129">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 [<span data-ttu-id="75e6b-130">문자열</span><span class="sxs-lookup"><span data-stu-id="75e6b-130">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)
