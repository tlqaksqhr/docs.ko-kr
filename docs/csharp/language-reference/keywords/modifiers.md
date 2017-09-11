---
title: "한정자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- keywords [C#], modifiers
- modifiers [C#]
ms.assetid: c96691dd-b357-49ec-b5ae-03ca214fadfb
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9e2e7e5e3907ac9bb66676e749ddd55a8ac4836c
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="modifiers-c-reference"></a><span data-ttu-id="03c6a-102">한정자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="03c6a-102">Modifiers (C# Reference)</span></span>
<span data-ttu-id="03c6a-103">한정자는 형식 및 형식 멤버의 선언을 수정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="03c6a-103">Modifiers are used to modify declarations of types and type members.</span></span> <span data-ttu-id="03c6a-104">이 단원에서는 다음의 C# 한정자에 대해 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="03c6a-104">This section introduces the C# modifiers.</span></span>  
  
|<span data-ttu-id="03c6a-105">한정자</span><span class="sxs-lookup"><span data-stu-id="03c6a-105">Modifier</span></span>|<span data-ttu-id="03c6a-106">용도</span><span class="sxs-lookup"><span data-stu-id="03c6a-106">Purpose</span></span>|  
|--------------|-------------|  
|[<span data-ttu-id="03c6a-107">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="03c6a-107">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)<br /><br /> <span data-ttu-id="03c6a-108">-   [public](../../../csharp/language-reference/keywords/public.md)</span><span class="sxs-lookup"><span data-stu-id="03c6a-108">-   [public](../../../csharp/language-reference/keywords/public.md)</span></span><br /><span data-ttu-id="03c6a-109">-   [private](../../../csharp/language-reference/keywords/private.md)</span><span class="sxs-lookup"><span data-stu-id="03c6a-109">-   [private](../../../csharp/language-reference/keywords/private.md)</span></span><br /><span data-ttu-id="03c6a-110">-   [internal](../../../csharp/language-reference/keywords/internal.md)</span><span class="sxs-lookup"><span data-stu-id="03c6a-110">-   [internal](../../../csharp/language-reference/keywords/internal.md)</span></span><br /><span data-ttu-id="03c6a-111">-   [protected](../../../csharp/language-reference/keywords/protected.md)</span><span class="sxs-lookup"><span data-stu-id="03c6a-111">-   [protected](../../../csharp/language-reference/keywords/protected.md)</span></span>|<span data-ttu-id="03c6a-112">형식 및 형식 멤버의 선언된 액세스 가능성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03c6a-112">Specifies the declared accessibility of types and type members.</span></span>|  
|[<span data-ttu-id="03c6a-113">abstract</span><span class="sxs-lookup"><span data-stu-id="03c6a-113">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)|<span data-ttu-id="03c6a-114">클래스가 다른 클래스의 기본 클래스로만 사용됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="03c6a-114">Indicates that a class is intended only to be a base class of other classes.</span></span>|  
|[<span data-ttu-id="03c6a-115">async</span><span class="sxs-lookup"><span data-stu-id="03c6a-115">async</span></span>](../../../csharp/language-reference/keywords/async.md)|<span data-ttu-id="03c6a-116">수정된 메서드, 람다 식 또는 무명 메서드가 비동기임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="03c6a-116">Indicates that the modified method, lambda expression, or anonymous method is asynchronous.</span></span>|  
|[<span data-ttu-id="03c6a-117">const</span><span class="sxs-lookup"><span data-stu-id="03c6a-117">const</span></span>](../../../csharp/language-reference/keywords/const.md)|<span data-ttu-id="03c6a-118">필드 또는 지역 변수의 값을 수정할 수 없도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03c6a-118">Specifies that the value of the field or the local variable cannot be modified.</span></span>|  
|[<span data-ttu-id="03c6a-119">event</span><span class="sxs-lookup"><span data-stu-id="03c6a-119">event</span></span>](../../../csharp/language-reference/keywords/event.md)|<span data-ttu-id="03c6a-120">이벤트를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="03c6a-120">Declares an event.</span></span>|  
|[<span data-ttu-id="03c6a-121">extern</span><span class="sxs-lookup"><span data-stu-id="03c6a-121">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)|<span data-ttu-id="03c6a-122">메서드가 외부에서 구현됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="03c6a-122">Indicates that the method is implemented externally.</span></span>|  
|[<span data-ttu-id="03c6a-123">new</span><span class="sxs-lookup"><span data-stu-id="03c6a-123">new</span></span>](../../../csharp/language-reference/keywords/new.md)|<span data-ttu-id="03c6a-124">기본 클래스에서 상속된 멤버를 명시적으로 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="03c6a-124">Explicitly hides a member inherited from a base class.</span></span>|  
|[<span data-ttu-id="03c6a-125">override</span><span class="sxs-lookup"><span data-stu-id="03c6a-125">override</span></span>](../../../csharp/language-reference/keywords/override.md)|<span data-ttu-id="03c6a-126">기본 클래스에서 상속된 가상 멤버의 새 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03c6a-126">Provides a new implementation of a virtual member inherited from a base class.</span></span>|  
|[<span data-ttu-id="03c6a-127">partial</span><span class="sxs-lookup"><span data-stu-id="03c6a-127">partial</span></span>](../../../csharp/language-reference/keywords/partial-type.md)|<span data-ttu-id="03c6a-128">동일한 어셈블리 전체에서 partial 클래스, 구조체 및 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="03c6a-128">Defines partial classes, structs and methods throughout the same assembly.</span></span>|  
|[<span data-ttu-id="03c6a-129">readonly</span><span class="sxs-lookup"><span data-stu-id="03c6a-129">readonly</span></span>](../../../csharp/language-reference/keywords/readonly.md)|<span data-ttu-id="03c6a-130">선언의 일부로 또는 동일한 클래스의 생성자에서만 값을 할당받을 수 있는 필드를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="03c6a-130">Declares a field that can only be assigned values as part of the declaration or in a constructor in the same class.</span></span>|  
|[<span data-ttu-id="03c6a-131">sealed</span><span class="sxs-lookup"><span data-stu-id="03c6a-131">sealed</span></span>](../../../csharp/language-reference/keywords/sealed.md)|<span data-ttu-id="03c6a-132">클래스가 상속될 수 없도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="03c6a-132">Specifies that a class cannot be inherited.</span></span>|  
|[<span data-ttu-id="03c6a-133">static</span><span class="sxs-lookup"><span data-stu-id="03c6a-133">static</span></span>](../../../csharp/language-reference/keywords/static.md)|<span data-ttu-id="03c6a-134">특정 개체가 아니라 형식 자체에만 속하는 멤버를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="03c6a-134">Declares a member that belongs to the type itself instead of to a specific object.</span></span>|  
|[<span data-ttu-id="03c6a-135">unsafe</span><span class="sxs-lookup"><span data-stu-id="03c6a-135">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)|<span data-ttu-id="03c6a-136">안전하지 않은 컨텍스트를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="03c6a-136">Declares an unsafe context.</span></span>|  
|[<span data-ttu-id="03c6a-137">virtual</span><span class="sxs-lookup"><span data-stu-id="03c6a-137">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)|<span data-ttu-id="03c6a-138">파생 클래스의 재정의 멤버에 의해 구현이 변경될 수 있는 메서드 또는 접근자를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="03c6a-138">Declares a method or an accessor whose implementation can be changed by an overriding member in a derived class.</span></span>|  
|[<span data-ttu-id="03c6a-139">volatile</span><span class="sxs-lookup"><span data-stu-id="03c6a-139">volatile</span></span>](../../../csharp/language-reference/keywords/volatile.md)|<span data-ttu-id="03c6a-140">필드가 운영 체제, 하드웨어 또는 동시에 실행되는 스레드 등에 의해 프로그램에서 수정될 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="03c6a-140">Indicates that a field can be modified in the program by something such as the operating system, the hardware, or a concurrently executing thread.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="03c6a-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03c6a-141">See Also</span></span>  
 <span data-ttu-id="03c6a-142">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="03c6a-142">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="03c6a-143">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="03c6a-143">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="03c6a-144">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="03c6a-144">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)

