---
title: "속성 디자인"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- member design guidelines, properties
- properties [.NET Framework], design guidelines
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 477b3b69ce1b8a3bb160e8e120885239e3d99e56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="property-design"></a><span data-ttu-id="0f208-102">속성 디자인</span><span class="sxs-lookup"><span data-stu-id="0f208-102">Property Design</span></span>
<span data-ttu-id="0f208-103">속성 메서드 기술적으로 매우 유사 하지만는 해당 사용 시나리오 측면에서 매우 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-103">Although properties are technically very similar to methods, they are quite different in terms of their usage scenarios.</span></span> <span data-ttu-id="0f208-104">이러한 스마트 필드도 이해 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-104">They should be seen as smart fields.</span></span> <span data-ttu-id="0f208-105">필드가 호출 구문 및 메서드의 유연성을가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-105">They have the calling syntax of fields, and the flexibility of methods.</span></span>  
  
 <span data-ttu-id="0f208-106">**✓ 않습니다** 호출자 속성의 값을 변경할 수 없어야 하는 경우 가져오기 전용 속성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-106">**✓ DO** create get-only properties if the caller should not be able to change the value of the property.</span></span>  
  
 <span data-ttu-id="0f208-107">염두에서에 둬야 되는 경우의 형식 속성이 변경 가능한 참조 형식인, 가져오기 전용 속성은 경우에 속성 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-107">Keep in mind that if the type of the property is a mutable reference type, the property value can be changed even if the property is get-only.</span></span>  
  
 <span data-ttu-id="0f208-108">**X 하지 않으면** getter 보다 광범위 한 액세스 가능성을 가진 setter에 설정 전용 속성 또는 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-108">**X DO NOT** provide set-only properties or properties with the setter having broader accessibility than the getter.</span></span>  
  
 <span data-ttu-id="0f208-109">예를 들어 public setter 및 getter 보호 된 속성을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="0f208-109">For example, do not use properties with a public setter and a protected getter.</span></span>  
  
 <span data-ttu-id="0f208-110">속성 getter를 제공할 수 없는 경우 대신 메서드로 기능을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-110">If the property getter cannot be provided, implement the functionality as a method instead.</span></span> <span data-ttu-id="0f208-111">메서드 이름에 시작 하는 것이 좋습니다. `Set` 고 무엇는 지정한 속성에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-111">Consider starting the method name with `Set` and follow with what you would have named the property.</span></span> <span data-ttu-id="0f208-112">예를 들어 <xref:System.AppDomain> 라는 메서드가 있으며 `SetCachePath` 라는 집합 으로만 이동 가능한 속성 대신 `CachePath`합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-112">For example, <xref:System.AppDomain> has a method called `SetCachePath` instead of having a set-only property called `CachePath`.</span></span>  
  
 <span data-ttu-id="0f208-113">**✓ 않습니다** 기본값 보안상 또는 치명적인 오류가 비효율적인 코드에서 발생 하지 않습니다 보장 하는 모든 속성에 대 한 적절 한 기본값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-113">**✓ DO** provide sensible default values for all properties, ensuring that the defaults do not result in a security hole or terribly inefficient code.</span></span>  
  
 <span data-ttu-id="0f208-114">**✓ 않습니다** 속성을 개체의 임시 잘못 된 상태에이 인해 경우에 순서에 관계 없이 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-114">**✓ DO** allow properties to be set in any order even if this results in a temporary invalid state of the object.</span></span>  
  
 <span data-ttu-id="0f208-115">것 여기서 한 속성의 일부 값 잘못 되었을 수 지점에 상호 관련 되도록 두 개 이상의 속성에 대 한 동일한 개체에서 다른 속성의 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-115">It is common for two or more properties to be interrelated to a point where some values of one property might be invalid given the values of other properties on the same object.</span></span> <span data-ttu-id="0f208-116">이러한 경우 잘못 된 상태에서 발생 한 예외를 서로 관련 된 속성은 개체에서 함께 사용할 실제로 될 때까지 연기 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-116">In such cases, exceptions resulting from the invalid state should be postponed until the interrelated properties are actually used together by the object.</span></span>  
  
 <span data-ttu-id="0f208-117">**✓ 않습니다** 속성 setter 예외를 throw 하는 경우 이전 값을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-117">**✓ DO** preserve the previous value if a property setter throws an exception.</span></span>  
  
 <span data-ttu-id="0f208-118">**하지 말고 X** 속성 getter에서 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-118">**X AVOID** throwing exceptions from property getters.</span></span>  
  
 <span data-ttu-id="0f208-119">속성 getter에서 단순 작업 해야 및 사전 조건이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-119">Property getters should be simple operations and should not have any preconditions.</span></span> <span data-ttu-id="0f208-120">Getter 예외를 throw 하 고, 메서드가 되도록 아마도 재설계 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-120">If a getter can throw an exception, it should probably be redesigned to be a method.</span></span> <span data-ttu-id="0f208-121">이 규칙 인덱서, 여기서 기대할 예외는 인수 유효성 검사의 결과 적용 되지 않습니다 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-121">Notice that this rule does not apply to indexers, where we do expect exceptions as a result of validating the arguments.</span></span>  
  
