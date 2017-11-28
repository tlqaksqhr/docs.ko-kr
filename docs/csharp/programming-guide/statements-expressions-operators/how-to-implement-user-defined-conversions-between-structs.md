---
title: "방법: 구조체 간의 사용자 정의 변환 구현(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: user-defined conversions [C#]
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
caps.latest.revision: "11"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7d86cbd48347e6951f6b6883a385d80d68697c9c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-user-defined-conversions-between-structs-c-programming-guide"></a><span data-ttu-id="6e01e-102">방법: 구조체 간의 사용자 정의 변환 구현(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="6e01e-102">How to: Implement User-Defined Conversions Between Structs (C# Programming Guide)</span></span>
<span data-ttu-id="6e01e-103">이 예제에서는 두 개의 구조체 `RomanNumeral` 및 `BinaryNumeral`을 정의하고 두 구조체 간의 변환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6e01e-103">This example defines two structs, `RomanNumeral` and `BinaryNumeral`, and demonstrates conversions between them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e01e-104">예제</span><span class="sxs-lookup"><span data-stu-id="6e01e-104">Example</span></span>  
 [!code-csharp[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="6e01e-105">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="6e01e-105">Robust Programming</span></span>  
  
-   <span data-ttu-id="6e01e-106">앞의 예제에는 아래 문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e01e-106">In the previous example, the statement:</span></span>  
  
     [!code-csharp[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]  
  
     <span data-ttu-id="6e01e-107">위 문은 `RomanNumeral`에서 `BinaryNumeral`로의 변환을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6e01e-107">performs a conversion from a `RomanNumeral` to a `BinaryNumeral`.</span></span> <span data-ttu-id="6e01e-108">`RomanNumeral`에서 `BinaryNumeral`로의 직접 변환이 없으므로 캐스트를 사용하여 `RomanNumeral`에서 `int`로 변환한 후 다른 캐스트를 사용하여 `int`에서 `BinaryNumeral`로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="6e01e-108">Because there is no direct conversion from `RomanNumeral` to `BinaryNumeral`, a cast is used to convert from a `RomanNumeral` to an `int`, and another cast to convert from an `int` to a `BinaryNumeral`.</span></span>  
  
-   <span data-ttu-id="6e01e-109">또한 아래 문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e01e-109">Also the statement</span></span>  
  
     [!code-csharp[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]  
  
     <span data-ttu-id="6e01e-110">위 문은 `BinaryNumeral`에서 `RomanNumeral`로의 변환을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6e01e-110">performs a conversion from a `BinaryNumeral` to a `RomanNumeral`.</span></span> <span data-ttu-id="6e01e-111">`RomanNumeral`은 `BinaryNumeral`에서의 암시적 변환을 정의하기 때문에 캐스트가 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e01e-111">Because `RomanNumeral` defines an implicit conversion from `BinaryNumeral`, no cast is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e01e-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e01e-112">See Also</span></span>  
 [<span data-ttu-id="6e01e-113">C# 참조</span><span class="sxs-lookup"><span data-stu-id="6e01e-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="6e01e-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="6e01e-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6e01e-115">변환 연산자</span><span class="sxs-lookup"><span data-stu-id="6e01e-115">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)
