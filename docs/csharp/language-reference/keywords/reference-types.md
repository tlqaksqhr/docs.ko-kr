---
title: "참조 형식(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.referencetypes
dev_langs:
- CSharp
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
caps.latest.revision: 15
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
ms.openlocfilehash: ed7b9c8ed4aa1136c09049c8ffd6c68beeeb2a48
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="reference-types-c-reference"></a><span data-ttu-id="2e1d8-102">참조 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="2e1d8-102">Reference Types (C# Reference)</span></span>
<span data-ttu-id="2e1d8-103">C# 형식은 참조 형식과 값 형식 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e1d8-103">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="2e1d8-104">참조 형식의 변수에는 데이터(개체)에 대한 참조가 저장되며, 값 형식의 변수에는 해당 데이터가 직접 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e1d8-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="2e1d8-105">참조 형식에서는 두 가지 변수가 같은 개체를 참조할 수 있으므로 한 변수에 대한 작업이 다른 변수에서 참조하는 개체에 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e1d8-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="2e1d8-106">값 형식에서는 각 변수에 데이터의 자체 사본이 들어 있으며 한 변수의 작업이 다른 변수에 영향을 미칠 수 없습니다(ref 및 out 매개 변수 제외, [ref](../../../csharp/language-reference/keywords/ref.md) 및 [out 매개 변수 한정자](../../../csharp/language-reference/keywords/out-parameter-modifier.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="2e1d8-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of ref and out parameter variables, see [ref](../../../csharp/language-reference/keywords/ref.md) and [out parameter modifier](../../../csharp/language-reference/keywords/out-parameter-modifier.md)).</span></span>  
  
 <span data-ttu-id="2e1d8-107">다음 키워드는 참조 형식을 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e1d8-107">The following keywords are used to declare reference types:</span></span>  
  
-   [<span data-ttu-id="2e1d8-108">class</span><span class="sxs-lookup"><span data-stu-id="2e1d8-108">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
  
-   [<span data-ttu-id="2e1d8-109">interface</span><span class="sxs-lookup"><span data-stu-id="2e1d8-109">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
  
-   [<span data-ttu-id="2e1d8-110">delegate</span><span class="sxs-lookup"><span data-stu-id="2e1d8-110">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)  
  
 <span data-ttu-id="2e1d8-111">C#는 다음과 같은 기본 참조 형식도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2e1d8-111">C# also provides the following built-in reference types:</span></span>  
  
-   [<span data-ttu-id="2e1d8-112">dynamic</span><span class="sxs-lookup"><span data-stu-id="2e1d8-112">dynamic</span></span>](../../../csharp/language-reference/keywords/dynamic.md)  
  
-   [<span data-ttu-id="2e1d8-113">object</span><span class="sxs-lookup"><span data-stu-id="2e1d8-113">object</span></span>](../../../csharp/language-reference/keywords/object.md)  
  
-   [<span data-ttu-id="2e1d8-114">string</span><span class="sxs-lookup"><span data-stu-id="2e1d8-114">string</span></span>](../../../csharp/language-reference/keywords/string.md)  
  
## <a name="see-also"></a><span data-ttu-id="2e1d8-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2e1d8-115">See Also</span></span>  
 <span data-ttu-id="2e1d8-116">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="2e1d8-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="2e1d8-117">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2e1d8-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="2e1d8-118">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="2e1d8-118">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="2e1d8-119">[형식](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="2e1d8-119">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 [<span data-ttu-id="2e1d8-120">값 형식</span><span class="sxs-lookup"><span data-stu-id="2e1d8-120">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)

