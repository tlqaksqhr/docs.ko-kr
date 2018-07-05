---
title: C# 7.3의 새로운 기능
description: C# 7.3의 새로운 기능에 대한 개요입니다.
ms.date: 05/16/2018
ms.openlocfilehash: 135351fa06a498e4aa90cb4d9372880b8119de0f
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106777"
---
# <a name="whats-new-in-c-73"></a><span data-ttu-id="056fc-103">C# 7.3의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="056fc-103">What's new in C# 7.3</span></span>

<span data-ttu-id="056fc-104">C# 7.3 릴리스에는 두 개의 기본 테마가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-104">There are two main themes to the C# 7.3 release.</span></span> <span data-ttu-id="056fc-105">하나의 테마는 안전한 코드의 성능을 안전하지 않은 코드만큼 향상할 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-105">One theme provides features that enable safe code to be as performant as unsafe code.</span></span> <span data-ttu-id="056fc-106">두 번째 테마는 기존 기능에 대한 점진적인 개선을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-106">The second theme provides incremental improvements to existing features.</span></span> <span data-ttu-id="056fc-107">또한 새 컴파일러 옵션이 이 릴리스에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-107">In addition, new compiler options were added in this release.</span></span>

<span data-ttu-id="056fc-108">다음 새로운 기능은 안전한 코드에 대해 향상된 성능의 테마를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-108">The following new features support the theme of better performance for safe code:</span></span>

- <span data-ttu-id="056fc-109">고정하지 않고 고정 필드에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-109">You can access fixed fields without pinning.</span></span>
- <span data-ttu-id="056fc-110">`ref` 지역 변수를 다시 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-110">You can reassign `ref` local variables.</span></span>
- <span data-ttu-id="056fc-111">`stackalloc` 배열에서 이니셜라이저를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-111">You can use initializers on `stackalloc` arrays.</span></span>
- <span data-ttu-id="056fc-112">패턴을 지원하는 모든 형식과 함께 `fixed` 문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-112">You can use `fixed` statements with any type that supports a pattern.</span></span>
- <span data-ttu-id="056fc-113">추가적인 제네릭 제약 조건을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-113">You can use additional generic constraints.</span></span>

<span data-ttu-id="056fc-114">기존 기능이 다음과 같이 개선되었습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-114">The following enhancements were made to existing features:</span></span>

- <span data-ttu-id="056fc-115">튜플 형식으로 `==` 및 `!=`를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-115">You can test `==` and `!=` with tuple types.</span></span>
- <span data-ttu-id="056fc-116">더 많은 위치에서 식 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-116">You can use expression variables in more locations.</span></span>
- <span data-ttu-id="056fc-117">자동 구현 속성의 지원 필드에 특성을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-117">You may attach attributes to the backing field of auto-implemented properties.</span></span>
- <span data-ttu-id="056fc-118">인수에서 `in`만 다른 경우 메서드 해결이 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-118">Method resolution when arguments differ by `in` has been improved.</span></span>
- <span data-ttu-id="056fc-119">이제 오버로드 해결에 모호한 사례가 감소했습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-119">Overload resolution now has fewer ambiguous cases.</span></span>

<span data-ttu-id="056fc-120">새 컴파일러 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-120">The new compiler options are:</span></span>

- <span data-ttu-id="056fc-121">`-publicsign` - OSS(오픈 소스 소프트웨어) 시그니처를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-121">`-publicsign` to enable Open Source Software (OSS) signing of assemblies.</span></span>
- <span data-ttu-id="056fc-122">`-pathmap` - 소스 디렉터리에 대한 매핑을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-122">`-pathmap` to provide a mapping for source directories.</span></span>

<span data-ttu-id="056fc-123">이 문서의 나머지 부분에서는 각 개선 사항에 대해 자세히 알아보기 위한 세부 정보와 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-123">The remainder of this article provides details and links to learn more about each of the improvements.</span></span>

## <a name="enabling-more-performant-safe-code"></a><span data-ttu-id="056fc-124">성능이 향상된 안전한 코드 사용</span><span class="sxs-lookup"><span data-stu-id="056fc-124">Enabling more performant safe code</span></span>

