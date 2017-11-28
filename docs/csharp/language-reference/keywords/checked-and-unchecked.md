---
title: "Checked 및 Unchecked(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4b7b18b39dbfa7ed0818d9ea6e9e62ef79a9f5b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="checked-and-unchecked-c-reference"></a><span data-ttu-id="c6efe-102">Checked 및 Unchecked(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="c6efe-102">Checked and Unchecked (C# Reference)</span></span>
<span data-ttu-id="c6efe-103">checked 컨텍스트 또는 unchecked 컨텍스트에서 C# 문을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6efe-103">C# statements can execute in either checked or unchecked context.</span></span> <span data-ttu-id="c6efe-104">checked 컨텍스트에서는 산술 오버플로가 있으면 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c6efe-104">In a checked context, arithmetic overflow raises an exception.</span></span> <span data-ttu-id="c6efe-105">unchecked 컨텍스트에서는 산술 오버플로가 무시되며 결과가 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="c6efe-105">In an unchecked context, arithmetic overflow is ignored and the result is truncated.</span></span>  
  
-   <span data-ttu-id="c6efe-106">[checked](../../../csharp/language-reference/keywords/checked.md) checked 컨텍스트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c6efe-106">[checked](../../../csharp/language-reference/keywords/checked.md) Specify checked context.</span></span>  
  
-   <span data-ttu-id="c6efe-107">[unchecked](../../../csharp/language-reference/keywords/unchecked.md) unchecked 컨텍스트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c6efe-107">[unchecked](../../../csharp/language-reference/keywords/unchecked.md) Specify unchecked context.</span></span>  
  
 <span data-ttu-id="c6efe-108">`checked`도 `unchecked`도 지정하지 않으면 기본 컨텍스트는 컴파일러 옵션 등의 외부 요인에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="c6efe-108">If neither `checked` nor `unchecked` is specified, the default context depends on external factors such as compiler options.</span></span>  
  
 <span data-ttu-id="c6efe-109">오버플로 검사의 영향을 받는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c6efe-109">The following operations are affected by the overflow checking:</span></span>  
  
-   <span data-ttu-id="c6efe-110">정수 계열 형식에 다음의 미리 정의된 연산자를 사용하는 식</span><span class="sxs-lookup"><span data-stu-id="c6efe-110">Expressions using the following predefined operators on integral types:</span></span>  
  
     <span data-ttu-id="c6efe-111">`++` `--` - (단항)   `+` -   `*` `/`</span><span class="sxs-lookup"><span data-stu-id="c6efe-111">`++` `--` - (unary)   `+` -   `*` `/`</span></span>  
  
-   <span data-ttu-id="c6efe-112">정수 형식 간의 명시적 숫자 변환</span><span class="sxs-lookup"><span data-stu-id="c6efe-112">Explicit numeric conversions between integral types.</span></span>  
  
 <span data-ttu-id="c6efe-113">[/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) 컴파일러 옵션을 사용하면 `checked` 또는 `unchecked` 키워드의 범위에 명시적으로 포함되지 않은 모든 정수 산술 문에 대해 checked 또는 unchecked 컨텍스트를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6efe-113">The [/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) compiler option lets you specify checked or unchecked context for all integer arithmetic statements that are not explicitly in the scope of a `checked` or `unchecked` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6efe-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6efe-114">See Also</span></span>  
 [<span data-ttu-id="c6efe-115">C# 참조</span><span class="sxs-lookup"><span data-stu-id="c6efe-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="c6efe-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="c6efe-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c6efe-117">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="c6efe-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="c6efe-118">문 키워드</span><span class="sxs-lookup"><span data-stu-id="c6efe-118">Statement Keywords</span></span>](../../../csharp/language-reference/keywords/statement-keywords.md)
