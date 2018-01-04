---
title: "클래스, 구조체 및 인터페이스의 이름"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- type names, guidelines
- classes [.NET Framework], names
- enumerations [.NET Framework], names
- names [.NET Framework], interfaces
- common type names
- names [.NET Framework], type names
- names [.NET Framework], classes
- interfaces [.NET Framework], names
- generic type parameters
ms.assetid: 87a4b0da-ed64-43b1-ac43-968576c444ce
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7c76fccec77454cb4551e427e254fe84d9a60299
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="names-of-classes-structs-and-interfaces"></a><span data-ttu-id="0ffb4-102">클래스, 구조체 및 인터페이스의 이름</span><span class="sxs-lookup"><span data-stu-id="0ffb4-102">Names of Classes, Structs, and Interfaces</span></span>
<span data-ttu-id="0ffb4-103">다음에 나오는 이름 지정 지침 일반 형식의 이름 지정에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-103">The naming guidelines that follow apply to general type naming.</span></span>  
  
 <span data-ttu-id="0ffb4-104">**✓ 않습니다** 명사 또는 명사구를 PascalCasing를 사용 하 여으로 클래스 및 구조체 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-104">**✓ DO** name classes and structs with nouns or noun phrases, using PascalCasing.</span></span>  
  
 <span data-ttu-id="0ffb4-105">이 동사 구 붙은 메서드에서 형식 이름을 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-105">This distinguishes type names from methods, which are named with verb phrases.</span></span>  
  
 <span data-ttu-id="0ffb4-106">**✓ 않습니다** 형용사 구 또는 경우에 따라 명사 또는 명사구 인터페이스 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-106">**✓ DO** name interfaces with adjective phrases, or occasionally with nouns or noun phrases.</span></span>  
  
 <span data-ttu-id="0ffb4-107">명사 및 명사구를 거의 사용 해야 하며 형식을 추상 클래스와 인터페이스 하지 되어야 함을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-107">Nouns and noun phrases should be used rarely and they might indicate that the type should be an abstract class, and not an interface.</span></span>  
  
 <span data-ttu-id="0ffb4-108">**X 하지 않으면** 클래스 이름 (예: "C")는 접두사를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-108">**X DO NOT** give class names a prefix (e.g., "C").</span></span>  
  
 <span data-ttu-id="0ffb4-109">**✓ 고려** 기본 클래스의 이름으로 클래스를 파생 종료 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-109">**✓ CONSIDER** ending the name of derived classes with the name of the base class.</span></span>  
  
 <span data-ttu-id="0ffb4-110">이 매우 읽을 수 하 고 관계를 명확 하 게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-110">This is very readable and explains the relationship clearly.</span></span> <span data-ttu-id="0ffb4-111">이 코드의 예로: `ArgumentOutOfRangeException`, 하는 한 종류의 `Exception`, 및 `SerializableAttribute`, 하는 한 종류의 `Attribute`합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-111">Some examples of this in code are: `ArgumentOutOfRangeException`, which is a kind of `Exception`, and `SerializableAttribute`, which is a kind of `Attribute`.</span></span> <span data-ttu-id="0ffb4-112">그러나 되기;이 지침을 적용할 때 적절 한 판단 신호를 사용 하 여 예를 들어는 `Button` 클래스는 일종의 `Control` 이벤트 있지만 `Control` 이름에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-112">However, it is important to use reasonable judgment in applying this guideline; for example, the `Button` class is a kind of `Control` event, although `Control` doesn’t appear in its name.</span></span>  
  
 <span data-ttu-id="0ffb4-113">**✓ 않습니다** 문자로 접두사 인터페이스 이름을 I, 유형을 인터페이스 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-113">**✓ DO** prefix interface names with the letter I, to indicate that the type is an interface.</span></span>  
  
 <span data-ttu-id="0ffb4-114">예를 들어 `IComponent` (설명이 포함 된 명사) `ICustomAttributeProvider` (명사구) 및 `IPersistable` (명사)은 적절 한 인터페이스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-114">For example, `IComponent` (descriptive noun), `ICustomAttributeProvider` (noun phrase), and `IPersistable` (adjective) are appropriate interface names.</span></span> <span data-ttu-id="0ffb4-115">다른 형식 이름에서와 마찬가지로 약어를 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-115">As with other type names, avoid abbreviations.</span></span>  
  
 <span data-ttu-id="0ffb4-116">**✓ 않습니다** 이름으로 "I" 접두사 인터페이스 이름에는 클래스는 인터페이스의 표준 구현 클래스-인터페이스 쌍을 정의 하는 경우에 다른 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-116">**✓ DO** ensure that the names differ only by the "I" prefix on the interface name when you are defining a class–interface pair where the class is a standard implementation of the interface.</span></span>  
  