<span data-ttu-id="056fc-125">안전하게 실행할 C# 코드 및 안전하지 않은 코드를 작성할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-125">You should be able to write C# code safely that performs as well as unsafe code.</span></span> <span data-ttu-id="056fc-126">안전한 코드를 사용하면 버퍼 오버런, 이상 포인터 및 기타 메모리 액세스 오류와 같은 오류 클래스를 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-126">Safe code avoids classes of errors, such as buffer overruns, stray pointers, and other memory access errors.</span></span> <span data-ttu-id="056fc-127">이러한 새 기능은 확인 가능한 안전한 코드의 기능을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-127">These new features expand the capabilities of verifiable safe code.</span></span> <span data-ttu-id="056fc-128">안전한 구문을 사용하여 더 많은 코드를 작성하도록 노력하세요.</span><span class="sxs-lookup"><span data-stu-id="056fc-128">Strive to write more of your code using safe constructs.</span></span> <span data-ttu-id="056fc-129">이러한 기능을 사용하면 이 작업이 더 쉬워집니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-129">These features make that easier.</span></span>

### <a name="indexing-fixed-fields-does-not-require-pinning"></a><span data-ttu-id="056fc-130">`fixed` 필드 인덱싱에 고정이 필요하지 않음</span><span class="sxs-lookup"><span data-stu-id="056fc-130">Indexing `fixed` fields does not require pinning</span></span>

<span data-ttu-id="056fc-131">다음 구조체를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-131">Consider this struct:</span></span>

```csharp
unsafe struct S
{
    public fixed int myFixedField[10];
}
```

<span data-ttu-id="056fc-132">이전 버전의 C#에서는 `myFixedField`의 일부인 정수 중 하나에 액세스하려면 변수를 고정해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-132">In earlier versions of C#, you needed to pin a variable to access one of the integers that are part of `myFixedField`.</span></span> <span data-ttu-id="056fc-133">이제 다음 코드는 안전한 컨텍스트에서 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-133">Now, the following code compiles in a safe context:</span></span>

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        int p = s.myFixedField[5];
    }
}
```

<span data-ttu-id="056fc-134">`p` 변수는 `myFixedField`의 한 요소에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-134">The variable `p` accesses one element in `myFixedField`.</span></span> <span data-ttu-id="056fc-135">별도의 `int*` 변수를 선언할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-135">You don't need to declare a separate `int*` variable.</span></span> <span data-ttu-id="056fc-136">`unsafe` 컨텍스트는 계속 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-136">Note that you still need an `unsafe` context.</span></span> <span data-ttu-id="056fc-137">이전 버전의 C#에서는 두 번째 고정 포인터를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-137">In earlier versions of C#, you need to declare a second fixed pointer:</span></span>

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        fixed (int* ptr = s.myFixedField)
        {
            int p = ptr[5];
        }
    }
}
```

<span data-ttu-id="056fc-138">자세한 내용은 [`fixed` 문](../language-reference/keywords/fixed-statement.md)에 대한 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="056fc-138">Fore more information, see the article on the [`fixed` statement](../language-reference/keywords/fixed-statement.md).</span></span>

### <a name="ref-local-variables-may-be-reassigned"></a><span data-ttu-id="056fc-139">`ref` 지역 변수를 다시 할당할 수 있음</span><span class="sxs-lookup"><span data-stu-id="056fc-139">`ref` local variables may be reassigned</span></span>

<span data-ttu-id="056fc-140">이제 `ref` 지역 변수를 다시 할당하여 초기화된 후 다른 인스턴스를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-140">Now, `ref` locals may be reassigned to refer to different instances after being initialized.</span></span> <span data-ttu-id="056fc-141">이제 다음 코드가 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-141">The following code now compiles:</span></span>

```csharp
ref VeryLargeStruct refLocal = ref veryLargeStruct; // initialization
refLocal = ref anotherVeryLargeStruct; // reassigned, refLocal refers to different storage.
```

