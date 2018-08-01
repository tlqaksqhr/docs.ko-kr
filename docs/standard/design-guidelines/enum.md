---
title: 열거형 디자인
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 544f617ca3a352814504125d7a61d70db5a81566
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33579251"
---
# <a name="enum-design"></a><span data-ttu-id="bb3e5-102">열거형 디자인</span><span class="sxs-lookup"><span data-stu-id="bb3e5-102">Enum Design</span></span>
<span data-ttu-id="bb3e5-103">열거형은 특수 한 유형의 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-103">Enums are a special kind of value type.</span></span> <span data-ttu-id="bb3e5-104">열거형의 두 종류가: 단순 열거형 및 플래그 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-104">There are two kinds of enums: simple enums and flag enums.</span></span>  
  
 <span data-ttu-id="bb3e5-105">단순 열거형 선택 항목의 닫힌된 작은 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-105">Simple enums represent small closed sets of choices.</span></span> <span data-ttu-id="bb3e5-106">단순 열거형의 일반적인 예에는 한 색 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-106">A common example of the simple enum is a set of colors.</span></span>  
  
 <span data-ttu-id="bb3e5-107">플래그 열거형 enum 값에 비트 작업을 지원 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-107">Flag enums are designed to support bitwise operations on the enum values.</span></span> <span data-ttu-id="bb3e5-108">플래그 열거형의 일반적인 예에는 옵션의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-108">A common example of the flags enum is a list of options.</span></span>  
  
 <span data-ttu-id="bb3e5-109">**✓ DO** 열거형을 사용 하 여 강력한 형식의 매개 변수, 속성 및 값 집합을 나타내는 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-109">**✓ DO** use an enum to strongly type parameters, properties, and return values that represent sets of values.</span></span>  
  
 <span data-ttu-id="bb3e5-110">**✓ DO** 정적 상수 대신 열거형을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-110">**✓ DO** favor using an enum instead of static constants.</span></span>  
  
 <span data-ttu-id="bb3e5-111">**X DO NOT** 집합 (예: 운영 체제 버전, 친구, 등의 이름입니다.)에 대 한 열거형을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-111">**X DO NOT** use an enum for open sets (such as the operating system version, names of your friends, etc.).</span></span>  
  
 <span data-ttu-id="bb3e5-112">**X DO NOT** 나중에 사용할 수는 예약 된 열거형 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-112">**X DO NOT** provide reserved enum values that are intended for future use.</span></span>  
  
 <span data-ttu-id="bb3e5-113">항상 단순히 기존 열거형에 이후 단계에서 값을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-113">You can always simply add values to the existing enum at a later stage.</span></span> <span data-ttu-id="bb3e5-114">참조 [열거형에 값 추가](#add_value) 에 대 한 자세한 내용은 열거형에 값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-114">See [Adding Values to Enums](#add_value) for more details on adding values to enums.</span></span> <span data-ttu-id="bb3e5-115">예약된 값만 실제 값 집합이 오염 하며 하 사용자 오류가 발생할 수입니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-115">Reserved values just pollute the set of real values and tend to lead to user errors.</span></span>  
  
 <span data-ttu-id="bb3e5-116">**X AVOID** 열거형 값을 하나만로 공개적으로 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-116">**X AVOID** publicly exposing enums with only one value.</span></span>  
  
 <span data-ttu-id="bb3e5-117">C Api의 다음 버전의 확장을 위한 일반적인 방법은 메서드 시그니처를 예약 된 매개 변수를 추가 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-117">A common practice for ensuring future extensibility of C APIs is to add reserved parameters to method signatures.</span></span> <span data-ttu-id="bb3e5-118">이러한 예약 된 매개 변수 이며 기본값은 단일 열거형으로 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-118">Such reserved parameters can be expressed as enums with a single default value.</span></span> <span data-ttu-id="bb3e5-119">관리 되는 Api에서 수행 되어야이 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-119">This should not be done in managed APIs.</span></span> <span data-ttu-id="bb3e5-120">메서드 오버 로드 매개 변수는 이후 릴리스에서 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-120">Method overloading allows adding parameters in future releases.</span></span>  
  
 <span data-ttu-id="bb3e5-121">**X DO NOT** 열거형에 센티널 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-121">**X DO NOT** include sentinel values in enums.</span></span>  
  
 <span data-ttu-id="bb3e5-122">프레임 워크 개발자가 경우에 따라 변수가 이기는 하지만 센티널 값은 프레임 워크의 사용자에 게 혼동입니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-122">Although they are sometimes helpful to framework developers, sentinel values are confusing to users of the framework.</span></span> <span data-ttu-id="bb3e5-123">열거형에 의해 표현 된 집합에서 값 중 하나 되 고 아닌 열거형의 상태를 추적 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-123">They are used to track the state of the enum rather than being one of the values from the set represented by the enum.</span></span>  
  
 <span data-ttu-id="bb3e5-124">**✓ DO** 단순 열거형에는 0 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-124">**✓ DO** provide a value of zero on simple enums.</span></span>  
  
 <span data-ttu-id="bb3e5-125">다음과 같이 "None"입니다. 값을 호출 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-125">Consider calling the value something like "None."</span></span> <span data-ttu-id="bb3e5-126">이러한 값이 특정 열거형에 적합 하지 않은 경우 열거형에 대 한 가장 일반적인 기본값 0의 내부 값을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-126">If such a value is not appropriate for this particular enum, the most common default value for the enum should be assigned the underlying value of zero.</span></span>  
  
 <span data-ttu-id="bb3e5-127">**✓ CONSIDER** 를 사용 하 여 <xref:System.Int32> (대부분의 프로그래밍 언어의 기본값) 열거형의 내부 형식으로 다음 중 하나에 해당 하지 않는 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-127">**✓ CONSIDER** using <xref:System.Int32> (the default in most programming languages) as the underlying type of an enum unless any of the following is true:</span></span>  
  
-   <span data-ttu-id="bb3e5-128">열거형 플래그 열거형은 있으며 32 개 이상의 플래그가 하거나 나중에 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-128">The enum is a flags enum and you have more than 32 flags, or expect to have more in the future.</span></span>  
  
-   <span data-ttu-id="bb3e5-129">기본 형식이 다를 수 해야 <xref:System.Int32> 다른 크기 열거형 비관리 코드와 쉽게 상호 운용성에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-129">The underlying type needs to be different than <xref:System.Int32> for easier interoperability with unmanaged code expecting different-size enums.</span></span>  
  
-   <span data-ttu-id="bb3e5-130">더 작은 기본 형식이 하면 공간이 크게 절약으로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-130">A smaller underlying type would result in substantial savings in space.</span></span> <span data-ttu-id="bb3e5-131">제어 흐름에 대 한 인수로 서 주로 사용할 열거형을 예상할 경우 크기 거의 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-131">If you expect the enum to be used mainly as an argument for flow of control, the size makes little difference.</span></span> <span data-ttu-id="bb3e5-132">한 크기 절감 효과가 매우 길어질 수 있습니다 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="bb3e5-132">The size savings might be significant if:</span></span>  
  
    -   <span data-ttu-id="bb3e5-133">매우 자주 인스턴스화된 구조체 또는 클래스의 필드로 사용할 enum을 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-133">You expect the enum to be used as a field in a very frequently instantiated structure or class.</span></span>  
  
    -   <span data-ttu-id="bb3e5-134">원하는 큰 배열 또는 열거형 인스턴스의 컬렉션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-134">You expect users to create large arrays or collections of the enum instances.</span></span>  
  
    -   <span data-ttu-id="bb3e5-135">Serialize 할 열거형의 인스턴스 수가 많은 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-135">You expect a large number of instances of the enum to be serialized.</span></span>  
  
 <span data-ttu-id="bb3e5-136">메모리 사용량에 대 한 관리 되는 개체는 수 항상 `DWORD`-정렬 되므로 여러 열거형 또는 다른 작은 구조를 항상 때문에 총 인스턴스 크기 차이 확인 하기 위해 포함 된 더 작은 열거형을 압축 하는 인스턴스에 효과적으로 필요 최대 반올림 하 고는 `DWORD`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-136">For in-memory usage, be aware that managed objects are always `DWORD`-aligned, so you effectively need multiple enums or other small structures in an instance to pack a smaller enum with in order to make a difference, because the total instance size is always going to be rounded up to a `DWORD`.</span></span>  
  
 <span data-ttu-id="bb3e5-137">**✓ DO** 단 수 명사 또는 명사구 단순 열거형 및 플래그 열거형 복수 명사 또는 명사구로 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-137">**✓ DO** name flag enums with plural nouns or noun phrases and simple enums with singular nouns or noun phrases.</span></span>  
  
 <span data-ttu-id="bb3e5-138">**X DO NOT** 확장 <xref:System.Enum?displayProperty=nameWithType> 직접 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-138">**X DO NOT** extend <xref:System.Enum?displayProperty=nameWithType> directly.</span></span>  
  
 <span data-ttu-id="bb3e5-139"><xref:System.Enum?displayProperty=nameWithType> 특별 한 형식 CLR에서 만드는 데 사용자 정의 열거형.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-139"><xref:System.Enum?displayProperty=nameWithType> is a special type used by the CLR to create user-defined enumerations.</span></span> <span data-ttu-id="bb3e5-140">대부분의 프로그래밍 언어에이 기능에 액세스할 수 있는 프로그래밍 요소를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-140">Most programming languages provide a programming element that gives you access to this functionality.</span></span> <span data-ttu-id="bb3e5-141">예를 들어 C#에서 `enum` 키워드를 사용 하는 열거형을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-141">For example, in C# the `enum` keyword is used to define an enumeration.</span></span>  
  
<a name="design"></a>   
### <a name="designing-flag-enums"></a><span data-ttu-id="bb3e5-142">디자인 플래그 열거형</span><span class="sxs-lookup"><span data-stu-id="bb3e5-142">Designing Flag Enums</span></span>  
 <span data-ttu-id="bb3e5-143">**✓ DO** 적용 된 <xref:System.FlagsAttribute?displayProperty=nameWithType> 플래그 열거형에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-143">**✓ DO** apply the <xref:System.FlagsAttribute?displayProperty=nameWithType> to flag enums.</span></span> <span data-ttu-id="bb3e5-144">이 특성을 단순 열거형에 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-144">Do not apply this attribute to simple enums.</span></span>  
  
 <span data-ttu-id="bb3e5-145">**✓ DO** 수 자유롭게 결합 비트 OR 연산을 사용 하 여 플래그 열거형 값에 2의 제곱을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-145">**✓ DO** use powers of two for the flag enum values so they can be freely combined using the bitwise OR operation.</span></span>  
  
 <span data-ttu-id="bb3e5-146">**✓ CONSIDER** 플래그의 조합을 사용 되는 일반적으로 특수 한 열거 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-146">**✓ CONSIDER** providing special enum values for commonly used combinations of flags.</span></span>  
  
 <span data-ttu-id="bb3e5-147">비트 연산은 고급 개념 및 간단한 작업에 필요한 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-147">Bitwise operations are an advanced concept and should not be required for simple tasks.</span></span> <span data-ttu-id="bb3e5-148"><xref:System.IO.FileAccess.ReadWrite> 이러한 특수 값의 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-148"><xref:System.IO.FileAccess.ReadWrite> is an example of such a special value.</span></span>  
  
 <span data-ttu-id="bb3e5-149">**X AVOID** 만들기 플래그 열거형 값의 조합이 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-149">**X AVOID** creating flag enums where certain combinations of values are invalid.</span></span>  
  
 <span data-ttu-id="bb3e5-150">**X AVOID** 값 "플래그를 모두 선택 취소"를 나타내는 적절 하 게 다음 지침에서 설명 했 듯이 라는 하지 않는 한 enum 값이 0 인 플래그를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-150">**X AVOID** using flag enum values of zero unless the value represents "all flags are cleared" and is named appropriately, as prescribed by the next guideline.</span></span>  
  
 <span data-ttu-id="bb3e5-151">**✓ DO** 0 플래그 열거형의 값 이름을 `None`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-151">**✓ DO** name the zero value of flag enums `None`.</span></span> <span data-ttu-id="bb3e5-152">플래그 열거형에 대 한 값 해야 항상 의미가 "플래그를 모두 선택 취소 합니다."</span><span class="sxs-lookup"><span data-stu-id="bb3e5-152">For a flag enum, the value must always mean "all flags are cleared."</span></span>  
  
<a name="add_value"></a>   
### <a name="adding-value-to-enums"></a><span data-ttu-id="bb3e5-153">열거형에 값 추가</span><span class="sxs-lookup"><span data-stu-id="bb3e5-153">Adding Value to Enums</span></span>  
 <span data-ttu-id="bb3e5-154">매우 일반적 검색 후 이미 제공 된 열거형에 값을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-154">It is very common to discover that you need to add values to an enum after you have already shipped it.</span></span> <span data-ttu-id="bb3e5-155">잠재적인 응용 프로그램 호환성 문제는 기존 API에서 새로 추가 된 값이 반환 하는 경우 되므로 잘못 작성 된 응용 프로그램의 새 값을 제대로 처리 하지 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-155">There is a potential application compatibility problem when the newly added value is returned from an existing API, because poorly written applications might not handle the new value correctly.</span></span>  
  
 <span data-ttu-id="bb3e5-156">**✓ CONSIDER** 작은 호환성 위험 불구 하 고 열거형에 값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-156">**✓ CONSIDER** adding values to enums, despite a small compatibility risk.</span></span>  
  
 <span data-ttu-id="bb3e5-157">열거형에 대 한 추가 인해 발생 하는 응용 프로그램 호환성 문제에 대 한 실제 데이터를 설정한 경우에 새과 이전 값을 반환 하는 새로운 API를 추가 하는 것이 좋습니다. 하 고 이전 값만 반환 합니다. 계속 하는 이전 API에 사용할 수 없게 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-157">If you have real data about application incompatibilities caused by additions to an enum, consider adding a new API that returns the new and old values, and deprecate the old API, which should continue returning just the old values.</span></span> <span data-ttu-id="bb3e5-158">이렇게 하면 기존 응용 프로그램 호환성을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb3e5-158">This will ensure that your existing applications remain compatible.</span></span>  
  
 <span data-ttu-id="bb3e5-159">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="bb3e5-159">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="bb3e5-160">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="bb3e5-160">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb3e5-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb3e5-161">See Also</span></span>  
 [<span data-ttu-id="bb3e5-162">형식 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="bb3e5-162">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="bb3e5-163">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="bb3e5-163">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
