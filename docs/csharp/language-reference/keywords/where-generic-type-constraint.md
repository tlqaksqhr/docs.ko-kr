---
title: "where(제네릭 형식 제약 조건)(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- whereconstraint
- whereconstraint_CSharpKeyword
helpviewer_keywords: where (generic type constraint) [C#]
ms.assetid: d7aa871b-0714-416a-bab2-96f87ada4310
caps.latest.revision: "10"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f2b7b159689aa771d3f9d59e3b1dd340c85b1d79
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="where-generic-type-constraint-c-reference"></a><span data-ttu-id="206a8-102">where(제네릭 형식 제약 조건)(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="206a8-102">where (generic type constraint) (C# Reference)</span></span>
<span data-ttu-id="206a8-103">제네릭 형식 정의에서 `where` 절은 제네릭 선언에 정의된 형식 매개 변수의 인수로 사용할 수 있는 형식에 대한 제약 조건을 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="206a8-103">In a generic type definition, the `where` clause is used to specify constraints on the types that can be used as arguments for a type parameter defined in a generic declaration.</span></span> <span data-ttu-id="206a8-104">예를 들어 형식 매개 변수 `T`가 <xref:System.IComparable%601> 인터페이스를 구현하도록 제네릭 클래스 `MyGenericClass`를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="206a8-104">For example, you can declare a generic class, `MyGenericClass`, such that the type parameter `T` implements the <xref:System.IComparable%601> interface:</span></span>  
  
```csharp  
public class MyGenericClass<T> where T:IComparable { }  
```  
  
> [!NOTE]
>  <span data-ttu-id="206a8-105">쿼리 식의 where 절에 대한 자세한 내용은 [where 절](../../../csharp/language-reference/keywords/where-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="206a8-105">For more information on the where clause in a query expression, see [where clause](../../../csharp/language-reference/keywords/where-clause.md).</span></span>  
  
 <span data-ttu-id="206a8-106">인터페이스 제약 조건 외에도 `where` 절에는 기본 클래스 제약 조건을 포함할 수 있습니다. 여기서는 제네릭 형식에 대한 형식 인수로서 사용할 수 있도록, 지정된 클래스를 기본 클래스로(또는 해당 클래스 자체로) 형식에 포함하도록 명시합니다.</span><span class="sxs-lookup"><span data-stu-id="206a8-106">In addition to interface constraints, a `where` clause can include a base class constraint, which states that a type must have the specified class as a base class (or be that class itself) in order to be used as a type argument for that generic type.</span></span> <span data-ttu-id="206a8-107">그러한 제약 조건이 사용되는 경우 해당 형식 매개 변수에 대한 다른 제약 조건 앞에 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="206a8-107">If such a constraint is used, it must appear before any other constraints on that type parameter.</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_1.cs)]  
  
 <span data-ttu-id="206a8-108">`where` 절에 생성자 제약 조건이 포함될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="206a8-108">The `where` clause may also include a constructor constraint.</span></span> <span data-ttu-id="206a8-109">새 연산자를 사용하여 형식 매개 변수의 인스턴스를 만들 수 있습니다. 그러나 그렇게 하려면 생성자 제약 조건 `new()`로 형식 매개 변수를 제한해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="206a8-109">It is possible to create an instance of a type parameter using the new operator; however, in order to do so the type parameter must be constrained by the constructor constraint, `new()`.</span></span> <span data-ttu-id="206a8-110">[new () 제약 조건](../../../csharp/language-reference/keywords/new-constraint.md)을 사용하면 컴파일러는 제공된 인수에 액세스 가능하고 매개 변수가 없는 생성자(또는 기본 생성자)가 있어야 한다는 것을 알게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="206a8-110">The [new() Constraint](../../../csharp/language-reference/keywords/new-constraint.md) lets the compiler know that any type argument supplied must have an accessible parameterless--or default-- constructor.</span></span> <span data-ttu-id="206a8-111">예:</span><span class="sxs-lookup"><span data-stu-id="206a8-111">For example:</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_2.cs)]  
  
 <span data-ttu-id="206a8-112">`new()` 제약 조건은 `where` 절 맨 끝에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="206a8-112">The `new()` constraint appears last in the `where` clause.</span></span>  
  
 <span data-ttu-id="206a8-113">형식 매개 변수가 여러 개이면 각 형식 매개 변수에 하나의 `where` 절을 사용합니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="206a8-113">With multiple type parameters, use one `where` clause for each type parameter, for example:</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_3.cs)]  
  
 <span data-ttu-id="206a8-114">제약 조건을 다음과 같이 제네릭 메서드의 형식 매개 변수에 첨부할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="206a8-114">You can also attach constraints to type parameters of generic methods, like this:</span></span>  
  
```csharp  
public bool MyMethod<T>(T t) where T : IMyInterface { }  
```  
  
 <span data-ttu-id="206a8-115">대리자에 대한 형식 매개 변수 제약 조건을 설명하는 구문은 메서드의 구문과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="206a8-115">Notice that the syntax to describe type parameter constraints on delegates is the same as that of methods:</span></span>  
  
```csharp  
delegate T MyDelegate<T>() where T : new()  
```  
  
 <span data-ttu-id="206a8-116">제네릭 대리자에 대한 자세한 내용은 [제네릭 대리자](../../../csharp/programming-guide/generics/generic-delegates.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="206a8-116">For information on generic delegates, see [Generic Delegates](../../../csharp/programming-guide/generics/generic-delegates.md).</span></span>  
  
 <span data-ttu-id="206a8-117">제약 조건의 구문 및 사용에 대한 자세한 내용은 [형식 매개 변수에 대한 제약 조건](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="206a8-117">For details on the syntax and use of constraints, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="206a8-118">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="206a8-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="206a8-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="206a8-119">See Also</span></span>  
 [<span data-ttu-id="206a8-120">C# 참조</span><span class="sxs-lookup"><span data-stu-id="206a8-120">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="206a8-121">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="206a8-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="206a8-122">제네릭 소개</span><span class="sxs-lookup"><span data-stu-id="206a8-122">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
 [<span data-ttu-id="206a8-123">new 제약 조건</span><span class="sxs-lookup"><span data-stu-id="206a8-123">new Constraint</span></span>](../../../csharp/language-reference/keywords/new-constraint.md)  
 [<span data-ttu-id="206a8-124">형식 매개 변수에 대한 제약 조건</span><span class="sxs-lookup"><span data-stu-id="206a8-124">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)
