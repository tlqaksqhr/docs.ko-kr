---
title: "Checked 및 Unchecked(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
caps.latest.revision: 17
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
ms.openlocfilehash: 744f59dbf7ee8370010ff76d4e9dde20490de403
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="checked-and-unchecked-c-reference"></a><span data-ttu-id="0fc2c-102">Checked 및 Unchecked(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="0fc2c-102">Checked and Unchecked (C# Reference)</span></span>
<span data-ttu-id="0fc2c-103">checked 컨텍스트 또는 unchecked 컨텍스트에서 C# 문을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fc2c-103">C# statements can execute in either checked or unchecked context.</span></span> <span data-ttu-id="0fc2c-104">checked 컨텍스트에서는 산술 오버플로가 있으면 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0fc2c-104">In a checked context, arithmetic overflow raises an exception.</span></span> <span data-ttu-id="0fc2c-105">unchecked 컨텍스트에서는 산술 오버플로가 무시되며 결과가 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="0fc2c-105">In an unchecked context, arithmetic overflow is ignored and the result is truncated.</span></span>  
  
-   <span data-ttu-id="0fc2c-106">[checked](../../../csharp/language-reference/keywords/checked.md) checked 컨텍스트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0fc2c-106">[checked](../../../csharp/language-reference/keywords/checked.md) Specify checked context.</span></span>  
  
-   <span data-ttu-id="0fc2c-107">[unchecked](../../../csharp/language-reference/keywords/unchecked.md) unchecked 컨텍스트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0fc2c-107">[unchecked](../../../csharp/language-reference/keywords/unchecked.md) Specify unchecked context.</span></span>  
  
 <span data-ttu-id="0fc2c-108">`checked`도 `unchecked`도 지정하지 않으면 기본 컨텍스트는 컴파일러 옵션 등의 외부 요인에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="0fc2c-108">If neither `checked` nor `unchecked` is specified, the default context depends on external factors such as compiler options.</span></span>  
  
 <span data-ttu-id="0fc2c-109">오버플로 검사의 영향을 받는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0fc2c-109">The following operations are affected by the overflow checking:</span></span>  
  
-   <span data-ttu-id="0fc2c-110">정수 계열 형식에 다음의 미리 정의된 연산자를 사용하는 식</span><span class="sxs-lookup"><span data-stu-id="0fc2c-110">Expressions using the following predefined operators on integral types:</span></span>  
  
     <span data-ttu-id="0fc2c-111">`++` `--` - (단항)   `+` -   `*` `/`</span><span class="sxs-lookup"><span data-stu-id="0fc2c-111">`++` `--` - (unary)   `+` -   `*` `/`</span></span>  
  
-   <span data-ttu-id="0fc2c-112">정수 형식 간의 명시적 숫자 변환</span><span class="sxs-lookup"><span data-stu-id="0fc2c-112">Explicit numeric conversions between integral types.</span></span>  
  
 <span data-ttu-id="0fc2c-113">[/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) 컴파일러 옵션을 사용하면 `checked` 또는 `unchecked` 키워드의 범위에 명시적으로 포함되지 않은 모든 정수 산술 문에 대해 checked 또는 unchecked 컨텍스트를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fc2c-113">The [/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) compiler option lets you specify checked or unchecked context for all integer arithmetic statements that are not explicitly in the scope of a `checked` or `unchecked` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fc2c-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0fc2c-114">See Also</span></span>  
 <span data-ttu-id="0fc2c-115">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="0fc2c-115">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="0fc2c-116">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0fc2c-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="0fc2c-117">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="0fc2c-117">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 [<span data-ttu-id="0fc2c-118">문 키워드</span><span class="sxs-lookup"><span data-stu-id="0fc2c-118">Statement Keywords</span></span>](../../../csharp/language-reference/keywords/statement-keywords.md)

