---
title: "as(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- as_CSharpKeyword
- as
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a4f2964f32a4139ffeb6d51b761f1176a57c5be6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="as-c-reference"></a><span data-ttu-id="f9407-102">as(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="f9407-102">as (C# Reference)</span></span>
<span data-ttu-id="f9407-103">`as` 연산자를 사용하여 호환되는 참조 형식 또는 [nullable 형식](../../../csharp/programming-guide/nullable-types/index.md) 간에 특정 형식의 변환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9407-103">You can use the `as` operator to perform certain types of conversions between compatible reference types or [nullable types](../../../csharp/programming-guide/nullable-types/index.md).</span></span> <span data-ttu-id="f9407-104">다음 코드는 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9407-104">The following code shows an example.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_1.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="f9407-105">설명</span><span class="sxs-lookup"><span data-stu-id="f9407-105">Remarks</span></span>  
 <span data-ttu-id="f9407-106">`as` 연산자는 캐스트 작업과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="f9407-106">The `as` operator is like a cast operation.</span></span> <span data-ttu-id="f9407-107">하지만 변환할 수 없는 경우 `as`는 예외를 발생시키지 않고 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f9407-107">However, if the conversion isn't possible, `as` returns `null` instead of raising an exception.</span></span> <span data-ttu-id="f9407-108">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9407-108">Consider the following example:</span></span>  
  
```  
expression as type  
```  
  
 <span data-ttu-id="f9407-109">`expression` 변수가 한 번만 계산된다는 점을 제외하고 코드는 다음 식과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f9407-109">The code is equivalent to the following expression except that the `expression` variable is evaluated only one time.</span></span>  
  
```  
expression is type ? (type)expression : (type)null  
```  
  
 <span data-ttu-id="f9407-110">`as` 연산자는 참조 변환, nullable 변환 및 boxing 변환만 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f9407-110">Note that the `as` operator performs only reference conversions, nullable conversions, and boxing conversions.</span></span> <span data-ttu-id="f9407-111">`as` 연산자는 캐스트 식을 사용하여 수행해야 하는 사용자 정의 변환 등의 기타 변환을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f9407-111">The `as` operator can't perform other conversions, such as user-defined conversions, which should instead be performed by using cast expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9407-112">예제</span><span class="sxs-lookup"><span data-stu-id="f9407-112">Example</span></span>  
 [!code-csharp[csrefKeywordsOperator#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="f9407-113">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="f9407-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f9407-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9407-114">See Also</span></span>  
 [<span data-ttu-id="f9407-115">C# 참조</span><span class="sxs-lookup"><span data-stu-id="f9407-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f9407-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="f9407-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f9407-117">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="f9407-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="f9407-118">is</span><span class="sxs-lookup"><span data-stu-id="f9407-118">is</span></span>](../../../csharp/language-reference/keywords/is.md)  
 [<span data-ttu-id="f9407-119">?: 연산자</span><span class="sxs-lookup"><span data-stu-id="f9407-119">?: Operator</span></span>](../../../csharp/language-reference/operators/conditional-operator.md)  
 [<span data-ttu-id="f9407-120">연산자 키워드</span><span class="sxs-lookup"><span data-stu-id="f9407-120">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
