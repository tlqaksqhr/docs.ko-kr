---
title: "#<a name=\"if-c-reference\"></a>if(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '#if'
helpviewer_keywords: '#if directive [C#]'
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e4e3b79f64f5190d48d7248726ecdf031ad685e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="if-c-reference"></a><span data-ttu-id="707fd-102">#if(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="707fd-102">#if (C# Reference)</span></span>
<span data-ttu-id="707fd-103">C# 컴파일러는 `#if` 지시문과 [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) 지시문이 차례로 확인되면 지정된 기호가 정의되어 있어야 지시문 사이의 코드를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="707fd-103">When the C# compiler encounters an `#if` directive, followed eventually by an [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) directive, it will compile the code between the directives only if the specified symbol is defined.</span></span>  <span data-ttu-id="707fd-104">C 및 C++와 달리 기호에 숫자 값을 할당할 수는 없습니다. C#의 #if 문은 부울이며 기호가 정의되었는지 여부만을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="707fd-104">Unlike C and C++, you cannot assign a numeric value to a symbol; the #if statement in C# is Boolean and only tests whether the symbol has been defined or not.</span></span> <span data-ttu-id="707fd-105">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="707fd-105">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
 <span data-ttu-id="707fd-106">[==](../../../csharp/language-reference/operators/equality-comparison-operator.md)(같음), [!=](../../../csharp/language-reference/operators/not-equal-operator.md)(같지 않음) 연산자는 [true](../../../csharp/language-reference/keywords/true.md) 또는 [false](../../../csharp/language-reference/keywords/false.md)를 테스트할 때만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="707fd-106">You can use the operators [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) (equality), [!=](../../../csharp/language-reference/operators/not-equal-operator.md) (inequality) only to test for [true](../../../csharp/language-reference/keywords/true.md) or [false](../../../csharp/language-reference/keywords/false.md) .</span></span> <span data-ttu-id="707fd-107">true가 반환되면 기호가 정의된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="707fd-107">True means the symbol is defined.</span></span> <span data-ttu-id="707fd-108">`#if DEBUG` 문의 의미는 `#if (DEBUG == true)`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="707fd-108">The statement `#if DEBUG` has the same meaning as `#if (DEBUG == true)`.</span></span> <span data-ttu-id="707fd-109">[&&](../../../csharp/language-reference/operators/conditional-and-operator.md)(및), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)(또는), [!](../../../csharp/language-reference/operators/logical-negation-operator.md)(아님)</span><span class="sxs-lookup"><span data-stu-id="707fd-109">You can use the operators [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) (and), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) (or), and [!](../../../csharp/language-reference/operators/logical-negation-operator.md)</span></span> <span data-ttu-id="707fd-110">연산자를 사용하면 여러 기호가 정의되었는지 여부를 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="707fd-110">(not) to evaluate whether multiple symbols have been defined.</span></span> <span data-ttu-id="707fd-111">기호와 연산자를 괄호로 묶을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="707fd-111">You can also group symbols and operators with parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="707fd-112">설명</span><span class="sxs-lookup"><span data-stu-id="707fd-112">Remarks</span></span>  
 <span data-ttu-id="707fd-113">`#if`를 [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) 및 [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) 지시문과 함께 사용하면 하나 이상의 기호 유무에 따라 코드를 포함하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="707fd-113">`#if`, along with the [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md), and [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) directives, lets you include or exclude code based on the existence of one or more symbols.</span></span> <span data-ttu-id="707fd-114">따라서 코드를 디버그 빌드용으로 컴파일하거나 특정 구성용으로 컴파일할 때 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="707fd-114">This can be useful when compiling code for a debug build or when compiling for a specific configuration.</span></span>  
  
 <span data-ttu-id="707fd-115">`#if` 지시문으로 시작되는 조건부 지시문은 `#endif` 지시문을 사용하여 명시적으로 종료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="707fd-115">A conditional directive beginning with a `#if` directive must explicitly be terminated with a `#endif` directive.</span></span>  
  
 <span data-ttu-id="707fd-116">`#define`을 사용하면 기호를 정의할 수 있습니다. 그러면 `#if` 지시문으로 전달되는 식으로 해당 기호를 사용하는 경우 식이 `true`로 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="707fd-116">`#define` lets you define a symbol, such that, by using the symbol as the expression passed to the `#if` directive, the expression will evaluate to `true`.</span></span>  
  
 <span data-ttu-id="707fd-117">[/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) 컴파일러 옵션으로 기호를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="707fd-117">You can also define a symbol with the [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="707fd-118">[#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)로 기호 정의를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="707fd-118">You can undefine a symbol with [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span></span>  
  
 <span data-ttu-id="707fd-119">`/define` 또는 `#define`으로 정의하는 기호는 동일한 이름의 변수와 충돌하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="707fd-119">A symbol that you define with `/define` or with `#define` does not conflict with a variable of the same name.</span></span> <span data-ttu-id="707fd-120">즉, 변수 이름이 전처리기 지시문에 전달되지 않아야 하며 전처리기 지시문을 통해서만 기호를 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="707fd-120">That is, a variable name should not be passed to a preprocessor directive and a symbol can only be evaluated by a preprocessor directive.</span></span>  
  
 <span data-ttu-id="707fd-121">`#define`을 사용하여 만든 기호의 범위는 해당 기호가 정의된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="707fd-121">The scope of a symbol created with `#define` is the file in which it was defined.</span></span>  
  
## <a name="example"></a><span data-ttu-id="707fd-122">예제</span><span class="sxs-lookup"><span data-stu-id="707fd-122">Example</span></span>  
  
```csharp
// preprocessor_if.cs  
#define DEBUG
#define MYTEST  
using System;  
public class MyClass   
{  
    static void Main()   
    {  
#if (DEBUG && !MYTEST)  
        Console.WriteLine("DEBUG is defined");  
#elif (!DEBUG && MYTEST)  
        Console.WriteLine("MYTEST is defined");  
#elif (DEBUG && MYTEST)  
        Console.WriteLine("DEBUG and MYTEST are defined");  
#else  
        Console.WriteLine("DEBUG and MYTEST are not defined");  
#endif  
    }  
}  
```  
  
 <span data-ttu-id="707fd-123">**DEBUG and MYTEST are defined**</span><span class="sxs-lookup"><span data-stu-id="707fd-123">**DEBUG and MYTEST are defined**</span></span>  
## <a name="see-also"></a><span data-ttu-id="707fd-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="707fd-124">See Also</span></span>  
 [<span data-ttu-id="707fd-125">C# 참조</span><span class="sxs-lookup"><span data-stu-id="707fd-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="707fd-126">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="707fd-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="707fd-127">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="707fd-127">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
