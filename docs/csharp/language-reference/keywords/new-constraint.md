---
title: new 제약 조건(C# 참조)
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: 77c955102ba9cede831c85838a6a7e57025ad35b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33268998"
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="73b17-102">new 제약 조건(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="73b17-102">new Constraint (C# Reference)</span></span>
<span data-ttu-id="73b17-103">`new` 제약 조건은 제네릭 클래스 선언의 모든 형식 인수에 매개 변수가 없는 public 생성자가 있어야 하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="73b17-103">The `new` constraint specifies that any type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="73b17-104">새 제약 조건을 사용하려면 추상 형식일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73b17-104">To use the new constraint, the type cannot be abstract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73b17-105">예</span><span class="sxs-lookup"><span data-stu-id="73b17-105">Example</span></span>  
 <span data-ttu-id="73b17-106">다음 예제와 같이 제네릭 클래스가 형식의 새 인스턴스를 만드는 경우 형식 매개 변수에 `new` 제약 조건을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="73b17-106">Apply the `new` constraint to a type parameter when your generic class creates new instances of the type, as shown in the following example:</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="73b17-107">예</span><span class="sxs-lookup"><span data-stu-id="73b17-107">Example</span></span>  
 <span data-ttu-id="73b17-108">다른 제약 조건과 함께 `new()` 제약 조건을 사용하는 경우 마지막에 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73b17-108">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]  
  
 <span data-ttu-id="73b17-109">자세한 내용은 [형식 매개 변수에 대한 제약 조건](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73b17-109">For more information, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="73b17-110">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="73b17-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="73b17-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73b17-111">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="73b17-112">C# 참조</span><span class="sxs-lookup"><span data-stu-id="73b17-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="73b17-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="73b17-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="73b17-114">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="73b17-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="73b17-115">연산자 키워드</span><span class="sxs-lookup"><span data-stu-id="73b17-115">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="73b17-116">제네릭</span><span class="sxs-lookup"><span data-stu-id="73b17-116">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
