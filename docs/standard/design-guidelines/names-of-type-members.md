---
title: 형식 멤버의 이름
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- events [.NET Framework], names
- methods [.NET Framework], names
- type members
- properties [.NET Framework], names
- fields, names
- field names
- names [.NET Framework], type members
- members [.NET Framework], type
ms.assetid: af5a0903-36af-4c2a-b848-cf959affeaa5
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6584eecb2df652f12fd14710bb5f15933aead541
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="names-of-type-members"></a><span data-ttu-id="d60b3-102">형식 멤버의 이름</span><span class="sxs-lookup"><span data-stu-id="d60b3-102">Names of Type Members</span></span>
<span data-ttu-id="d60b3-103">형식 멤버의 내용이: 메서드, 속성, 이벤트, 생성자 및 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-103">Types are made of members: methods, properties, events, constructors, and fields.</span></span> <span data-ttu-id="d60b3-104">다음 섹션에서는 형식 멤버 이름 지정에 대 한 지침을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-104">The following sections describe guidelines for naming type members.</span></span>  
  
## <a name="names-of-methods"></a><span data-ttu-id="d60b3-105">메서드의 이름</span><span class="sxs-lookup"><span data-stu-id="d60b3-105">Names of Methods</span></span>  
 <span data-ttu-id="d60b3-106">메서드 작업을 수행 하는 방법은 이기 때문에 디자인 지침도 록 요구할 메서드 이름이 동사 또는 동사 구입니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-106">Because methods are the means of taking action, the design guidelines require that method names be verbs or verb phrases.</span></span> <span data-ttu-id="d60b3-107">또한이 지침을 따르면 명사 또는 형용사 구 이름 속성에서 메서드 이름을 구분 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-107">Following this guideline also serves to distinguish method names from property and type names, which are noun or adjective phrases.</span></span>  
  
 <span data-ttu-id="d60b3-108">**✓ 않습니다** 동사 또는 동사 구 메서드 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-108">**✓ DO** give methods names that are verbs or verb phrases.</span></span>  
  
```  
public class String {  
    public int CompareTo(...);  
    public string[] Split(...);  
    public string Trim();  
}  
```  
  
## <a name="names-of-properties"></a><span data-ttu-id="d60b3-109">속성의 이름</span><span class="sxs-lookup"><span data-stu-id="d60b3-109">Names of Properties</span></span>  
 <span data-ttu-id="d60b3-110">다른 멤버와 달리 형용사 명사나 명사구 속성 지정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-110">Unlike other members, properties should be given noun phrase or adjective names.</span></span> <span data-ttu-id="d60b3-111">속성 데이터를 나타내며 속성의 이름을 반영 하는 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-111">That is because a property refers to data, and the name of the property reflects that.</span></span> <span data-ttu-id="d60b3-112">PascalCasing 속성 이름에 항상 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-112">PascalCasing is always used for property names.</span></span>  
  
 <span data-ttu-id="d60b3-113">**✓ 않습니다** 명사나 명사구, 형용사를 사용 하 여 속성 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-113">**✓ DO** name properties using a noun, noun phrase, or adjective.</span></span>  
  
 <span data-ttu-id="d60b3-114">**하지 않으면 X** 다음 예제와 같이 "Get" 메서드의 이름과 일치 하는 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-114">**X DO NOT** have properties that match the name of "Get" methods as in the following example:</span></span>  
  
 `public string TextWriter { get {...} set {...} }`  
 `public string GetTextWriter(int value) { ... }`  
  
 <span data-ttu-id="d60b3-115">이 패턴은 일반적으로 속성 메서드를 실제로 되어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-115">This pattern typically indicates that the property should really be a method.</span></span>  
  
 <span data-ttu-id="d60b3-116">**✓ 않습니다** 단 수 구문 "List" 또는 "컬렉션입니다." 다음을 사용 하는 대신 컬렉션의 항목을 설명 하는 복수 구문으로 컬렉션의 속성 이름</span><span class="sxs-lookup"><span data-stu-id="d60b3-116">**✓ DO** name collection properties with a plural phrase describing the items in the collection instead of using a singular phrase followed by "List" or "Collection."</span></span>  
  
 <span data-ttu-id="d60b3-117">**✓ 않습니다** 찬성 구 사용 하는 부울 속성 이름은 (`CanSeek` 대신 `CantSeek`).</span><span class="sxs-lookup"><span data-stu-id="d60b3-117">**✓ DO** name Boolean properties with an affirmative phrase (`CanSeek` instead of `CantSeek`).</span></span> <span data-ttu-id="d60b3-118">필요에 따라 붙일 수 있습니다. 또한 부울 속성 값을 추가 하는 경우에 하지만 "에" 또는 "Is", "을 수행할 수 있습니다,".</span><span class="sxs-lookup"><span data-stu-id="d60b3-118">Optionally, you can also prefix Boolean properties with "Is," "Can," or "Has," but only where it adds value.</span></span>  
  
 <span data-ttu-id="d60b3-119">**✓ 고려** 속성 형식으로 동일한 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-119">**✓ CONSIDER** giving a property the same name as its type.</span></span>  
  
 <span data-ttu-id="d60b3-120">예를 들어 다음과 같은 속성이 올바르게 가져오고 설정 이라는 enum 값 `Color`하므로 속성은 이름, `Color`:</span><span class="sxs-lookup"><span data-stu-id="d60b3-120">For example, the following property correctly gets and sets an enum value named `Color`, so the property is named `Color`:</span></span>  
  
```  
public enum Color {...}  
public class Control {  
    public Color Color { get {...} set {...} }  
}  
```  
  
