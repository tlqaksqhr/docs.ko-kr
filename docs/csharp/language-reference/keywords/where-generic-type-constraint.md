---
title: "where(제네릭 형식 제약 조건)(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- whereconstraint
- whereconstraint_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- where (generic type constraint) [C#]
ms.assetid: d7aa871b-0714-416a-bab2-96f87ada4310
caps.latest.revision: 10
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
ms.openlocfilehash: 8e81640ee56ed672bb09242a070fdf167740874b
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="where-generic-type-constraint-c-reference"></a><span data-ttu-id="e6a14-102">where(제네릭 형식 제약 조건)(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="e6a14-102">where (generic type constraint) (C# Reference)</span></span>
<span data-ttu-id="e6a14-103">제네릭 형식 정의에서 `where` 절은 제네릭 선언에 정의된 형식 매개 변수의 인수로 사용할 수 있는 형식에 대한 제약 조건을 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6a14-103">In a generic type definition, the `where` clause is used to specify constraints on the types that can be used as arguments for a type parameter defined in a generic declaration.</span></span> <span data-ttu-id="e6a14-104">예를 들어 형식 매개 변수 `T`가 <xref:System.IComparable%601> 인터페이스를 구현하도록 제네릭 클래스 `MyGenericClass`를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a14-104">For example, you can declare a generic class, `MyGenericClass`, such that the type parameter `T` implements the <xref:System.IComparable%601> interface:</span></span>  
  
```csharp  
public class MyGenericClass<T> where T:IComparable { }  
```  
  
> [!NOTE]
>  <span data-ttu-id="e6a14-105">쿼리 식의 where 절에 대한 자세한 내용은 [where 절](../../../csharp/language-reference/keywords/where-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6a14-105">For more information on the where clause in a query expression, see [where clause](../../../csharp/language-reference/keywords/where-clause.md).</span></span>  
  
 <span data-ttu-id="e6a14-106">인터페이스 제약 조건 외에도 `where` 절에는 기본 클래스 제약 조건을 포함할 수 있습니다. 여기서는 제네릭 형식에 대한 형식 인수로서 사용할 수 있도록, 지정된 클래스를 기본 클래스로(또는 해당 클래스 자체로) 형식에 포함하도록 명시합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a14-106">In addition to interface constraints, a `where` clause can include a base class constraint, which states that a type must have the specified class as a base class (or be that class itself) in order to be used as a type argument for that generic type.</span></span> <span data-ttu-id="e6a14-107">그러한 제약 조건이 사용되는 경우 해당 형식 매개 변수에 대한 다른 제약 조건 앞에 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a14-107">If such a constraint is used, it must appear before any other constraints on that type parameter.</span></span>  
  
 <span data-ttu-id="e6a14-108">[!code-cs[csrefKeywordsContextual#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e6a14-108">[!code-cs[csrefKeywordsContextual#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_1.cs)]</span></span>  
  
 <span data-ttu-id="e6a14-109">`where` 절에 생성자 제약 조건이 포함될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a14-109">The `where` clause may also include a constructor constraint.</span></span> <span data-ttu-id="e6a14-110">새 연산자를 사용하여 형식 매개 변수의 인스턴스를 만들 수 있습니다. 그러나 그렇게 하려면 생성자 제약 조건 `new()`(으)로 형식 매개 변수를 제한해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a14-110">It is possible to create an instance of a type parameter using the new operator; however, in order to do so the type parameter must be constrained by the constructor constraint, `new()`.</span></span> <span data-ttu-id="e6a14-111">[new () 제약 조건](../../../csharp/language-reference/keywords/new-constraint.md)을 사용하면 컴파일러는 제공된 형식 인수에는 액세스 가능하며 매개 변수가 없는 생성자(또는 기본 생성자)가 있어야 한다는 것을 알게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6a14-111">The [new() Constraint](../../../csharp/language-reference/keywords/new-constraint.md) lets the compiler know that any type argument supplied must have an accessible parameterless--or default-- constructor.</span></span> <span data-ttu-id="e6a14-112">예:</span><span class="sxs-lookup"><span data-stu-id="e6a14-112">For example:</span></span>  
  
 <span data-ttu-id="e6a14-113">[!code-cs[csrefKeywordsContextual#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="e6a14-113">[!code-cs[csrefKeywordsContextual#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_2.cs)]</span></span>  
  
 <span data-ttu-id="e6a14-114">`new()` 제약 조건은 `where` 절 맨 끝에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e6a14-114">The `new()` constraint appears last in the `where` clause.</span></span>  
  
 <span data-ttu-id="e6a14-115">형식 매개 변수가 여러 개이면 각 형식 매개 변수에 하나의 `where` 절을 사용합니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a14-115">With multiple type parameters, use one `where` clause for each type parameter, for example:</span></span>  
  
 <span data-ttu-id="e6a14-116">[!code-cs[csrefKeywordsContextual#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="e6a14-116">[!code-cs[csrefKeywordsContextual#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_3.cs)]</span></span>  
  
 <span data-ttu-id="e6a14-117">제약 조건을 다음과 같이 제네릭 메서드의 형식 매개 변수에 첨부할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6a14-117">You can also attach constraints to type parameters of generic methods, like this:</span></span>  
  
```csharp  
public bool MyMethod<T>(T t) where T : IMyInterface { }  
```  
  
 <span data-ttu-id="e6a14-118">대리자에 대한 형식 매개 변수 제약 조건을 설명하는 구문은 메서드의 구문과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="e6a14-118">Notice that the syntax to describe type parameter constraints on delegates is the same as that of methods:</span></span>  
  
```csharp  
delegate T MyDelegate<T>() where T : new()  
```  
  
 <span data-ttu-id="e6a14-119">제네릭 대리자에 대한 자세한 내용은 [제네릭 대리자](../../../csharp/programming-guide/generics/generic-delegates.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6a14-119">For information on generic delegates, see [Generic Delegates](../../../csharp/programming-guide/generics/generic-delegates.md).</span></span>  
  
 <span data-ttu-id="e6a14-120">제약 조건의 구문 및 사용에 대한 자세한 내용은 [형식 매개 변수에 대한 제약 조건](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6a14-120">For details on the syntax and use of constraints, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e6a14-121">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="e6a14-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e6a14-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e6a14-122">See Also</span></span>  
 <span data-ttu-id="e6a14-123">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e6a14-123">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e6a14-124">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e6a14-124">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e6a14-125">[제네릭 소개](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span><span class="sxs-lookup"><span data-stu-id="e6a14-125">[Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span></span>  
 <span data-ttu-id="e6a14-126">[new 제약 조건](../../../csharp/language-reference/keywords/new-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="e6a14-126">[new Constraint](../../../csharp/language-reference/keywords/new-constraint.md) </span></span>  
 [<span data-ttu-id="e6a14-127">형식 매개 변수에 대한 제약 조건</span><span class="sxs-lookup"><span data-stu-id="e6a14-127">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)

