---
title: "#<a name=\"define-c-reference\"></a>define(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#define'
dev_langs:
- CSharp
helpviewer_keywords:
- '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
caps.latest.revision: 22
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
ms.openlocfilehash: 8ace15f79480c9aeb0fcb4c7d46c207d4904cef0
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="define-c-reference"></a><span data-ttu-id="6ae8e-102">#define(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="6ae8e-102">#define (C# Reference)</span></span>
<span data-ttu-id="6ae8e-103">`#define`을 사용하여 기호를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-103">You use `#define` to define a symbol.</span></span> <span data-ttu-id="6ae8e-104">기호를 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 지시문에 전달되는 식으로 사용하는 경우 식이 다음 예제와 같이 `true`로 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-104">When you use the symbol as the expression that's passed to the [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive, the expression will evaluate to `true`, as the following example shows:</span></span>  
  
 <span data-ttu-id="6ae8e-105">`#`  `define`   `DEBUG`</span><span class="sxs-lookup"><span data-stu-id="6ae8e-105">`#`  `define`   `DEBUG`</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ae8e-106">설명</span><span class="sxs-lookup"><span data-stu-id="6ae8e-106">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ae8e-107">C 및 C++에서 일반적으로 수행하듯이 `#define` 지시문을 사용하여 상수 값을 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-107">The `#define` directive cannot be used to declare constant values as is typically done in C and C++.</span></span> <span data-ttu-id="6ae8e-108">C#의 상수는 클래스 또는 구조체의 정적 멤버로 가장 잘 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-108">Constants in C# are best defined as static members of a class or struct.</span></span> <span data-ttu-id="6ae8e-109">이러한 상수가 여러 개 있는 경우 상수를 포함할 별도의 "Constants" 클래스를 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-109">If you have several such constants, consider creating a separate "Constants" class to hold them.</span></span>  
  
 <span data-ttu-id="6ae8e-110">기호를 사용하여 컴파일 조건을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-110">Symbols can be used to specify conditions for compilation.</span></span> <span data-ttu-id="6ae8e-111">[#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 또는 [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md)를 사용하여 기호를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-111">You can test for the symbol with either [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) or [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md).</span></span> <span data-ttu-id="6ae8e-112">`conditional` 특성을 사용하여 조건부 컴파일을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-112">You can also use the `conditional` attribute to perform conditional compilation.</span></span>  
  
 <span data-ttu-id="6ae8e-113">기호를 정의할 수 있지만 기호에 값을 할당할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-113">You can define a symbol, but you cannot assign a value to a symbol.</span></span> <span data-ttu-id="6ae8e-114">`#define` 지시문은 파일에서 전처리기 지시문이 아닌 명령을 사용하기 전에 나와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-114">The `#define` directive must appear in the file before you use any instructions that aren't also preprocessor directives.</span></span>  
  
 <span data-ttu-id="6ae8e-115">[/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) 컴파일러 옵션으로 기호를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-115">You can also define a symbol with the [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="6ae8e-116">[#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)로 기호 정의를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-116">You can undefine a symbol with [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span></span>  
  
 <span data-ttu-id="6ae8e-117">`/define` 또는 `#define`으로 정의하는 기호는 동일한 이름의 변수와 충돌하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-117">A symbol that you define with `/define` or with `#define` does not conflict with a variable of the same name.</span></span> <span data-ttu-id="6ae8e-118">즉, 변수 이름이 전처리기 지시문에 전달되지 않아야 하며, 전처리기 지시문을 통해서만 기호를 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-118">That is, a variable name should not be passed to a preprocessor directive and a symbol can only be evaluated by a preprocessor directive.</span></span>  
  
 <span data-ttu-id="6ae8e-119">`#define`을 사용하여 만든 기호의 범위는 기호가 정의된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-119">The scope of a symbol that was created by using `#define` is the file in which the symbol was defined.</span></span>  
  
 <span data-ttu-id="6ae8e-120">다음 예제와 같이, `#define` 지시문을 파일 맨 위에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-120">As the following example shows, you must put `#define` directives at the top of the file.</span></span>  
  
```csharp  
#define DEBUG  
//#define TRACE  
#undef TRACE  
  
using System;  
  
public class TestDefine  
{  
    static void Main()  
    {  
#if (DEBUG)  
        Console.WriteLine("Debugging is enabled.");  
#endif  
  
#if (TRACE)  
     Console.WriteLine("Tracing is enabled.");  
#endif  
    }  
}  
// Output:  
// Debugging is enabled.  
```  
  
 <span data-ttu-id="6ae8e-121">기호 정의를 해제하는 방법의 예는 [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ae8e-121">For an example of how to undefine a symbol, see [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ae8e-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ae8e-122">See Also</span></span>  
 <span data-ttu-id="6ae8e-123">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="6ae8e-123">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="6ae8e-124">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6ae8e-124">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6ae8e-125">[C# 전처리기 지시문](../../../csharp/language-reference/preprocessor-directives/index.md) </span><span class="sxs-lookup"><span data-stu-id="6ae8e-125">[C# Preprocessor Directives](../../../csharp/language-reference/preprocessor-directives/index.md) </span></span>  
 <span data-ttu-id="6ae8e-126">[const](../../../csharp/language-reference/keywords/const.md) </span><span class="sxs-lookup"><span data-stu-id="6ae8e-126">[const](../../../csharp/language-reference/keywords/const.md) </span></span>  
 <span data-ttu-id="6ae8e-127">[방법: 추적 및 디버그를 사용한 조건부 컴파일](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md) </span><span class="sxs-lookup"><span data-stu-id="6ae8e-127">[How to: Compile Conditionally with Trace and Debug](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md) </span></span>  
 <span data-ttu-id="6ae8e-128">[#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) </span><span class="sxs-lookup"><span data-stu-id="6ae8e-128">[#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) </span></span>  
 [<span data-ttu-id="6ae8e-129">#if</span><span class="sxs-lookup"><span data-stu-id="6ae8e-129">#if</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)

