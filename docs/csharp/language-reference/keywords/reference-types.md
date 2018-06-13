---
title: 참조 형식(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: cca9826c658581be38866410d5f966b1c7c35772
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267341"
---
# <a name="reference-types-c-reference"></a><span data-ttu-id="c7b6f-102">참조 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="c7b6f-102">Reference Types (C# Reference)</span></span>
<span data-ttu-id="c7b6f-103">C# 형식은 참조 형식과 값 형식 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7b6f-103">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="c7b6f-104">참조 형식의 변수에는 데이터(개체)에 대한 참조가 저장되며, 값 형식의 변수에는 해당 데이터가 직접 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7b6f-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="c7b6f-105">참조 형식에서는 두 가지 변수가 같은 개체를 참조할 수 있으므로 한 변수에 대한 작업이 다른 변수에서 참조하는 개체에 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7b6f-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="c7b6f-106">값 형식에서는 각 변수에 데이터의 자체 사본이 들어 있으며 한 변수의 작업이 다른 변수에 영향을 미칠 수 없습니다(in, ref 및 out 매개 변수 제외, [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) 및 [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) 매개 변수 한정자 참조).</span><span class="sxs-lookup"><span data-stu-id="c7b6f-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of in, ref and out parameter variables; see [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) and [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter modifier).</span></span>  
  
 <span data-ttu-id="c7b6f-107">다음 키워드는 참조 형식을 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7b6f-107">The following keywords are used to declare reference types:</span></span>  
  
-   [<span data-ttu-id="c7b6f-108">class</span><span class="sxs-lookup"><span data-stu-id="c7b6f-108">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
  
-   [<span data-ttu-id="c7b6f-109">interface</span><span class="sxs-lookup"><span data-stu-id="c7b6f-109">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
  
-   [<span data-ttu-id="c7b6f-110">delegate</span><span class="sxs-lookup"><span data-stu-id="c7b6f-110">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)  
  
 <span data-ttu-id="c7b6f-111">C#는 다음과 같은 기본 참조 형식도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c7b6f-111">C# also provides the following built-in reference types:</span></span>  
  
-   [<span data-ttu-id="c7b6f-112">dynamic</span><span class="sxs-lookup"><span data-stu-id="c7b6f-112">dynamic</span></span>](../../../csharp/language-reference/keywords/dynamic.md)  
  
-   [<span data-ttu-id="c7b6f-113">object</span><span class="sxs-lookup"><span data-stu-id="c7b6f-113">object</span></span>](../../../csharp/language-reference/keywords/object.md)  
  
-   [<span data-ttu-id="c7b6f-114">string</span><span class="sxs-lookup"><span data-stu-id="c7b6f-114">string</span></span>](../../../csharp/language-reference/keywords/string.md)  
  
## <a name="see-also"></a><span data-ttu-id="c7b6f-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7b6f-115">See Also</span></span>  
 [<span data-ttu-id="c7b6f-116">C# 참조</span><span class="sxs-lookup"><span data-stu-id="c7b6f-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="c7b6f-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="c7b6f-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c7b6f-118">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="c7b6f-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="c7b6f-119">유형</span><span class="sxs-lookup"><span data-stu-id="c7b6f-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="c7b6f-120">값 형식</span><span class="sxs-lookup"><span data-stu-id="c7b6f-120">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)