## <a name="names-of-generic-type-parameters"></a><span data-ttu-id="0ffb4-117">제네릭 형식 매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="0ffb4-117">Names of Generic Type Parameters</span></span>  
 <span data-ttu-id="0ffb4-118">제네릭은.NET Framework 2.0에 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-118">Generics were added to .NET Framework 2.0.</span></span> <span data-ttu-id="0ffb4-119">도입 된 새로운 종류의 라는 식별자는 기능인 *형식 매개 변수*합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-119">The feature introduced a new kind of identifier called *type parameter*.</span></span>  
  
 <span data-ttu-id="0ffb4-120">**✓ 않습니다** 단일 문자 이름을 완전히 자체 설명 하 고 설명 하는 이름 값을 더 하지 않는 경우 제외 설명적인 이름으로 name 제네릭 형식 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-120">**✓ DO** name generic type parameters with descriptive names unless a single-letter name is completely self-explanatory and a descriptive name would not add value.</span></span>  
  
 <span data-ttu-id="0ffb4-121">**✓ 고려** 를 사용 하 여 `T` 단일 문자 형식 매개 변수를 사용 하는 형식에 대 한 형식 매개 변수 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-121">**✓ CONSIDER** using `T` as the type parameter name for types with one single-letter type parameter.</span></span>  
  
```  
public int IComparer<T> { ... }  
public delegate bool Predicate<T>(T item);  
public struct Nullable<T> where T:struct { ... }  
```  
  
 <span data-ttu-id="0ffb4-122">**✓ 않습니다** 설명적인 형식 매개 변수 이름 앞에 `T`합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-122">**✓ DO** prefix descriptive type parameter names with `T`.</span></span>  
  
```  
public interface ISessionChannel<TSession> where TSession : ISession{  
    TSession Session { get; }  
}  
```  
  
 <span data-ttu-id="0ffb4-123">**✓ 고려** 제약 조건을 나타내는 매개 변수 이름의 형식 매개 변수에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-123">**✓ CONSIDER** indicating constraints placed on a type parameter in the name of the parameter.</span></span>  
  
 <span data-ttu-id="0ffb4-124">예를 들어 한 매개 변수를 제한할 `ISession` 파일명 `TSession`합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-124">For example, a parameter constrained to `ISession` might be called `TSession`.</span></span>  
  
## <a name="names-of-common-types"></a><span data-ttu-id="0ffb4-125">공용 형식의 이름</span><span class="sxs-lookup"><span data-stu-id="0ffb4-125">Names of Common Types</span></span>  
 <span data-ttu-id="0ffb4-126">**✓ 않습니다** 또는 특정.NET Framework 형식이 구현에서 파생 된 형식의 이름을 지정할 때 다음 표에 설명 된 지침을 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-126">**✓ DO** follow the guidelines described in the following table when naming types derived from or implementing certain .NET Framework types.</span></span>  
  
