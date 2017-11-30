---
title: "스레드 로컬 저장소: 스레드 상대 정적 필드 및 데이터 슬롯"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], local storage
- threading [.NET Framework], thread-relative static fields
- local thread storage
- TLS
ms.assetid: c633a4dc-a790-4ed1-96b5-f72bd968b284
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 39dd80d378171563f2aadadaa146278e8a417d32
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="thread-local-storage-thread-relative-static-fields-and-data-slots"></a><span data-ttu-id="f4d83-102">스레드 로컬 저장소: 스레드 상대 정적 필드 및 데이터 슬롯</span><span class="sxs-lookup"><span data-stu-id="f4d83-102">Thread Local Storage: Thread-Relative Static Fields and Data Slots</span></span>
<span data-ttu-id="f4d83-103">스레드 및 응용 프로그램 도메인에 고유한 관리 되는 스레드 로컬 저장소 (TLS) 데이터를 저장을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-103">You can use managed thread local storage (TLS) to store data that is unique to a thread and application domain.</span></span> <span data-ttu-id="f4d83-104">.NET Framework에서 제공 하는 두 가지 방법으로 사용 하도록 관리 TLS: 스레드 상대 정적 필드 및 데이터 슬롯입니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-104">The .NET Framework provides two ways to use managed TLS: thread-relative static fields and data slots.</span></span>  
  
-   <span data-ttu-id="f4d83-105">스레드 관련 정적 필드를 사용 하 여 (스레드 상대 `Shared` Visual Basic의 필드) 컴파일 타임에 정확한 요구 사항을 예상할 수 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="f4d83-105">Use thread-relative static fields (thread-relative `Shared` fields in Visual Basic) if you can anticipate your exact needs at compile time.</span></span> <span data-ttu-id="f4d83-106">스레드 관련 정적 필드는 최적의 성능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-106">Thread-relative static fields provide the best performance.</span></span> <span data-ttu-id="f4d83-107">또한 제공 컴파일 타임 형식 검사의 이점을 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-107">They also give you the benefits of compile-time type checking.</span></span>  
  
-   <span data-ttu-id="f4d83-108">실제 요구 사항을 런타임에만 노출 될 수 있습니다 하는 경우 데이터 슬롯을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-108">Use data slots when your actual requirements might be discovered only at run time.</span></span> <span data-ttu-id="f4d83-109">데이터 형식으로 저장 됩니다 및 데이터 슬롯은 느리고 스레드 상대 정적 필드 보다 사용 <xref:System.Object>이므로 사용 하기 전에 올바른 형식으로 캐스팅 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-109">Data slots are slower and more awkward to use than thread-relative static fields, and data is stored as type <xref:System.Object>, so you must cast it to the correct type before you use it.</span></span>  
  
 <span data-ttu-id="f4d83-110">관리 되지 않는 c + +를 사용 하 여 `TlsAlloc` 슬롯을 동적으로 할당 하 고 `__declspec(thread)` 변수 스레드 상대 저장소에 할당 되는 선언 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-110">In unmanaged C++, you use `TlsAlloc` to allocate slots dynamically and `__declspec(thread)` to declare that a variable should be allocated in thread-relative storage.</span></span> <span data-ttu-id="f4d83-111">이 동작의 관리 되는 버전을 제공 하는 스레드 상대 정적 필드 및 데이터 슬롯입니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-111">Thread-relative static fields and data slots provide the managed version of this behavior.</span></span>  
  
 <span data-ttu-id="f4d83-112">에 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], 사용할 수 있습니다는 <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType> 클래스는 개체가 처음 사용 하는 경우 지연 초기화 하는 스레드 로컬 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-112">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use the <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType> class to create thread-local objects that are initialized lazily when the object is first consumed.</span></span> <span data-ttu-id="f4d83-113">자세한 내용은 [초기화 지연](../../../docs/framework/performance/lazy-initialization.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f4d83-113">For more information, see [Lazy Initialization](../../../docs/framework/performance/lazy-initialization.md).</span></span>  
  
## <a name="uniqueness-of-data-in-managed-tls"></a><span data-ttu-id="f4d83-114">관리 되는 TLS에 있는 데이터의 고유성</span><span class="sxs-lookup"><span data-stu-id="f4d83-114">Uniqueness of Data in Managed TLS</span></span>  
 <span data-ttu-id="f4d83-115">스레드 상대 정적 필드 또는 데이터 슬롯을 사용 하는지 여부를 관리 되는 TLS에 있는 데이터는 스레드 및 응용 프로그램 도메인의 조합에 고유 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-115">Whether you use thread-relative static fields or data slots, data in managed TLS is unique to the combination of thread and application domain.</span></span>  
  
