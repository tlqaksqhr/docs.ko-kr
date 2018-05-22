---
title: 식 본문 멤버(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- expression-bodied members[C#]
- C# language, expresion-bodied members
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 800280ed9ceaf69b825bb2a3c2c3d0d5f829922d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="expression-bodied-members-c-programming-guide"></a><span data-ttu-id="990df-102">식 본문 멤버(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="990df-102">Expression-bodied members (C# programming guide)</span></span>
<span data-ttu-id="990df-103">식 본문 정의를 사용하면 간결하고 읽을 수 있는 형식으로 멤버 구현을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="990df-103">Expression body definitions let you provide a member's implementation in a very concise, readable form.</span></span> <span data-ttu-id="990df-104">메서드 또는 속성과 같은 지원되는 멤버에 대한 논리가 단일 식으로 구성된 경우 식 본문 정의를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="990df-104">You can use an expression body definition whenever the logic for any supported member, such as a method or property, consists of a single expression.</span></span> <span data-ttu-id="990df-105">식 본문 정의의 일반 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="990df-105">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="990df-106">여기서 *expression*은 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="990df-106">where *expression* is a valid expression.</span></span> 

<span data-ttu-id="990df-107">C# 6에서는 메서드 및 속성 가져오기 접근자에 대해 식 본문 정의 지원이 도입되었으며 C# 7.0에서는 지원이 확장되었습니다.</span><span class="sxs-lookup"><span data-stu-id="990df-107">Support for expression body definitions was introduced for methods and property get accessors in C# 6 and was expanded in C# 7.0.</span></span> <span data-ttu-id="990df-108">다음 표에 나열된 형식 멤버와 함께 식 본문 정의를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="990df-108">Expression body definitions can be used with the type members listed in the following table:</span></span> 

|<span data-ttu-id="990df-109">멤버</span><span class="sxs-lookup"><span data-stu-id="990df-109">Member</span></span>  |<span data-ttu-id="990df-110">지원 버전</span><span class="sxs-lookup"><span data-stu-id="990df-110">Supported as of...</span></span> |
|---------|---------|
|[<span data-ttu-id="990df-111">메서드</span><span class="sxs-lookup"><span data-stu-id="990df-111">Method</span></span>](#methods)  |<span data-ttu-id="990df-112">C# 6</span><span class="sxs-lookup"><span data-stu-id="990df-112">C# 6</span></span> |
|[<span data-ttu-id="990df-113">생성자</span><span class="sxs-lookup"><span data-stu-id="990df-113">Constructor</span></span>](#constructors)   |<span data-ttu-id="990df-114">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="990df-114">C# 7.0</span></span> |
|[<span data-ttu-id="990df-115">종료자</span><span class="sxs-lookup"><span data-stu-id="990df-115">Finalizer</span></span>](#finalizers)     |<span data-ttu-id="990df-116">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="990df-116">C# 7.0</span></span> |
|[<span data-ttu-id="990df-117">속성 가져오기</span><span class="sxs-lookup"><span data-stu-id="990df-117">Property Get</span></span>](#property-get-statements)  |<span data-ttu-id="990df-118">C# 6</span><span class="sxs-lookup"><span data-stu-id="990df-118">C# 6</span></span> |
|[<span data-ttu-id="990df-119">속성 설정</span><span class="sxs-lookup"><span data-stu-id="990df-119">Property Set</span></span>](#property-set-statements)  |<span data-ttu-id="990df-120">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="990df-120">C# 7.0</span></span> |
|[<span data-ttu-id="990df-121">인덱서</span><span class="sxs-lookup"><span data-stu-id="990df-121">Indexer</span></span>](#indexers)       |<span data-ttu-id="990df-122">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="990df-122">C# 7.0</span></span> |

## <a name="methods"></a><span data-ttu-id="990df-123">메서드</span><span class="sxs-lookup"><span data-stu-id="990df-123">Methods</span></span>

<span data-ttu-id="990df-124">식 본문 메서드는 형식이 메서드의 반환 형식과 일치하는 값을 반환하거나 `void`를 반환하는 메서드의 경우 일부 작업을 수행하는 단일 식으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="990df-124">An expression-bodied method consists of a single expression that returns a value whose type matches the method's return type, or, for methods that return `void`, that performs some operation.</span></span> <span data-ttu-id="990df-125">예를 들어 <xref:System.Object.ToString%2A> 메서드를 재정의하는 형식에는 일반적으로 현재 개체의 문자열 표현을 반환하는 단일 식이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="990df-125">For example, types that override the <xref:System.Object.ToString%2A> method typically include a single expression that returns the string representation of the current object.</span></span> 

<span data-ttu-id="990df-126">다음 예제에<xref:System.Object.ToString%2A> 메서드를 식 본문 정의로 재정의하는 `Person` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="990df-126">The following example defines a `Person` class that overrides the <xref:System.Object.ToString%2A> method with an expression body definition.</span></span> <span data-ttu-id="990df-127">또한 이름을 콘솔에 표시하는 `Show` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="990df-127">It also defines a `Show` method that displays a name to the console.</span></span> <span data-ttu-id="990df-128">`return` 키워드는 `ToString` 식 본문 정의에 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="990df-128">Note that the `return` keyword is not used in the `ToString` expression body definition.</span></span>

[!code-csharp[expression-bodied-methods](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-methods.cs)]  

<span data-ttu-id="990df-129">자세한 내용은 [메서드(C# 프로그래밍 가이드)](../classes-and-structs/methods.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="990df-129">For more information, see [Methods (C# Programming Guide)](../classes-and-structs/methods.md).</span></span>
 
## <a name="constructors"></a><span data-ttu-id="990df-130">생성자</span><span class="sxs-lookup"><span data-stu-id="990df-130">Constructors</span></span>

<span data-ttu-id="990df-131">생성자에 대한 식 본문 정의는 일반적으로 생성자의 인수를 처리하거나 인스턴스 상태를 초기화하는 단일 할당 식 또는 메서드 호출로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="990df-131">An expression body definition for a constructor typically consists of a single assignment expression or a method call that handles the constructor's arguments or initializes instance state.</span></span> 

<span data-ttu-id="990df-132">다음 예제에서는 생성자에 *name*이라는 단일 문자열 매개 변수가 있는 `Location` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="990df-132">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="990df-133">식 본문 정의에서 `Name` 속성에 인수를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="990df-133">The expression body definition assigns the argument to the `Name` property.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="990df-134">자세한 내용은 [생성자(C# 프로그래밍 가이드)](../classes-and-structs/constructors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="990df-134">For more information, see [Constructors (C# Programming Guide)](../classes-and-structs/constructors.md).</span></span>

## <a name="finalizers"></a><span data-ttu-id="990df-135">종료자</span><span class="sxs-lookup"><span data-stu-id="990df-135">Finalizers</span></span>

<span data-ttu-id="990df-136">종료자에 대한 식 본문 정의에는 일반적으로 관리되지 않는 리소스를 해제하는 문 등의 정리 문이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="990df-136">An expression body definition for a finalizer typically contains cleanup statements, such as statements that release unmanaged resources.</span></span>

<span data-ttu-id="990df-137">다음 예제에서는 식 본문 정의를 사용하여 종료자가 호출되었음을 나타내는 종료자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="990df-137">The following example defines a finalizer that uses an expression body definition to indicate that the finalizer has been called.</span></span>

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  

<span data-ttu-id="990df-138">자세한 내용은 [종료자(C# 프로그래밍 가이드)](../classes-and-structs/destructors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="990df-138">For more information, see [Finalizers (C# Programming Guide)](../classes-and-structs/destructors.md).</span></span>

## <a name="property-get-statements"></a><span data-ttu-id="990df-139">속성 가져오기 문</span><span class="sxs-lookup"><span data-stu-id="990df-139">Property get statements</span></span>

<span data-ttu-id="990df-140">속성 가져오기 접근자를 직접 구현하려는 경우 단순히 속성 값을 반환하는 단일 식에 대해 식 본문 정의를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="990df-140">If you choose to implement a property get accessor yourself, you can use an expression body definition for single expressions that simply return the property value.</span></span> <span data-ttu-id="990df-141">`return` 문은 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="990df-141">Note that the `return` statement isn't used.</span></span>

<span data-ttu-id="990df-142">다음 예제에서는 `Location.Name` 속성을 정의합니다. 이 속성의 속성 가져오기 접근자는 해당 속성을 지원하는 private `locationName` 필드의 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="990df-142">The following example defines a `Location.Name` property whose property get accessor returns the value of the private `locationName` field that backs the property.</span></span> 

[!code-csharp[expression-bodied-property-getter](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="990df-143">식 본문 정의를 사용하는 읽기 전용 속성은 명시적 `set` 문 없이 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="990df-143">Read-only properties that use an expression body definition can be implemented without an explicit `set` statement.</span></span> <span data-ttu-id="990df-144">사용되는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="990df-144">The syntax is:</span></span>

```csharp
PropertyName => returnValue;
```

<span data-ttu-id="990df-145">다음 예제에서는 `Location` 클래스를 정의합니다. 이 클래스의 읽기 전용 `Name` 속성은 private `locationName` 필드의 값을 반환하는 식 본문 정의로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="990df-145">The following example defines a `Location` class whose read-only `Name` property is implemented as an expression body definition that returns the value of the private `locationName` field.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-readonly.cs#1)]  

<span data-ttu-id="990df-146">자세한 내용은 [속성(C# 프로그래밍 가이드)](../classes-and-structs/properties.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="990df-146">For more information, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="property-set-statements"></a><span data-ttu-id="990df-147">속성 설정 문</span><span class="sxs-lookup"><span data-stu-id="990df-147">Property set statements</span></span>

<span data-ttu-id="990df-148">속성 설정 접근자를 직접 구현하려는 경우 속성을 지원하는 필드에 값을 할당하는 한 줄 식에 대해 식 본문 정의를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="990df-148">If you choose to implement a property set accessor yourself, you can use an expression body definition for a single-line expression that assigns a value to the field that backs the property.</span></span>

<span data-ttu-id="990df-149">다음 예제에서는 `Location.Name` 속성을 정의합니다. 이 속성의 속성 설정 문은 해당 속성을 지원하는 private `locationName` 필드에 입력 인수를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="990df-149">The following example defines a `Location.Name` property whose property set statement assigns its input argument to the private `locationName` field that backs the property.</span></span>

[!code-csharp[expression-bodied-property-setter](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="990df-150">자세한 내용은 [속성(C# 프로그래밍 가이드)](../classes-and-structs/properties.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="990df-150">For more information, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="indexers"></a><span data-ttu-id="990df-151">인덱서</span><span class="sxs-lookup"><span data-stu-id="990df-151">Indexers</span></span>

<span data-ttu-id="990df-152">속성과 마찬가지로, get 접근자가 값을 반환하는 단일 문으로 구성되거나 set 접근자가 단순 할당을 수행하는 경우 인덱서의 get 및 set 접근자는 식 본문 정의로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="990df-152">Like properties, an indexer's get and set accessors consist of expression body definitions if the get accessor consists of a single statement that returns a value or the set accessor performs a simple assignment.</span></span>

<span data-ttu-id="990df-153">다음 예제에서는 다양한 스포츠의 이름이 포함된 내부 <xref:System.String> 배열을 포함하는 `Sports`라는 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="990df-153">The following example defines a class named `Sports` that includes an internal <xref:System.String> array that contains the names of a number of sports.</span></span> <span data-ttu-id="990df-154">인덱서의 get 및 set 접근자는 둘 다 식 본문 정의로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="990df-154">Both the indexer's get and set accessors are implemented as expression body definitions.</span></span>

[!code-csharp[expression-bodied-indexer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-indexers.cs#1)] 

<span data-ttu-id="990df-155">자세한 내용은 [인덱서(C# 프로그래밍 가이드)](../indexers/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="990df-155">For more information, see [Indexers (C# Programming Guide)](../indexers/index.md).</span></span>