### <a name="indexed-property-design"></a><span data-ttu-id="0f208-122">인덱싱된 속성 디자인</span><span class="sxs-lookup"><span data-stu-id="0f208-122">Indexed Property Design</span></span>  
 <span data-ttu-id="0f208-123">인덱싱된 속성은 매개 변수가 있을 수 있으며 배열 인덱싱와 유사한 특수 구문을 사용 하 여 호출할 수 있는 특수 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-123">An indexed property is a special property that can have parameters and can be called with special syntax similar to array indexing.</span></span>  
  
 <span data-ttu-id="0f208-124">인덱싱된 속성은 일반적으로 인덱서 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-124">Indexed properties are commonly referred to as indexers.</span></span> <span data-ttu-id="0f208-125">인덱서는 논리적 컬렉션의 항목에 대 한 액세스를 제공 하는 Api에만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-125">Indexers should be used only in APIs that provide access to items in a logical collection.</span></span> <span data-ttu-id="0f208-126">예를 들어 문자열은 문자 및 인덱서를 집합이 <xref:System.String?displayProperty=nameWithType> 해당 문자에 액세스 하는 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-126">For example, a string is a collection of characters, and the indexer on <xref:System.String?displayProperty=nameWithType> was added to access its characters.</span></span>  
  
 <span data-ttu-id="0f208-127">**✓ 고려** 인덱서를 사용 하 여 내부 배열에 저장 된 데이터에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-127">**✓ CONSIDER** using indexers to provide access to data stored in an internal array.</span></span>  
  
 <span data-ttu-id="0f208-128">**✓ 고려** 컬렉션 항목을 나타내는 형식에 인덱서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-128">**✓ CONSIDER** providing indexers on types representing collections of items.</span></span>  
  
 <span data-ttu-id="0f208-129">**하지 말고 X** 를 사용 하 여 인덱싱된 속성 둘 이상의 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-129">**X AVOID** using indexed properties with more than one parameter.</span></span>  
  
 <span data-ttu-id="0f208-130">디자인에 여러 개의 매개 변수가 필요한 경우 속성 논리를 컬렉션에 실제로 접근자를 나타내는지 여부를 다시 고려해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-130">If the design requires multiple parameters, reconsider whether the property really represents an accessor to a logical collection.</span></span> <span data-ttu-id="0f208-131">표시 되지 않는 메서드를 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-131">If it does not, use methods instead.</span></span> <span data-ttu-id="0f208-132">메서드 이름에 시작 하는 것이 좋습니다. `Get` 또는 `Set`합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-132">Consider starting the method name with `Get` or `Set`.</span></span>  
  
 <span data-ttu-id="0f208-133">**하지 말고 X** 외의 다른 매개 변수 형식 가진 인덱서 <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, 또는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-133">**X AVOID** indexers with parameter types other than <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, or an enum.</span></span>  
  
 <span data-ttu-id="0f208-134">디자인에는 다른 형식의 매개 변수가 필요한 경우 다시 확인 API 논리를 컬렉션에 실제로 접근자를 나타내는지 여부를 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-134">If the design requires other types of parameters, strongly reevaluate whether the API really represents an accessor to a logical collection.</span></span> <span data-ttu-id="0f208-135">그렇지 않은 경우 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-135">If it does not, use a method.</span></span> <span data-ttu-id="0f208-136">메서드 이름에 시작 하는 것이 좋습니다. `Get` 또는 `Set`합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-136">Consider starting the method name with `Get` or `Set`.</span></span>  
  
 <span data-ttu-id="0f208-137">**✓ 않습니다** 이름을 사용 하 여 `Item` 에 대 한는 분명히 더 나은 이름일 경우를 제외 인덱싱된 속성 (예:, 참조는 <xref:System.String.Chars%2A> 속성을 `System.String`).</span><span class="sxs-lookup"><span data-stu-id="0f208-137">**✓ DO** use the name `Item` for indexed properties unless there is an obviously better name (e.g., see the <xref:System.String.Chars%2A> property on `System.String`).</span></span>  
  
 <span data-ttu-id="0f208-138">C#에서는 인덱서 항목 이름은 기본적으로는 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-138">In C#, indexers are by default named Item.</span></span> <span data-ttu-id="0f208-139"><xref:System.Runtime.CompilerServices.IndexerNameAttribute> 는이 이름을 사용자 지정 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-139">The <xref:System.Runtime.CompilerServices.IndexerNameAttribute> can be used to customize this name.</span></span>  
  
 <span data-ttu-id="0f208-140">**X 하지 않으면** 인덱서 및 메서드는 의미가 동일한 형식으로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-140">**X DO NOT** provide both an indexer and methods that are semantically equivalent.</span></span>  
  
 <span data-ttu-id="0f208-141">**X 하지 않으면** 둘 이상의 제품군의 한 가지 형식으로 오버 로드 된 인덱서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-141">**X DO NOT** provide more than one family of overloaded indexers in one type.</span></span>  
  
 <span data-ttu-id="0f208-142">이 옵션은 C# 컴파일러에 의해 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-142">This is enforced by the C# compiler.</span></span>  
  
 <span data-ttu-id="0f208-143">**X 하지 않으면** 인덱싱된 속성을 사용 하 여 기본이 아닌 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-143">**X DO NOT** use nondefault indexed properties.</span></span>  
  
 <span data-ttu-id="0f208-144">이 옵션은 C# 컴파일러에 의해 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-144">This is enforced by the C# compiler.</span></span>  
  
