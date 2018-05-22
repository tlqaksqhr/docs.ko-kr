---
title: 메서드 매개 변수(C# 참조)
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
ms.openlocfilehash: 8a8d300661eec42030900dd9ee85a17e66aa0922
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="e62f8-102">메서드 매개 변수(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="e62f8-102">Method Parameters (C# Reference)</span></span>

<span data-ttu-id="e62f8-103">[in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) 또는 [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) 없이 메서드에 대해 선언된 매개 변수는 값으로 호출된 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="e62f8-103">Parameters declared for a method without [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), are passed to the called method by value.</span></span> <span data-ttu-id="e62f8-104">메서드에서 해당 값을 변경할 수 있지만, 제어가 호출하는 프로시저로 다시 전달되면 변경된 값이 보존되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e62f8-104">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="e62f8-105">메서드 매개 변수 키워드를 사용하여 이 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e62f8-105">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="e62f8-106">이 섹션에서는 메서드 매개 변수를 선언할 때 사용할 수 있는 키워드를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e62f8-106">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
-   <span data-ttu-id="e62f8-107">[params](../../../csharp/language-reference/keywords/params.md)는 이 매개 변수가 가변 개수의 인수를 사용할 수 있음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e62f8-107">[params](../../../csharp/language-reference/keywords/params.md) specifies that this parameter may take a variable number of arguments.</span></span>
  
-   <span data-ttu-id="e62f8-108">[in](../../../csharp/language-reference/keywords/in-parameter-modifier.md)은 이 매개 변수를 참조로 전달할 수 있지만 호출된 메서드로만 읽을 수 있음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e62f8-108">[in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) specifies that this parameter is passed by reference but is only read by the called method.</span></span>
  
-   <span data-ttu-id="e62f8-109">[ref](../../../csharp/language-reference/keywords/ref.md)는 이 매개 변수를 참조로 전달할 수 있고 호출된 메서드로 읽거나 쓸 수 있음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e62f8-109">[ref](../../../csharp/language-reference/keywords/ref.md) specifies that this parameter is passed by reference and may be read or written by the called method.</span></span>
  
-   <span data-ttu-id="e62f8-110">[out](../../../csharp/language-reference/keywords/out-parameter-modifier.md)는 이 매개 변수가 참조로 전달되고 호출된 메서드에 의해 기록되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e62f8-110">[out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) specifies that this parameter is passed by reference and is written by the called method.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e62f8-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e62f8-111">See Also</span></span>  
 [<span data-ttu-id="e62f8-112">C# 참조</span><span class="sxs-lookup"><span data-stu-id="e62f8-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e62f8-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="e62f8-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e62f8-114">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="e62f8-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
