---
title: "new 제약 조건(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8557e056a664fd470b1f185b619d81235c8fcba7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="48f20-102">new 제약 조건(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="48f20-102">new Constraint (C# Reference)</span></span>
<span data-ttu-id="48f20-103">`new` 제약 조건은 제네릭 클래스 선언의 모든 형식 인수에 매개 변수가 없는 public 생성자가 있어야 하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="48f20-103">The `new` constraint specifies that any type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="48f20-104">새 제약 조건을 사용하려면 추상 형식일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="48f20-104">To use the new constraint, the type cannot be abstract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48f20-105">예제</span><span class="sxs-lookup"><span data-stu-id="48f20-105">Example</span></span>  
 <span data-ttu-id="48f20-106">다음 예제와 같이 제네릭 클래스가 형식의 새 인스턴스를 만드는 경우 형식 매개 변수에 `new` 제약 조건을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="48f20-106">Apply the `new` constraint to a type parameter when your generic class creates new instances of the type, as shown in the following example:</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="48f20-107">예제</span><span class="sxs-lookup"><span data-stu-id="48f20-107">Example</span></span>  
 <span data-ttu-id="48f20-108">다른 제약 조건과 함께 `new()` 제약 조건을 사용하는 경우 마지막에 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48f20-108">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]  
  
 <span data-ttu-id="48f20-109">자세한 내용은 [형식 매개 변수에 대한 제약 조건](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="48f20-109">For more information, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="48f20-110">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="48f20-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="48f20-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="48f20-111">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="48f20-112">C# 참조</span><span class="sxs-lookup"><span data-stu-id="48f20-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="48f20-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="48f20-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="48f20-114">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="48f20-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="48f20-115">연산자 키워드</span><span class="sxs-lookup"><span data-stu-id="48f20-115">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="48f20-116">제네릭</span><span class="sxs-lookup"><span data-stu-id="48f20-116">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