-   <span data-ttu-id="f4d83-116">응용 프로그램 도메인 내에서 스레드를 하나씩 두 스레드 슬롯 또는 동일한 필드를 사용 하는 경우에 다른 스레드에서 데이터를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-116">Within an application domain, one thread cannot modify data from another thread, even when both threads use the same field or slot.</span></span>  
  
-   <span data-ttu-id="f4d83-117">여러 응용 프로그램 도메인에서 동일한 필드 또는 슬롯을 액세스 하는 스레드를 각 응용 프로그램 도메인에서 별도 값을 유지 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-117">When a thread accesses the same field or slot from multiple application domains, a separate value is maintained in each application domain.</span></span>  
  
 <span data-ttu-id="f4d83-118">예를 들어 스레드를 설정 하는 경우 다른 응용 프로그램 도메인을 입력 하 고 필드의 값을 검색 하는 스레드 상대 정적 필드의 값, 두 번째 응용 프로그램 도메인에서 검색 된 값이 첫 번째 응용 프로그램 도메인의 값에서과 다른 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-118">For example, if a thread sets the value of a thread-relative static field, enters another application domain, and then retrieves the value of the field, the value retrieved in the second application domain differs from the value in the first application domain.</span></span> <span data-ttu-id="f4d83-119">두 번째 응용 프로그램 도메인의 필드에 대 한 새 값을 설정 필드 값의 첫 번째 응용 프로그램 도메인에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-119">Setting a new value for the field in the second application domain does not affect the field's value in the first application domain.</span></span>  
  
 <span data-ttu-id="f4d83-120">마찬가지로, 스레드를 두 개의 서로 다른 응용 프로그램 도메인에서 동일한 이름의 데이터 슬롯을 가져오면 첫 번째 응용 프로그램 도메인에서 데이터는 두 번째 응용 프로그램 도메인에 있는 데이터의 독립적인 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-120">Similarly, when a thread gets the same named data slot in two different application domains, the data in the first application domain remains independent of the data in the second application domain.</span></span>  
  
## <a name="thread-relative-static-fields"></a><span data-ttu-id="f4d83-121">스레드 관련 정적 필드</span><span class="sxs-lookup"><span data-stu-id="f4d83-121">Thread-Relative Static Fields</span></span>  
 <span data-ttu-id="f4d83-122">데이터의 일부는 스레드 및 응용 프로그램 도메인 조합에 고유한 항상 알고 있는 경우 적용 된 <xref:System.ThreadStaticAttribute> 특성을 정적 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-122">If you know that a piece of data is always unique to a thread and application-domain combination, apply the <xref:System.ThreadStaticAttribute> attribute to the static field.</span></span> <span data-ttu-id="f4d83-123">다른 정적 필드를 사용할 때 처럼 필드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-123">Use the field as you would use any other static field.</span></span> <span data-ttu-id="f4d83-124">필드의 데이터는 사용 하 여 각 스레드에 고유 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-124">The data in the field is unique to each thread that uses it.</span></span>  
  
 <span data-ttu-id="f4d83-125">스레드 관련 정적 필드 데이터 슬롯의 경우 보다 더 나은 성능을 제공할 및 컴파일 타임 형식 검사의 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-125">Thread-relative static fields provide better performance than data slots and have the benefit of compile-time type checking.</span></span>  
  
 <span data-ttu-id="f4d83-126">주의 모든 클래스 생성자 코드 필드에 액세스 하는 첫 번째 컨텍스트에서 첫 번째 스레드에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-126">Be aware that any class constructor code will run on the first thread in the first context that accesses the field.</span></span> <span data-ttu-id="f4d83-127">모든 다른 스레드 또는 컨텍스트에서 동일한 응용 프로그램 도메인에서 필드로 초기화 됩니다 `null` (`Nothing` Visual basic에서)은 참조 형식 또는 값 있더라도 값 형식이 기본값으로 경우.</span><span class="sxs-lookup"><span data-stu-id="f4d83-127">In all other threads or contexts in the same application domain, the fields will be initialized to `null` (`Nothing` in Visual Basic) if they are reference types, or to their default values if they are value types.</span></span> <span data-ttu-id="f4d83-128">따라서 안됩니다 클래스 생성자 스레드 상대 정적 필드를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-128">Therefore, you should not rely on class constructors to initialize thread-relative static fields.</span></span> <span data-ttu-id="f4d83-129">대신, 스레드 상대 정적 필드를 초기화 하지 않도록 하 고에 초기화 된다고 가정 `null` (`Nothing`) 또는를 기본값으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-129">Instead, avoid initializing thread-relative static fields and assume that they are initialized to `null` (`Nothing`) or to their default values.</span></span>  
  
