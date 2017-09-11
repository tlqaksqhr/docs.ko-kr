---
title: "방법: 문자열을 숫자로 변환(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- conversions [C#]
- conversions [C#], string to int
- converting strings to int [C#]
- strings [C#], converting to int
ms.assetid: 467b9979-86ee-4afd-b734-30299cda91e3
caps.latest.revision: 34
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 08d13e40a385ce8e9011b508b04361b2e050f904
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-convert-a-string-to-a-number-c-programming-guide"></a><span data-ttu-id="8a6cc-102">방법: 문자열을 숫자로 변환(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="8a6cc-102">How to: Convert a String to a Number (C# Programming Guide)</span></span>
<span data-ttu-id="8a6cc-103"><xref:System.Convert> 클래스의 메서드를 사용하거나 다양한 숫자 형식(int, long, float 등)에 있는 `TryParse` 메서드를 사용하여 [문자열](../../../csharp/language-reference/keywords/string.md)을 숫자로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a6cc-103">You can convert a [string](../../../csharp/language-reference/keywords/string.md) to a number by using methods in the <xref:System.Convert> class or by using the `TryParse` method found on the various numeric types (int, long, float, etc.).</span></span>  
  
 <span data-ttu-id="8a6cc-104">문자열이 있는 경우 `TryParse` 메서드(예: `int.TryParse("11")`)를 호출하면 약간 더 효율적이고 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="8a6cc-104">If you have a string, it is slightly more efficient and straightforward to call a `TryParse` method (for example, `int.TryParse("11")`).</span></span>  <span data-ttu-id="8a6cc-105">`Convert` 메서드 사용은 <xref:System.IConvertible>을 구현하는 일반 개체에 더 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="8a6cc-105">Using a `Convert` method is more useful for general objects that implement <xref:System.IConvertible>.</span></span>  
  
 <span data-ttu-id="8a6cc-106">`Parse` 또는 `TryParse` 메서드는 <xref:System.Int32?displayProperty=fullName> 형식과 같이 문자열에 포함되는 숫자 형식에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a6cc-106">You can use `Parse` or `TryParse` methods on the numeric type you expect the string contains, such as the <xref:System.Int32?displayProperty=fullName> type.</span></span>  <span data-ttu-id="8a6cc-107"><xref:System.Convert.ToUInt32%2A?displayProperty=fullName> 메서드는 <xref:System.Int32.Parse%2A>를 내부적으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8a6cc-107">The <xref:System.Convert.ToUInt32%2A?displayProperty=fullName> method uses <xref:System.Int32.Parse%2A> internally.</span></span>  <span data-ttu-id="8a6cc-108">문자열이 올바른 형식이 아닌 경우 `Parse`는 예외를 throw하는 반면 `TryParse`는 [false](../../../csharp/language-reference/keywords/false.md)를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8a6cc-108">If the string is not in a valid format, `Parse` throws an exception whereas `TryParse` returns [false](../../../csharp/language-reference/keywords/false.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a6cc-109">예제</span><span class="sxs-lookup"><span data-stu-id="8a6cc-109">Example</span></span>  
 <span data-ttu-id="8a6cc-110">`Parse` 및 `TryParse` 메서드는 문자열의 시작과 끝에 있는 공백을 무시하지만 다른 모든 문자는 적절한 숫자 형식(int, long, ulong, float, 10진수 등)을 구성하는 문자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a6cc-110">The `Parse` and `TryParse` methods ignore whitespace at the beginning and at the end of the string, but all other characters must be characters that form the appropriate numeric type (int, long, ulong, float, decimal, etc.).</span></span>  <span data-ttu-id="8a6cc-111">숫자를 구성하는 문자 내에 공백이 있으면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="8a6cc-111">Any whitespace within the characters that form the number cause an error.</span></span>  <span data-ttu-id="8a6cc-112">예를 들어 `decimal.TryParse`를 사용하여 "10", "10.3", "  10  "은 구문 분석할 수 있지만 이 메서드를 사용하여 "10X", "1 0"(공백 포함), "10 .3"(공백 포함), "10e1"(`float.TryParse` 사용) 등에서 10을 구문 분석할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a6cc-112">For example, you can use `decimal.TryParse` to parse "10", "10.3", "  10  ", but you cannot use this method to parse 10 from "10X", "1 0" (note space), "10 .3" (note space), "10e1" (`float.TryParse` works here), and so on.</span></span>  
  
 <span data-ttu-id="8a6cc-113">다음 예제에서는 `Parse` 및 `TryParse`에 대한 호출이 성공하는 경우와 실패하는 경우를 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8a6cc-113">The examples below demonstrate both successful and unsuccessful calls to `Parse` and `TryParse`.</span></span>  
  
 <span data-ttu-id="8a6cc-114">[!code-cs[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8a6cc-114">[!code-cs[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]</span></span>  
<span data-ttu-id="8a6cc-115">[!code-cs[csProgGuideTypes#25](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="8a6cc-115">[!code-cs[csProgGuideTypes#25](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_2.cs)]</span></span>  
<span data-ttu-id="8a6cc-116">[!code-cs[csProgGuideTypes#26](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="8a6cc-116">[!code-cs[csProgGuideTypes#26](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_3.cs)]</span></span>  
<span data-ttu-id="8a6cc-117">[!code-cs[csProgGuideTypes#27](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="8a6cc-117">[!code-cs[csProgGuideTypes#27](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_4.cs)]</span></span>  
<span data-ttu-id="8a6cc-118">[!code-cs[csProgGuideTypes#28](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="8a6cc-118">[!code-cs[csProgGuideTypes#28](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_5.cs)]</span></span>  
<span data-ttu-id="8a6cc-119">[!code-cs[csProgGuideTypes#100](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="8a6cc-119">[!code-cs[csProgGuideTypes#100](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_6.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a6cc-120">예제</span><span class="sxs-lookup"><span data-stu-id="8a6cc-120">Example</span></span>  
 <span data-ttu-id="8a6cc-121">다음 표에는 사용할 수 있는 <xref:System.Convert> 클래스의 메서드 일부가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a6cc-121">The following table lists some of the methods from the <xref:System.Convert> class that you can use.</span></span>  
  
|<span data-ttu-id="8a6cc-122">숫자 형식</span><span class="sxs-lookup"><span data-stu-id="8a6cc-122">Numeric Type</span></span>|<span data-ttu-id="8a6cc-123">메서드</span><span class="sxs-lookup"><span data-stu-id="8a6cc-123">Method</span></span>|  
|------------------|------------|  
|`decimal`|<xref:System.Convert.ToDecimal%28System.String%29>|  
|`float`|<xref:System.Convert.ToSingle%28System.String%29>|  
|`double`|<xref:System.Convert.ToDouble%28System.String%29>|  
|`short`|<xref:System.Convert.ToInt16%28System.String%29>|  
|`int`|<xref:System.Convert.ToInt32%28System.String%29>|  
|`long`|<xref:System.Convert.ToInt64%28System.String%29>|  
|`ushort`|<xref:System.Convert.ToUInt16%28System.String%29>|  
|`uint`|<xref:System.Convert.ToUInt32%28System.String%29>|  
|`ulong`|<xref:System.Convert.ToUInt64%28System.String%29>|  
  
 <span data-ttu-id="8a6cc-124">이 예제에서는 <xref:System.Convert.ToInt32%28System.String%29?displayProperty=fullName> 메서드를 호출하여 입력 [string](../../../csharp/language-reference/keywords/string.md)을 [int](../../../csharp/language-reference/keywords/int.md)로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="8a6cc-124">This example calls the <xref:System.Convert.ToInt32%28System.String%29?displayProperty=fullName> method to convert an input [string](../../../csharp/language-reference/keywords/string.md) to an [int](../../../csharp/language-reference/keywords/int.md) .</span></span> <span data-ttu-id="8a6cc-125">코드는 이 메서드에서 throw할 수 있는 두 가지 가장 일반적인 예외인 <xref:System.FormatException>과 <xref:System.OverflowException>을 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="8a6cc-125">The code catches the two most common exceptions that can be thrown by this method, <xref:System.FormatException> and <xref:System.OverflowException>.</span></span> <span data-ttu-id="8a6cc-126">정수 저장소 위치를 오버플로하지 않고 숫자를 증가시킬 수 있는 경우 프로그램에서 결과에 1을 더하여 출력을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="8a6cc-126">If the number can be incremented without overflowing the integer storage location, the program adds 1 to the result and prints the output.</span></span>  
  
 <span data-ttu-id="8a6cc-127">[!code-cs[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8a6cc-127">[!code-cs[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]</span></span>  
<span data-ttu-id="8a6cc-128">[!code-cs[csProgGuideTypes#24](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="8a6cc-128">[!code-cs[csProgGuideTypes#24](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_7.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a6cc-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a6cc-129">See Also</span></span>  
 <span data-ttu-id="8a6cc-130">[형식](../../../csharp/programming-guide/types/index.md) </span><span class="sxs-lookup"><span data-stu-id="8a6cc-130">[Types](../../../csharp/programming-guide/types/index.md) </span></span>  
 <span data-ttu-id="8a6cc-131">[방법: 문자열이 숫자 값을 나타내는지 확인](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md) </span><span class="sxs-lookup"><span data-stu-id="8a6cc-131">[How to: Determine Whether a String Represents a Numeric Value](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md) </span></span>  
 [<span data-ttu-id="8a6cc-132">.NET Framework 4 서식 유틸리티</span><span class="sxs-lookup"><span data-stu-id="8a6cc-132">.NET Framework 4 Formatting Utility</span></span>](http://code.msdn.microsoft.com/NET-Framework-4-Formatting-9c4dae8d)

