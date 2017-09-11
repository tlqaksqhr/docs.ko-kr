---
title: "new 제약 조건(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
caps.latest.revision: 20
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
ms.openlocfilehash: 762941794184605f90443ed8f36c88ecfa50aa84
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="4a5b3-102">new 제약 조건(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="4a5b3-102">new Constraint (C# Reference)</span></span>
<span data-ttu-id="4a5b3-103">`new` 제약 조건은 제네릭 클래스 선언의 모든 형식 인수에 매개 변수가 없는 public 생성자가 있어야 하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5b3-103">The `new` constraint specifies that any type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="4a5b3-104">새 제약 조건을 사용하려면 추상 형식일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4a5b3-104">To use the new constraint, the type cannot be abstract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a5b3-105">예제</span><span class="sxs-lookup"><span data-stu-id="4a5b3-105">Example</span></span>  
 <span data-ttu-id="4a5b3-106">다음 예제와 같이 제네릭 클래스가 형식의 새 인스턴스를 만드는 경우 형식 매개 변수에 `new` 제약 조건을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5b3-106">Apply the `new` constraint to a type parameter when your generic class creates new instances of the type, as shown in the following example:</span></span>  
  
 <span data-ttu-id="4a5b3-107">[!code-cs[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4a5b3-107">[!code-cs[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a5b3-108">예제</span><span class="sxs-lookup"><span data-stu-id="4a5b3-108">Example</span></span>  
 <span data-ttu-id="4a5b3-109">다른 제약 조건과 함께 `new()` 제약 조건을 사용하는 경우 마지막에 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a5b3-109">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>  
  
 <span data-ttu-id="4a5b3-110">[!code-cs[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="4a5b3-110">[!code-cs[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]</span></span>  
  
 <span data-ttu-id="4a5b3-111">자세한 내용은 [형식 매개 변수에 대한 제약 조건](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4a5b3-111">For more information, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="4a5b3-112">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="4a5b3-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4a5b3-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a5b3-113">See Also</span></span>  
 <span data-ttu-id="4a5b3-114"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="4a5b3-114"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="4a5b3-115">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="4a5b3-115">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="4a5b3-116">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4a5b3-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="4a5b3-117">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="4a5b3-117">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="4a5b3-118">[연산자 키워드](../../../csharp/language-reference/keywords/operator-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="4a5b3-118">[Operator Keywords](../../../csharp/language-reference/keywords/operator-keywords.md) </span></span>  
 [<span data-ttu-id="4a5b3-119">제네릭</span><span class="sxs-lookup"><span data-stu-id="4a5b3-119">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)

