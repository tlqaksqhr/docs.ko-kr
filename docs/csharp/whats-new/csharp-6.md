---
title: C# 6의 새로운 기능 - C# 가이드
description: C# 버전 6의 새로운 기능을 알아봅니다.
ms.date: 09/22/2016
ms.assetid: 4d879f69-f889-4d3f-a781-75194e143400
ms.openlocfilehash: 00aeb3ed940acfca748a1a9eb876fd0133baf6c0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="whats-new-in-c-6"></a><span data-ttu-id="a6b8a-103">C# 6의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="a6b8a-103">What's New in C# 6</span></span>

<span data-ttu-id="a6b8a-104">C#의 6.0 릴리스에는 개발자의 생산성을 개선하는 많은 기능이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-104">The 6.0 release of C# contained many features that improve productivity for developers.</span></span> <span data-ttu-id="a6b8a-105">이 릴리스의 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-105">Features in this release include:</span></span>

* <span data-ttu-id="a6b8a-106">[읽기 전용 Auto 속성](#read-only-auto-properties):</span><span class="sxs-lookup"><span data-stu-id="a6b8a-106">[Read-only Auto-properties](#read-only-auto-properties):</span></span>
    - <span data-ttu-id="a6b8a-107">생성자에서만 설정할 수 있는 읽기 전용 auto 속성을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-107">You can create read-only auto-properties that can be set only in constructors.</span></span>
* <span data-ttu-id="a6b8a-108">[Auto 속성 이니셜라이저](#auto-property-initializers)</span><span class="sxs-lookup"><span data-stu-id="a6b8a-108">[Auto-Property Initializers](#auto-property-initializers):</span></span>
    - <span data-ttu-id="a6b8a-109">Auto 속성의 초기 값을 설정하는 초기화 식을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-109">You can write initialization expressions to set the initial value of an auto-property.</span></span>
* <span data-ttu-id="a6b8a-110">[식 본문 함수 멤버](#expression-bodied-function-members):</span><span class="sxs-lookup"><span data-stu-id="a6b8a-110">[Expression-bodied function members](#expression-bodied-function-members):</span></span>
    - <span data-ttu-id="a6b8a-111">람다 식을 사용하여 한 줄 메서드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-111">You can author one-line methods using lambda expressions.</span></span>
* <span data-ttu-id="a6b8a-112">[using static](#using-static):</span><span class="sxs-lookup"><span data-stu-id="a6b8a-112">[using static](#using-static):</span></span>
    - <span data-ttu-id="a6b8a-113">단일 클래스의 모든 메서드를 현재 네임스페이스로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-113">You can import all the methods of a single class into the current namespace.</span></span>
* <span data-ttu-id="a6b8a-114">[Null - 조건 연산자](#null-conditional-operators):</span><span class="sxs-lookup"><span data-stu-id="a6b8a-114">[Null - conditional operators](#null-conditional-operators):</span></span>
    - <span data-ttu-id="a6b8a-115">Null 조건 연산자를 사용하여 null이 있는지 계속 확인하면서 개체의 멤버에 간결하고 안전하게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-115">You can concisely and safely access members of an object while still checking for null with the null conditional operator.</span></span>
* <span data-ttu-id="a6b8a-116">[문자열 보간](#string-interpolation):</span><span class="sxs-lookup"><span data-stu-id="a6b8a-116">[String Interpolation](#string-interpolation):</span></span>
    - <span data-ttu-id="a6b8a-117">위치 인수 대신 인라인 식을 사용하여 문자열 서식 지정 식을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-117">You can write string formatting expressions using inline expressions instead of positional arguments.</span></span>
* <span data-ttu-id="a6b8a-118">[예외 필터](#exception-filters):</span><span class="sxs-lookup"><span data-stu-id="a6b8a-118">[Exception filters](#exception-filters):</span></span>
    - <span data-ttu-id="a6b8a-119">예외 속성 또는 기타 프로그램 상태에 따라 식을 catch할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-119">You can catch expressions based on properties of the exception or other program state.</span></span> 
* <span data-ttu-id="a6b8a-120">[nameof 식](#nameof-expressions):</span><span class="sxs-lookup"><span data-stu-id="a6b8a-120">[nameof Expressions](#nameof-expressions):</span></span>
    - <span data-ttu-id="a6b8a-121">컴파일러를 통해 기호의 문자열 표현을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-121">You can let the compiler generate string representations of symbols.</span></span>
* <span data-ttu-id="a6b8a-122">[catch 및 finally 블록의 await](#await-in-catch-and-finally-blocks):</span><span class="sxs-lookup"><span data-stu-id="a6b8a-122">[await in catch and finally blocks](#await-in-catch-and-finally-blocks):</span></span>
    - <span data-ttu-id="a6b8a-123">이전에 허용되지 않았던 위치에서 `await` 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-123">You can use `await` expressions in locations that previously disallowed them.</span></span>
* <span data-ttu-id="a6b8a-124">[인덱스 이니셜라이저](#index-initializers):</span><span class="sxs-lookup"><span data-stu-id="a6b8a-124">[index initializers](#index-initializers):</span></span>
    - <span data-ttu-id="a6b8a-125">시퀀스 컨테이너 및 연관 컨테이너에 대한 초기화 식을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-125">You can author initialization expressions for associative containers as well as sequence containers.</span></span>
* <span data-ttu-id="a6b8a-126">[컬렉션 이니셜라이저의 확장 메서드](#extension-add-methods-in-collection-initializers):</span><span class="sxs-lookup"><span data-stu-id="a6b8a-126">[Extension methods for collection initializers](#extension-add-methods-in-collection-initializers):</span></span>
    - <span data-ttu-id="a6b8a-127">컬렉션 이니셜라이저는 멤버 메서드 이외에 액세스 가능한 확장 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-127">Collection initializers can rely on accessible extension methods, in addition to member methods.</span></span>
* <span data-ttu-id="a6b8a-128">[향상된 오버로드 확인](#improved-overload-resolution):</span><span class="sxs-lookup"><span data-stu-id="a6b8a-128">[Improved overload resolution](#improved-overload-resolution):</span></span>
    - <span data-ttu-id="a6b8a-129">이전에 모호한 호출을 생성한 일부 구문이 이제 제대로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-129">Some constructs that previously generated ambiguous method calls now resolve correctly.</span></span>

<span data-ttu-id="a6b8a-130">이러한 기능의 전반적인 영향은 더 읽기 쉬운 더 간결한 코드를 작성한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-130">The overall effect of these features is that you write more concise code that is also more readable.</span></span> <span data-ttu-id="a6b8a-131">많은 일반적인 사례에 대한 더 적은 의례가 구문에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-131">The syntax contains less ceremony for many common practices.</span></span> <span data-ttu-id="a6b8a-132">더 적은 의례로 디자인 의도를 더 쉽게 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-132">It's easier to see the design intent with less ceremony.</span></span> <span data-ttu-id="a6b8a-133">이러한 기능을 알고 있으면 생산성이 향상되고 더 읽기 쉬운 코드를 작성하고 언어의 구문보다 핵심 기능에 더 집중하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-133">Learn these features well, and you'll be more productive, write more readable code, and concentrate more on your core features than on the constructs of the language.</span></span>

<span data-ttu-id="a6b8a-134">이 항목의 나머지 부분에서는 이러한 기능을 각각 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-134">The remainder of this topic provides details on each of these features.</span></span>

## <a name="auto-property-enhancements"></a><span data-ttu-id="a6b8a-135">Auto 속성 향상된 기능</span><span class="sxs-lookup"><span data-stu-id="a6b8a-135">Auto-Property enhancements</span></span> 

<span data-ttu-id="a6b8a-136">자동으로 구현된 속성에 대한 구문(대개 “auto 속성"이라고 함) 덕분에 간단한 get 및 set 접근자가 포함된 속성을 매우 쉽게 만들 수 있습니다:</span><span class="sxs-lookup"><span data-stu-id="a6b8a-136">The syntax for automatically implemented properties (usually referred to as 'auto-properties') made it very easy to create properties that had simple get and set accessors:</span></span>

[!code-csharp[ClassicAutoProperty](../../../samples/snippets/csharp/new-in-6/oldcode.cs#ClassicAutoProperty)]

<span data-ttu-id="a6b8a-137">하지만 이 간단한 구문은 auto 속성 사용을 지원할 수 있는 디자인 종류를 제한했습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-137">However, this simple syntax limited the kinds of designs you could support using auto-properties.</span></span> <span data-ttu-id="a6b8a-138">C# 6에서는 더 많은 시나리오에서 사용할 수 있도록 auto 속성 기능이 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-138">C# 6 improves the auto-properties capabilities so that you can use them in more scenarios.</span></span> <span data-ttu-id="a6b8a-139">지원 필드를 직접 자주 선언하고 조작하는 더 자세한 구문을 대신 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-139">You won't need to fall back on the more verbose syntax of declaring and manipulating the backing field by hand so often.</span></span>

<span data-ttu-id="a6b8a-140">새 구문은 읽기 전용 속성에 대한 시나리오와 auto 속성 뒤에서 변수 저장소를 초기화하는 시나리오를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-140">The new syntax addresses scenarios for read-only properties, and for initializing the variable storage behind an auto-property.</span></span>

### <a name="read-only-auto-properties"></a><span data-ttu-id="a6b8a-141">읽기 전용 auto 속성</span><span class="sxs-lookup"><span data-stu-id="a6b8a-141">Read-only auto-properties</span></span>

<span data-ttu-id="a6b8a-142">*읽기 전용 auto 속성*은 변경할 수 없는 형식을 만드는 더 간결한 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-142">*Read-only auto-properties* provide a more concise syntax to create immutable types.</span></span> <span data-ttu-id="a6b8a-143">C#의 이전 버전에서 변경할 수 없는 형식을 사용하는 것과 가장 가까운 방법은 private setter를 선언하는 것이었습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-143">The closest you could get to immutable types in earlier versions of C# was to declare private setters:</span></span>

[!code-csharp[ClassicReadOnlyAutoProperty](../../../samples/snippets/csharp/new-in-6/oldcode.cs#ClassicReadOnlyAutoProperty)]
 
<span data-ttu-id="a6b8a-144">이 구문을 사용하면 컴파일러에서는 형식이 실제로 변경할 수 없는지 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-144">Using this syntax, the compiler doesn't ensure that the type really is immutable.</span></span> <span data-ttu-id="a6b8a-145">`FirstName` 및 `LastName` 속성이 클래스 외부의 코드에서 수정되지 않도록만 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-145">It only enforces that the `FirstName` and `LastName` properties are not modified from any code outside the class.</span></span>

<span data-ttu-id="a6b8a-146">읽기 전용 auto 속성은 실제 읽기 전용 동작을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-146">Read-only auto-properties enable true read-only behavior.</span></span> <span data-ttu-id="a6b8a-147">get 접근자만 사용하여 auto 속성을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-147">You declare the auto-property with only a get accessor:</span></span>

[!code-csharp[ReadOnlyAutoProperty](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadOnlyAutoProperty)]

<span data-ttu-id="a6b8a-148">`FirstName` 및 `LastName` 속성은 생성자 본문에서만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-148">The `FirstName` and `LastName` properties can be set only in the body of a constructor:</span></span>

[!code-csharp[ReadOnlyAutoPropertyConstructor](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadOnlyAutoPropertyConstructor)]

<span data-ttu-id="a6b8a-149">다른 메서드에서 `LastName`을 설정하려고 하면 `CS0200` 컴파일 오류가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-149">Trying to set `LastName` in another method generates a `CS0200` compilation error:</span></span>

```csharp
public class Student
{
    public string LastName { get;  }

    public void ChangeName(string newLastName)
    {
        // Generates CS0200: Property or indexer cannot be assigned to -- it is read only
        LastName = newLastName;
    }
}
```

<span data-ttu-id="a6b8a-150">이 기능은 변경할 수 없는 형식을 만들고 더 간결하고 편리한 auto 속성 구문을 사용하기 위한 실제 언어 지원을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-150">This feature enables true language support for creating immutable types and using the more concise and convenient auto-property syntax.</span></span>

### <a name="auto-property-initializers"></a><span data-ttu-id="a6b8a-151">Auto 속성 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="a6b8a-151">Auto-Property Initializers</span></span>

<span data-ttu-id="a6b8a-152">*Auto 속성 이니셜라이저*를 통해 속성 선언의 일부로 auto 속성의 초기 값을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-152">*Auto-Property Initializers* let you declare the initial value for an auto-property as part of the property declaration.</span></span>  <span data-ttu-id="a6b8a-153">이전 버전에서는 이러한 속성에 setter를 포함해야 하고, 지원 필드에서 사용되는 데이터 저장소를 초기화하려면 해당 setter를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-153">In earlier versions, these properties would need to have setters and you would need to use that setter to initialize the data storage used by the backing field.</span></span> <span data-ttu-id="a6b8a-154">이름이 포함된 학생 및 학생의 성적 목록에 이 클래스를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-154">Consider this class for a student that contains the name and a list of the student's grades:</span></span>

[!code-csharp[Construction](../../../samples/snippets/csharp/new-in-6/oldcode.cs#Construction)]
 
<span data-ttu-id="a6b8a-155">이 클래스가 커지면 다른 생성자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-155">As this class grows, you may include other constructors.</span></span> <span data-ttu-id="a6b8a-156">각 생성자는 이 필드를 초기화해야 합니다. 초기화하지 않으면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-156">Each constructor needs to initialize this field, or you'll introduce errors.</span></span>

<span data-ttu-id="a6b8a-157">C# 6에서는 auto 속성 선언에서 auto 속성에 사용되는 저장소의 초기 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-157">C# 6 enables you to assign an initial value for the storage used by an auto-property in the auto-property declaration:</span></span>

[!code-csharp[Initialization](../../../samples/snippets/csharp/new-in-6/newcode.cs#Initialization)]

<span data-ttu-id="a6b8a-158">`Grades` 멤버는 선언된 위치에서 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-158">The `Grades` member is initialized where it is declared.</span></span> <span data-ttu-id="a6b8a-159">따라서 더 쉽게 정확히 한 번 초기화를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-159">That makes it easier to perform the initialization exactly once.</span></span> <span data-ttu-id="a6b8a-160">초기화가 속성 선언의 일부이므로 `Student` 개체에 대한 public 인터페이스를 통해 저장소를 균등하게 할당하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-160">The initialization is part of the property declaration, making it easier to equate the storage allocation with public interface for `Student` objects.</span></span>

<span data-ttu-id="a6b8a-161">다음과 같이 속성 이니셜라이저는 읽기 전용 속성 및 읽기/쓰기 속성과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-161">Property Initializers can be used with read/write properties as well as read-only properties, as shown here.</span></span>

[!code-csharp[ReadWriteInitialization](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadWriteInitialization)]

## <a name="expression-bodied-function-members"></a><span data-ttu-id="a6b8a-162">식 본문 함수 멤버</span><span class="sxs-lookup"><span data-stu-id="a6b8a-162">Expression-bodied function members</span></span>

<span data-ttu-id="a6b8a-163">여기서 작성하는 많은 멤버의 본문은 식으로 표현될 수 있는 하나의 식으로만 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-163">The body of a lot of members that we write consist of only one statement that can be represented as an expression.</span></span> <span data-ttu-id="a6b8a-164">대신 식 본문 멤버를 작성하여 해당 구문을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-164">You can reduce that syntax by writing an expression-bodied member instead.</span></span> <span data-ttu-id="a6b8a-165">이 내용은 메서드 및 읽기 전용 속성에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-165">It works for methods and read-only properties.</span></span> <span data-ttu-id="a6b8a-166">예를 들어 `ToString()`의 재정의가 좋은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-166">For example, an override of `ToString()` is often a great candidate:</span></span>

[!code-csharp[ToStringExpressionMember](../../../samples/snippets/csharp/new-in-6/newcode.cs#ToStringExpressionMember)]

<span data-ttu-id="a6b8a-167">읽기 전용 속성에서도 식 본문 멤버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-167">You can also use expression-bodied members in read-only properties as well:</span></span>

[!code-csharp[FullNameExpressionMember](../../../samples/snippets/csharp/new-in-6/newcode.cs#FullNameExpressionMember)]

## <a name="using-static"></a><span data-ttu-id="a6b8a-168">using static</span><span class="sxs-lookup"><span data-stu-id="a6b8a-168">using static</span></span>

<span data-ttu-id="a6b8a-169">*using static* 향상된 기능을 사용하여 단일 클래스의 정적 메서드를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-169">The *using static* enhancement enables you to import the static methods of a single class.</span></span> <span data-ttu-id="a6b8a-170">이전에는 `using` 문으로 네임스페이스의 모든 형식을 가져왔습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-170">Previously, the `using` statement imported all types in a namespace.</span></span> 

<span data-ttu-id="a6b8a-171">일반적으로 전체 코드에서 클래스의 정적 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-171">Often we use a class' static methods throughout our code.</span></span> <span data-ttu-id="a6b8a-172">클래스 이름을 반복해서 입력하면 코드의 의미가 모호해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-172">Repeatedly typing the class name can obscure the meaning of your code.</span></span> <span data-ttu-id="a6b8a-173">일반적인 예는 많은 숫자 계산을 수행하는 클래스를 작성하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-173">A common example is when you write classes that perform many numeric calculations.</span></span>
<span data-ttu-id="a6b8a-174">코드는 <xref:System.Math.Sin%2A>, <xref:System.Math.Sqrt%2A>, 및 <xref:System.Math> 클래스의 여러 가지 메서드에 대한 기타 호출로 복잡해집니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-174">Your code will be littered with <xref:System.Math.Sin%2A>, <xref:System.Math.Sqrt%2A> and other calls to different methods in the <xref:System.Math> class.</span></span> <span data-ttu-id="a6b8a-175">새 `using static` 구문을 사용하면 이러한 클래스를 훨씬 더 깔끔하게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-175">The new `using static` syntax can make these classes much cleaner to read.</span></span> <span data-ttu-id="a6b8a-176">사용 중인 클래스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-176">You specify the class you're using:</span></span>

[!code-csharp[UsingStaticMath](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticMath)]

<span data-ttu-id="a6b8a-177">이제 <xref:System.Math> 클래스를 한정하지 않고 <xref:System.Math> 클래스에서 정적 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-177">And now, you can use any static method in the <xref:System.Math> class without qualifying the <xref:System.Math> class.</span></span> <span data-ttu-id="a6b8a-178"><xref:System.Math> 클래스는 인스턴스 메서드를 포함하지 않으므로 이 기능에 대한 좋은 사용 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-178">The <xref:System.Math> class is a great use case for this feature because it does not contain any instance methods.</span></span> <span data-ttu-id="a6b8a-179">`using static`을 사용하여 정적 및 인스턴스 메서드가 둘 다 포함된 클래스에 대한 클래스의 정적 메서드를 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-179">You can also use `using static` to import a class' static methods for a class that has both static and instance methods.</span></span> <span data-ttu-id="a6b8a-180">가장 유용한 예 중 하나는 <xref:System.String>입니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-180">One of the most useful examples is <xref:System.String>:</span></span>

[!code-csharp[UsingStatic](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStatic)]

> [!NOTE]
> <span data-ttu-id="a6b8a-181">static using 문에서는 정규화된 클래스 이름 `System.String`을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-181">You must use the fully qualified class name, `System.String` in a static using statement.</span></span> <span data-ttu-id="a6b8a-182">대신 `string` 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-182">You cannot use the `string` keyword instead.</span></span> 

<span data-ttu-id="a6b8a-183">이제 <xref:System.String> 클래스에 정의된 정적 메서드를 해당 클래스의 멤버로 한정하지 않고 해당 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-183">You can now call static methods defined in the <xref:System.String> class without qualifying those methods as members of that class:</span></span>

[!code-csharp[UsingStaticString](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticString)]

<span data-ttu-id="a6b8a-184">`static using` 기능 및 확장 메서드는 흥미로운 방식으로 상호 작용하고 언어 디자인에는 해당 상호 작용을 구체적으로 처리하는 몇 가지 규칙이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-184">The `static using` feature and extension methods interact in interesting ways, and the language design included some rules that specifically address those interactions.</span></span> <span data-ttu-id="a6b8a-185">목적은 기존 코드베이스에서 주요한 변경이 발생할 가능성을 최소화하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-185">The goal is to minimize any chances of breaking changes in existing codebases, including yours.</span></span>

<span data-ttu-id="a6b8a-186">확장 메서드는 정적 메서드로 호출될 때가 아닌 확장 메서드 호출 구문을 사용하여 호출될 때만 범위 내에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-186">Extension methods are only in scope when called using the extension method invocation syntax, not when called as a static method.</span></span>
<span data-ttu-id="a6b8a-187">일반적으로 LINQ 쿼리에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-187">You'll often see this in LINQ queries.</span></span> <span data-ttu-id="a6b8a-188"><xref:System.Linq.Enumerable>을 가져와 LINQ 패턴을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-188">You can import the LINQ pattern by importing <xref:System.Linq.Enumerable>.</span></span>

[!code-csharp[UsingStaticLinq](../../../samples/snippets/csharp/new-in-6/newcode.cs#usingStaticLinq)]

<span data-ttu-id="a6b8a-189">이 작업은 <xref:System.Linq.Enumerable> 클래스의 모든 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-189">This imports all the methods in the <xref:System.Linq.Enumerable> class.</span></span>
<span data-ttu-id="a6b8a-190">그러나 확장 메서드는 확장 메서드로 호출될 때만 범위 내에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-190">However, the extension methods are only in scope when called as extension methods.</span></span> <span data-ttu-id="a6b8a-191">정적 메서드 구문을 사용하여 호출될 경우 범위 내에 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-191">They are not in scope if they are called using the static method syntax:</span></span>

[!code-csharp[UsingStaticLinqMethod](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticLinkMethod)]

<span data-ttu-id="a6b8a-192">이 결정은 일반적으로 확장 메서드는 확장 메서드 호출 식을 사용하여 호출되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-192">This decision is because extension methods are typically called using extension method invocation expressions.</span></span> <span data-ttu-id="a6b8a-193">드물지만 확장 메서드가 정적 메서드 호출 구문을 사용하여 호출될 경우에는 모호성이 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-193">In the rare case where they are called using the static method call syntax it is to resolve ambiguity.</span></span>
<span data-ttu-id="a6b8a-194">호출의 일부로 클래스 이름을 요구하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-194">Requiring the class name as part of the invocation seems wise.</span></span>

<span data-ttu-id="a6b8a-195">`static using`의 마지막 한 가지 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-195">There's one last feature of `static using`.</span></span> <span data-ttu-id="a6b8a-196">`static using` 지시문은 모든 중첩 형식도 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-196">The `static using` directive also imports any nested types.</span></span> <span data-ttu-id="a6b8a-197">이 기능을 통해 한정 없이 중첩 형식을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-197">That enables you to reference any nested types without qualification.</span></span>

## <a name="null-conditional-operators"></a><span data-ttu-id="a6b8a-198">Null 조건 연산자</span><span class="sxs-lookup"><span data-stu-id="a6b8a-198">Null-conditional operators</span></span>

<span data-ttu-id="a6b8a-199">Null 값은 코드를 복잡하게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-199">Null values complicate code.</span></span> <span data-ttu-id="a6b8a-200">`null`을 역참조하지 않는지 확인하려면 변수의 모든 액세스를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-200">You need to check every access of variables to ensure you are not dereferencing `null`.</span></span> <span data-ttu-id="a6b8a-201">*null 조건 연산자*를 사용하면 이러한 확인이 훨씬 더 쉽고 유연합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-201">The *null conditional operator* makes those checks much easier and fluid.</span></span>

<span data-ttu-id="a6b8a-202">멤버 액세스 `.`를 `?.`로 바꾸면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-202">Simply replace the member access `.` with `?.`:</span></span>

[!code-csharp[NullConditional](../../../samples/snippets/csharp/new-in-6/program.cs#NullConditional)]

<span data-ttu-id="a6b8a-203">이전 예제에서 person 개체가 `null`인 경우 `first` 변수에 `null`이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-203">In the preceding example, the variable `first` is assigned `null` if the person object is `null`.</span></span> <span data-ttu-id="a6b8a-204">null이 아닌 경우 `FirstName` 속성의 값이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-204">Otherwise, it gets assigned the value of the `FirstName` property.</span></span> <span data-ttu-id="a6b8a-205">가장 중요한 점은 `?.`는 `person` 변수가 `null`일 경우 이 코드 줄이 `NullReferenceException`을 생성하지 않음을 의미한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-205">Most importantly, the `?.` means that this line of code does not generate a `NullReferenceException` when the `person` variable is `null`.</span></span> <span data-ttu-id="a6b8a-206">대신 이 코드 줄은 단락되고 `null`을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-206">Instead, it short-circuits and produces `null`.</span></span>

<span data-ttu-id="a6b8a-207">또한 이 식은 `person` 값에 관계없이 `string`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-207">Also, note that this expression returns a `string`, regardless of the value of `person`.</span></span>
<span data-ttu-id="a6b8a-208">단락의 경우 반환된 `null` 값은 전체 식과 일치하도록 형식화됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-208">In the case of short circuiting, the `null` value returned is typed to match the full expression.</span></span>

<span data-ttu-id="a6b8a-209">이 구문을 *null 결합* 연산자와 함께 사용하여 속성 중 하나가 `null`일 경우 기본값을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-209">You can often use this construct with the *null coalescing* operator to assign default values when one of the properties are `null`:</span></span>

[!code-csharp[NullCoalescing](../../../samples/snippets/csharp/new-in-6/program.cs#NullCoalescing)]

<span data-ttu-id="a6b8a-210">`?.` 연산자의 오른쪽 피연산자는 속성 또는 필드로 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-210">The right hand side operand of the `?.` operator is not limited to properties or fields.</span></span>
<span data-ttu-id="a6b8a-211">메서드를 조건부로 호출하는 데 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-211">You can also use it to conditionally invoke methods.</span></span> <span data-ttu-id="a6b8a-212">null 조건 연산자와 함께 멤버 함수를 사용하는 가장 일반적인 경우는 `null`일 수 있는 대리자(또는 이벤트 처리기)를 안전하게 호출하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-212">The most common use of member functions with the null conditional operator is to safely invoke delegates (or event handlers) that may be `null`.</span></span>  <span data-ttu-id="a6b8a-213">이 작업을 수행하려면 `?.` 연산자를 통해 대리자의 `Invoke` 메서드를 호출하여 멤버에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-213">You'll do this by calling the delegate's `Invoke` method using the `?.` operator to access the member.</span></span> <span data-ttu-id="a6b8a-214">예제는</span><span class="sxs-lookup"><span data-stu-id="a6b8a-214">You can see an example in the</span></span>  
<span data-ttu-id="a6b8a-215">[대리자 패턴](../delegates-patterns.md#handling-null-delegates) 항목에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-215">[delegate patterns](../delegates-patterns.md#handling-null-delegates) topic.</span></span>

<span data-ttu-id="a6b8a-216">`?.` 연산자 규칙을 적용하면 연산자의 왼쪽이 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-216">The rules of the `?.` operator ensure that the left-hand side of the operator is evaluated only once.</span></span> <span data-ttu-id="a6b8a-217">이 기능은 중요하고 이벤트 처리기 사용 예제를 비롯한 많은 관용구를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-217">This is important and enables many idioms, including the example using event handlers.</span></span> <span data-ttu-id="a6b8a-218">먼저 이벤트 처리기 사용법을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-218">Let's start with the event handler usage.</span></span> <span data-ttu-id="a6b8a-219">C#의 이전 버전에서는 다음과 같이 코드를 작성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-219">In previous versions of C#, you were encouraged to write code like this:</span></span>

```csharp
var handler = this.SomethingHappened;
if (handler != null)
    handler(this, eventArgs);
```

<span data-ttu-id="a6b8a-220">더 간단한 구문보다 이 방법을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-220">This was preferred over a simpler syntax:</span></span>

```csharp
// Not recommended
if (this.SomethingHappened != null)
    this.SomethingHappened(this, eventArgs);
```

> [!IMPORTANT]
> <span data-ttu-id="a6b8a-221">이전 예제에서는 경합 상태를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-221">The preceding example introduces a race condition.</span></span> <span data-ttu-id="a6b8a-222">`SomethingHappened` 이벤트는 `null`에 대해 확인될 경우 구독자를 포함할 수 있고 해당 구독자는 이벤트가 발생하기 전에 제거되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-222">The `SomethingHappened` event may have subscribers when checked against `null`, and those subscribers may have been removed before the event is raised.</span></span> <span data-ttu-id="a6b8a-223">이로 인해 <xref:System.NullReferenceException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-223">That would cause a <xref:System.NullReferenceException> to be thrown.</span></span>

<span data-ttu-id="a6b8a-224">이 두 번째 버전에서 `SomethingHappened` 이벤트 처리기는 테스트될 때 null이 아닐 수 있지만 다른 코드가 처리기를 제거할 경우 이벤트 처리기가 호출될 때 null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-224">In this second version, the `SomethingHappened` event handler might be non-null when tested, but if other code removes a handler, it could still be null when the event handler was called.</span></span>

<span data-ttu-id="a6b8a-225">컴파일러에서는 `?.` 식의 왼쪽(`this.SomethingHappened`)이 한 번 계산되도록 하는 `?.` 연산자에 대한 코드를 생성하고 결과는 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-225">The compiler generates code for the `?.` operator that ensures the left side (`this.SomethingHappened`) of the `?.` expression is evaluated once, and the result is cached:</span></span>

```csharp
// preferred in C# 6:
this.SomethingHappened?.Invoke(this, eventArgs);
```

<span data-ttu-id="a6b8a-226">왼쪽이 한 번만 계산되도록 하면 `?.`의 왼쪽에서 메서드 호출을 비롯한 모든 식을 사용할 수 있습니다. 이 방법에서 의도하지 않은 결과가 발생하더라도 한 번 계산되므로 의도하지 않은 결과도 한 번만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-226">Ensuring that the left side is evaluated only once also enables you to use any expression, including method calls, on the left side of the `?.` Even if these have side-effects, they are evaluated once, so the side effects occur only once.</span></span> <span data-ttu-id="a6b8a-227">[이벤트](../events-overview.md#language-support-for-events)에 대한 내용에서 예제를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-227">You can see an example in our content on [events](../events-overview.md#language-support-for-events).</span></span>

## <a name="string-interpolation"></a><span data-ttu-id="a6b8a-228">문자열 보간</span><span class="sxs-lookup"><span data-stu-id="a6b8a-228">String Interpolation</span></span>

<span data-ttu-id="a6b8a-229">C# 6에는 형식 문자열 및 다른 문자열 값을 생성하기 위해 계산되는 식에서 문자열을 작성하기 위한 새 구문이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-229">C# 6 contains new syntax for composing strings from a format string and expressions that are evaluated to produce other string values.</span></span>

<span data-ttu-id="a6b8a-230">기존에는 `string.Format` 같은 메서드에서 위치 매개 변수를 사용해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-230">Traditionally, you needed to use positional parameters in a method like `string.Format`:</span></span>

[!code-csharp[stringFormat](../../../samples/snippets/csharp/new-in-6/oldcode.cs#stringFormat)]

<span data-ttu-id="a6b8a-231">C# 6에서는 새 [문자열 보간](../language-reference/tokens/interpolated.md) 기능을 통해 서식 문자열에 식을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-231">With C# 6, the new [string interpolation](../language-reference/tokens/interpolated.md) feature enables you to embed the expressions in the format string.</span></span> <span data-ttu-id="a6b8a-232">간단히 문자열 앞에 `$`를 추가하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-232">Simply preface the string with `$`:</span></span>

[!code-csharp[stringInterpolation](../../../samples/snippets/csharp/new-in-6/newcode.cs#FullNameExpressionMember)]

<span data-ttu-id="a6b8a-233">이 초기 예제에서는 대체 식에 속성 식을 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-233">This initial example uses property expressions for the substituted expressions.</span></span> <span data-ttu-id="a6b8a-234">임의 식을 사용하도록 이 구문을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-234">You can expand on this syntax to use any expression.</span></span> <span data-ttu-id="a6b8a-235">예를 들어 보간의 일부로 학생의 성적 점수 평균을 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-235">For example, you could compute a student's grade point average as part of the interpolation:</span></span>

[!code-csharp[stringInterpolationExpression](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationExpression)]

<span data-ttu-id="a6b8a-236">이전 예제를 실행하면 `Grades.Average()`에 대한 출력에 원하는 것보다 더 많은 소수 자릿수가 포함됨을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-236">Running the preceding example, you would find that the output for `Grades.Average()` might have more decimal places than you would like.</span></span> <span data-ttu-id="a6b8a-237">문자열 보간 구문은 이전 서식 메서드를 통해 제공되는 모든 서식 문자열을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-237">The string interpolation syntax supports all the format strings available using earlier formatting methods.</span></span> <span data-ttu-id="a6b8a-238">중괄호 내에 서식 문자열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-238">You add the format strings inside the braces.</span></span> <span data-ttu-id="a6b8a-239">서식 지정할 식 다음에 `:`을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-239">Add a `:` following the expression to format:</span></span>

[!code-csharp[stringInterpolationFormat](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationFormat)]

<span data-ttu-id="a6b8a-240">이전 코드 줄은 소수 자릿수가 두 개인 부동 소수점 숫자로 `Grades.Average()` 값의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-240">The preceding line of code formats the value for `Grades.Average()` as a floating-point number with two decimal places.</span></span>

<span data-ttu-id="a6b8a-241">`:`은 항상 서식이 지정되는 식과 서식 문자열 사이의 구분 기호로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-241">The `:` is always interpreted as the separator between the expression being formatted and the format string.</span></span> <span data-ttu-id="a6b8a-242">식에서 `:`을 조건 연산자와 같은 다른 방식으로 사용할 경우 이로 인해 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-242">This can introduce problems when your expression uses a `:` in another way, such as a conditional operator:</span></span>

```csharp
public string GetGradePointPercentages() =>
    $"Name: {LastName}, {FirstName}. G.P.A: {Grades.Any() ? Grades.Average() : double.NaN:F2}";
```

<span data-ttu-id="a6b8a-243">이전 예제에서 `:`은 조건 연산자의 일부가 아닌 서식 문자열의 시작으로 구문 분석됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-243">In the preceding example, the `:` is parsed as the beginning of the format string, not part of the conditional operator.</span></span> <span data-ttu-id="a6b8a-244">이 문제가 발생할 때마다 식을 괄호로 묶어 컴파일러가 식을 의도한 대로 해석하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-244">In all cases where this happens, you can surround the expression with parentheses to force the compiler to interpret the expression as you intend:</span></span>

[!code-csharp[stringInterpolationConditional](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationConditional)]

<span data-ttu-id="a6b8a-245">중괄호 사이에 배치할 수 있는 식에 대한 제한 사항은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-245">There aren't any limitations on the expressions you can place between the braces.</span></span> <span data-ttu-id="a6b8a-246">보간된 문자열 내부에서 복잡한 LINQ 쿼리를 실행하여 계산을 수행하고 결과를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-246">You can execute a complex LINQ query inside an interpolated string to perform computations and display the result:</span></span>

[!code-csharp[stringInterpolationLinq](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationLinq)]

<span data-ttu-id="a6b8a-247">이 샘플에서 문자열 보간 식을 또 다른 문자열 보간 식 내부에 중첩할 수도 있음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-247">You can see from this sample that you can even nest a string interpolation expression inside another string interpolation expression.</span></span> <span data-ttu-id="a6b8a-248">이 예제는 프로덕션 코드에서 원하는 것보다 훨씬 더 복잡할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-248">This example is very likely more complex than you would want in production code.</span></span>
<span data-ttu-id="a6b8a-249">오히려 기능의 범위를 잘 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-249">Rather, it is illustrative of the breadth of the feature.</span></span> <span data-ttu-id="a6b8a-250">모든 C# 식은 보간된 문자열의 중괄호 사이에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-250">Any C# expression can be placed between the curly braces of an interpolated string.</span></span>

### <a name="string-interpolation-and-specific-cultures"></a><span data-ttu-id="a6b8a-251">문자열 보간 및 특정 문화권</span><span class="sxs-lookup"><span data-stu-id="a6b8a-251">String interpolation and specific cultures</span></span>

<span data-ttu-id="a6b8a-252">이전 섹션에 나와 있는 모든 예제는 코드가 실행되는 컴퓨터에서 현재 문화권과 언어를 사용하여 문자열의 서식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-252">All the examples shown in the preceding section format the strings using the current culture and language on the machine where the code executes.</span></span> <span data-ttu-id="a6b8a-253">일반적으로 특정 문화권을 사용하여 생성된 문자열의 서식을 지정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-253">Often you may need to format the string produced using a specific culture.</span></span>
<span data-ttu-id="a6b8a-254">이렇게 하려면 문자열 보간에 의해 생성된 개체가 암시적으로 <xref:System.FormattableString>으로 변환될 수 있다는 사실을 참고하세요.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-254">To do that use the fact that the object produced by a string interpolation can be implicitly converted to <xref:System.FormattableString>.</span></span>

<span data-ttu-id="a6b8a-255"><xref:System.FormattableString> 인스턴스에는 서식 문자열 및 문자열로 변환하기 전에 식을 계산한 결과가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-255">The <xref:System.FormattableString> instance contains the format string, and the results of evaluating the expressions before converting them to strings.</span></span> <span data-ttu-id="a6b8a-256"><xref:System.FormattableString>의 public 메서드를 사용하여 문자열의 서식을 지정할 때 문화권을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-256">You can use public methods of <xref:System.FormattableString> to specify the culture when formatting a string.</span></span> <span data-ttu-id="a6b8a-257">예를 들어 다음 예에서는 독일 문화권을 사용하여 문자열을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-257">For example, the following example produces a string using German culture.</span></span> <span data-ttu-id="a6b8a-258">(',' 문자를 소수 구분 기호로 사용하고 '.' 문자를 천 단위 구분 기호로 사용합니다.)</span><span class="sxs-lookup"><span data-stu-id="a6b8a-258">(It uses the ',' character for the decimal separator, and the '.' character as the thousands separator.)</span></span>

```csharp
FormattableString str = $"Average grade is {s.Grades.Average()}";
var gradeStr = str.ToString(new System.Globalization.CultureInfo("de-DE"));
```

<span data-ttu-id="a6b8a-259">자세한 내용은 [문자열 보간](../language-reference/tokens/interpolated.md) 토픽을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-259">For more information, see the [String interpolation](../language-reference/tokens/interpolated.md) topic.</span></span>

## <a name="exception-filters"></a><span data-ttu-id="a6b8a-260">예외 필터</span><span class="sxs-lookup"><span data-stu-id="a6b8a-260">Exception Filters</span></span>

<span data-ttu-id="a6b8a-261">C# 6의 또 다른 새로운 기능은 *예외 필터*입니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-261">Another new feature in C# 6 is *exception filters*.</span></span> <span data-ttu-id="a6b8a-262">예외 필터는 지정된 catch 절을 적용해야 하는 경우를 결정하는 절입니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-262">Exception Filters are clauses that determine when a given catch clause should be applied.</span></span>
<span data-ttu-id="a6b8a-263">예외 필터에 사용된 식이 `true`로 계산되면 catch 절은 예외에 대한 일반적인 처리를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-263">If the expression used for an exception filter evaluates to `true`, the catch clause performs its normal processing on an exception.</span></span> <span data-ttu-id="a6b8a-264">식이 `false`로 계산되면 `catch` 절을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-264">If the expression evaluates to `false`, then the `catch` clause is skipped.</span></span>

<span data-ttu-id="a6b8a-265">한 가지 사용 예는 예외에 대한 정보를 검사하여 `catch` 절이 예외를 처리할 수 있는지 결정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-265">One use is to examine information about an exception to determine if a `catch` clause can process the exception:</span></span>

[!code-csharp[ExceptionFilter](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#ExceptionFilter)]

<span data-ttu-id="a6b8a-266">예외 필터에서 생성된 코드는 throw되지만 처리되지 않은 예외에 대한 더 나은 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-266">The code generated by exception filters provides better information about an exception that is thrown and not processed.</span></span> <span data-ttu-id="a6b8a-267">예외 필터가 언어에 추가되기 전에 다음과 같이 코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-267">Before exception filters were added to the language, you would need to create code like the following:</span></span>

[!code-csharp[ExceptionFilterOld](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#ExceptionFilterOld)]

<span data-ttu-id="a6b8a-268">이러한 두 개의 예제에서는 예외가 throw된 지점이 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-268">The point where the exception is thrown changes between these two examples.</span></span>
<span data-ttu-id="a6b8a-269">이전 코드에서 `throw` 절이 사용된 경우 크래시 덤프의 스택 추적 분석 또는 검사에서는 catch 절의 `throw` 문에서 예외가 throw되었음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-269">In the previous code, where a `throw` clause is used, any stack trace analysis or examination of crash dumps will show that the exception was thrown from the `throw` statement in your catch clause.</span></span> <span data-ttu-id="a6b8a-270">실제 예외 개체에는 원래 호출 스택이 포함되지만 이 throw 지점과 원래 throw 지점 위치 사이에 있는 호출 스택의 변수에 대한 모든 기타 정보가 손실되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-270">The actual exception object will contain the original call stack, but all other information about any variables in the call stack between this throw point and the location of the original throw point has been lost.</span></span> 

<span data-ttu-id="a6b8a-271">예외 필터를 사용하여 코드를 처리하는 방법과 달리 예외 필터 식은 `false`로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-271">Contrast that with how the code using an exception filter is processed: the exception filter expression evaluates to `false`.</span></span> <span data-ttu-id="a6b8a-272">따라서 실행이 `catch` 절로 들어가지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-272">Therefore, execution never enters the `catch` clause.</span></span> <span data-ttu-id="a6b8a-273">`catch` 절이 실행되지 않으면 스택 해제가 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-273">Because the `catch` clause does not execute, no stack unwinding takes place.</span></span> <span data-ttu-id="a6b8a-274">이는 나중에 수행되는 디버깅 활동을 위해 원래 throw 위치가 보존됨을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-274">That means the original throw location is preserved for any debugging activities that would take place later.</span></span>

<span data-ttu-id="a6b8a-275">예외 형식만 사용하는 대신 예외의 필드 또는 속성을 계산해야 할 때마다 예외 필터를 사용하여 더 많은 디버깅 정보를 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-275">Whenever you need to evaluate fields or properties of an exception, instead of relying solely on the exception type, use an exception filter to preserve more debugging information.</span></span>

<span data-ttu-id="a6b8a-276">예외 필터를 사용하는 또 다른 권장 패턴은 루틴을 기록하는 데 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-276">Another recommended pattern with exception filters is to use them for logging routines.</span></span> <span data-ttu-id="a6b8a-277">이 방법은 예외 필터가 `false`로 계산될 때 예외 throw 지점을 보존하는 방식을 이용합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-277">This usage also leverages the manner in which the exception throw point is preserved when an exception filter evaluates to `false`.</span></span>

<span data-ttu-id="a6b8a-278">로깅 메서드는 인수가 무조건 `false`를 반환하는 예외인 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-278">A logging method would be a method whose argument is the exception that unconditionally returns `false`:</span></span>

[!code-csharp[ExceptionFilterLogging](../../../samples/snippets/csharp/new-in-6/ExceptionFilterHelpers.cs#ExceptionFilterLogging)]

<span data-ttu-id="a6b8a-279">예외를 기록하려고 할 때마다 catch 절을 추가하고 이 메서드를 예외 필터로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-279">Whenever you want to log an exception, you can add a catch clause, and use this method as the exception filter:</span></span>

[!code-csharp[LogException](../../../samples/snippets/csharp/new-in-6/program.cs#LogException)]

<span data-ttu-id="a6b8a-280">예외는 catch되지 않습니다. `LogException` 메서드는 항상 `false`를 반환하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-280">The exceptions are never caught, because the `LogException` method always returns `false`.</span></span> <span data-ttu-id="a6b8a-281">항상 false인 예외 필터는 이 로깅 처리기를 다른 예외 처리기 앞에 배치할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-281">That always false exception filter means that you can place this logging handler before any other exception handlers:</span></span>

[!code-csharp[LogExceptionRecovery](../../../samples/snippets/csharp/new-in-6/program.cs#LogExceptionRecovery)]

<span data-ttu-id="a6b8a-282">이전 예제에서는 예외 필터의 매우 중요한 부분을 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-282">The preceding example highlights a very important facet of exception filters.</span></span>
<span data-ttu-id="a6b8a-283">예외 필터는 더 일반적인 예외 catch 절이 더 구체적인 절 앞에 나타날 수 있는 시나리오를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-283">The exception filters enable scenarios where a more general exception catch clause may appear before a more specific one.</span></span> <span data-ttu-id="a6b8a-284">같은 예외 형식이 여러 catch 절에 표시되게 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-284">It's also possible to have the same exception type appear in multiple catch clauses:</span></span>

[!code-csharp[HandleNotChanged](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#HandleNotChanged)]

<span data-ttu-id="a6b8a-285">또 다른 권장 패턴을 사용하면 디버거가 연결될 때 catch 절이 예외를 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-285">Another recommended pattern helps prevent catch clauses from processing exceptions when a debugger is attached.</span></span> <span data-ttu-id="a6b8a-286">이 방법을 사용하여 디버거를 통해 응용 프로그램을 실행하고 예외가 throw될 때 실행을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-286">This technique enables you to run an application with the debugger, and stop execution when an exception is thrown.</span></span>

<span data-ttu-id="a6b8a-287">코드에서 디버거가 연결되지 않을 때만 복구 코드가 실행되도록 예외 필터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-287">In your code, add an exception filter so that any recovery code executes only when a debugger is not attached:</span></span>

[!code-csharp[LogExceptionDebugger](../../../samples/snippets/csharp/new-in-6/program.cs#LogExceptionDebugger)]

<span data-ttu-id="a6b8a-288">코드에 이 예외 코드를 추가한 후 처리되지 않은 모든 예외에서 중단되도록 디버거를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-288">After adding this in code, you set your debugger to break on all unhandled exceptions.</span></span> <span data-ttu-id="a6b8a-289">디버거에서 프로그램을 실행합니다. 그러면 `PerformFailingOperation()`이 `RecoverableException`을 throw할 때마다 디버거가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-289">Run the program under the debugger, and the debugger breaks whenever `PerformFailingOperation()` throws a `RecoverableException`.</span></span>
<span data-ttu-id="a6b8a-290">false 반환 예외 필터로 인해 catch 절이 실행되지 않으므로 디버거가 프로그램을 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-290">The debugger breaks your program, because the catch clause won't be executed due to the false-returning exception filter.</span></span>

## <a name="nameof-expressions"></a><span data-ttu-id="a6b8a-291">`nameof` 식</span><span class="sxs-lookup"><span data-stu-id="a6b8a-291">`nameof` Expressions</span></span>

<span data-ttu-id="a6b8a-292">`nameof` 식은 기호 이름으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-292">The `nameof` expression evaluates to the name of a symbol.</span></span> <span data-ttu-id="a6b8a-293">변수, 속성 또는 멤버 필드의 이름이 필요할 때마다 도구를 작동하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-293">It's a great way to get tools working whenever you need the name of a variable, a property, or a member field.</span></span>

<span data-ttu-id="a6b8a-294">`nameof`의 가장 일반적인 사용 예 중 하나는 예외를 일으킨 기호의 이름을 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-294">One of the most common uses for `nameof` is to provide the name of a symbol that caused an exception:</span></span>

[!code-csharp[nameof](../../../samples/snippets/csharp/new-in-6/NewCode.cs#UsingStaticString)]

<span data-ttu-id="a6b8a-295">또 다른 사용 예는 `INotifyPropertyChanged` 인터페이스를 구현하는 XAML 기반 응용 프로그램에서 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-295">Another use is with XAML based applications that implement the `INotifyPropertyChanged` interface:</span></span>

[!code-csharp[nameofNotify](../../../samples/snippets/csharp/new-in-6/viewmodel.cs#nameofNotify)]

<span data-ttu-id="a6b8a-296">상수 문자열에 비해 `nameof` 연산자 사용의 장점은 도구가 기호를 인식할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-296">The advantage of using the `nameof` operator over a constant string is that tools can understand the symbol.</span></span> <span data-ttu-id="a6b8a-297">리팩터링 도구를 사용하여 기호 이름을 바꿀 경우 `nameof` 식에서 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-297">If you use refactoring tools to rename the symbol, it will rename it in the `nameof` expression.</span></span> <span data-ttu-id="a6b8a-298">상수 문자열에는 이 장점이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-298">Constant strings don't have that advantage.</span></span> <span data-ttu-id="a6b8a-299">원하는 편집기에서 직접 변수 이름을 바꿔 보세요. 그러면 모든 `nameof` 식도 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-299">Try it yourself in your favorite editor: rename a variable, and any `nameof` expressions will update as well.</span></span>

<span data-ttu-id="a6b8a-300">인수의 정규화된 이름을 사용하는 경우에도 `nameof` 식은 인수의 정규화되지 않은 이름을 생성합니다(이전 예제에서는 `LastName`).</span><span class="sxs-lookup"><span data-stu-id="a6b8a-300">The `nameof` expression produces the unqualified name of its argument (`LastName` in the previous examples) even if you use the fully qualified name for the argument:</span></span>

[!code-csharp[QualifiedNameofNotify](../../../samples/snippets/csharp/new-in-6/viewmodel.cs#QualifiedNameofNotify)]

<span data-ttu-id="a6b8a-301">이 `nameof` 식은 `UXComponents.ViewModel.FirstName`이 아닌 `FirstName`을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-301">This `nameof` expression produces `FirstName`, not `UXComponents.ViewModel.FirstName`.</span></span>

## <a name="await-in-catch-and-finally-blocks"></a><span data-ttu-id="a6b8a-302">Catch 및 Finally 블록의 Await</span><span class="sxs-lookup"><span data-stu-id="a6b8a-302">Await in Catch and Finally blocks</span></span>

<span data-ttu-id="a6b8a-303">C# 5에는 `await` 식을 배치할 수 있는 위치에 대한 여러 제한 사항이 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-303">C# 5 had several limitations around where you could place `await` expressions.</span></span>
<span data-ttu-id="a6b8a-304">제한 사항 중 하나가 C# 6에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-304">One of those has been removed in C# 6.</span></span> <span data-ttu-id="a6b8a-305">이제 `catch` 또는 `finally` 식에서 `await`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-305">You can now use `await` in `catch` or `finally` expressions.</span></span> 

<span data-ttu-id="a6b8a-306">catch 및 finally 블록에 await 식을 추가하면 식 처리 방식이 복잡하게 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-306">The addition of await expressions in catch and finally blocks may appear to complicate how those are processed.</span></span> <span data-ttu-id="a6b8a-307">어떻게 보이는지 설명하는 예제를 추가해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-307">Let's add an example to discuss how this appears.</span></span> <span data-ttu-id="a6b8a-308">비동기 메서드의 finally 절에서 await 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-308">In any async method, you can use an await expression in a finally clause.</span></span>

<span data-ttu-id="a6b8a-309">C# 6에서는 catch 식에서 대기할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-309">With C# 6, you can also await in catch expressions.</span></span> <span data-ttu-id="a6b8a-310">이 방법이 로깅 시나리오에서 가장 일반적을 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-310">This is most often used with logging scenarios:</span></span>

[!code-csharp[AwaitFinally](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#AwaitFinally)]

<span data-ttu-id="a6b8a-311">`catch` 및 `finally` 절 내부에 `await` 지원을 추가하기 위한 구현 세부 정보에 따라 동작이 동기 코드에 대한 동작과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-311">The implementation details for adding `await` support inside `catch` and `finally` clauses ensures that the behavior is consistent with the behavior for synchronous code.</span></span> <span data-ttu-id="a6b8a-312">`catch` 또는 `finally` 절에서 실행되는 코드가 throw되면 실행은 다음 바깥쪽 블록에서 적합한 `catch` 절을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-312">When code executed in a `catch` or `finally` clause throws, execution looks for a suitable `catch` clause in the next surrounding block.</span></span> <span data-ttu-id="a6b8a-313">현재 예외가 있는 경우 해당 예외가 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-313">If there was a current exception, that exception is lost.</span></span> <span data-ttu-id="a6b8a-314">`catch` 및 `finally` 절에서 대기된 식에서도 같은 작업이 수행됩니다. 적합한 `catch`가 검색되고 현재 예외(있는 경우)가 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-314">The same happens with awaited expressions in `catch` and `finally` clauses: a suitable `catch` is searched for, and the current exception, if any, is lost.</span></span>  

> [!NOTE]
> <span data-ttu-id="a6b8a-315">이 동작 때문에 새 예외가 추가되지 않도록 `catch` 및 `finally` 절을 신중하게 작성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-315">This behavior is the reason it's recommended to write `catch` and `finally` clauses carefully, to avoid introducing new exceptions.</span></span>

## <a name="index-initializers"></a><span data-ttu-id="a6b8a-316">인덱스 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="a6b8a-316">Index Initializers</span></span>

<span data-ttu-id="a6b8a-317">*인덱스 이니셜라이저*는 컬렉션 이니셜라이저를 더 일관되게 만드는 두 가지 기능 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-317">*Index Initializers* is one of two features that make collection initializers more consistent.</span></span> <span data-ttu-id="a6b8a-318">C#의 이전 예제에서는 시퀀스 스타일 컬렉션에서만 *컬렉션 이니셜라이저*를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-318">In earlier releases of C#, you could use *collection initializers* only with sequence style collections:</span></span>

[!code-csharp[ListInitializer](../../../samples/snippets/csharp/new-in-6/initializers.cs#ListInitializer)]

<span data-ttu-id="a6b8a-319">이제 <xref:System.Collections.Generic.Dictionary%602> 컬렉션 및 비슷한 형식에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-319">Now, you can also use them with <xref:System.Collections.Generic.Dictionary%602> collections and similar types:</span></span>

[!code-csharp[DictionaryInitializer](../../../samples/snippets/csharp/new-in-6/initializers.cs#DictionaryInitializer)]

<span data-ttu-id="a6b8a-320">이 기능은 여러 버전에 대한 시퀀스 컨테이너를 대신한 것과 비슷한 구문을 사용하여 연관 컨테이너를 초기화할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-320">This feature means that associative containers can be initialized using syntax similar to what's been in place for sequence containers for several versions.</span></span>

### <a name="extension-add-methods-in-collection-initializers"></a><span data-ttu-id="a6b8a-321">컬렉션 이니셜라이저의 확장 `Add` 메서드</span><span class="sxs-lookup"><span data-stu-id="a6b8a-321">Extension `Add` methods in collection initializers</span></span>

<span data-ttu-id="a6b8a-322">컬렉션을 더 쉽게 초기화하도록 하는 또 다른 기능은 `Add` 메서드에 *확장 메서드*를 사용하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-322">Another feature that makes collection initialization easier is the ability to use an *extension method* for the `Add` method.</span></span> <span data-ttu-id="a6b8a-323">이 기능은 Visual Basic의 패리티를 위해 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-323">This feature was added for parity with Visual Basic.</span></span> 

<span data-ttu-id="a6b8a-324">이 기능은 의미상으로 새 항목을 추가하기 위해 다른 이름을 가진 메서드가 포함된 사용자 지정 컬렉션 클래스가 있는 경우 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-324">The feature is most useful when you have a custom collection class that has a method with a different name to semantically add new items.</span></span>

<span data-ttu-id="a6b8a-325">예를 들어 다음과 같은 학생 컬렉션을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-325">For example, consider a collection of students like this:</span></span>

[!code-csharp[Enrollment](../../../samples/snippets/csharp/new-in-6/enrollment.cs#Enrollment)]

<span data-ttu-id="a6b8a-326">`Enroll` 메서드는 학생을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-326">The `Enroll` method adds a student.</span></span> <span data-ttu-id="a6b8a-327">그러나 `Add` 패턴을 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-327">But it doesn't follow the `Add` pattern.</span></span>
<span data-ttu-id="a6b8a-328">C#의 이전 버전에서는 `Enrollment` 개체와 함께 컬렉션 이니셜라이저를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-328">In previous versions of C#, you could not use collection initializers with an `Enrollment` object:</span></span>

[!code-csharp[InitializeEnrollment](../../../samples/snippets/csharp/new-in-6/classList.cs#InitializeEnrollment)]

<span data-ttu-id="a6b8a-329">이제 함께 사용할 수 있지만 `Add`를 `Enroll`에 매핑하는 확장 메서드를 만들 경우로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-329">Now you can, but only if you create an extension method that maps `Add` to `Enroll`:</span></span>

[!code-csharp[ExtensionAdd](../../../samples/snippets/csharp/new-in-6/classList.cs#ExtensionAdd)]

<span data-ttu-id="a6b8a-330">이 기능을 통해 수행하는 작업은 확장 메서드를 만들어 컬렉션에 항목을 추가하는 모든 메서드를 `Add` 메서드에 매핑하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-330">What you are doing with this feature is to map whatever method adds items to a collection to a method named `Add` by creating an extension method:</span></span> 

[!code-csharp[Enrollment](../../../samples/snippets/csharp/new-in-6/enrollment.cs#Enrollment)]
[!code-csharp[ExtensionAddSample](../../../samples/snippets/csharp/new-in-6/classList.cs#ExtensionAddSample)]

## <a name="improved-overload-resolution"></a><span data-ttu-id="a6b8a-331">향상된 오버로드 확인</span><span class="sxs-lookup"><span data-stu-id="a6b8a-331">Improved overload resolution</span></span>

<span data-ttu-id="a6b8a-332">이 마지막 기능은 알지 못하는 기능일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-332">This last feature is one you probably won't notice.</span></span> <span data-ttu-id="a6b8a-333">C# 컴파일러의 이전 버전에서 람다 식을 포함하는 일부 메서드 호출이 모호한 것으로 확인될 수 있는 구문이 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-333">There were constructs where the previous version of the C# compiler may have found some method calls involving lambda expressions ambiguous.</span></span> <span data-ttu-id="a6b8a-334">이 메서드를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-334">Consider this method:</span></span>

[!code-csharp[AsyncMethod](../../../samples/snippets/csharp/new-in-6/overloads.cs#AsyncMethod)]

<span data-ttu-id="a6b8a-335">C#의 이전 버전에서는 메서드 그룹 구문을 통한 해당 메서드 호출이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-335">In earlier versions of C#, calling that method using the method group syntax would fail:</span></span>

[!code-csharp[MethodGroup](../../../samples/snippets/csharp/new-in-6/overloads.cs#MethodGroup)]
 
<span data-ttu-id="a6b8a-336">이전 컴파일러에서는 `Task.Run(Action)` 및 `Task.Run(Func<Task>())`를 제대로 구분할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-336">The earlier compiler could not distinguish correctly between `Task.Run(Action)` and `Task.Run(Func<Task>())`.</span></span> <span data-ttu-id="a6b8a-337">이전 버전에서는 람다 식을 인수로 사용해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-337">In previous versions, you'd need to use a lambda expression as an argument:</span></span>

[!code-csharp[Lambda](../../../samples/snippets/csharp/new-in-6/overloads.cs#Lambda)]

<span data-ttu-id="a6b8a-338">C# 6 컴파일러에서는 `Task.Run(Func<Task>())`가 더 나은 선택인지 제대로 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b8a-338">The C# 6 compiler correctly determines that `Task.Run(Func<Task>())` is a better choice.</span></span>
