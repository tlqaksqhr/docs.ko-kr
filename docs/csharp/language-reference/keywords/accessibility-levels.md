---
title: "액세스 가능성 수준(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 77124554d7a0b38414e154e024aceddbfffcfbd4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="accessibility-levels-c-reference"></a><span data-ttu-id="bbb85-102">액세스 가능성 수준(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="bbb85-102">Accessibility Levels (C# Reference)</span></span>
<span data-ttu-id="bbb85-103">액세스 한정자 [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) 또는 [private](../../../csharp/language-reference/keywords/private.md)을 사용하여 멤버에 대한 다음 선언된 액세스 가능성 수준 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bbb85-103">Use the access modifiers, [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or [private](../../../csharp/language-reference/keywords/private.md), to specify one of the following declared accessibility levels for members.</span></span>  
  
|<span data-ttu-id="bbb85-104">선언된 액세스 가능성</span><span class="sxs-lookup"><span data-stu-id="bbb85-104">Declared accessibility</span></span>|<span data-ttu-id="bbb85-105">의미</span><span class="sxs-lookup"><span data-stu-id="bbb85-105">Meaning</span></span>|  
|----------------------------|-------------|  
|`public`|<span data-ttu-id="bbb85-106">액세스가 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bbb85-106">Access is not restricted.</span></span>|  
|`protected`|<span data-ttu-id="bbb85-107">액세스가 포함하는 클래스 또는 포함하는 클래스에서 파생된 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbb85-107">Access is limited to the containing class or types derived from the containing class.</span></span>|  
|`internal`|<span data-ttu-id="bbb85-108">액세스가 현재 어셈블리로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbb85-108">Access is limited to the current assembly.</span></span>|  
|`protected internal`|<span data-ttu-id="bbb85-109">액세스가 현재 어셈블리 또는 포함하는 클래스에서 파생된 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbb85-109">Access is limited to the current assembly or types derived from the containing class.</span></span>|  
|`private`|<span data-ttu-id="bbb85-110">액세스가 포함하는 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbb85-110">Access is limited to the containing type.</span></span>|  
|`private protected`|<span data-ttu-id="bbb85-111">액세스가 포함 하는 클래스 또는 포함 하는 현재 어셈블리 내의 클래스에서 파생 된 형식으로 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbb85-111">Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>|  
  
 <span data-ttu-id="bbb85-112">하나의 액세스 한정자를 사용할 수는 멤버 또는 형식을 제외 하 고 사용 하는 경우는 `protected internal` 또는 `private protected` 조합 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbb85-112">Only one access modifier is allowed for a member or type, except when you use the `protected internal` or `private protected` combinations.</span></span>  
  
 <span data-ttu-id="bbb85-113">네임스페이스에는 액세스 한정자가 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bbb85-113">Access modifiers are not allowed on namespaces.</span></span> <span data-ttu-id="bbb85-114">네임스페이스에는 액세스 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bbb85-114">Namespaces have no access restrictions.</span></span>  
  
 <span data-ttu-id="bbb85-115">멤버 선언이 발생한 컨텍스트에 따라 특정 선언된 액세스 가능성만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbb85-115">Depending on the context in which a member declaration occurs, only certain declared accessibilities are permitted.</span></span> <span data-ttu-id="bbb85-116">액세스 한정자가 멤버 선언에서 지정되지 않으면 기본 액세스 가능성이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbb85-116">If no access modifier is specified in a member declaration, a default accessibility is used.</span></span>  
  
 <span data-ttu-id="bbb85-117">다른 형식에 중첩되지 않은 최상위 형식에는 `internal` 또는 `public` 액세스 가능성만 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbb85-117">Top-level types, which are not nested in other types, can only have `internal` or `public` accessibility.</span></span> <span data-ttu-id="bbb85-118">이러한 형식에 대한 기본 액세스 가능성은 `internal`입니다.</span><span class="sxs-lookup"><span data-stu-id="bbb85-118">The default accessibility for these types is `internal`.</span></span>  
  
 <span data-ttu-id="bbb85-119">다음 표에 나와 있는 대로 다른 형식의 멤버인 중첩 형식에는 선언된 액세스 가능성이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbb85-119">Nested types, which are members of other types, can have declared accessibilities as indicated in the following table.</span></span>  
  
|<span data-ttu-id="bbb85-120">소속 그룹</span><span class="sxs-lookup"><span data-stu-id="bbb85-120">Members of</span></span>|<span data-ttu-id="bbb85-121">기본 멤버 액세스 가능성</span><span class="sxs-lookup"><span data-stu-id="bbb85-121">Default member accessibility</span></span>|<span data-ttu-id="bbb85-122">멤버의 허용된 선언된 액세스 가능성</span><span class="sxs-lookup"><span data-stu-id="bbb85-122">Allowed declared accessibility of the member</span></span>|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|<span data-ttu-id="bbb85-123">없음</span><span class="sxs-lookup"><span data-stu-id="bbb85-123">None</span></span>|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|<span data-ttu-id="bbb85-124">없음</span><span class="sxs-lookup"><span data-stu-id="bbb85-124">None</span></span>|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 <span data-ttu-id="bbb85-125">중첩된 형식의 액세스 가능성은 액세스 가능 도메인에 따라 다릅니다. [액세스 가능성 도메인](../../../csharp/language-reference/keywords/accessibility-domain.md)은 멤버에 대해 선언된 액세스 가능성 및 한 수준 위 형식의 액세스 가능성 도메인에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbb85-125">The accessibility of a nested type depends on its [accessibility domain](../../../csharp/language-reference/keywords/accessibility-domain.md), which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="bbb85-126">그러나 중첩 형식의 액세스 가능 도메인은 포함하는 형식의 액세스 가능 도메인을 벗어날 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bbb85-126">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="bbb85-127">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="bbb85-127">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bbb85-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bbb85-128">See Also</span></span>  
 [<span data-ttu-id="bbb85-129">C# 참조</span><span class="sxs-lookup"><span data-stu-id="bbb85-129">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="bbb85-130">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="bbb85-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="bbb85-131">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="bbb85-131">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="bbb85-132">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="bbb85-132">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="bbb85-133">접근성 도메인</span><span class="sxs-lookup"><span data-stu-id="bbb85-133">Accessibility Domain</span></span>](../../../csharp/language-reference/keywords/accessibility-domain.md)  
 [<span data-ttu-id="bbb85-134">접근성 수준 사용에 대한 제한</span><span class="sxs-lookup"><span data-stu-id="bbb85-134">Restrictions on Using Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)  
 [<span data-ttu-id="bbb85-135">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="bbb85-135">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="bbb85-136">public</span><span class="sxs-lookup"><span data-stu-id="bbb85-136">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="bbb85-137">private</span><span class="sxs-lookup"><span data-stu-id="bbb85-137">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="bbb85-138">protected</span><span class="sxs-lookup"><span data-stu-id="bbb85-138">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="bbb85-139">internal</span><span class="sxs-lookup"><span data-stu-id="bbb85-139">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