<span data-ttu-id="056fc-142">자세한 내용은 [`ref` 반환 및 `ref` 지역](../programming-guide/classes-and-structs/ref-returns.md)에 대한 아티클 및 [`foreach`](../language-reference/keywords/foreach-in.md)에 대한 아티클을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="056fc-142">For more information, see the article on [`ref` returns and `ref` locals](../programming-guide/classes-and-structs/ref-returns.md), and the article on [`foreach`](../language-reference/keywords/foreach-in.md).</span></span>

### <a name="stackalloc-arrays-support-initializers"></a><span data-ttu-id="056fc-143">`stackalloc` 배열이 이니셜라이저를 지원함</span><span class="sxs-lookup"><span data-stu-id="056fc-143">`stackalloc` arrays support initializers</span></span>

<span data-ttu-id="056fc-144">초기화할 때 배열의 요소 값을 지정할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-144">You've been able to specify the values for elements in an array when you initialize it:</span></span>

```csharp
var arr = new int[3] {1, 2, 3};
var arr2 = new int[] {1, 2, 3};
```

<span data-ttu-id="056fc-145">이제 `stackalloc`로 선언된 배열에 동일한 구문을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-145">Now, that same syntax can be applied to arrays that are declared with `stackalloc`:</span></span>

```csharp
int* pArr = stackalloc int[3] {1, 2, 3};
int* pArr2 = stackalloc int[] {1, 2, 3};
Span<int> arr = stackalloc [] {1, 2, 3};
```

