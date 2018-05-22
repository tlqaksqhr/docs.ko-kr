---
title: '방법: 16진수 문자열과 숫자 형식 간 변환(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
helpviewer_keywords:
- hexadecimal strings [C#], converting to numeric type
- conversions [C#], hexidecimal strings
- strings [C#], converting hexadecimal strings
- hexadecimal strings [C#]
ms.assetid: 7115c49f-7d1d-40c3-8bd9-aae0cc1d46b6
ms.openlocfilehash: 1a5bde0a9169a78e179a69c7a2f4080e5a465f54
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-convert-between-hexadecimal-strings-and-numeric-types-c-programming-guide"></a><span data-ttu-id="1fae0-102">방법: 16진수 문자열과 숫자 형식 간 변환(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="1fae0-102">How to: Convert Between Hexadecimal Strings and Numeric Types (C# Programming Guide)</span></span>
<span data-ttu-id="1fae0-103">이 예제에서는 다음 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1fae0-103">These examples show you how to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="1fae0-104">[string](../../../csharp/language-reference/keywords/string.md)에 있는 각 문자의 16진수 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1fae0-104">Obtain the hexadecimal value of each character in a [string](../../../csharp/language-reference/keywords/string.md).</span></span>  
  
-   <span data-ttu-id="1fae0-105">16진수 문자열의 각 값에 해당하는 [char](../../../csharp/language-reference/keywords/char.md)을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1fae0-105">Obtain the [char](../../../csharp/language-reference/keywords/char.md) that corresponds to each value in a hexadecimal string.</span></span>  
  
-   <span data-ttu-id="1fae0-106">16진수 `string`을 [int](../../../csharp/language-reference/keywords/int.md)로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="1fae0-106">Convert a hexadecimal `string` to an [int](../../../csharp/language-reference/keywords/int.md).</span></span>  
  
-   <span data-ttu-id="1fae0-107">16진수 `string`을 [float](../../../csharp/language-reference/keywords/float.md)로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="1fae0-107">Convert a hexadecimal `string` to a [float](../../../csharp/language-reference/keywords/float.md).</span></span>  
  
-   <span data-ttu-id="1fae0-108">[byte](../../../csharp/language-reference/keywords/byte.md) 배열을 16진수 `string`으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="1fae0-108">Convert a [byte](../../../csharp/language-reference/keywords/byte.md) array to a hexadecimal `string`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fae0-109">예</span><span class="sxs-lookup"><span data-stu-id="1fae0-109">Example</span></span>  
 <span data-ttu-id="1fae0-110">이 예제에서는 `string`에 있는 각 문자의 16진수 값을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="1fae0-110">This example outputs the hexadecimal value of each character in a `string`.</span></span> <span data-ttu-id="1fae0-111">먼저 `string`을 문자 배열로 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="1fae0-111">First it parses the `string` to an array of characters.</span></span> <span data-ttu-id="1fae0-112">그런 다음 각 문자에서 <xref:System.Convert.ToInt32%28System.Char%29>를 호출하여 해당 숫자 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1fae0-112">Then it calls <xref:System.Convert.ToInt32%28System.Char%29> on each character to obtain its numeric value.</span></span> <span data-ttu-id="1fae0-113">마지막으로, `string`에서 숫자의 형식을 16진수 표현으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1fae0-113">Finally, it formats the number as its hexadecimal representation in a `string`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#30](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="1fae0-114">예</span><span class="sxs-lookup"><span data-stu-id="1fae0-114">Example</span></span>  
 <span data-ttu-id="1fae0-115">이 예제에서는 16진수 값의 `string`을 구문 분석하고 각 16진수 값에 해당하는 문자를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="1fae0-115">This example parses a `string` of hexadecimal values and outputs the character corresponding to each hexadecimal value.</span></span> <span data-ttu-id="1fae0-116">먼저 [Split(Char\[\])](xref:System.String.Split(System.Char[])) 메서드를 호출하여 각 16진수 값을 배열의 개별 `string`으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1fae0-116">First it calls the [Split(Char\[\])](xref:System.String.Split(System.Char[])) method to obtain each hexadecimal value as an individual `string` in an array.</span></span> <span data-ttu-id="1fae0-117">그런 다음 <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29>를 호출하여 16진수 값을 [int](../../../csharp/language-reference/keywords/int.md)로 표현된 10진수 값으로 변환합니다. 문자 코드에 해당하는 문자를 가져오는 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1fae0-117">Then it calls <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> to convert the hexadecimal value to a decimal value represented as an [int](../../../csharp/language-reference/keywords/int.md). It shows two different ways to obtain the character corresponding to that character code.</span></span> <span data-ttu-id="1fae0-118">첫 번째 방법은 정수 인수에 해당하는 문자를 `string`으로 반환하는 <xref:System.Char.ConvertFromUtf32%28System.Int32%29>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1fae0-118">The first technique uses <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, which returns the character corresponding to the integer argument as a `string`.</span></span> <span data-ttu-id="1fae0-119">두 번째 방법은 `int`를 [char](../../../csharp/language-reference/keywords/char.md)로 명시적으로 캐스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="1fae0-119">The second technique explicitly casts the `int` to a [char](../../../csharp/language-reference/keywords/char.md).</span></span>  
  
 [!code-csharp[csProgGuideTypes#31](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="1fae0-120">예</span><span class="sxs-lookup"><span data-stu-id="1fae0-120">Example</span></span>  
 <span data-ttu-id="1fae0-121">이 예제에서는 <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29> 메서드를 호출하여 16진수 `string`을 정수로 변환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1fae0-121">This example shows another way to convert a hexadecimal `string` to an integer, by calling the <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29> method.</span></span>  
  
 [!code-csharp[csProgGuideTypes#32](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="1fae0-122">예</span><span class="sxs-lookup"><span data-stu-id="1fae0-122">Example</span></span>  
 <span data-ttu-id="1fae0-123">다음 예제에서는 <xref:System.BitConverter?displayProperty=nameWithType> 클래스 및 <xref:System.Int32.Parse%2A?displayProperty=nameWithType> 메서드를 사용하여 16진수 `string`을 [float](../../../csharp/language-reference/keywords/float.md)로 변환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1fae0-123">The following example shows how to convert a hexadecimal `string` to a [float](../../../csharp/language-reference/keywords/float.md) by using the <xref:System.BitConverter?displayProperty=nameWithType> class and the <xref:System.Int32.Parse%2A?displayProperty=nameWithType> method.</span></span>  
  
 [!code-csharp[csProgGuideTypes#39](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_4.cs)]  
  
## <a name="example"></a><span data-ttu-id="1fae0-124">예</span><span class="sxs-lookup"><span data-stu-id="1fae0-124">Example</span></span>  
 <span data-ttu-id="1fae0-125">다음 예제에서는 <xref:System.BitConverter?displayProperty=nameWithType> 클래스를 사용하여 [byte](../../../csharp/language-reference/keywords/byte.md) 배열을 16진수 문자열로 변환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1fae0-125">The following example shows how to convert a [byte](../../../csharp/language-reference/keywords/byte.md) array to a hexadecimal string by using the <xref:System.BitConverter?displayProperty=nameWithType> class.</span></span>  
  
 [!code-csharp[csProgGuideTypes#38](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_5.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="1fae0-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1fae0-126">See Also</span></span>  
 [<span data-ttu-id="1fae0-127">표준 숫자 형식 문자열</span><span class="sxs-lookup"><span data-stu-id="1fae0-127">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)  
 [<span data-ttu-id="1fae0-128">유형</span><span class="sxs-lookup"><span data-stu-id="1fae0-128">Types</span></span>](../../../csharp/programming-guide/types/index.md)  
 [<span data-ttu-id="1fae0-129">방법: 문자열이 숫자 값을 나타내는지 확인</span><span class="sxs-lookup"><span data-stu-id="1fae0-129">How to: Determine Whether a String Represents a Numeric Value</span></span>](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)
