---
title: "매개 변수 전달(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d9e0e06d67f9da39c6b55f91e35d4a75b43353f3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="passing-parameters-c-programming-guide"></a><span data-ttu-id="2abb6-102">매개 변수 전달(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="2abb6-102">Passing Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="2abb6-103">C#에서는 인수를 값 또는 참조로 매개 변수에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2abb6-103">In C#, arguments can be passed to parameters either by value or by reference.</span></span> <span data-ttu-id="2abb6-104">참조로 전달하면 함수 멤버, 메서드, 속성, 인덱서, 연산자 및 생성자가 매개 변수의 값을 변경하고 해당 변경 내용을 호출 환경에서 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2abb6-104">Passing by reference enables function members, methods, properties, indexers, operators, and constructors to change the value of the parameters and have that change persist in the calling environment.</span></span> <span data-ttu-id="2abb6-105">참조로 매개 변수를 전달하려면 `ref` 또는 `out` 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2abb6-105">To pass a parameter by reference, use the `ref` or `out` keyword.</span></span> <span data-ttu-id="2abb6-106">간단히 설명하기 위해 이 항목의 예제에서는 `ref` 키워드만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2abb6-106">For simplicity, only the `ref` keyword is used in the examples in this topic.</span></span> <span data-ttu-id="2abb6-107">`ref` 및 `out` 간의 차이점에 대한 자세한 내용은 [ref](../../../csharp/language-reference/keywords/ref.md), [out](../../../csharp/language-reference/keywords/out.md) 및 [ref 및 out을 사용하여 배열 전달](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2abb6-107">For more information about the difference between `ref` and `out`, see [ref](../../../csharp/language-reference/keywords/ref.md), [out](../../../csharp/language-reference/keywords/out.md), and [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="2abb6-108">다음 예제에서는 값 및 참조 매개 변수 간의 차이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2abb6-108">The following example illustrates the difference between value and reference parameters.</span></span>  
  
 [!code-csharp[csProgGuideParameters#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-parameters_1.cs)]  
  
 <span data-ttu-id="2abb6-109">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2abb6-109">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="2abb6-110">값 형식 매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="2abb6-110">Passing Value-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md)  
  
-   [<span data-ttu-id="2abb6-111">참조 형식 매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="2abb6-111">Passing Reference-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="2abb6-112">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="2abb6-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2abb6-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2abb6-113">See Also</span></span>  
 [<span data-ttu-id="2abb6-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="2abb6-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2abb6-115">메서드</span><span class="sxs-lookup"><span data-stu-id="2abb6-115">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)