## <a name="data-slots"></a><span data-ttu-id="f4d83-130">데이터 슬롯</span><span class="sxs-lookup"><span data-stu-id="f4d83-130">Data Slots</span></span>  
 <span data-ttu-id="f4d83-131">.NET Framework에서는 스레드 및 응용 프로그램 도메인의 조합에 고유한 동적 데이터 슬롯입니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-131">The .NET Framework provides dynamic data slots that are unique to a combination of thread and application-domain.</span></span> <span data-ttu-id="f4d83-132">두 가지 방법으로 데이터 슬롯의: 명명 된 슬롯 및 명명 되지 않은 슬롯입니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-132">There are two types of data slots: named slots and unnamed slots.</span></span> <span data-ttu-id="f4d83-133">둘 다 사용 하 여 구현 되는 <xref:System.LocalDataStoreSlot> 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-133">Both are implemented by using the <xref:System.LocalDataStoreSlot> structure.</span></span>  
  
-   <span data-ttu-id="f4d83-134">명명된 된 데이터 슬롯을 만들려면 사용는 <xref:System.Threading.Thread.AllocateNamedDataSlot%2A?displayProperty=nameWithType> 또는 <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="f4d83-134">To create a named data slot, use the <xref:System.Threading.Thread.AllocateNamedDataSlot%2A?displayProperty=nameWithType> or <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f4d83-135">전달 하 고 이름을 기존의 명명 된 슬롯에 대 한 참조를 가져오려면는 <xref:System.Threading.Thread.GetNamedDataSlot%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="f4d83-135">To get a reference to an existing named slot, pass its name to the <xref:System.Threading.Thread.GetNamedDataSlot%2A> method.</span></span>  
  
-   <span data-ttu-id="f4d83-136">명명 되지 않은 데이터 슬롯을 만들려면 사용은 <xref:System.Threading.Thread.AllocateDataSlot%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="f4d83-136">To create an unnamed data slot, use the <xref:System.Threading.Thread.AllocateDataSlot%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="f4d83-137">명명 된 슬롯과 명명 되지 않은 및 둘 다에 사용 된 <xref:System.Threading.Thread.SetData%2A?displayProperty=nameWithType> 및 <xref:System.Threading.Thread.GetData%2A?displayProperty=nameWithType> 설정 및 슬롯에 대 한 정보를 검색 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="f4d83-137">For both named and unnamed slots, use the <xref:System.Threading.Thread.SetData%2A?displayProperty=nameWithType> and <xref:System.Threading.Thread.GetData%2A?displayProperty=nameWithType> methods to set and retrieve the information in the slot.</span></span> <span data-ttu-id="f4d83-138">이 해당를 현재 실행 중인 스레드에 대 한 데이터에만 적용 하는 정적 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-138">These are static methods that always act on the data for the thread that is currently executing them.</span></span>  
  
 <span data-ttu-id="f4d83-139">명명 된 슬롯에 해당 이름을 전달 하 여 필요할 때 슬롯을 검색할 수 없으므로 편리할 수 있습니다는 <xref:System.Threading.Thread.GetNamedDataSlot%2A> 명명 되지 않은 슬롯에 대 한 참조를 유지 하는 대신 메서드.</span><span class="sxs-lookup"><span data-stu-id="f4d83-139">Named slots can be convenient, because you can retrieve the slot when you need it by passing its name to the <xref:System.Threading.Thread.GetNamedDataSlot%2A> method, instead of maintaining a reference to an unnamed slot.</span></span> <span data-ttu-id="f4d83-140">그러나 다른 구성 요소는 스레드 관련 저장소에 동일한 이름을 사용 하 여 스레드 구성 요소와 다른 구성 요소가 모두에서 코드를 실행 하는 경우 두 가지 구성 요소가 다른 사용자의 데이터 손상 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4d83-140">However, if another component uses the same name for its thread-relative storage and a thread executes code from both your component and the other component, the two components might corrupt each other's data.</span></span> <span data-ttu-id="f4d83-141">(이 시나리오에서는 두 구성 요소를 동일한 응용 프로그램 도메인에서 실행 되 고 있는지와 동일한 데이터를 공유 하도록 설계 되지 않은)</span><span class="sxs-lookup"><span data-stu-id="f4d83-141">(This scenario assumes that both components are running in the same application domain, and that they are not designed to share the same data.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4d83-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f4d83-142">See Also</span></span>  
 <xref:System.ContextStaticAttribute>  
 <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=nameWithType>  
 <xref:System.ThreadStaticAttribute>  
 <xref:System.Runtime.Remoting.Messaging.CallContext>  
 [<span data-ttu-id="f4d83-143">스레딩</span><span class="sxs-lookup"><span data-stu-id="f4d83-143">Threading</span></span>](../../../docs/standard/threading/index.md)