## <a name="names-of-events"></a><span data-ttu-id="d60b3-121">이벤트의 이름</span><span class="sxs-lookup"><span data-stu-id="d60b3-121">Names of Events</span></span>  
 <span data-ttu-id="d60b3-122">이벤트를 발생 또는 발생 한 하나 작업을 항상 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-122">Events always refer to some action, either one that is happening or one that has occurred.</span></span> <span data-ttu-id="d60b3-123">따라서 메서드의 경우와 마찬가지로 동사와 함께 이벤트 라고 하며 동사 시제 이벤트가 발생 한 경우 시간을 나타내는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-123">Therefore, as with methods, events are named with verbs, and verb tense is used to indicate the time when the event is raised.</span></span>  
  
 <span data-ttu-id="d60b3-124">**✓ 않습니다** 동사 또는 동사 구를 사용 하 여 이벤트 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-124">**✓ DO** name events with a verb or a verb phrase.</span></span>  
  
 <span data-ttu-id="d60b3-125">예를 들면 `Clicked`, `Painting`, `DroppedDown`등입니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-125">Examples include `Clicked`, `Painting`, `DroppedDown`, and so on.</span></span>  
  
 <span data-ttu-id="d60b3-126">**✓ 않습니다** 부여의 개념을 사용 하 여 이벤트 이름을 이전 및 이후, 현재 및 과거 시제를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-126">**✓ DO** give events names with a concept of before and after, using the present and past tenses.</span></span>  
  
 <span data-ttu-id="d60b3-127">예를 들어 닫기 이벤트는 창이 닫히기 전에 발생 하는 호출 되 `Closing`, 하나는 창이 닫혀 있는 후에 발생 하는 호출 되 고 `Closed`합니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-127">For example, a close event that is raised before a window is closed would be called `Closing`, and one that is raised after the window is closed would be called `Closed`.</span></span>  
  
 <span data-ttu-id="d60b3-128">**X 하지 않으면** "Before" 또는 "After" 접두사 또는 접미어를 나타내는 사전 및 사후 이벤트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-128">**X DO NOT** use "Before" or "After" prefixes or postfixes to indicate pre- and post-events.</span></span> <span data-ttu-id="d60b3-129">사용 하 여 현재 및 과거 시제 앞서 설명한 합니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-129">Use present and past tenses as just described.</span></span>  
  
 <span data-ttu-id="d60b3-130">**✓ 않습니다** 다음 예제와 같이 "EventHandler" 접미사를 사용 이벤트 처리기 (이벤트 형식으로 사용 되는 대리자)의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-130">**✓ DO** name event handlers (delegates used as types of events) with the "EventHandler" suffix, as shown in the following example:</span></span>  
  
 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`  
  
 <span data-ttu-id="d60b3-131">**✓ 않습니다** 의 두 매개 변수를 사용 하 여 `sender` 및 `e` 이벤트 처리기에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-131">**✓ DO** use two parameters named `sender` and `e` in event handlers.</span></span>  
  
 <span data-ttu-id="d60b3-132">보낸 사람 매개 변수는 이벤트를 발생 시킨 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-132">The sender parameter represents the object that raised the event.</span></span> <span data-ttu-id="d60b3-133">보낸 사람 매개 변수는 일반적으로 형식 `object`를 더 구체적인 형식을 사용 하는 것이 불가능 한 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-133">The sender parameter is typically of type `object`, even if it is possible to employ a more specific type.</span></span>  
  
 <span data-ttu-id="d60b3-134">**✓ 않습니다** 이름을 이벤트 인수 클래스 "EventArgs" 접미사를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-134">**✓ DO** name event argument classes with the "EventArgs" suffix.</span></span>  
  
## <a name="names-of-fields"></a><span data-ttu-id="d60b3-135">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d60b3-135">Names of Fields</span></span>  
 <span data-ttu-id="d60b3-136">필드 이름 지정 지침 정적 공용 및 보호 된 필드에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-136">The field-naming guidelines apply to static public and protected fields.</span></span> <span data-ttu-id="d60b3-137">내부 및 전용 필드 지침을 다루지 않은 하 고 공용 또는 보호 된 인스턴스 필드에서 허용 되지 않습니다는 [멤버 디자인 지침](../../../docs/standard/design-guidelines/member.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-137">Internal and private fields are not covered by guidelines, and public or protected instance fields are not allowed by the [member design guidelines](../../../docs/standard/design-guidelines/member.md).</span></span>  
  
 <span data-ttu-id="d60b3-138">**✓ 않습니다** PascalCasing 필드 이름에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-138">**✓ DO** use PascalCasing in field names.</span></span>  
  
 <span data-ttu-id="d60b3-139">**✓ 않습니다** 명사나 명사구, 형용사를 사용 하 여 필드 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-139">**✓ DO** name fields using a noun, noun phrase, or adjective.</span></span>  
  
 <span data-ttu-id="d60b3-140">**X 하지 않으면** 필드 이름에 접두사를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-140">**X DO NOT** use a prefix for field names.</span></span>  
  
 <span data-ttu-id="d60b3-141">예를 들어 사용 하지 마십시오 "g_" 또는 "s_" 정적 필드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d60b3-141">For example, do not use "g_" or "s_" to indicate static fields.</span></span>  
  
 <span data-ttu-id="d60b3-142">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="d60b3-142">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="d60b3-143">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="d60b3-143">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d60b3-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d60b3-144">See Also</span></span>  
 [<span data-ttu-id="d60b3-145">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="d60b3-145">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="d60b3-146">명명 지침</span><span class="sxs-lookup"><span data-stu-id="d60b3-146">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
