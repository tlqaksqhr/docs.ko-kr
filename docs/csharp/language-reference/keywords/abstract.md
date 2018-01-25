---
title: "abstract(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- abstract
- abstract_CSharpKeyword
helpviewer_keywords: abstract keyword [C#]
ms.assetid: b0797770-c1f3-4b4d-9441-b9122602a6bb
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: bd26583c42302d8ce9ba4dd22119713548111236
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="abstract-c-reference"></a><span data-ttu-id="1d4ae-102">abstract(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="1d4ae-102">abstract (C# Reference)</span></span>
<span data-ttu-id="1d4ae-103">`abstract` 한정자는 수정되는 항목에 누락되거나 불완전한 구현이 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ae-103">The `abstract` modifier indicates that the thing being modified has a missing or incomplete implementation.</span></span> <span data-ttu-id="1d4ae-104">abstract 한정자는 클래스, 메서드, 속성, 인덱서 및 이벤트와 함께 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ae-104">The abstract modifier can be used with classes, methods, properties, indexers, and events.</span></span> <span data-ttu-id="1d4ae-105">클래스 선언에서 `abstract` 한정자를 사용하여 클래스가 다른 클래스의 기본 클래스로만 사용됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ae-105">Use the `abstract` modifier in a class declaration to indicate that a class is intended only to be a base class of other classes.</span></span> <span data-ttu-id="1d4ae-106">abstract로 표시되거나 추상 클래스에 포함된 멤버는 추상 클래스에서 파생 클래스에 의해 구현되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ae-106">Members marked as abstract, or included in an abstract class, must be implemented by classes that derive from the abstract class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d4ae-107">예</span><span class="sxs-lookup"><span data-stu-id="1d4ae-107">Example</span></span>  
 <span data-ttu-id="1d4ae-108">이 예제에서 `Square` 클래스는 `ShapesClass`에서 파생되므로 `Area` 구현을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ae-108">In this example, the class `Square` must provide an implementation of `Area` because it derives from `ShapesClass`:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_1.cs)]  
  
 <span data-ttu-id="1d4ae-109">다음 기능이 있는 추상 클래스:</span><span class="sxs-lookup"><span data-stu-id="1d4ae-109">Abstract classes have the following features:</span></span>  
  
-   <span data-ttu-id="1d4ae-110">추상 클래스는 인스턴스화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ae-110">An abstract class cannot be instantiated.</span></span>  
  
-   <span data-ttu-id="1d4ae-111">추상 클래스에 추상 메서드 및 접근자가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ae-111">An abstract class may contain abstract methods and accessors.</span></span>  
  
-   <span data-ttu-id="1d4ae-112">[sealed](../../../csharp/language-reference/keywords/sealed.md) 한정자를 사용하여 추상 클래스를 수정할 수는 없습니다. 두 한정자가 상반된 의미를 가지기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ae-112">It is not possible to modify an abstract class with the [sealed](../../../csharp/language-reference/keywords/sealed.md) modifier because the two modifers have opposite meanings.</span></span> <span data-ttu-id="1d4ae-113">`sealed` 한정자를 사용하면 클래스가 상속되지 않고 `abstract` 한정자를 사용하려면 클래스가 상속되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ae-113">The `sealed` modifier prevents a class from being inherited and the `abstract` modifier requires a class to be inherited.</span></span>  
  
-   <span data-ttu-id="1d4ae-114">추상 클래스에서 추상이 아닌 파생 클래스에는 모든 상속된 메서드 및 접근자의 실제 구현이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ae-114">A non-abstract class derived from an abstract class must include actual implementations of all inherited abstract methods and accessors.</span></span>  
  
 <span data-ttu-id="1d4ae-115">메서드 또는 속성 선언에서 `abstract` 한정자를 사용하여 메서드 또는 속성에 구현이 포함되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ae-115">Use the `abstract` modifier in a method or property declaration to indicate that the method or property does not contain implementation.</span></span>  
  
 <span data-ttu-id="1d4ae-116">추상 메서드에는 다음과 같은 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ae-116">Abstract methods have the following features:</span></span>  
  
-   <span data-ttu-id="1d4ae-117">추상 메서드는 암시적으로 가상 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ae-117">An abstract method is implicitly a virtual method.</span></span>  
  
-   <span data-ttu-id="1d4ae-118">추상 메서드 선언은 추상 클래스에서만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ae-118">Abstract method declarations are only permitted in abstract classes.</span></span>  
  
-   <span data-ttu-id="1d4ae-119">추상 메서드 선언은 실제 구현을 제공하지 않으므로 메서드 본문이 없습니다. 메서드 선언은 세미콜론으로 끝나고 시그니처 뒤에 중괄호({ })가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ae-119">Because an abstract method declaration provides no actual implementation, there is no method body; the method declaration simply ends with a semicolon and there are no curly braces ({ }) following the signature.</span></span> <span data-ttu-id="1d4ae-120">예:</span><span class="sxs-lookup"><span data-stu-id="1d4ae-120">For example:</span></span>  
  
    ```csharp  
    public abstract void MyMethod();  
    ```  
  
     <span data-ttu-id="1d4ae-121">구현은 추상이 아닌 클래스의 멤버인 재정의 메서드 [override](../../../csharp/language-reference/keywords/override.md)에 의해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ae-121">The implementation is provided by an overriding method[override](../../../csharp/language-reference/keywords/override.md), which is a member of a non-abstract class.</span></span>  
  
-   <span data-ttu-id="1d4ae-122">추상 메서드 선언에서 [static](../../../csharp/language-reference/keywords/static.md) 또는 [virtual](../../../csharp/language-reference/keywords/virtual.md) 한정자를 사용하는 것은 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ae-122">It is an error to use the [static](../../../csharp/language-reference/keywords/static.md) or [virtual](../../../csharp/language-reference/keywords/virtual.md) modifiers in an abstract method declaration.</span></span>  
  
 <span data-ttu-id="1d4ae-123">선언 및 호출 구문의 차이점을 제외하고 추상 속성은 추상 메서드처럼 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ae-123">Abstract properties behave like abstract methods, except for the differences in declaration and invocation syntax.</span></span>  
  
-   <span data-ttu-id="1d4ae-124">정적 속성에서 `abstract` 한정자를 사용하는 것은 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ae-124">It is an error to use the `abstract` modifier on a static property.</span></span>  
  
-   <span data-ttu-id="1d4ae-125">[override](../../../csharp/language-reference/keywords/override.md) 한정자를 사용하는 속성 선언을 포함하여 상속된 추상 속성을 파생 클래스에서 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ae-125">An abstract inherited property can be overridden in a derived class by including a property declaration that uses the [override](../../../csharp/language-reference/keywords/override.md) modifier.</span></span>  
  
 <span data-ttu-id="1d4ae-126">추상 클래스에 대한 자세한 내용은 [추상 및 봉인 클래스와 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d4ae-126">For more information about abstract classes, see [Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
 <span data-ttu-id="1d4ae-127">추상 클래스는 모든 인터페이스 멤버에 대한 구현을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ae-127">An abstract class must provide implementation for all interface members.</span></span>  
  
 <span data-ttu-id="1d4ae-128">인터페이스를 구현하는 추상 클래스는 인터페이스 메서드를 추상 메서드에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ae-128">An abstract class that implements an interface might map the interface methods onto abstract methods.</span></span> <span data-ttu-id="1d4ae-129">예:</span><span class="sxs-lookup"><span data-stu-id="1d4ae-129">For example:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="1d4ae-130">예</span><span class="sxs-lookup"><span data-stu-id="1d4ae-130">Example</span></span>  
 <span data-ttu-id="1d4ae-131">이 예제에서 `DerivedClass` 클래스는 추상 클래스 `BaseClass`에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ae-131">In this example, the class `DerivedClass` is derived from an abstract class `BaseClass`.</span></span> <span data-ttu-id="1d4ae-132">추상 클래스에는 추상 메서드 `AbstractMethod` 및 두 개의 추상 속성 `X` 및 `Y`가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ae-132">The abstract class contains an abstract method, `AbstractMethod`, and two abstract properties, `X` and `Y`.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_3.cs)]  
  
 <span data-ttu-id="1d4ae-133">앞의 예제에서 다음과 같이 문을 사용하여 추상 클래스를 인스턴스화하려고 하면,</span><span class="sxs-lookup"><span data-stu-id="1d4ae-133">In the preceding example, if you attempt to instantiate the abstract class by using a statement like this:</span></span>  
  
```csharp
BaseClass bc = new BaseClass();   // Error  
```  
  
<span data-ttu-id="1d4ae-134">컴파일러가 추상 클래스 'BaseClass'의 인스턴스를 만들 수 없다는 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d4ae-134">You will get an error saying that the compiler cannot create an instance of the abstract class 'BaseClass'.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="1d4ae-135">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="1d4ae-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1d4ae-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d4ae-136">See Also</span></span>  
 [<span data-ttu-id="1d4ae-137">C# 참조</span><span class="sxs-lookup"><span data-stu-id="1d4ae-137">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="1d4ae-138">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="1d4ae-138">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1d4ae-139">한정자</span><span class="sxs-lookup"><span data-stu-id="1d4ae-139">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="1d4ae-140">virtual</span><span class="sxs-lookup"><span data-stu-id="1d4ae-140">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)  
 [<span data-ttu-id="1d4ae-141">override</span><span class="sxs-lookup"><span data-stu-id="1d4ae-141">override</span></span>](../../../csharp/language-reference/keywords/override.md)  
 [<span data-ttu-id="1d4ae-142">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="1d4ae-142">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
