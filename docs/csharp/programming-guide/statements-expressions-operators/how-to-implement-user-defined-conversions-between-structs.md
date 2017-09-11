---
title: "방법: 구조체 간의 사용자 정의 변환 구현(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- user-defined conversions [C#]
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
caps.latest.revision: 11
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
ms.openlocfilehash: cc8856bb3bf8943c1b6648f7d81447a3e59b9489
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-implement-user-defined-conversions-between-structs-c-programming-guide"></a><span data-ttu-id="eb5f1-102">방법: 구조체 간의 사용자 정의 변환 구현(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="eb5f1-102">How to: Implement User-Defined Conversions Between Structs (C# Programming Guide)</span></span>
<span data-ttu-id="eb5f1-103">이 예제에서는 두 개의 구조체 `RomanNumeral` 및 `BinaryNumeral`을 정의하고 두 구조체 간의 변환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eb5f1-103">This example defines two structs, `RomanNumeral` and `BinaryNumeral`, and demonstrates conversions between them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb5f1-104">예제</span><span class="sxs-lookup"><span data-stu-id="eb5f1-104">Example</span></span>  
 <span data-ttu-id="eb5f1-105">[!code-cs[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="eb5f1-105">[!code-cs[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="eb5f1-106">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="eb5f1-106">Robust Programming</span></span>  
  
-   <span data-ttu-id="eb5f1-107">앞의 예제에는 아래 문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb5f1-107">In the previous example, the statement:</span></span>  
  
     <span data-ttu-id="eb5f1-108">[!code-cs[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="eb5f1-108">[!code-cs[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]</span></span>  
  
     <span data-ttu-id="eb5f1-109">위 문은 `RomanNumeral`에서 `BinaryNumeral`로의 변환을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5f1-109">performs a conversion from a `RomanNumeral` to a `BinaryNumeral`.</span></span> <span data-ttu-id="eb5f1-110">`RomanNumeral`에서 `BinaryNumeral`로의 직접 변환이 없으므로 캐스트를 사용하여 `RomanNumeral`에서 `int`로 변환한 후 다른 캐스트를 사용하여 `int`에서 `BinaryNumeral`로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5f1-110">Because there is no direct conversion from `RomanNumeral` to `BinaryNumeral`, a cast is used to convert from a `RomanNumeral` to an `int`, and another cast to convert from an `int` to a `BinaryNumeral`.</span></span>  
  
-   <span data-ttu-id="eb5f1-111">또한 아래 문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb5f1-111">Also the statement</span></span>  
  
     <span data-ttu-id="eb5f1-112">[!code-cs[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="eb5f1-112">[!code-cs[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]</span></span>  
  
     <span data-ttu-id="eb5f1-113">위 문은 `BinaryNumeral`에서 `RomanNumeral`로의 변환을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb5f1-113">performs a conversion from a `BinaryNumeral` to a `RomanNumeral`.</span></span> <span data-ttu-id="eb5f1-114">`RomanNumeral`은 `BinaryNumeral`에서의 암시적 변환을 정의하기 때문에 캐스트가 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eb5f1-114">Because `RomanNumeral` defines an implicit conversion from `BinaryNumeral`, no cast is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb5f1-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eb5f1-115">See Also</span></span>  
 <span data-ttu-id="eb5f1-116">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="eb5f1-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="eb5f1-117">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="eb5f1-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="eb5f1-118">변환 연산자</span><span class="sxs-lookup"><span data-stu-id="eb5f1-118">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)

