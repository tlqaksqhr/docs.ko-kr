---
title: 관리되지 않는 리소스 정리
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Close method
- Dispose method
- garbage collector
- garbage collection, unmanaged resources
- cleanup operations
- explicit cleanups
- unmanaged resource cleanup
- Finalize method
ms.assetid: a17b0066-71c2-4ba4-9822-8e19332fc213
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e32d2d4424d05b95af1eda400974da3293b8499
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575936"
---
# <a name="cleaning-up-unmanaged-resources"></a><span data-ttu-id="671ba-102">관리되지 않는 리소스 정리</span><span class="sxs-lookup"><span data-stu-id="671ba-102">Cleaning Up Unmanaged Resources</span></span>
<span data-ttu-id="671ba-103">사용자 앱에서 만드는 대부분의 개체에 대해 .NET의 가비지 수집기를 사용하여 메모리 관리를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-103">For the majority of the objects that your app creates, you can rely on .NET's garbage collector to handle memory management.</span></span> <span data-ttu-id="671ba-104">그러나 관리되지 않는 리소스를 포함하는 개체를 만든 경우에는 응용 프로그램에서 해당 개체의 사용을 마치면 이러한 리소스를 명시적으로 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-104">However, when you create objects that include unmanaged resources, you must explicitly release those resources when you finish using them in your app.</span></span> <span data-ttu-id="671ba-105">가장 일반적인 형태의 관리되지 않는 리소스로는 파일, 창, 네트워크 연결 또는 데이터베이스 연결 등의 운영 체제 리소스를 래핑하는 개체를 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-105">The most common types of unmanaged resource are objects that wrap operating system resources, such as files, windows, network connections, or database connections.</span></span> <span data-ttu-id="671ba-106">가비지 수집기에서는 관리되지 않는 리소스를 캡슐화하는 개체의 수명을 추적할 수 있지만, 관리되지 않는 리소스를 해제하고 정리하는 방법에 대해서는 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-106">Although the garbage collector is able to track the lifetime of an object that encapsulates an unmanaged resource, it doesn't know how to release and clean up the unmanaged resource.</span></span>  
  
 <span data-ttu-id="671ba-107">형식이 관리되지 않는 리소스를 사용하는 경우 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-107">If your types use unmanaged resources, you should do the following:</span></span>  
  
-   <span data-ttu-id="671ba-108">[삭제 패턴](../../../docs/standard/design-guidelines/dispose-pattern.md)을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-108">Implement the [dispose pattern](../../../docs/standard/design-guidelines/dispose-pattern.md).</span></span> <span data-ttu-id="671ba-109">이를 수행하려면 관리되지 않는 리소스의 명확한 해제를 활성화하기 위해 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> 구현을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-109">This requires that you provide an <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation to enable the deterministic release of  unmanaged resources.</span></span> <span data-ttu-id="671ba-110">개체 및 해당 개체에서 사용하는 리소스가 더 이상 필요하지 않은 경우 형식의 소비자가 <xref:System.IDisposable.Dispose%2A>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-110">A consumer of your type calls <xref:System.IDisposable.Dispose%2A> when the object (and the resources it uses) is no longer needed.</span></span> <span data-ttu-id="671ba-111"><xref:System.IDisposable.Dispose%2A> 메서드가 관리되지 않는 리소스를 즉시 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-111">The <xref:System.IDisposable.Dispose%2A> method immediately releases the unmanaged resources.</span></span>  
  
