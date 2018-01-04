---
title: "확장 가능한 개체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: extensible objects [WCF]
ms.assetid: bc88cefc-31fb-428e-9447-6d20a7d452af
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e7d7b5245130a7581efbf9badb0699f57a6743dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="extensible-objects"></a><span data-ttu-id="29410-102">확장 가능한 개체</span><span class="sxs-lookup"><span data-stu-id="29410-102">Extensible Objects</span></span>
<span data-ttu-id="29410-103">새 기능과 함께 기존 런타임 클래스를 확장하거나 새 상태를 개체에 추가하기 위해 확장명 가능한 개체 패턴이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="29410-103">The extensible object pattern is used to either extend existing runtime classes with new functionality or to add new state to an object.</span></span> <span data-ttu-id="29410-104">확장명 가능한 개체 중 하나에 연결된 확장은 이 개체에서 액세스할 수 있는 확장명 가능한 일반 개체에 연결된 공유 상태 및 기능에 액세스하는 처리 시에 매우 다른 단계에서 동작을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="29410-104">Extensions, attached to one of the extensible objects, enable behaviors at very different stages in processing to access shared state and functionality attached to a common extensible object that they can access.</span></span>  
  
## <a name="the-iextensibleobjectt-pattern"></a><span data-ttu-id="29410-105">IExtensibleObject\<T > 패턴</span><span class="sxs-lookup"><span data-stu-id="29410-105">The IExtensibleObject\<T> Pattern</span></span>  
 <span data-ttu-id="29410-106">확장 가능한 개체 패턴에는 세 가지 인터페이스인 <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601> 및 <xref:System.ServiceModel.IExtensionCollection%601>이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29410-106">There are three interfaces in the extensible object pattern: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601>, and <xref:System.ServiceModel.IExtensionCollection%601>.</span></span>  
  
 <span data-ttu-id="29410-107"><xref:System.ServiceModel.IExtensibleObject%601> 인터페이스는 <xref:System.ServiceModel.IExtension%601> 개체가 해당 기능을 사용자 지정할 수 있도록 하는 형식에 의해 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="29410-107">The <xref:System.ServiceModel.IExtensibleObject%601> interface is implemented by types that allow <xref:System.ServiceModel.IExtension%601> objects to customize their functionality.</span></span>  
  
 <span data-ttu-id="29410-108">확장 가능한 개체를 사용하면 <xref:System.ServiceModel.IExtension%601> 개체를 동적으로 집계할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29410-108">Extensible objects allow dynamic aggregation of <xref:System.ServiceModel.IExtension%601> objects.</span></span> <span data-ttu-id="29410-109"><xref:System.ServiceModel.IExtension%601> 개체는 다음 인터페이스로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="29410-109"><xref:System.ServiceModel.IExtension%601> objects are characterized by the following interface:</span></span>  
  