### <a name="property-change-notification-events"></a><span data-ttu-id="0f208-145">속성 변경 알림 이벤트</span><span class="sxs-lookup"><span data-stu-id="0f208-145">Property Change Notification Events</span></span>  
 <span data-ttu-id="0f208-146">경우에 따라 속성 값의 변경 내용 사용자에 게 알리는 이벤트를 제공할 것이 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-146">Sometimes it is useful to provide an event notifying the user of changes in a property value.</span></span> <span data-ttu-id="0f208-147">예를 들어 `System.Windows.Forms.Control` 발생 한 `TextChanged` 이벤트의 값 보다 이후 해당 `Text` 속성이 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-147">For example, `System.Windows.Forms.Control` raises a `TextChanged` event after the value of its `Text` property has changed.</span></span>  
  
 <span data-ttu-id="0f208-148">**✓ 고려** 를 발생 시키는 변경 알림 이벤트 고급 수준의 Api (일반적으로 디자이너 구성 요소)의 속성 값이 수정 된 경우.</span><span class="sxs-lookup"><span data-stu-id="0f208-148">**✓ CONSIDER** raising change notification events when property values in high-level APIs (usually designer components) are modified.</span></span>  
  
 <span data-ttu-id="0f208-149">사용자에 게 알려 개체의 속성을 변경 하는 경우에 대 한 좋은 시나리오 이면 개체의 속성에 대 한 변경 알림 이벤트를 발생 시켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-149">If there is a good scenario for a user to know when a property of an object is changing, the object should raise a change notification event for the property.</span></span>  
  
 <span data-ttu-id="0f208-150">그러나 기본 형식, 컬렉션 등 낮은 수준의 Api에 대 한 이러한 이벤트를 발생 시키는 때문에 오버 헤드가 될 가능성이있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-150">However, it is unlikely to be worth the overhead to raise such events for low-level APIs such as base types or collections.</span></span> <span data-ttu-id="0f208-151">예를 들어 <xref:System.Collections.Generic.List%601> 에 새 항목이 목록에 추가 될 때 이러한 이벤트를 발생 시 키 지는 및 `Count` 속성 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-151">For example, <xref:System.Collections.Generic.List%601> would not raise such events when a new item is added to the list and the `Count` property changes.</span></span>  
  
 <span data-ttu-id="0f208-152">**✓ 고려** 알림 이벤트 속성의 값이 외부 강제를 통해 변경 될 때 변경 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-152">**✓ CONSIDER** raising change notification events when the value of a property changes via external forces.</span></span>  
  
 <span data-ttu-id="0f208-153">속성 값을 외부 요인 (방식 외의 다른 개체에서 메서드를 호출 하 여)을 통해 변경 되 면 발생 시키는 값이 변경 및 변경 된 개발자에 게 이벤트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-153">If a property value changes via some external force (in a way other than by calling methods on the object), raise events indicate to the developer that the value is changing and has changed.</span></span> <span data-ttu-id="0f208-154">좋은 예로 `Text` 텍스트 상자 컨트롤의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-154">A good example is the `Text` property of a text box control.</span></span> <span data-ttu-id="0f208-155">사용자의 텍스트를 입력 하는 경우는 `TextBox`, 속성 값이 자동으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f208-155">When the user types text in a `TextBox`, the property value automatically changes.</span></span>  
  
 <span data-ttu-id="0f208-156">*일부 © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="0f208-156">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="0f208-157">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="0f208-157">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f208-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f208-158">See Also</span></span>  
 [<span data-ttu-id="0f208-159">멤버 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="0f208-159">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="0f208-160">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="0f208-160">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
