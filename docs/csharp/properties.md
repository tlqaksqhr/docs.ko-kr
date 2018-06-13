---
title: 속성
description: 유효성 검사, 계산된 값, 지연 평가, 속성 변경 알림 기능을 포함하는 C# 속성에 대해 알아봅니다.
ms.date: 04/25/2018
ms.openlocfilehash: d4fa7b6117bec63c41318dd4bcc3850ce55a5907
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
ms.locfileid: "33956240"
---
# <a name="properties"></a><span data-ttu-id="f2613-103">속성</span><span class="sxs-lookup"><span data-stu-id="f2613-103">Properties</span></span>

<span data-ttu-id="f2613-104">속성은 C#의 주요 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-104">Properties are first class citizens in C#.</span></span> <span data-ttu-id="f2613-105">언어는 개발자가 디자인 의도를 정확하게 표현하는 코드를 작성할 수 있는 구문을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-105">The language defines syntax that enables developers to write code that accurately expresses their design intent.</span></span>

<span data-ttu-id="f2613-106">속성은 액세스 시 필드처럼 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-106">Properties behave like fields when they are accessed.</span></span>
<span data-ttu-id="f2613-107">그러나 필드와 달리 속성은 속성에 액세스하거나 할당할 때 실행되는 문을 정의하는 접근자로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-107">However, unlike fields, properties are implemented with accessors that define the statements executed when a property is accessed or assigned.</span></span>

## <a name="property-syntax"></a><span data-ttu-id="f2613-108">속성 구문</span><span class="sxs-lookup"><span data-stu-id="f2613-108">Property syntax</span></span>

<span data-ttu-id="f2613-109">속성 구문은 필드에 대한 자연 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-109">The syntax for properties is a natural extension to fields.</span></span> <span data-ttu-id="f2613-110">필드는 저장소 위치를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-110">A field defines a storage location:</span></span>

