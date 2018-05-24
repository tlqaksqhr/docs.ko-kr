---
title: Checked 및 Unchecked(C# 참조)
ms.date: 05/15/2018
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
ms.openlocfilehash: f8e292a67fab49b5fc3616e438d063eca2617274
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/18/2018
---
# <a name="checked-and-unchecked-c-reference"></a><span data-ttu-id="fef3a-102">Checked 및 Unchecked(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="fef3a-102">Checked and Unchecked (C# Reference)</span></span>
<span data-ttu-id="fef3a-103">checked 컨텍스트 또는 unchecked 컨텍스트에서 C# 문을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef3a-103">C# statements can execute in either checked or unchecked context.</span></span> <span data-ttu-id="fef3a-104">checked 컨텍스트에서는 산술 오버플로가 있으면 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fef3a-104">In a checked context, arithmetic overflow raises an exception.</span></span> <span data-ttu-id="fef3a-105">unchecked 컨텍스트에서는 산술 오버플로가 무시되고 대상 형식에 맞지 않는 상위 비트가 삭제되어 해당 결과가 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="fef3a-105">In an unchecked context, arithmetic overflow is ignored and the result is truncated by discarding any high-order bits that don't fit in the destination type.</span></span>  
  
-   <span data-ttu-id="fef3a-106">[checked](checked.md) checked 컨텍스트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fef3a-106">[checked](checked.md) Specify checked context.</span></span>  
  
-   <span data-ttu-id="fef3a-107">[unchecked](unchecked.md) unchecked 컨텍스트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fef3a-107">[unchecked](unchecked.md) Specify unchecked context.</span></span>  
  
 <span data-ttu-id="fef3a-108">오버플로 검사의 영향을 받는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fef3a-108">The following operations are affected by the overflow checking:</span></span>  
  
-   <span data-ttu-id="fef3a-109">정수 계열 형식에 다음의 미리 정의된 연산자를 사용하는 식</span><span class="sxs-lookup"><span data-stu-id="fef3a-109">Expressions using the following predefined operators on integral types:</span></span>  
  
     <span data-ttu-id="fef3a-110">`++`, `--`, `-`(단항), `+`, `-`, `*`, `/`</span><span class="sxs-lookup"><span data-stu-id="fef3a-110">`++`, `--`, unary `-`, `+`, `-`, `*`, `/`</span></span>  
  
-   <span data-ttu-id="fef3a-111">정수 형식 간이나 `float` 또는 `double`에서 정수 형식으로의 명시적 숫자 변환</span><span class="sxs-lookup"><span data-stu-id="fef3a-111">Explicit numeric conversions between integral types, or from `float` or `double` to an integral type.</span></span>  
  
 <span data-ttu-id="fef3a-112">`checked`도 `unchecked`도 지정하지 않으면 상수가 아닌 식(런타임에 계산되는 식)의 기본 컨텍스트는 [-checked](../compiler-options/checked-compiler-option.md) 컴파일러 옵션의 값으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="fef3a-112">If neither `checked` nor `unchecked` is specified, the default context for non-constant expressions (expressions that are evaluated at run time) is defined by the value of the [-checked](../compiler-options/checked-compiler-option.md) compiler option.</span></span> <span data-ttu-id="fef3a-113">기본적으로 이 옵션의 값은 설정되지 않으며 unchecked 컨텍스트에서 산술 연산이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fef3a-113">By default the value of that option is unset and arithmetic operations are executed in an unchecked context.</span></span>
 
 <span data-ttu-id="fef3a-114">상수 식(컴파일 시간에 완전히 계산될 수 있는 식)의 경우 기본 컨텍스트는 항상 checked입니다.</span><span class="sxs-lookup"><span data-stu-id="fef3a-114">For constant expressions (expressions that can be fully evaluated at compile time), the default context is always checked.</span></span> <span data-ttu-id="fef3a-115">상수 식이 unchecked 컨텍스트에 명시적으로 배치되지 않는 경우 식에 대한 컴파일 시간 계산 중 발생하는 오버플로로 인해 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fef3a-115">Unless a constant expression is explicitly placed in an unchecked context, overflows that occur during the compile-time evaluation of the expression cause compile-time errors.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fef3a-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fef3a-116">See Also</span></span>  
 [<span data-ttu-id="fef3a-117">C# 참조</span><span class="sxs-lookup"><span data-stu-id="fef3a-117">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="fef3a-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="fef3a-118">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="fef3a-119">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="fef3a-119">C# Keywords</span></span>](index.md)  
 [<span data-ttu-id="fef3a-120">문 키워드</span><span class="sxs-lookup"><span data-stu-id="fef3a-120">Statement Keywords</span></span>](statement-keywords.md)