-   <span data-ttu-id="671ba-112">형식의 소비자가 실수로 <xref:System.IDisposable.Dispose%2A>를 호출하지 않은 경우 해제되는 관리되지 않는 리소스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-112">Provide for your unmanaged resources to be released in the event that a consumer of your type forgets to call <xref:System.IDisposable.Dispose%2A>.</span></span> <span data-ttu-id="671ba-113">여기에는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-113">There are two ways to do this:</span></span>  
  
    -   <span data-ttu-id="671ba-114">SafeHandle을 사용하여 관리되지 않는 리소스를 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-114">Use a safe handle to wrap your unmanaged resource.</span></span> <span data-ttu-id="671ba-115">이것이 권장되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-115">This is the recommended technique.</span></span> <span data-ttu-id="671ba-116">SafeHandle은 <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> 클래스에서 파생되며, 강력한 <xref:System.Object.Finalize%2A> 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-116">Safe handles are derived from the <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> class and include a robust <xref:System.Object.Finalize%2A> method.</span></span> <span data-ttu-id="671ba-117">SafeHandle을 사용하면 <xref:System.IDisposable> 인터페이스를 간단하게 구현하고 <xref:System.Runtime.InteropServices.SafeHandle.Dispose%2A> 구현에서 SafeHandle의 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-117">When you use a safe handle, you simply implement the <xref:System.IDisposable> interface and call your safe handle's <xref:System.Runtime.InteropServices.SafeHandle.Dispose%2A> method in your <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="671ba-118"><xref:System.IDisposable.Dispose%2A> 메서드가 호출되지 않는 경우 가비지 수집기에 의해 SafeHandle의 종료자가 자동으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-118">The safe handle's finalizer is called automatically by the garbage collector if its <xref:System.IDisposable.Dispose%2A> method is not called.</span></span>  
  
         <span data-ttu-id="671ba-119">또는</span><span class="sxs-lookup"><span data-stu-id="671ba-119">—or—</span></span>  
  
    -   <span data-ttu-id="671ba-120"><xref:System.Object.Finalize%2A?displayProperty=nameWithType> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-120">Override the <xref:System.Object.Finalize%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="671ba-121">종료를 사용하면 형식의 소비자가 명확하게 삭제할 수 있도록 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>를 호출하지 못한 경우 관리되지 않는 리소스가 명확하지 않게 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-121">Finalization enables the non-deterministic release of unmanaged resources when the consumer of a type fails to call <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> to dispose of them deterministically.</span></span> <span data-ttu-id="671ba-122">그러나 개체 종료가 복잡하고 오류가 발생하기 쉬운 작업일 수 있기 때문에 고유한 종료자를 제공하는 대신 SafeHandle을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-122">However, because object finalization can be a complex and error-prone operation, we recommend that you use a safe handle instead of providing your own finalizer.</span></span>  
  
 <span data-ttu-id="671ba-123">그러면 형식의 소비자가 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> 구현을 직접 호출하여 관리되지 않는 리소스가 사용하는 메모리를 확보할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-123">Consumers of your type can then call your <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation directly to free memory used by unmanaged resources.</span></span> <span data-ttu-id="671ba-124"><xref:System.IDisposable.Dispose%2A> 메서드를 제대로 구현하면 SafeHandle의 <xref:System.Object.Finalize%2A> 메서드 또는 <xref:System.Object.Finalize%2A?displayProperty=nameWithType> 메서드의 고유한 재정의가 <xref:System.IDisposable.Dispose%2A> 메서드가 호출되지 않는 경우 리소스를 정리하는 보호 기능이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-124">When you properly implement a <xref:System.IDisposable.Dispose%2A> method, either your safe handle's <xref:System.Object.Finalize%2A> method or your own override of the <xref:System.Object.Finalize%2A?displayProperty=nameWithType> method becomes a safeguard to clean up resources in the event that the <xref:System.IDisposable.Dispose%2A> method is not called.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="671ba-125">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="671ba-125">In This Section</span></span>  
 [<span data-ttu-id="671ba-126">Dispose 메서드 구현</span><span class="sxs-lookup"><span data-stu-id="671ba-126">Implementing a Dispose Method</span></span>](../../../docs/standard/garbage-collection/implementing-dispose.md)  
 <span data-ttu-id="671ba-127">관리되지 않는 리소스를 해제하기 위해 [삭제 패턴](../../../docs/standard/design-guidelines/dispose-pattern.md)을 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-127">Describes how to implement the [dispose pattern](../../../docs/standard/design-guidelines/dispose-pattern.md) for releasing unmanaged resources.</span></span>  
  
 [<span data-ttu-id="671ba-128">IDisposable을 구현하는 개체 사용</span><span class="sxs-lookup"><span data-stu-id="671ba-128">Using Objects That Implement IDisposable</span></span>](../../../docs/standard/garbage-collection/using-objects.md)  
 <span data-ttu-id="671ba-129">형식의 소비자가 <xref:System.IDisposable.Dispose%2A> 구현이 호출되었는지 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-129">Describes how consumers of a type ensure that its <xref:System.IDisposable.Dispose%2A> implementation is called.</span></span> <span data-ttu-id="671ba-130">이를 수행하는 경우 C# `using` 문 또는 Visual Basic `Using` 문을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-130">We recommend using the C# `using` statement or the Visual Basic `Using` statement to do this.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="671ba-131">참조</span><span class="sxs-lookup"><span data-stu-id="671ba-131">Reference</span></span>  
 <xref:System.IDisposable?displayProperty=nameWithType>  
 <span data-ttu-id="671ba-132">관리되지 않은 리소스 해제를 위한 <xref:System.IDisposable.Dispose%2A> 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-132">Defines the <xref:System.IDisposable.Dispose%2A> method for releasing unmanaged resources.</span></span>  
  
 <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
 <span data-ttu-id="671ba-133">관리되지 않는 리소스가 <xref:System.IDisposable.Dispose%2A> 메서드에 의해 해제되지 않은 경우 개체 종료 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-133">Provides for object finalization if unmanaged resources are not released by the <xref:System.IDisposable.Dispose%2A> method.</span></span>  
  
 <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>  
 <span data-ttu-id="671ba-134">종료를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-134">Suppresses finalization.</span></span> <span data-ttu-id="671ba-135">이 메서드는 종료자가 실행되지 않도록 방지하기 위해 통상 `Dispose` 메서드에서 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="671ba-135">This method is customarily called from a `Dispose` method to prevent a finalizer from executing.</span></span>