<span data-ttu-id="056fc-146">자세한 내용은 언어 참조에서 [`stackalloc` 문](../language-reference/keywords/stackalloc.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="056fc-146">For more information, see the [`stackalloc` statement](../language-reference/keywords/stackalloc.md) article in the language reference.</span></span>

### <a name="more-types-support-the-fixed-statement"></a><span data-ttu-id="056fc-147">더 많은 형식이 `fixed` 문을 지원함</span><span class="sxs-lookup"><span data-stu-id="056fc-147">More types support the `fixed` statement</span></span>

<span data-ttu-id="056fc-148">`fixed` 문은 제한된 형식 집합을 지원했습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-148">The `fixed` statement supported a limited set of types.</span></span> <span data-ttu-id="056fc-149">C# 7.3부터 `ref T` 또는 `ref readonly T`를 반환하는 `GetPinnableReference()` 메서드를 포함하는 모든 형식이 `fixed`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-149">Starting with C# 7.3, any type that contains a `GetPinnableReference()` method that returns a `ref T` or `ref readonly T` may be `fixed`.</span></span> <span data-ttu-id="056fc-150">이 기능을 추가하면 `fixed`를 <xref:System.Span%601?displayProperty=nameWithType> 및 관련 형식과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-150">Adding this feature means that `fixed` can be used with <xref:System.Span%601?displayProperty=nameWithType> and related types.</span></span>

<span data-ttu-id="056fc-151">자세한 내용은 언어 참조에서 [`fixed` 문](../language-reference/keywords/fixed-statement.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="056fc-151">For more information, see the [`fixed` statement](../language-reference/keywords/fixed-statement.md) article in the language reference.</span></span>

### <a name="enhanced-generic-constraints"></a><span data-ttu-id="056fc-152">향상된 제네릭 제약 조건</span><span class="sxs-lookup"><span data-stu-id="056fc-152">Enhanced generic constraints</span></span>

<span data-ttu-id="056fc-153">이제 형식 매개 변수에 대한 기본 클래스 제약 조건으로 <xref:System.Enum?displayProperty=nameWithType> 또는 <xref:System.Delegate?displayProperty=nameWithType> 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-153">You can now specify the type <xref:System.Enum?displayProperty=nameWithType> or <xref:System.Delegate?displayProperty=nameWithType> as base class constraints for a type parameter.</span></span>

<span data-ttu-id="056fc-154">또한 새 `unmanaged` 제약 조건을 사용하여 형식 매개 변수가 **관리되지 않는 형식**이 되도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-154">You can also use the new `unmanaged` constraint, to specify that a type parameter must be an **unmanaged type**.</span></span> <span data-ttu-id="056fc-155">**관리되지 않는 형식**은 참조 형식이 아니고 모든 중첩 수준의 참조 형식을 포함하지 않는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-155">An **unmanaged type** is a type that isn't a reference type and doesn't contain any reference type at any level of nesting.</span></span>

<span data-ttu-id="056fc-156">자세한 내용은 [`where` 제네릭 제약 조건](../language-reference/keywords/where-generic-type-constraint.md) 및 [형식 매개 변수 제약 조건](../programming-guide/generics/constraints-on-type-parameters.md)에 대한 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="056fc-156">For more information, see the articles on [`where` generic constraints](../language-reference/keywords/where-generic-type-constraint.md) and [constraints on type parameters](../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

## <a name="make-existing-features-better"></a><span data-ttu-id="056fc-157">기존 기능의 향상</span><span class="sxs-lookup"><span data-stu-id="056fc-157">Make existing features better</span></span>

<span data-ttu-id="056fc-158">두 번째 테마는 언어의 기능에 대한 개선을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-158">The second theme provides improvements to features in the language.</span></span> <span data-ttu-id="056fc-159">이러한 기능은 C#를 작성할 때 생산성을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-159">These features improve productivity when writing C#.</span></span>

### <a name="tuples-support--and-"></a><span data-ttu-id="056fc-160">튜플은 `==` 및 `!=`를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-160">Tuples support `==` and `!=`</span></span>

<span data-ttu-id="056fc-161">C# 튜플 형식은 이제 `==` 및 `!=`를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-161">The C# tuple types now support `==` and `!=`.</span></span> <span data-ttu-id="056fc-162">자세한 내용은 [튜플](../tuples.md)에 대한 문서에서 [같음](../tuples.md#equality-and-tuples)을 다루는 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="056fc-162">Fore more information, see the section covering [equality](../tuples.md#equality-and-tuples) in the article on [tuples](../tuples.md).</span></span>

### <a name="attach-attributes-to-the-backing-fields-for-auto-implemented-properties"></a><span data-ttu-id="056fc-163">자동 구현 속성의 지원 필드에 특성 연결</span><span class="sxs-lookup"><span data-stu-id="056fc-163">Attach attributes to the backing fields for auto-implemented properties</span></span>

<span data-ttu-id="056fc-164">이제 다음 구문이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-164">This syntax is now supported:</span></span>

```csharp
[field: SomeThingAboutFieldAttribute]
public int SomeProperty { get; set; }
```

<span data-ttu-id="056fc-165">`SomeThingAboutFieldAttribute` 특성은 `SomeProperty`에 대한 컴파일러 생성 지원 필드에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-165">The attribute `SomeThingAboutFieldAttribute` is applied to the compiler generated backing field for `SomeProperty`.</span></span> <span data-ttu-id="056fc-166">자세한 내용은 C# 프로그래밍 가이드의 [특성](../programming-guide/concepts/attributes/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="056fc-166">For more information, see [attributes](../programming-guide/concepts/attributes/index.md) in the C# programming guide.</span></span>

### <a name="in-method-overload-resolution-tiebreaker"></a><span data-ttu-id="056fc-167">`in` 메서드 오버로드 해결 순위 결정</span><span class="sxs-lookup"><span data-stu-id="056fc-167">`in` method overload resolution tiebreaker</span></span>

<span data-ttu-id="056fc-168">`in` 인수 한정자가 추가된 경우 이러한 두 메서드로 인해 모호성이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-168">When the `in` argument modifier was added, these two methods would cause an ambiguity:</span></span>

```csharp
static void M(S arg);
static void M(in S arg);
```

<span data-ttu-id="056fc-169">이제 값 기준(이전 예제의 첫 번째) 오버로드가 읽기 전용 참조 기준 버전보다 더 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-169">Now, the by value (first in the preceding example) overload is better than the by readonly reference version.</span></span> <span data-ttu-id="056fc-170">읽기 전용 참조 인수를 사용하여 버전을 호출하려면 메서드를 호출할 때 `in` 한정자를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-170">To call the version with the readonly reference argument, you must include the `in` modifier when calling the method.</span></span>

> [!NOTE]
> <span data-ttu-id="056fc-171">이는 버그 수정으로 구현되었습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-171">This was implemented as a bug fix.</span></span> <span data-ttu-id="056fc-172">이것은 언어 버전이 “7.2”로 설정된 경우에도 더 이상 모호하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-172">This no longer is ambiguous even with the language version set to "7.2".</span></span>

<span data-ttu-id="056fc-173">자세한 내용은 [`in` 매개 변수 한정자](../language-reference/keywords/in-parameter-modifier.md)에 대한 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="056fc-173">For more information, see the article on the [`in` parameter modifier](../language-reference/keywords/in-parameter-modifier.md).</span></span>

### <a name="extend-expression-variables-in-initializers"></a><span data-ttu-id="056fc-174">이니셜라이저에서 식 변수 확장</span><span class="sxs-lookup"><span data-stu-id="056fc-174">Extend expression variables in initializers</span></span>

<span data-ttu-id="056fc-175">`out` 변수 선언이 허용하기 위해 C# 7.0에 추가된 구문은 필드 이니셜라이저, 속성 이니셜라이저, 생성자 이니셜라이저 및 쿼리 절을 포함하도록 확장되었습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-175">The syntax added in C# 7.0 to allow `out` variable declarations has been extended to include field initializers, property initializers, constructor initializers, and query clauses.</span></span> <span data-ttu-id="056fc-176">이를 통해 다음 예제와 같은 코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-176">It enables code such as the following example:</span></span>

```csharp
public class B
{
   public B(int i, out int j)
   {
      j = i;
   }
}

public class D : B
{
   public D(int i) : B(i, out var j)
   {
      Console.WriteLine($"The value of 'j' is {j}");
   }
}
```

### <a name="improved-overload-candidates"></a><span data-ttu-id="056fc-177">향상된 오버로드 후보</span><span class="sxs-lookup"><span data-stu-id="056fc-177">Improved overload candidates</span></span>

<span data-ttu-id="056fc-178">모든 릴리스에서 오버로드 해결 규칙은 모호한 메서드 호출에 “분명한” 선택이 있는 상황을 해결하도록 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-178">In every release, the overload resolution rules get updated to address situations where ambiguous method invocations have an "obvious" choice.</span></span> <span data-ttu-id="056fc-179">이 릴리스는 컴파일러가 분명한 선택 항목을 선택하도록 도와주는 세 가지 새로운 규칙을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-179">This release adds three new rules to help the compiler pick the obvious choice:</span></span>

1. <span data-ttu-id="056fc-180">메서드 그룹에 인스턴스와 정적 멤버가 둘 다 포함되어 있으면 인스턴스 수신기 또는 컨텍스트 없이 호출되는 경우 컴파일러는 인스턴스 멤버를 버립니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-180">When a method group contains both instance and static members, the compiler discards the instance members if the method was invoked without an instance receiver or context.</span></span> <span data-ttu-id="056fc-181">메서드가 인스턴스 수신기를 통해 호출된 경우 컴파일러는 정적 멤버를 버립니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-181">The compiler discards the static members if the method was invoked with an instance receiver.</span></span> <span data-ttu-id="056fc-182">수신기가 없는 경우 컴파일러는 정적 컨텍스트에 정적 멤버만 포함하고, 이외의 경우에는 정적 및 인스턴스 멤버를 둘 다 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-182">When there is no receiver, the compiler includes only static members in a static context, otherwise both static and instance members.</span></span> <span data-ttu-id="056fc-183">수신기가 모호하게 인스턴스 또는 형식인 경우에는 컴파일러가 둘 다 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-183">When the receiver is ambiguously an instance or type, the compiler includes both.</span></span> <span data-ttu-id="056fc-184">암시적 `this` 인스턴스 수신기를 사용할 수 없는 정적 컨텍스트에는 정적 멤버와 같이 `this`가 정의되지 않은 멤버의 본문과 필드 이니셜라이저 및 생성자 이니셜라이저와 같이 `this`를 사용할 수 없는 위치가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-184">A static context, where an implicit `this` instance receiver cannot be used, includes the body of members where no `this` is defined, such as static members, as well as places where `this` cannot be used, such as field initializers and constructor-initializers.</span></span>
1. <span data-ttu-id="056fc-185">형식 인수가 해당 제약 조건을 충족하지 않는 제네릭 메서드가 메서드 그룹에 포함된 경우 이러한 멤버는 후보 집합에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-185">When a method group contains some generic methods whose type arguments do not satisfy their constraints, these members are removed from the candidate set.</span></span>
1. <span data-ttu-id="056fc-186">메서드 그룹 변환의 경우 반환 형식이 대리자의 반환 형식과 일치하지 않는 후보 메서드가 집합에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-186">For a method group conversion, candidate methods whose return type doesn't match up with the delegate's return type are removed from the set.</span></span>

<span data-ttu-id="056fc-187">어떤 메서드가 더 나은지 알고 있으면 모호한 메서드 오버로드에 대한 컴파일러 오류가 감소하므로 이 변경을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-187">You'll only notice this change because you'll find fewer compiler errors for ambiguous method overloads when you are sure which method is better.</span></span>

## <a name="new-compiler-options"></a><span data-ttu-id="056fc-188">새로운 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="056fc-188">New compiler options</span></span>

<span data-ttu-id="056fc-189">새로운 컴파일러 옵션은 C# 프로그램에 대한 새로운 빌드 및 DevOps 시나리오를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-189">New compiler options support new build and DevOps scenarios for C# programs.</span></span>

### <a name="public-or-open-source-signing"></a><span data-ttu-id="056fc-190">공개 또는 오픈 소스 서명</span><span class="sxs-lookup"><span data-stu-id="056fc-190">Public or Open Source signing</span></span>

<span data-ttu-id="056fc-191">`-publicsign` 컴파일러 옵션은 공개 키를 사용하여 어셈블리에 서명하도록 컴파일러에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-191">The `-publicsign` compiler option instructs the compiler to sign the assembly using a public key.</span></span> <span data-ttu-id="056fc-192">어셈블리는 서명됨으로 표시되지만 시그니처는 공개 키에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-192">The assembly is marked as signed, but the signature is taken from the public key.</span></span> <span data-ttu-id="056fc-193">이 옵션을 사용하면 공개 키를 사용하여 오픈 소스 프로젝트에서 서명된 어셈블리를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-193">This option enables you to build signed assemblies from open-source projects using a public key.</span></span>

<span data-ttu-id="056fc-194">자세한 내용은 [-publicsign 컴파일러 옵션](../language-reference/compiler-options/publicsign-compiler-option.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="056fc-194">For more information, see the [-publicsign compiler option](../language-reference/compiler-options/publicsign-compiler-option.md) article.</span></span>

### <a name="pathmap"></a><span data-ttu-id="056fc-195">pathmap</span><span class="sxs-lookup"><span data-stu-id="056fc-195">pathmap</span></span>

<span data-ttu-id="056fc-196">`-pathmap` 컴파일러 옵션은 빌드 환경의 소스 경로를 매핑된 소스 경로로 바꾸도록 컴파일러에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-196">The `-pathmap` compiler option instructs the compiler to replace source paths from the build environment with mapped source paths.</span></span> <span data-ttu-id="056fc-197">`-pathmap` 옵션은 컴파일러에서 작성된 PDB 파일의 소스 경로 또는 <xref:System.Runtime.CompilerServices.CallerFilePathAttribute>를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="056fc-197">The `-pathmap` option controls the source path written by the compiler to PDB files or for the <xref:System.Runtime.CompilerServices.CallerFilePathAttribute>.</span></span>

<span data-ttu-id="056fc-198">자세한 내용은 [-pathmap 컴파일러 옵션](../language-reference/compiler-options/pathmap-compiler-option.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="056fc-198">For more information, see the [-pathmap compiler option](../language-reference/compiler-options/pathmap-compiler-option.md) article.</span></span>
