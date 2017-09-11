---
title: "방법: 문자열이 숫자 값을 나타내는지 확인(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- numeric strings [C#]
- validating numeric input [C#]
- strings [C#], numeric
ms.assetid: a4e84e10-ea0a-489f-a868-503dded9d85f
caps.latest.revision: 9
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
ms.openlocfilehash: d2f89f4a4771625389a04f5c92829c91d66eb207
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-determine-whether-a-string-represents-a-numeric-value-c-programming-guide"></a><span data-ttu-id="624f6-102">방법: 문자열이 숫자 값을 나타내는지 확인(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="624f6-102">How to: Determine Whether a String Represents a Numeric Value (C# Programming Guide)</span></span>
<span data-ttu-id="624f6-103">문자열이 지정된 숫자 형식의 유효한 표현인지 확인하려면 모든 기본 숫자 형식 및 <xref:System.DateTime>, <xref:System.Net.IPAddress> 등의 형식에 의해서도 구현되는 정적 `TryParse` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="624f6-103">To determine whether a string is a valid representation of a specified numeric type, use the static `TryParse` method that is implemented by all primitive numeric types and also by types such as <xref:System.DateTime> and <xref:System.Net.IPAddress>.</span></span> <span data-ttu-id="624f6-104">다음 예제에서는 "108"이 유효한 [int](../../../csharp/language-reference/keywords/int.md)인지 확인하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="624f6-104">The following example shows how to determine whether "108" is a valid [int](../../../csharp/language-reference/keywords/int.md).</span></span>  
  
```  
int i = 0;   
string s = "108";  
bool result = int.TryParse(s, out i); //i now = 108  
```  
  
 <span data-ttu-id="624f6-105">문자열이 숫자가 아닌 문자를 포함하거나, 숫자 값이 지정한 특정 형식에 비해 너무 크거나 너무 작은 경우 `TryParse`는 false를 반환하고 out 매개 변수를 0으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="624f6-105">If the string contains nonnumeric characters or the numeric value is too large or too small for the particular type you have specified, `TryParse` returns false and sets the out parameter to zero.</span></span> <span data-ttu-id="624f6-106">그렇지 않으면 true를 반환하고 out 매개 변수를 문자열의 숫자 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="624f6-106">Otherwise, it returns true and sets the out parameter to the numeric value of the string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="624f6-107">문자열이 숫자만 포함해도 사용하는 `TryParse` 메서드의 형식에 유효하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="624f6-107">A string may contain only numeric characters and still not be valid for the type whose `TryParse` method that you use.</span></span> <span data-ttu-id="624f6-108">예를 들어 "256"은 `byte`에 유효한 값이 아니지만 `int`에는 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="624f6-108">For example, "256" is not a valid value for `byte` but it is valid for `int`.</span></span> <span data-ttu-id="624f6-109">"98.6"은 `int`에 유효한 값이 아니지만 유효한 `decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="624f6-109">"98.6" is not a valid value for `int` but it is a valid `decimal`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="624f6-110">예제</span><span class="sxs-lookup"><span data-stu-id="624f6-110">Example</span></span>  
 <span data-ttu-id="624f6-111">다음 예제에서는`long`, `byte` 및 `decimal` 값의 문자열 표현과 함께 `TryParse`를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="624f6-111">The following examples show how to use `TryParse` with string representations of `long`, `byte`, and `decimal` values.</span></span>  
  
 <span data-ttu-id="624f6-112">[!code-cs[csProgGuideStrings#14](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-determine-whether-a-string-represents-a-numeric-value_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="624f6-112">[!code-cs[csProgGuideStrings#14](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-determine-whether-a-string-represents-a-numeric-value_1.cs)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="624f6-113">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="624f6-113">Robust Programming</span></span>  
 <span data-ttu-id="624f6-114">또한 기본 숫자 형식은 문자열이 유효한 숫자가 아닌 경우 예외를 throw하는 `Parse` 정적 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="624f6-114">Primitive numeric types also implement the `Parse` static method, which throws an exception if the string is not a valid number.</span></span> <span data-ttu-id="624f6-115">일반적으로 숫자가 유효하지 않은 경우 단순히 false를 반환하는 `TryParse`가 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="624f6-115">`TryParse` is generally more efficient because it just returns false if the number is not valid.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="624f6-116">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="624f6-116">.NET Framework Security</span></span>  
 <span data-ttu-id="624f6-117">항상 `TryParse` 또는 `Parse` 메서드를 사용하여 텍스트 상자, 콤보 상자 등의 컨트롤에서 들어오는 사용자 입력의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="624f6-117">Always use the `TryParse` or `Parse` methods to validate user input from controls such as text boxes and combo boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="624f6-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="624f6-118">See Also</span></span>  
 <span data-ttu-id="624f6-119">[방법: 바이트 배열을 정수로 변환](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md) </span><span class="sxs-lookup"><span data-stu-id="624f6-119">[How to: Convert a byte Array to an int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md) </span></span>  
 <span data-ttu-id="624f6-120">[방법: 문자열을 숫자로 변환](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md) </span><span class="sxs-lookup"><span data-stu-id="624f6-120">[How to: Convert a String to a Number](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md) </span></span>  
 <span data-ttu-id="624f6-121">[방법: 16진수 문자열과 숫자 형식 간 변환](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md) </span><span class="sxs-lookup"><span data-stu-id="624f6-121">[How to: Convert Between Hexadecimal Strings and Numeric Types](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md) </span></span>  
 <span data-ttu-id="624f6-122">[숫자 문자열 구문 분석](../../../standard/base-types/parsing-numeric.md) </span><span class="sxs-lookup"><span data-stu-id="624f6-122">[Parsing Numeric Strings](../../../standard/base-types/parsing-numeric.md) </span></span>  
 [<span data-ttu-id="624f6-123">형식 서식 지정</span><span class="sxs-lookup"><span data-stu-id="624f6-123">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)