```  
public interface IExtension<T>  
where T : IExtensibleObject<T>  
{  
    void Attach(T owner);  
    void Detach(T owner);  
}  
```  
  
 <span data-ttu-id="29410-110">형식 제한은 <xref:System.ServiceModel.IExtensibleObject%601>인 클래스에 대해서만 확장이 정의될 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="29410-110">The type restriction guarantees that extensions can only be defined for classes that are <xref:System.ServiceModel.IExtensibleObject%601>.</span></span> <span data-ttu-id="29410-111"><xref:System.ServiceModel.IExtension%601.Attach%2A> 및 <xref:System.ServiceModel.IExtension%601.Detach%2A>는 집계 또는 분배 알림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="29410-111"><xref:System.ServiceModel.IExtension%601.Attach%2A> and <xref:System.ServiceModel.IExtension%601.Detach%2A> provide notification of aggregation or disaggregation.</span></span>  
  
 <span data-ttu-id="29410-112">구현에서 확장을 추가하고 소유자에서 제거할 수 있는 시기를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29410-112">It is valid for implementations to restrict when they may be added and removed from an owner.</span></span> <span data-ttu-id="29410-113">예를 들어 완전히 제거를 허용하지 않거나, 소유자 또는 확장이 특정 상태에 있을 때 확장 추가 또는 제거를 허용하지 않거나, 여러 소유자에 동시에 추가하는 것을 허용하지 않거나, 단일 추가 후에만 단일 제거를 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29410-113">For example, you can disallow removal entirely, disallowing adding or removing extensions when the owner or extension are in a certain state, disallow adding to multiple owners concurrently, or allow only a single addition followed by a single remove.</span></span>  
  
 <span data-ttu-id="29410-114"><xref:System.ServiceModel.IExtension%601>에서는 다른 관리되는 표준 인터페이스와의 상호 작용을 나타내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29410-114"><xref:System.ServiceModel.IExtension%601> does not imply any interactions with other standard managed interfaces.</span></span> <span data-ttu-id="29410-115">특히 소유자 개체의 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> 메서드는 일반적으로 확장을 분리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29410-115">Specifically, the <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> method on the owner object does not normally detach its extensions.</span></span>  
  
 <span data-ttu-id="29410-116">확장 컬렉션에 추가 되 면 <xref:System.ServiceModel.IExtension%601.Attach%2A> 컬렉션에 진입 하기 전에 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29410-116">When an extension is added to the collection, <xref:System.ServiceModel.IExtension%601.Attach%2A> is called before it goes into the collection.</span></span> <span data-ttu-id="29410-117">확장 컬렉션에서 제거 되 면 <xref:System.ServiceModel.IExtension%601.Detach%2A> 제거 된 후 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29410-117">When an extension is removed from the collection, <xref:System.ServiceModel.IExtension%601.Detach%2A> is called after it is removed.</span></span> <span data-ttu-id="29410-118">수단 (적절 한 동기화 가정) 확장 신뢰할 수 있는 해당 하는 동안 컬렉션에서 발견 되 고이 범위에 속함 <xref:System.ServiceModel.IExtension%601.Attach%2A> 및 <xref:System.ServiceModel.IExtension%601.Detach%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="29410-118">This means (assuming appropriate synchronization) an extension can count on only being found in the collection while it is between <xref:System.ServiceModel.IExtension%601.Attach%2A> and <xref:System.ServiceModel.IExtension%601.Detach%2A>.</span></span>  
  
 <span data-ttu-id="29410-119"><xref:System.ServiceModel.IExtensionCollection%601.FindAll%60%601%2A> 또는 <xref:System.ServiceModel.IExtensionCollection%601.Find%60%601%2A>에 전달된 개체가 <xref:System.ServiceModel.IExtension%601>일 필요는 없지만(예를 들어 아무 개체나 전달할 수 있음) 반환되는 확장은 <xref:System.ServiceModel.IExtension%601>입니다.</span><span class="sxs-lookup"><span data-stu-id="29410-119">The object passed to <xref:System.ServiceModel.IExtensionCollection%601.FindAll%60%601%2A> or <xref:System.ServiceModel.IExtensionCollection%601.Find%60%601%2A> need not be <xref:System.ServiceModel.IExtension%601> (for example, you can pass any object), but the returned extension is an <xref:System.ServiceModel.IExtension%601>.</span></span>  
  
 <span data-ttu-id="29410-120">컬렉션에 확장이 없는 경우는 <xref:System.ServiceModel.IExtension%601>, <xref:System.ServiceModel.IExtensionCollection%601.Find%60%601%2A> null을 반환 하 고 <xref:System.ServiceModel.IExtensionCollection%601.FindAll%60%601%2A> 빈 컬렉션을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="29410-120">If no extension in the collection is an <xref:System.ServiceModel.IExtension%601>, <xref:System.ServiceModel.IExtensionCollection%601.Find%60%601%2A> returns null, and <xref:System.ServiceModel.IExtensionCollection%601.FindAll%60%601%2A> returns an empty collection.</span></span> <span data-ttu-id="29410-121">여러 확장을 구현 하는 경우 <xref:System.ServiceModel.IExtension%601>, <xref:System.ServiceModel.IExtensionCollection%601.Find%60%601%2A> 그 중 하나를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="29410-121">If multiple extensions implement <xref:System.ServiceModel.IExtension%601>, <xref:System.ServiceModel.IExtensionCollection%601.Find%60%601%2A> returns one of them.</span></span> <span data-ttu-id="29410-122"><xref:System.ServiceModel.IExtensionCollection%601.FindAll%60%601%2A>에서 반환되는 값은 스냅숏입니다.</span><span class="sxs-lookup"><span data-stu-id="29410-122">The value returned from <xref:System.ServiceModel.IExtensionCollection%601.FindAll%60%601%2A> is a snapshot.</span></span>  
  
 <span data-ttu-id="29410-123">두 가지 주요 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29410-123">There are two main scenarios.</span></span> <span data-ttu-id="29410-124">첫 번째 시나리오에서는 <xref:System.ServiceModel.IExtensibleObject%601.Extensions%2A> 속성을 개체에 상태를 삽입하는 형식 기반 사전으로 사용하여 다른 구성 요소에서 해당 형식으로 개체를 조회할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="29410-124">The first scenario uses the <xref:System.ServiceModel.IExtensibleObject%601.Extensions%2A> property as a type-based dictionary to insert state on an object to enable another component to look it up using the type.</span></span>  
  
 <span data-ttu-id="29410-125">두 번째 시나리오에서는 <xref:System.ServiceModel.IExtension%601.Attach%2A> 및 <xref:System.ServiceModel.IExtension%601.Detach%2A> 속성을 사용하여 개체가 이벤트 등록, 상태 전환 감시 등의 사용자 지정 동작에 참여할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="29410-125">The second scenario uses the <xref:System.ServiceModel.IExtension%601.Attach%2A> and <xref:System.ServiceModel.IExtension%601.Detach%2A> properties to enable an object to participate in custom behavior, such as registering for events, watching state transitions, and so on.</span></span>  
  
 <span data-ttu-id="29410-126"><xref:System.ServiceModel.IExtensionCollection%601> 인터페이스는 <xref:System.ServiceModel.IExtension%601>을 형식별로 검색할 수 있는 <xref:System.ServiceModel.IExtension%601> 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="29410-126">The <xref:System.ServiceModel.IExtensionCollection%601> interface is a collection of the <xref:System.ServiceModel.IExtension%601> objects that allow for retrieving the <xref:System.ServiceModel.IExtension%601> by its type.</span></span> <span data-ttu-id="29410-127"><xref:System.ServiceModel.IExtensionCollection%601.Find%60%601%2A?displayProperty=nameWithType>는 해당 형식의 <xref:System.ServiceModel.IExtension%601> 중에서 최근 추가된 개체만 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="29410-127"><xref:System.ServiceModel.IExtensionCollection%601.Find%60%601%2A?displayProperty=nameWithType> returns the most recently added object that is an <xref:System.ServiceModel.IExtension%601> of that type.</span></span>  
  