|<span data-ttu-id="0ffb4-127">Base Type</span><span class="sxs-lookup"><span data-stu-id="0ffb4-127">Base Type</span></span>|<span data-ttu-id="0ffb4-128">형식 파생/구현 지침</span><span class="sxs-lookup"><span data-stu-id="0ffb4-128">Derived/Implementing Type Guideline</span></span>|  
|---------------|------------------------------------------|  
|`System.Attribute`|<span data-ttu-id="0ffb4-129">**✓ 않습니다** 사용자 지정 특성 클래스의 이름에 "특성" 접미사를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-129">**✓ DO** add the suffix "Attribute" to names of custom attribute classes.</span></span>|  
|`System.Delegate`|<span data-ttu-id="0ffb4-130">**✓ 않습니다** 이벤트에 사용 되는 대리자의 이름에 "EventHandler" 접미사를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-130">**✓ DO** add the suffix "EventHandler" to names of delegates that are used in events.</span></span><br /><br /> <span data-ttu-id="0ffb4-131">**✓ 않습니다** 이외의 이벤트 처리기로 사용 되는 접미사 "Callback" 이름에 대리자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-131">**✓ DO** add the suffix "Callback" to names of delegates other than those used as event handlers.</span></span><br /><br /> <span data-ttu-id="0ffb4-132">**X 하지 않으면** "대리자" 접미사는 대리자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-132">**X DO NOT** add the suffix "Delegate" to a delegate.</span></span>|  
|`System.EventArgs`|<span data-ttu-id="0ffb4-133">**✓ 않습니다** "EventArgs입니다." 접미사 추가</span><span class="sxs-lookup"><span data-stu-id="0ffb4-133">**✓ DO** add the suffix "EventArgs."</span></span>|  
|`System.Enum`|<span data-ttu-id="0ffb4-134">**X 하지 않으면** 대신 해당 언어에서 지 원하는 키워드를 사용 하 여; 예를 들어 C#에서 사용 하 여이 클래스에서 파생 된 `enum` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-134">**X DO NOT** derive from this class; use the keyword supported by your language instead; for example, in C#, use the `enum` keyword.</span></span><br /><br /> <span data-ttu-id="0ffb4-135">**X 하지 않으면** "열거형" 또는 "Flag" 접미사 추가</span><span class="sxs-lookup"><span data-stu-id="0ffb4-135">**X DO NOT** add the suffix "Enum" or "Flag."</span></span>|  
|`System.Exception`|<span data-ttu-id="0ffb4-136">**✓ 않습니다** "예외" 접미사 추가</span><span class="sxs-lookup"><span data-stu-id="0ffb4-136">**✓ DO** add the suffix "Exception."</span></span>|  
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|<span data-ttu-id="0ffb4-137">**✓ 않습니다** "사전입니다." 접미사 추가</span><span class="sxs-lookup"><span data-stu-id="0ffb4-137">**✓ DO** add the suffix "Dictionary."</span></span> <span data-ttu-id="0ffb4-138">`IDictionary` 는 컬렉션의 특정 형식 이지만이 지침 뒤에 오는 보다 일반적인 컬렉션 지침 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-138">Note that `IDictionary` is a specific type of collection, but this guideline takes precedence over the more general collections guideline that follows.</span></span>|  
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|<span data-ttu-id="0ffb4-139">**✓ 않습니다** "Collection" 접미사 추가</span><span class="sxs-lookup"><span data-stu-id="0ffb4-139">**✓ DO** add the suffix "Collection."</span></span>|  
|`System.IO.Stream`|<span data-ttu-id="0ffb4-140">**✓ 않습니다** "스트림입니다." 접미사 추가</span><span class="sxs-lookup"><span data-stu-id="0ffb4-140">**✓ DO** add the suffix "Stream."</span></span>|  
|`CodeAccessPermission IPermission`|<span data-ttu-id="0ffb4-141">**✓ 않습니다** "권한" 접미사 추가</span><span class="sxs-lookup"><span data-stu-id="0ffb4-141">**✓ DO** add the suffix "Permission."</span></span>|  
  
## <a name="naming-enumerations"></a><span data-ttu-id="0ffb4-142">열거형 이름 지정</span><span class="sxs-lookup"><span data-stu-id="0ffb4-142">Naming Enumerations</span></span>  
 <span data-ttu-id="0ffb4-143">일반적 (열거형) 열거형 형식 이름에 표준 형식 명명 규칙 (PascalCasing 등) 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-143">Names of enumeration types (also called enums) in general should follow the standard type-naming rules (PascalCasing, etc.).</span></span> <span data-ttu-id="0ffb4-144">그러나 열거형에만 적용 되는 추가 지침이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-144">However, there are additional guidelines that apply specifically to enums.</span></span>  
  
 <span data-ttu-id="0ffb4-145">**✓ 않습니다** 비트 필드에 해당 값이 경우가 아니면 열거형에 대 한 단수형 형식 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-145">**✓ DO** use a singular type name for an enumeration unless its values are bit fields.</span></span>  
  
 <span data-ttu-id="0ffb4-146">**✓ 않습니다** 라고도 함 플래그 열거형 값으로 비트 필드 열거형에 대 한 복수 형식 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-146">**✓ DO** use a plural type name for an enumeration with bit fields as values, also called flags enum.</span></span>  
  
 <span data-ttu-id="0ffb4-147">**X 하지 않으면** enum 형식 이름에 "열거형" 접미사를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-147">**X DO NOT** use an "Enum" suffix in enum type names.</span></span>  
  
 <span data-ttu-id="0ffb4-148">**X 하지 않으면** "플래그를"를 사용 하 여 또는 열거형에서 "Flags" 접미사 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-148">**X DO NOT** use "Flag" or "Flags" suffixes in enum type names.</span></span>  
  
 <span data-ttu-id="0ffb4-149">**X 하지 않으면** 서식 있는 텍스트 열거형 등에 대 한 열거형 값 이름 (예: "ad" 열거형의 ADO.), "rtf"에 접두사를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffb4-149">**X DO NOT** use a prefix on enumeration value names (e.g., "ad" for ADO enums, "rtf" for rich text enums, etc.).</span></span>  
  
 <span data-ttu-id="0ffb4-150">*일부 © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="0ffb4-150">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="0ffb4-151">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="0ffb4-151">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ffb4-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ffb4-152">See Also</span></span>  
 [<span data-ttu-id="0ffb4-153">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="0ffb4-153">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="0ffb4-154">명명 지침</span><span class="sxs-lookup"><span data-stu-id="0ffb4-154">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