[!code-csharp[Person class with public fields](../../samples/snippets/csharp/properties/Person.cs#1)]

<span data-ttu-id="f2613-111">속성 정의에는 해당 속성의 값을 검색하고 할당하는 `get` 및 `set` 접근자에 대한 선언이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-111">A property definition contains declarations for a `get` and `set` accessor that retrieves and assigns the value of that property:</span></span>

[!code-csharp[Person class with public properties](../../samples/snippets/csharp/properties/Person.cs#2)]

<span data-ttu-id="f2613-112">위에 표시된 구문은 *자동 속성* 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-112">The syntax shown above is the *auto property* syntax.</span></span> <span data-ttu-id="f2613-113">컴파일러는 속성을 백업하는 필드의 저장소 위치를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-113">The compiler generates the storage location for the field that backs up the property.</span></span> <span data-ttu-id="f2613-114">또한 컴파일러는 `get` 및 `set` 접근자의 본문을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-114">The compiler also implements the body of the `get` and `set` accessors.</span></span>

<span data-ttu-id="f2613-115">때로는 해당 형식의 기본값이 아닌 값으로 속성을 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-115">Sometimes, you need to initialize a property to a value other than the default for its type.</span></span>  <span data-ttu-id="f2613-116">이 작업을 위해 C#에서는 닫는 중괄호 뒤에 속성의 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-116">C# enables that by setting a value after the closing brace for the property.</span></span> <span data-ttu-id="f2613-117">`FirstName` 속성의 초기 값을 `null` 대신 빈 문자열로 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-117">You may prefer the initial value for the `FirstName` property to be the empty string rather than `null`.</span></span> <span data-ttu-id="f2613-118">아래와 같이 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-118">You would specify that as shown below:</span></span>

[!code-csharp[Person class with properties and initializer](../../samples/snippets/csharp/properties/Person.cs#3)]

<span data-ttu-id="f2613-119">이 아티클의 뒷부분에서 살펴보겠지만 특정 초기화는 읽기 전용 속성에 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-119">Specific initialization is most useful for read-only properties, as you'll see later in this article.</span></span>

<span data-ttu-id="f2613-120">아래 표시된 대로 저장소를 직접 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-120">You can also define the storage yourself, as shown below:</span></span>

[!code-csharp[Person class with properties and backing field](../../samples/snippets/csharp/properties/Person.cs#4)]

<span data-ttu-id="f2613-121">속성 구현이 단일 식인 경우 getter 또는 setter에 대해 *식 본문 멤버*를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-121">When a property implementation is a single expression, you can use *expression-bodied members* for the getter or setter:</span></span>

[!code-csharp[Person class with properties and expression bodied getters and setters](../../samples/snippets/csharp/properties/Person.cs#5)]

<span data-ttu-id="f2613-122">이 아티클 전체에서 해당하는 경우 이 간소화된 구문이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-122">This simplified syntax will be used where applicable throughout this article.</span></span>

<span data-ttu-id="f2613-123">위에 표시된 속성 정의는 읽기/쓰기 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-123">The property definition shown above is a read-write property.</span></span> <span data-ttu-id="f2613-124">set 접근자에서 `value` 키워드를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-124">Notice the keyword `value` in the set accessor.</span></span> <span data-ttu-id="f2613-125">`set` 접근자에는 항상 `value`라는 단일 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-125">The `set` accessor always has a single parameter named `value`.</span></span> <span data-ttu-id="f2613-126">`get` 접근자는 속성 형식(이 예제에서는 `string`)으로 변환할 수 있는 값을 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-126">The `get` accessor must return a value that is convertible to the type of the property (`string` in this example).</span></span>

<span data-ttu-id="f2613-127">이것이 기본 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-127">That's the basics of the syntax.</span></span> <span data-ttu-id="f2613-128">다양한 디자인 구문을 지원하는 여러 가지 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-128">There are many different variations that support a variety of different design idioms.</span></span> <span data-ttu-id="f2613-129">각 변환에 대한 구문 옵션을 살펴보고 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-129">Let's explore, and learn the syntax options for each.</span></span>

## <a name="scenarios"></a><span data-ttu-id="f2613-130">시나리오</span><span class="sxs-lookup"><span data-stu-id="f2613-130">Scenarios</span></span>

<span data-ttu-id="f2613-131">위의 예제에서는 가장 간단한 속성 정의 사례 중 하나인 유효성 검사 없는 읽기/쓰기 속성을 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-131">The examples above showed one of the simplest cases of property definition: a read-write property with no validation.</span></span> <span data-ttu-id="f2613-132">`get` 및 `set` 접근자에서 원하는 코드를 작성하여 다양한 시나리오를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-132">By writing the code you want in the `get` and `set` accessors, you can create many different scenarios.</span></span>

### <a name="validation"></a><span data-ttu-id="f2613-133">유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f2613-133">Validation</span></span>

<span data-ttu-id="f2613-134">`set` 접근자에서 코드를 작성하여 속성으로 표현된 값이 항상 유효한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-134">You can write code in the `set` accessor to ensure that the values represented by a property are always valid.</span></span> <span data-ttu-id="f2613-135">예를 들어 이름을 비워 두거나 공백일 수 없다는 `Person` 클래스에 대한 규칙이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-135">For example, suppose one rule for the `Person` class is that the name cannot be blank or white space.</span></span> <span data-ttu-id="f2613-136">다음과 같이 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-136">You would write that as follows:</span></span>

[!code-csharp[Validating property setters](../../samples/snippets/csharp/properties/Person.cs#6)]

<span data-ttu-id="f2613-137">속성 setter 유효성 검사의 일부인 `throw` 식을 사용하여 앞의 예제를 간소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-137">The preceding example can be simplified by using a`throw` expression as part of the property setter validation:</span></span>

[!code-csharp[Validating property setters](../../samples/snippets/csharp/properties/Person.cs#7)]

<span data-ttu-id="f2613-138">위의 예제에서는 첫 번째 이름을 비워 두거나 공백일 수 없다는 규칙을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-138">The example above enforces the rule that the first name must not be blank or white space.</span></span> <span data-ttu-id="f2613-139">개발자가 작성하는 경우</span><span class="sxs-lookup"><span data-stu-id="f2613-139">If a developer writes</span></span>

```csharp
hero.FirstName = "";
```

<span data-ttu-id="f2613-140">해당 할당으로 인해 `ArgumentException`이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-140">That assignment throws an `ArgumentException`.</span></span> <span data-ttu-id="f2613-141">속성 set 접근자의 반환 형식이 void여야 하므로 예외를 throw하여 set 접근자에서 오류를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-141">Because a property set accessor must have a void return type, you report errors in the set accessor by throwing an exception.</span></span>

<span data-ttu-id="f2613-142">이 동일한 구문을 시나리오에서 필요한 항목으로 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-142">You can extend this same syntax to anything needed in your scenario.</span></span> <span data-ttu-id="f2613-143">서로 다른 속성 간의 관계를 확인하거나 모든 외부 조건에 대해 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-143">You can check the relationships between different properties, or validate against any external conditions.</span></span> <span data-ttu-id="f2613-144">유효한 모든 C# 문을 속성 접근자에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-144">Any valid C# statements are valid in a property accessor.</span></span>

### <a name="read-only"></a><span data-ttu-id="f2613-145">읽기 전용</span><span class="sxs-lookup"><span data-stu-id="f2613-145">Read-only</span></span>

<span data-ttu-id="f2613-146">이 시점까지 살펴본 모든 속성 정의는 공용 접근자를 사용한 읽기/쓰기 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-146">Up to this point, all the property definitions you have seen are read/write properties with public accessors.</span></span> <span data-ttu-id="f2613-147">속성에 유효한 유일한 액세스 가능성은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-147">That's not the only valid accessibility for properties.</span></span>
<span data-ttu-id="f2613-148">읽기 전용 속성을 만들거나 set 및 get 접근자에 대해 다른 액세스 가능성을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-148">You can create read-only properties, or give different accessibility to the set and get accessors.</span></span> <span data-ttu-id="f2613-149">`Person` 클래스가 해당 클래스의 다른 메서드에서만 `FirstName` 속성의 값을 변경할 수 있도록 한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-149">Suppose that your `Person` class should only enable changing the value of the `FirstName` property from other methods in that class.</span></span> <span data-ttu-id="f2613-150">set 접근자에 `public` 대신 `private` 액세스 가능성을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-150">You could give the set accessor `private` accessibility instead of `public`:</span></span>

[!code-csharp[Using a private setter for a publicly readonly property](../../samples/snippets/csharp/properties/Person.cs#8)]

<span data-ttu-id="f2613-151">이제 `FirstName` 속성을 모든 코드에서 액세스할 수 있지만 `Person` 클래스의 다른 코드에서만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-151">Now, the `FirstName` property can be accessed from any code, but it can only be assigned from other code in the `Person` class.</span></span>

<span data-ttu-id="f2613-152">set 또는 get 접근자에 제한적인 액세스 한정자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-152">You can add any restrictive access modifier to either the set or get accessors.</span></span> <span data-ttu-id="f2613-153">개별 접근자에 설정하는 액세스 한정자는 속성 정의의 액세스 한정자보다 더 제한적이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-153">Any access modifier you place on the individual accessor must be more limited than the access modifier on the property definition.</span></span> <span data-ttu-id="f2613-154">위 내용은 `FirstName` 속성이 `public`이지만 set 접근자가 `private`이므로 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-154">The above is legal because the `FirstName` property is `public`, but the set accessor is `private`.</span></span> <span data-ttu-id="f2613-155">`public` 접근자를 사용하여 `private` 속성을 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-155">You could not declare a `private` property with a `public` accessor.</span></span> <span data-ttu-id="f2613-156">속성 선언을 `protected`, `internal`, `protected internal` 또는 `private`로 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-156">Property declarations can also be declared `protected`, `internal`, `protected internal`, or, even `private`.</span></span>

<span data-ttu-id="f2613-157">`get` 접근자에 더 제한적인 한정자를 설정하는 것도 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-157">It is also legal to place the more restrictive modifier on the `get` accessor.</span></span> <span data-ttu-id="f2613-158">예를 들어 `public` 속성이 있지만 `get` 접근자를 `private`로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-158">For example, you could have a `public` property, but restrict the `get` accessor to `private`.</span></span> <span data-ttu-id="f2613-159">이 시나리오는 실제로 거의 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-159">That scenario is rarely done in practice.</span></span>

<span data-ttu-id="f2613-160">생성자 또는 속성 이니셜라이저에서만 설정할 수 있도록 속성 수정을 제한할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-160">You can also restrict modifications to a property so that it can only be set in a constructor or a property initializer.</span></span> <span data-ttu-id="f2613-161">다음과 같이 `Person` 클래스를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-161">You can modify the `Person` class so as follows:</span></span>

[!code-csharp[A readonly auto implemented property](../../samples/snippets/csharp/properties/Person.cs#9)]

<span data-ttu-id="f2613-162">이 기능은 읽기 전용 속성으로 노출되는 컬렉션을 초기화하는 데 주로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-162">This feature is most commonly used for initializing collections that are exposed as read-only properties:</span></span>

```csharp
public class Measurements
{
    public ICollection<DataPoint> points { get; } = new List<DataPoint>();
}
```

### <a name="computed-properties"></a><span data-ttu-id="f2613-163">계산된 속성</span><span class="sxs-lookup"><span data-stu-id="f2613-163">Computed properties</span></span>

<span data-ttu-id="f2613-164">속성은 멤버 필드의 값을 반환할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-164">A property does not need to simply return the value of a member field.</span></span> <span data-ttu-id="f2613-165">계산된 값을 반환하는 속성을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-165">You can create properties that return a computed value.</span></span> <span data-ttu-id="f2613-166">`Person` 개체를 확장하여 이름과 성을 연결해서 계산된 전체 이름을 반환하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-166">Let's expand the `Person` object to return the full name, computed by concatenating the first and last names:</span></span>

[!code-csharp[A computed property](../../samples/snippets/csharp/properties/Person.cs#10)]

<span data-ttu-id="f2613-167">위 예에서는 [문자열 보간](../csharp/language-reference/tokens/interpolated.md) 기능을 사용하여 전체 이름에 대한 서식이 지정된 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-167">The example above uses the [string interpolation](../csharp/language-reference/tokens/interpolated.md) feature to create the formatted string for the full name.</span></span>

<span data-ttu-id="f2613-168">계산된 `FullName` 속성을 만드는 보다 간결한 방법을 제공하는 *식 본문 멤버*를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-168">You can also use an *expression-bodied member*, which provides a more succinct way to create the computed `FullName` property:</span></span>

[!code-csharp[A computed property using an expression bodied member](../../samples/snippets/csharp/properties/Person.cs#11)]

<span data-ttu-id="f2613-169">*식 본문 멤버*는 *람다 식* 구문을 사용하여 단일 식이 포함된 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-169">*Expression-bodied members* use the *lambda expression* syntax to define methods that contain a single expression.</span></span> <span data-ttu-id="f2613-170">여기서 해당 식은 person 개체의 전체 이름을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-170">Here, that expression returns the full name for the person object.</span></span>

### <a name="cached-evaluated-properties"></a><span data-ttu-id="f2613-171">캐시된 평가 속성</span><span class="sxs-lookup"><span data-stu-id="f2613-171">Cached evaluated properties</span></span>

<span data-ttu-id="f2613-172">계산된 속성의 개념과 저장소를 혼합하고 *캐시된 평가 속성*을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-172">You can mix the concept of a computed property with storage and create a *cached evaluated property*.</span></span>  <span data-ttu-id="f2613-173">예를 들어 처음 액세스할 때만 문자열 형식이 지정되도록 `FullName` 속성을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-173">For example, you could update the `FullName` property so that the string formatting only happened the first time it was accessed:</span></span>

[!code-csharp[Caching the value of a computed property](../../samples/snippets/csharp/properties/Person.cs#12)]

<span data-ttu-id="f2613-174">하지만 위의 코드에는 버그가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-174">The above code contains a bug though.</span></span> <span data-ttu-id="f2613-175">코드가 `FirstName` 또는 `LastName` 속성의 값을 업데이트하는 경우 이전에 평가한 `fullName` 필드는 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-175">If code updates the value of either the `FirstName` or `LastName` property, the previously evaluated `fullName` field is invalid.</span></span> <span data-ttu-id="f2613-176">`fullName` 필드가 다시 평가되도록 `FirstName` 및 `LastName` 속성의 `set` 접근자를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-176">You modify the `set` accessors of the `FirstName` and `LastName` property so that the `fullName` field is calculated again:</span></span>

[!code-csharp[Invalidating the cache correctly](../../samples/snippets/csharp/properties/Person.cs#13)]

<span data-ttu-id="f2613-177">이 최종 버전은 필요한 경우에만 `FullName` 속성을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-177">This final version evaluates the `FullName` property only when needed.</span></span>
<span data-ttu-id="f2613-178">이전에 계산한 버전이 유효한 경우 해당 버전이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-178">If the previously calculated version is valid, it's used.</span></span> <span data-ttu-id="f2613-179">다른 상태 변경으로 인해 이전에 계산한 버전이 무효화된 경우 다시 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-179">If another state change invalidates the previously calculated version, it will be recalculated.</span></span> <span data-ttu-id="f2613-180">이 클래스를 사용하는 개발자는 구현 세부 정보를 알 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-180">Developers that use this class do not need to know the details of the implementation.</span></span> <span data-ttu-id="f2613-181">이러한 내부 변경 내용은 Person 개체의 사용에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-181">None of these internal changes affect the use of the Person object.</span></span> <span data-ttu-id="f2613-182">이것이 속성을 사용하여 개체의 데이터 멤버를 노출하는 주요 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-182">That's the key reason for using Properties to expose data members of an object.</span></span>

### <a name="attaching-attributes-to-auto-implemented-properties"></a><span data-ttu-id="f2613-183">자동 구현 속성에 특성 연결</span><span class="sxs-lookup"><span data-stu-id="f2613-183">Attaching attributes to auto-implemented properties</span></span>

<span data-ttu-id="f2613-184">C# 7.3부터 필드 특성은 자동 구현된 속성의 컴파일러에서 생성된 지원 필드에 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-184">Beginning with C# 7.3, field attributes can be attached to the compiler generated backing field in auto-implemented properties.</span></span> <span data-ttu-id="f2613-185">예를 들어 고유한 정수 `Id` 속성을 추가하는 `Person` 클래스에 대한 수정 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-185">For example, consider a revision to the `Person` class that adds a unique integer `Id` property.</span></span>
<span data-ttu-id="f2613-186">자동 구현 속성을 사용하여 `Id` 속성을 작성하지만 디자인은 `Id` 속성을 유지하기 위해 호출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-186">You write the`Id` property using an auto-implemented property, but your design does not call for persisting the `Id` property.</span></span> <span data-ttu-id="f2613-187"><xref:System.NonSerializedAttribute>는 속성이 아니라 필드에만 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-187">The <xref:System.NonSerializedAttribute> can only be attached to fields, not properties.</span></span> <span data-ttu-id="f2613-188">다음 예제와 같이 특성에 `field:` 지정자를 사용하여 `Id` 속성의 지원 필드에 <xref:System.NonSerializedAttribute>를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-188">You can attach the <xref:System.NonSerializedAttribute> to the backing field for the `Id` property by using the `field:` specifier on the attribute, as shown in the following example:</span></span>

[!code-csharp[Attaching attributes to a backing field](../../samples/snippets/csharp/properties/Person.cs#14)]

<span data-ttu-id="f2613-189">이 기술은 자동 구현 속성의 지원 필드에 연결하는 모든 특성에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-189">This technique works for any attribute you attach to the backing field on the auto-implemented property.</span></span>

### <a name="implementing-inotifypropertychanged"></a><span data-ttu-id="f2613-190">INotifyPropertyChanged 구현</span><span class="sxs-lookup"><span data-stu-id="f2613-190">Implementing INotifyPropertyChanged</span></span>

<span data-ttu-id="f2613-191">속성 접근자에서 코드를 작성해야 하는 최종 시나리오는 값이 변경되었다고 데이터 바인딩 클라이언트에 알리는 데 사용되는 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 지원하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-191">A final scenario where you need to write code in a property accessor is to support the <xref:System.ComponentModel.INotifyPropertyChanged> interface used to notify data binding clients that a value has changed.</span></span> <span data-ttu-id="f2613-192">속성의 값이 변경되면 개체가 <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged?displayProperty=nameWithType> 이벤트를 발생시켜 변경되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-192">When the value of a property changes, the object raises the <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged?displayProperty=nameWithType> event to indicate the change.</span></span> <span data-ttu-id="f2613-193">데이터 바인딩 라이브러리가 해당 변경 내용에 따라 차례로 표시 요소를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-193">The data binding libraries, in turn, update display elements based on that change.</span></span> <span data-ttu-id="f2613-194">아래 코드는 이 person 클래스의 `FirstName` 속성에 대해 `INotifyPropertyChanged`를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-194">The code below shows how you would implement `INotifyPropertyChanged` for the `FirstName` property of this person class.</span></span>

[!code-csharp[invalidating the cache correctly](../../samples/snippets/csharp/properties/Person.cs#15)]

<span data-ttu-id="f2613-195">`?.` 연산자를 *null 조건부 연산자*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-195">The `?.` operator is called the *null conditional operator*.</span></span> <span data-ttu-id="f2613-196">연산자의 오른쪽을 평가하기 전에 null 참조를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-196">It checks for a null reference before evaluating the right side of the operator.</span></span> <span data-ttu-id="f2613-197">최종 결과로, `PropertyChanged` 이벤트에 대한 구독자가 없는 경우 이벤트를 발생시키는 코드가 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-197">The end result is that if there are no subscribers to the `PropertyChanged` event, the code to raise the event doesn't execute.</span></span> <span data-ttu-id="f2613-198">해당 경우 이 확인을 수행하지 않으면 `NullReferenceException`이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-198">It would throw a `NullReferenceException` without this check in that case.</span></span> <span data-ttu-id="f2613-199">자세한 내용은 [`events`](delegates-events.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f2613-199">For more information, see [`events`](delegates-events.md).</span></span> <span data-ttu-id="f2613-200">또한 이 예제에서는 새 `nameof` 연산자를 사용하여 속성 이름 기호에서 해당 텍스트 표현으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-200">This example also uses the new `nameof` operator to convert from the property name symbol to its text representation.</span></span>
<span data-ttu-id="f2613-201">`nameof`를 사용하면 속성 이름을 잘못 입력하는 오류를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-201">Using `nameof` can reduce errors where you have mistyped the name of the property.</span></span>

<span data-ttu-id="f2613-202"><xref:System.ComponentModel.INotifyPropertyChanged>를 구현하는 작업은 필요한 시나리오를 지원하기 위해 접근자의 코드를 작성할 수 있는 경우의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-202">Again, implementing <xref:System.ComponentModel.INotifyPropertyChanged> is an example of a case where you can write code in your accessors to support the scenarios you need.</span></span>

## <a name="summing-up"></a><span data-ttu-id="f2613-203">요약</span><span class="sxs-lookup"><span data-stu-id="f2613-203">Summing up</span></span>

<span data-ttu-id="f2613-204">속성은 클래스 또는 개체에 있는 스마트 필드의 한 형태입니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-204">Properties are a form of smart fields in a class or object.</span></span> <span data-ttu-id="f2613-205">개체 외부에서는 개체의 필드와 유사하게 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-205">From outside the object, they appear like fields in the object.</span></span> <span data-ttu-id="f2613-206">그러나 C# 기능의 전체 팔레트를 사용하여 속성을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-206">However, properties can be implemented using the full palette of C# functionality.</span></span>
<span data-ttu-id="f2613-207">유효성 검사, 다른 액세스 가능성, 지연 평가 또는 시나리오에 필요한 모든 요구 사항을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2613-207">You can provide validation, different accessibility, lazy evaluation, or any requirements your scenarios need.</span></span>