### <a name="extensible-objects-in-windows-communication-foundation"></a><span data-ttu-id="29410-128">Windows Communication Foundation의 확장 가능한 개체</span><span class="sxs-lookup"><span data-stu-id="29410-128">Extensible Objects in Windows Communication Foundation</span></span>  
 <span data-ttu-id="29410-129">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에는 다음과 같은 네 개의 확장 가능한 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29410-129">There are four extensible objects in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]:</span></span>  
  
-   <span data-ttu-id="29410-130"><xref:System.ServiceModel.ServiceHostBase> – 서비스 호스트의 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="29410-130"><xref:System.ServiceModel.ServiceHostBase> – This is the base class for the service’s host.</span></span>  <span data-ttu-id="29410-131">이 클래스의 확장을 사용하여 <xref:System.ServiceModel.ServiceHostBase> 자체의 동작을 확장하거나 각 서비스의 상태를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29410-131">Extensions of this class can be used to extend the behavior of the <xref:System.ServiceModel.ServiceHostBase> itself or to store the state for each service.</span></span>  
  
-   <span data-ttu-id="29410-132"><xref:System.ServiceModel.InstanceContext> – 이 클래스는 서비스 형식의 인스턴스를 서비스 런타임과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="29410-132"><xref:System.ServiceModel.InstanceContext> – This class connects an instance of the service’s type with the service runtime.</span></span>  <span data-ttu-id="29410-133">인스턴스에 대한 정보와 <xref:System.ServiceModel.InstanceContext>의 포함 <xref:System.ServiceModel.ServiceHostBase>에 대한 참조가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29410-133">It contains information about the instance as well as a reference to the <xref:System.ServiceModel.InstanceContext>'s containing <xref:System.ServiceModel.ServiceHostBase>.</span></span> <span data-ttu-id="29410-134">이 클래스의 확장을 사용하여 <xref:System.ServiceModel.InstanceContext>의 동작을 확장하거나 각 서비스의 상태를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29410-134">Extensions of this class can be used to extend the behavior of the <xref:System.ServiceModel.InstanceContext> or to store the state for each service.</span></span>  
  
-   <span data-ttu-id="29410-135"><xref:System.ServiceModel.OperationContext> – 이 클래스는 런타임에서 각 작업에 대해 수집하는 작업 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="29410-135"><xref:System.ServiceModel.OperationContext> – This class represents the operation information that the runtime gathers for each operation.</span></span>  <span data-ttu-id="29410-136">여기에는 들어오는 메시지 헤더, 들어오는 메시지 속성, 들어오는 보안 ID, 기타 정보 등이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="29410-136">This includes information such as the incoming message headers, the incoming message properties, the incoming security identity, and other information.</span></span>  <span data-ttu-id="29410-137">이 클래스의 확장은 <xref:System.ServiceModel.OperationContext>의 동작을 확장하거나 각 작업의 상태를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29410-137">Extensions of this class can either extend the behavior of <xref:System.ServiceModel.OperationContext> or store the state for each operation.</span></span>  
  
-   <span data-ttu-id="29410-138"><xref:System.ServiceModel.IContextChannel> – 이 인터페이스를 사용하면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 런타임에 의해 작성된 채널 및 프록시에서 각 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29410-138"><xref:System.ServiceModel.IContextChannel> – This interface allows for the inspection of each state for the channels and proxies built by the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] runtime.</span></span>  <span data-ttu-id="29410-139">이 클래스의 확장은 <xref:System.ServiceModel.IClientChannel>의 동작을 확장하거나 이 동작을 사용하여 각 채널의 상태를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29410-139">Extensions of this class can either extend the behavior of <xref:System.ServiceModel.IClientChannel> or can use it to store the state for each channel.</span></span>  
  
-  
  
 <span data-ttu-id="29410-140">다음 코드 예제에서는 단순한 확장을 사용하여 <xref:System.ServiceModel.InstanceContext> 개체를 추적하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="29410-140">The following code example shows the use of a simple extension to track <xref:System.ServiceModel.InstanceContext> objects.</span></span>  
  
 [!code-csharp[IInstanceContextInitializer#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/iinstancecontextinitializer/cs/initializer.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="29410-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="29410-141">See Also</span></span>  
 <xref:System.ServiceModel.IExtensibleObject%601>  
 <xref:System.ServiceModel.IExtension%601>  
 <xref:System.ServiceModel.IExtensionCollection%601>
