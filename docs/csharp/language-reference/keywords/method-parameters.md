---
title: "메서드 매개 변수(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b20d2d233350cfb9de55cbd07e722082ec311597
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2018
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="62b78-102">메서드 매개 변수(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="62b78-102">Method Parameters (C# Reference)</span></span>

<span data-ttu-id="62b78-103">[in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) 또는 [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) 없이 메서드에 대해 선언된 매개 변수는 값으로 호출된 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="62b78-103">Parameters declared for a method without [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), are passed to the called method by value.</span></span> <span data-ttu-id="62b78-104">메서드에서 해당 값을 변경할 수 있지만, 제어가 호출하는 프로시저로 다시 전달되면 변경된 값이 보존되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62b78-104">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="62b78-105">메서드 매개 변수 키워드를 사용하여 이 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62b78-105">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="62b78-106">이 섹션에서는 메서드 매개 변수를 선언할 때 사용할 수 있는 키워드를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="62b78-106">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
-   [<span data-ttu-id="62b78-107">params</span><span class="sxs-lookup"><span data-stu-id="62b78-107">params</span></span>](../../../csharp/language-reference/keywords/params.md)  
  
-   [<span data-ttu-id="62b78-108">in</span><span class="sxs-lookup"><span data-stu-id="62b78-108">in</span></span>](../../../csharp/language-reference/keywords/in-parameter-modifier.md)  
  
-   [<span data-ttu-id="62b78-109">ref</span><span class="sxs-lookup"><span data-stu-id="62b78-109">ref</span></span>](../../../csharp/language-reference/keywords/ref.md)  
  
-   [<span data-ttu-id="62b78-110">out</span><span class="sxs-lookup"><span data-stu-id="62b78-110">out</span></span>](../../../csharp/language-reference/keywords/out-parameter-modifier.md)  
  
## <a name="see-also"></a><span data-ttu-id="62b78-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="62b78-111">See Also</span></span>  
 [<span data-ttu-id="62b78-112">C# 참조</span><span class="sxs-lookup"><span data-stu-id="62b78-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="62b78-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="62b78-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="62b78-114">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="62b78-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
