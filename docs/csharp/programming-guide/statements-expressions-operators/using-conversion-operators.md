---
title: "변환 연산자 사용(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- conversions [C#], operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
- implicit conversion operators [C#]
- explicit conversion operators [C#]
ms.assetid: caf36e89-c6c0-4b87-9f9e-85780a45c9a4
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5a43332df795d853c3060a604360adeaea5e3fd4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="using-conversion-operators-c-programming-guide"></a><span data-ttu-id="e715e-102">변환 연산자 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="e715e-102">Using Conversion Operators (C# Programming Guide)</span></span>
<span data-ttu-id="e715e-103">쉽게 사용할 수 있는 `implicit` 변환 연산자 또는 코드를 읽는 사람에게 형식을 변환함을 명확하게 나타내는 `explicit` 변환 연산자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e715e-103">You can use `implicit` conversion operators, which are easier to use, or `explicit` conversion operators, which clearly indicate to anyone reading the code that you're converting a type.</span></span> <span data-ttu-id="e715e-104">이 항목에서는 두 형식의 변환 연산자를 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e715e-104">This topic demonstrates both types of conversion operator.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e715e-105">단순 형식 변환에 대한 자세한 내용은 [방법: 문자열을 숫자로 변환](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [방법: 바이트 배열을 정수로 변환](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [방법: 16진수 문자열과 숫자 형식 간 변환](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md) 또는 <xref:System.Convert>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e715e-105">For information about simple type conversions, see [How to: Convert a String to a Number](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [How to: Convert a byte Array to an int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [How to: Convert Between Hexadecimal Strings and Numeric Types](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md), or <xref:System.Convert>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e715e-106">예제</span><span class="sxs-lookup"><span data-stu-id="e715e-106">Example</span></span>  
 <span data-ttu-id="e715e-107">명시적 변환 연산자의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e715e-107">This is an example of an explicit conversion operator.</span></span> <span data-ttu-id="e715e-108">이 연산자는 <xref:System.Byte> 형식에서 `Digit`라는 값 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="e715e-108">This operator converts from the type <xref:System.Byte> to a value type called `Digit`.</span></span> <span data-ttu-id="e715e-109">일부 바이트는 숫자로 변환할 수 없기 때문에 변환이 명시적이므로 `Main` 메서드와 같이 캐스트를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e715e-109">Because not all bytes can be converted to a digit, the conversion is explicit, meaning that a cast must be used, as shown in the `Main` method.</span></span>  
  
 [!code-csharp[csProgGuideStatements#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-conversion-operators_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="e715e-110">예제</span><span class="sxs-lookup"><span data-stu-id="e715e-110">Example</span></span>  
 <span data-ttu-id="e715e-111">이 예제에서는 앞의 예제에서 수행한 작업을 실행 취소하는 변환 연산자를 정의하여 암시적 변환 연산자를 보여 줍니다. 이 연산자는 `Digit`라는 값 클래스에서 정수 <xref:System.Byte> 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="e715e-111">This example demonstrates an implicit conversion operator by defining a conversion operator that undoes what the previous example did: it converts from a value class called `Digit` to the integral <xref:System.Byte> type.</span></span> <span data-ttu-id="e715e-112">모든 숫자를 <xref:System.Byte>로 변환할 수 있으므로 사용자에게 변환을 명시적으로 지정하도록 요구할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e715e-112">Because any digit can be converted to a <xref:System.Byte>, there's no need to force users to be explicit about the conversion.</span></span>  
  
 [!code-csharp[csProgGuideStatements#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-conversion-operators_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="e715e-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e715e-113">See Also</span></span>  
 [<span data-ttu-id="e715e-114">C# 참조</span><span class="sxs-lookup"><span data-stu-id="e715e-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e715e-115">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="e715e-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e715e-116">변환 연산자</span><span class="sxs-lookup"><span data-stu-id="e715e-116">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)  
 [<span data-ttu-id="e715e-117">is</span><span class="sxs-lookup"><span data-stu-id="e715e-117">is</span></span>](../../../csharp/language-reference/keywords/is.md)
