---
title: Dispose 메서드 구현
ms.date: 04/07/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- garbage collection, Dispose method
ms.assetid: eb4e1af0-3b48-4fbc-ad4e-fc2f64138bf9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acc661e8110892dc7daa603ef82b4bc5f167a970
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33579446"
---
# <a name="implementing-a-dispose-method"></a><span data-ttu-id="46746-102">Dispose 메서드 구현</span><span class="sxs-lookup"><span data-stu-id="46746-102">Implementing a Dispose method</span></span>

<span data-ttu-id="46746-103">응용 프로그램에서 사용되는 관리되지 않는 리소스를 해제하려면 <xref:System.IDisposable.Dispose%2A> 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="46746-103">You implement a <xref:System.IDisposable.Dispose%2A> method to release unmanaged resources used by your application.</span></span> <span data-ttu-id="46746-104">.NET 가비지 수집기는 관리되지 않는 메모리를 할당하거나 해제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46746-104">The .NET garbage collector does not allocate or release unmanaged memory.</span></span>  
  
<span data-ttu-id="46746-105">[삭제 패턴](../../../docs/standard/design-guidelines/dispose-pattern.md)이라고도 하는 개체 삭제 패턴에서는 개체의 수명에 순서를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="46746-105">The pattern for disposing an object, referred to as a [dispose pattern](../../../docs/standard/design-guidelines/dispose-pattern.md), imposes order on the lifetime of an object.</span></span> <span data-ttu-id="46746-106">삭제 패턴은 파일 핸들, 파이프 핸들, 레지스트리 핸들, 대기 핸들 또는 관리되지 않는 메모리의 블록에 대한 포인터와 같이 관리되지 않는 리소스에 액세스하는 개체에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="46746-106">The dispose pattern is used only for objects that access unmanaged resources, such as file and pipe handles, registry handles, wait handles, or pointers to blocks of unmanaged memory.</span></span> <span data-ttu-id="46746-107">이는 가비지 수집기가 사용되지 않은 관리되는 개체를 회수하는 데 매우 효율적이지만, 관리되지 않는 개체는 회수할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="46746-107">This is because the garbage collector is very efficient at reclaiming unused managed objects, but it is unable to reclaim unmanaged objects.</span></span>  
  
<span data-ttu-id="46746-108">삭제 패턴에는 두 가지 변형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46746-108">The dispose pattern has two variations:</span></span>  
  
* <span data-ttu-id="46746-109">형식이 SafeHandle(즉, <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>에서 파생된 클래스)에서 사용하는 관리되지 않는 리소스를 각각 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="46746-109">You wrap each unmanaged resource that a type uses in a safe handle (that is, in a class derived from <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>).</span></span> <span data-ttu-id="46746-110">이 경우 <xref:System.IDisposable> 인터페이스와 추가 `Dispose(Boolean)` 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="46746-110">In this case, you implement the <xref:System.IDisposable> interface and an additional `Dispose(Boolean)` method.</span></span> <span data-ttu-id="46746-111">이는 권장되는 변형이며, <xref:System.Object.Finalize%2A?displayProperty=nameWithType> 메서드를 재정의할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46746-111">This is the recommended variation and doesn't require overriding the <xref:System.Object.Finalize%2A?displayProperty=nameWithType> method.</span></span>  
  
  > [!NOTE]
  > <span data-ttu-id="46746-112"><xref:Microsoft.Win32.SafeHandles?displayProperty=nameWithType> 네임스페이스는 <xref:System.Runtime.InteropServices.SafeHandle>에서 파생된 클래스 집합을 제공합니다(이러한 클래스는 [SafeHandle 사용](#SafeHandles) 섹션에 나열되어 있음).</span><span class="sxs-lookup"><span data-stu-id="46746-112">The <xref:Microsoft.Win32.SafeHandles?displayProperty=nameWithType> namespace provides a set of classes derived from <xref:System.Runtime.InteropServices.SafeHandle>, which are listed in the [Using safe handles](#SafeHandles) section.</span></span> <span data-ttu-id="46746-113">관리되지 않는 리소스를 해제하는 데 적합한 클래스를 찾을 수 없는 경우 고유한 <xref:System.Runtime.InteropServices.SafeHandle> 서브클래스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46746-113">If you can't find a class that is suitable for releasing your unmanaged resource, you can implement your own subclass of <xref:System.Runtime.InteropServices.SafeHandle>.</span></span>  
  
* <span data-ttu-id="46746-114"><xref:System.IDisposable> 인터페이스와 추가 `Dispose(Boolean)` 메서드를 구현하고 <xref:System.Object.Finalize%2A?displayProperty=nameWithType> 메서드도 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="46746-114">You implement the <xref:System.IDisposable> interface and an additional `Dispose(Boolean)` method, and you also override the <xref:System.Object.Finalize%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="46746-115">형식의 소비자가 <xref:System.Object.Finalize%2A> 구현을 호출하지 않은 경우 관리되지 않는 리소스가 삭제되도록 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>를 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46746-115">You must override <xref:System.Object.Finalize%2A> to ensure that unmanaged resources are disposed of if your <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation is not called by a consumer of your type.</span></span> <span data-ttu-id="46746-116">이전 글머리 기호에 설명된 권장 방법을 사용하는 경우 <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> 클래스가 사용자 대신 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="46746-116">If you use the recommended technique discussed in the previous bullet, the <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> class does this on your behalf.</span></span>  
  
<span data-ttu-id="46746-117">리소스가 항상 적절하게 정리되게 하려면 예외를 throw하지 않고 <xref:System.IDisposable.Dispose%2A> 메서드를 여러 번 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46746-117">To help ensure that resources are always cleaned up appropriately, a <xref:System.IDisposable.Dispose%2A> method should be callable multiple times without throwing an exception.</span></span>  
  
<span data-ttu-id="46746-118"><xref:System.GC.KeepAlive%2A?displayProperty=nameWithType> 메서드의 코드 예제에서는 적극적인 가비지 수집으로 인해, 회수된 개체의 멤버가 아직 실행되는 동안 종료자가 실행되게 할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="46746-118">The code example provided for the <xref:System.GC.KeepAlive%2A?displayProperty=nameWithType> method shows how aggressive garbage collection can cause a finalizer to run while a member of the reclaimed object is still executing.</span></span> <span data-ttu-id="46746-119"><xref:System.GC.KeepAlive%2A> 메서드를 오래 실행한 후에는 <xref:System.IDisposable.Dispose%2A> 메서드를 호출하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="46746-119">It is a good idea to call the <xref:System.GC.KeepAlive%2A> method at the end of a lengthy <xref:System.IDisposable.Dispose%2A> method.</span></span>  
  
<a name="Dispose2"></a>
## <a name="dispose-and-disposeboolean"></a><span data-ttu-id="46746-120">Dispose() 및 Dispose(Boolean)</span><span class="sxs-lookup"><span data-stu-id="46746-120">Dispose() and Dispose(Boolean)</span></span>  

<span data-ttu-id="46746-121"><xref:System.IDisposable> 인터페이스에서는 매개 변수가 없는 단일 메서드인 <xref:System.IDisposable.Dispose%2A>를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46746-121">The <xref:System.IDisposable> interface requires the implementation of a single parameterless method, <xref:System.IDisposable.Dispose%2A>.</span></span> <span data-ttu-id="46746-122">그러나 삭제 패턴을 사용하려면 다음과 같은 두 가지 `Dispose` 메서드를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46746-122">However, the dispose pattern requires two `Dispose` methods to be implemented:</span></span>  
  
* <span data-ttu-id="46746-123">매개 변수가 없는 공용 비가상(Visual Basic의 `NonInheritable`) <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> 구현</span><span class="sxs-lookup"><span data-stu-id="46746-123">A public non-virtual (`NonInheritable` in Visual Basic) <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation that has no parameters.</span></span>  
  
* <span data-ttu-id="46746-124">시그니처가 다음과 같은 보호된 가상(Visual Basic의 `Overridable`) `Dispose` 메서드:</span><span class="sxs-lookup"><span data-stu-id="46746-124">A protected virtual (`Overridable` in Visual Basic) `Dispose` method whose signature is:</span></span>  
  
  [!code-csharp[Conceptual.Disposable#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/dispose1.cs#8)]
  [!code-vb[Conceptual.Disposable#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/dispose1.vb#8)]  
  
### <a name="the-dispose-overload"></a><span data-ttu-id="46746-125">Dispose() 오버로드</span><span class="sxs-lookup"><span data-stu-id="46746-125">The Dispose() overload</span></span>

<span data-ttu-id="46746-126">공용, 비가상(Visual Basic의 경우 `NonInheritable`), 매개 변수가 없는 `Dispose` 메서드는 형식의 소비자에 의해 호출되므로, 관리되지 않는 리소스를 해제하고 종료자(있는 경우)를 실행할 필요가 없음을 나타내기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="46746-126">Because the public, non-virtual (`NonInheritable` in Visual Basic), parameterless `Dispose` method is called by a consumer of the type, its purpose is to free unmanaged resources and to indicate that the finalizer, if one is present, doesn't have to run.</span></span> <span data-ttu-id="46746-127">이로 인해 다음과 같은 표준 구현이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="46746-127">Because of this, it has a standard implementation:</span></span>  
  
[!code-csharp[Conceptual.Disposable#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/dispose1.cs#7)]
[!code-vb[Conceptual.Disposable#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/dispose1.vb#7)]  
  
<span data-ttu-id="46746-128">`Dispose` 메서드가 모든 개체를 정리하므로, 가비지 수집기가 더 이상 개체의 <xref:System.Object.Finalize%2A?displayProperty=nameWithType> 재정의를 호출할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46746-128">The `Dispose` method performs all object cleanup, so the garbage collector no longer needs to call the objects' <xref:System.Object.Finalize%2A?displayProperty=nameWithType> override.</span></span> <span data-ttu-id="46746-129">따라서 <xref:System.GC.SuppressFinalize%2A> 메서드를 호출하면 가비지 수집기가 종료자를 실행하지 않도록 방지됩니다.</span><span class="sxs-lookup"><span data-stu-id="46746-129">Therefore, the call to the <xref:System.GC.SuppressFinalize%2A> method prevents the garbage collector from running the finalizer.</span></span> <span data-ttu-id="46746-130">형식에 종료자가 없는 경우 <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>에 대한 호출이 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46746-130">If the type has no finalizer, the call to <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> has no effect.</span></span> <span data-ttu-id="46746-131">`Dispose` 메서드의 두 번째 오버로드에서 실제로 관리되지 않는 리소스를 해제하는 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="46746-131">Note that the actual work of releasing unmanaged resources is performed by the second overload of the `Dispose` method.</span></span>  
  
### <a name="the-disposeboolean-overload"></a><span data-ttu-id="46746-132">Dispose(Boolean) 오버로드</span><span class="sxs-lookup"><span data-stu-id="46746-132">The Dispose(Boolean) overload</span></span>

<span data-ttu-id="46746-133">두 번째 오버로드에서 *disposing* 매개 변수는 메서드 호출이 <xref:System.IDisposable.Dispose%2A> 메서드(값은 `true`)에서 수행되는지 또는 종료자(값은 `false`)에서 수행되는지를 나타내는 <xref:System.Boolean>입니다.</span><span class="sxs-lookup"><span data-stu-id="46746-133">In the second overload, the *disposing* parameter is a <xref:System.Boolean> that indicates whether the method call comes from a <xref:System.IDisposable.Dispose%2A> method (its value is `true`) or from a finalizer (its value is `false`).</span></span>  
  
<span data-ttu-id="46746-134">메서드 본문은 다음과 같은 두 가지 코드 블록으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="46746-134">The body of the method consists of two blocks of code:</span></span>  
  
* <span data-ttu-id="46746-135">관리되지 않는 리소스를 해제하는 블록.</span><span class="sxs-lookup"><span data-stu-id="46746-135">A block that frees unmanaged resources.</span></span> <span data-ttu-id="46746-136">이 블록은 `disposing` 매개 변수의 값에 관계없이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="46746-136">This block executes regardless of the value of the `disposing` parameter.</span></span>  
  
* <span data-ttu-id="46746-137">관리되는 리소스를 해제하는 조건부 블록.</span><span class="sxs-lookup"><span data-stu-id="46746-137">A conditional block that frees managed resources.</span></span> <span data-ttu-id="46746-138">이 블록은 `disposing` 값이 `true`인 경우 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="46746-138">This block executes if the value of `disposing` is `true`.</span></span> <span data-ttu-id="46746-139">해제되는 관리되는 리소스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="46746-139">The managed resources that it frees can include:</span></span>  
  
  <span data-ttu-id="46746-140">**<xref:System.IDisposable>을 구현하는 관리되는 개체.**</span><span class="sxs-lookup"><span data-stu-id="46746-140">**Managed objects that implement <xref:System.IDisposable>.**</span></span> <span data-ttu-id="46746-141">조건부 블록을 사용하여 <xref:System.IDisposable.Dispose%2A> 구현을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46746-141">The conditional block can be used to call their <xref:System.IDisposable.Dispose%2A> implementation.</span></span> <span data-ttu-id="46746-142">관리되지 않는 리소스를 래핑하기 위해 SafeHandle을 사용한 경우 여기에서 <xref:System.Runtime.InteropServices.SafeHandle.Dispose%28System.Boolean%29?displayProperty=nameWithType> 구현을 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46746-142">If you have used a safe handle to wrap your unmanaged resource, you should call the <xref:System.Runtime.InteropServices.SafeHandle.Dispose%28System.Boolean%29?displayProperty=nameWithType> implementation here.</span></span>  
  
  <span data-ttu-id="46746-143">**많은 메모리를 사용하거나 부족한 리소스를 사용하는 관리되는 개체.**</span><span class="sxs-lookup"><span data-stu-id="46746-143">**Managed objects that consume large amounts of memory or consume scarce resources.**</span></span> <span data-ttu-id="46746-144">이러한 개체를 `Dispose` 메서드에서 명시적으로 해제하면 가비지 수집기에서 명확하지 않게 회수한 경우보다 빠르게 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46746-144">Freeing these objects explicitly in the `Dispose` method releases them faster than if they were reclaimed non-deterministically by the garbage collector.</span></span>  
  
<span data-ttu-id="46746-145">메서드 호출이 종료자에서 나오는 경우, 즉 *disposing*이 `false`인 경우 관리되지 않는 리소스를 해제하는 코드만 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="46746-145">If the method call comes from a finalizer (that is, if *disposing* is `false`), only the code that frees unmanaged resources executes.</span></span> <span data-ttu-id="46746-146">종료하는 동안 가비지 수집기가 관리되는 개체를 제거하는 순서가 정의되어 있지 않기 때문에 `Dispose` 값으로 이 `false` 오버로드를 호출하면 종료자가 이미 회수된 관리되는 리소스를 해제하려고 시도하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="46746-146">Because the order in which the garbage collector destroys managed objects during finalization is not defined, calling this `Dispose` overload with a value of `false` prevents the finalizer from trying to release managed resources that may have already been reclaimed.</span></span>  
  
## <a name="implementing-the-dispose-pattern-for-a-base-class"></a><span data-ttu-id="46746-147">기본 클래스에 대한 삭제 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="46746-147">Implementing the dispose pattern for a base class</span></span>

<span data-ttu-id="46746-148">기본 클래스에 대한 삭제 패턴을 구현하는 경우 다음을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46746-148">If you implement the dispose pattern for a base class, you must provide the following:</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="46746-149"><xref:System.IDisposable.Dispose>을 구현하고 `sealed`(Visual Basic의 경우 `NotInheritable`)가 아닌 모든 기본 클래스에 대해 이 패턴을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46746-149">You should implement this pattern for all base classes that implement <xref:System.IDisposable.Dispose> and are not `sealed` (`NotInheritable` in Visual Basic).</span></span>  
  
* <span data-ttu-id="46746-150"><xref:System.IDisposable.Dispose%2A> 메서드를 호출하는 `Dispose(Boolean)` 구현</span><span class="sxs-lookup"><span data-stu-id="46746-150">A <xref:System.IDisposable.Dispose%2A> implementation that calls the `Dispose(Boolean)` method.</span></span>  
  
* <span data-ttu-id="46746-151">실제로 리소스를 해제하는 작업을 수행하는 `Dispose(Boolean)` 메서드</span><span class="sxs-lookup"><span data-stu-id="46746-151">A `Dispose(Boolean)` method that performs the actual work of releasing resources.</span></span>  
  
* <span data-ttu-id="46746-152">관리되지 않는 리소스를 래핑하는 <xref:System.Runtime.InteropServices.SafeHandle>에서 파생된 클래스(권장) 또는 <xref:System.Object.Finalize%2A?displayProperty=nameWithType> 메서드 재정의</span><span class="sxs-lookup"><span data-stu-id="46746-152">Either a class derived from <xref:System.Runtime.InteropServices.SafeHandle> that wraps your unmanaged resource (recommended), or an override to the <xref:System.Object.Finalize%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="46746-153"><xref:System.Runtime.InteropServices.SafeHandle> 클래스는 사용자가 코딩할 필요가 없는 종료자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="46746-153">The <xref:System.Runtime.InteropServices.SafeHandle> class provides a finalizer that frees you from having to code one.</span></span>  
  
<span data-ttu-id="46746-154">SafeHandle을 사용하는 기본 클래스에 대한 삭제 패턴을 구현하는 일반적인 패턴은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="46746-154">Here's the general pattern for implementing the dispose pattern for a base class that uses a safe handle.</span></span>  
  
[!code-csharp[System.IDisposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/base1.cs#3)]
[!code-vb[System.IDisposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/base1.vb#3)]  
  
> [!NOTE]
> <span data-ttu-id="46746-155">이전 예제에서는 <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> 개체를 사용하여 패턴을 보여 줍니다. <xref:System.Runtime.InteropServices.SafeHandle>에서 파생된 개체를 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46746-155">The previous example uses a <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> object to illustrate the pattern; any object derived from <xref:System.Runtime.InteropServices.SafeHandle> could be used instead.</span></span> <span data-ttu-id="46746-156">예제에서는 해당 <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> 개체를 제대로 인스턴스화하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46746-156">Note that the example does not properly instantiate its <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> object.</span></span>  
  
<span data-ttu-id="46746-157"><xref:System.Object.Finalize%2A?displayProperty=nameWithType>를 재정의하는 기본 클래스에 대한 삭제 패턴을 구현하는 일반적인 패턴은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="46746-157">Here's the general pattern for implementing the dispose pattern for a base class that overrides <xref:System.Object.Finalize%2A?displayProperty=nameWithType>.</span></span>  
  
[!code-csharp[System.IDisposable#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/base2.cs#5)]
[!code-vb[System.IDisposable#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/base2.vb#5)]  
  
> [!NOTE]
> <span data-ttu-id="46746-158">C#에서 [소멸자](~/docs/csharp/programming-guide/classes-and-structs/destructors.md)를 정의하여 <xref:System.Object.Finalize%2A?displayProperty=nameWithType>를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="46746-158">In C#, you override <xref:System.Object.Finalize%2A?displayProperty=nameWithType> by defining a [destructor](~/docs/csharp/programming-guide/classes-and-structs/destructors.md).</span></span>  
  
## <a name="implementing-the-dispose-pattern-for-a-derived-class"></a><span data-ttu-id="46746-159">파생된 클래스에 대한 삭제 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="46746-159">Implementing the dispose pattern for a derived class</span></span>

<span data-ttu-id="46746-160"><xref:System.IDisposable>의 기본 클래스 구현은 파생된 클래스에 의해 상속되므로 <xref:System.IDisposable> 인터페이스를 구현하는 클래스에서 파생된 클래스가 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>을 구현하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46746-160">A class derived from a class that implements the <xref:System.IDisposable> interface shouldn't implement <xref:System.IDisposable>, because the base class implementation of <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> is inherited by its derived classes.</span></span> <span data-ttu-id="46746-161">대신 파생된 클래스에 대한 삭제 패턴을 구현하려면 다음을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="46746-161">Instead, to implement the dispose pattern for a derived class, you provide the following:</span></span>  
  
* <span data-ttu-id="46746-162">기본 클래스 메서드를 재정의하고 파생된 클래스의 리소스를 해제하는 실제 작업을 수행하는 `protected Dispose(Boolean)` 메서드.</span><span class="sxs-lookup"><span data-stu-id="46746-162">A `protected Dispose(Boolean)` method that overrides the base class method and performs the actual work of releasing the resources of the derived class.</span></span> <span data-ttu-id="46746-163">이 메서드도 기본 클래스의 `Dispose(Boolean)` 메서드를 호출하여 *disposing* 인수의 `true` 값을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="46746-163">This method should also call the `Dispose(Boolean)` method of the base class and pass it a value of `true` for the *disposing* argument.</span></span>  
  
* <span data-ttu-id="46746-164">관리되지 않는 리소스를 래핑하는 <xref:System.Runtime.InteropServices.SafeHandle>에서 파생된 클래스(권장) 또는 <xref:System.Object.Finalize%2A?displayProperty=nameWithType> 메서드 재정의</span><span class="sxs-lookup"><span data-stu-id="46746-164">Either a class derived from <xref:System.Runtime.InteropServices.SafeHandle> that wraps your unmanaged resource (recommended), or an override to the <xref:System.Object.Finalize%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="46746-165"><xref:System.Runtime.InteropServices.SafeHandle> 클래스는 사용자가 코딩할 필요가 없는 종료자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="46746-165">The <xref:System.Runtime.InteropServices.SafeHandle> class provides a finalizer that frees you from having to code one.</span></span> <span data-ttu-id="46746-166">종료자를 제공하는 경우 *disposing* 인수가 `false`인 `Dispose(Boolean)` 오버로드를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46746-166">If you do provide a finalizer, it should call the `Dispose(Boolean)` overload with a *disposing* argument of `false`.</span></span>  
  
<span data-ttu-id="46746-167">SafeHandle을 사용하는 파생된 클래스에 대한 삭제 패턴을 구현하는 일반적인 패턴은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="46746-167">Here's the general pattern for implementing the dispose pattern for a derived class that uses a safe handle:</span></span>  
  
[!code-csharp[System.IDisposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/derived1.cs#4)]
[!code-vb[System.IDisposable#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/derived1.vb#4)]  
  
> [!NOTE]
> <span data-ttu-id="46746-168">이전 예제에서는 <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> 개체를 사용하여 패턴을 보여 줍니다. <xref:System.Runtime.InteropServices.SafeHandle>에서 파생된 개체를 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46746-168">The previous example uses a <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> object to illustrate the pattern; any object derived from <xref:System.Runtime.InteropServices.SafeHandle> could be used instead.</span></span> <span data-ttu-id="46746-169">예제에서는 해당 <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> 개체를 제대로 인스턴스화하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46746-169">Note that the example does not properly instantiate its <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> object.</span></span>  
  
<span data-ttu-id="46746-170"><xref:System.Object.Finalize%2A?displayProperty=nameWithType>를 재정의하는 파생된 클래스에 대한 삭제 패턴을 구현하는 일반적인 패턴은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="46746-170">Here's the general pattern for implementing the dispose pattern for a derived class that overrides <xref:System.Object.Finalize%2A?displayProperty=nameWithType>:</span></span>  
  
[!code-csharp[System.IDisposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/derived2.cs#6)]
[!code-vb[System.IDisposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/derived2.vb#6)]  
  
> [!NOTE]
> <span data-ttu-id="46746-171">C#에서 [소멸자](~/docs/csharp/programming-guide/classes-and-structs/destructors.md)를 정의하여 <xref:System.Object.Finalize%2A?displayProperty=nameWithType>를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="46746-171">In C#, you override <xref:System.Object.Finalize%2A?displayProperty=nameWithType> by defining a [destructor](~/docs/csharp/programming-guide/classes-and-structs/destructors.md).</span></span>  
  
<a name="SafeHandles"></a>   
## <a name="using-safe-handles"></a><span data-ttu-id="46746-172">SafeHandle 사용</span><span class="sxs-lookup"><span data-stu-id="46746-172">Using safe handles</span></span>

<span data-ttu-id="46746-173">개체 종료자에 대한 코드를 작성하는 작업은 올바르게 수행되지 않을 경우 문제를 일으킬 수 있는 복잡한 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="46746-173">Writing code for an object's finalizer is a complex task that can cause problems if not done correctly.</span></span> <span data-ttu-id="46746-174">따라서 종료자를 구현하는 대신 <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> 개체를 생성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="46746-174">Therefore, we recommend that you construct <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> objects instead of implementing a finalizer.</span></span>  
  
<span data-ttu-id="46746-175"><xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> 클래스에서 파생된 클래스는 중단 없이 핸들을 할당 및 해제하여 개체 수명 문제를 단순화합니다.</span><span class="sxs-lookup"><span data-stu-id="46746-175">Classes derived from the <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> class simplify object lifetime issues by assigning and releasing handles without interruption.</span></span> <span data-ttu-id="46746-176">여기에는 응용 프로그램 도메인을 언로드하는 동안 실행이 보장되는 중요한 종료자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="46746-176">They contain a critical finalizer that is guaranteed to run while an application domain is unloading.</span></span> <span data-ttu-id="46746-177">SafeHandle을 사용하는 이점에 대한 자세한 내용은 <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="46746-177">For more information about the advantages of using a safe handle, see <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>.</span></span> <span data-ttu-id="46746-178"><xref:Microsoft.Win32.SafeHandles> 네임스페이스에서 다음과 같은 파생된 클래스가 SafeHandle을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="46746-178">The following derived classes in the <xref:Microsoft.Win32.SafeHandles> namespace provide safe handles:</span></span>  
  
* <span data-ttu-id="46746-179">파일, 메모리 매핑된 파일 및 파이프에 대한 <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>, <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedFileHandle> 및 <xref:Microsoft.Win32.SafeHandles.SafePipeHandle> 클래스</span><span class="sxs-lookup"><span data-stu-id="46746-179">The <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>, <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedFileHandle>, and <xref:Microsoft.Win32.SafeHandles.SafePipeHandle> class, for files, memory mapped files, and pipes.</span></span>  
  
* <span data-ttu-id="46746-180">메모리 뷰에 대한 <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> 클래스</span><span class="sxs-lookup"><span data-stu-id="46746-180">The <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> class, for memory views.</span></span>  
  
* <span data-ttu-id="46746-181">암호화 구문에 대한 <xref:Microsoft.Win32.SafeHandles.SafeNCryptKeyHandle>, <xref:Microsoft.Win32.SafeHandles.SafeNCryptProviderHandle> 및 <xref:Microsoft.Win32.SafeHandles.SafeNCryptSecretHandle> 클래스</span><span class="sxs-lookup"><span data-stu-id="46746-181">The <xref:Microsoft.Win32.SafeHandles.SafeNCryptKeyHandle>, <xref:Microsoft.Win32.SafeHandles.SafeNCryptProviderHandle>, and <xref:Microsoft.Win32.SafeHandles.SafeNCryptSecretHandle> classes, for cryptography constructs.</span></span>  
  
* <span data-ttu-id="46746-182">레지스트리 키에 대한 <xref:Microsoft.Win32.SafeHandles.SafeRegistryHandle> 클래스</span><span class="sxs-lookup"><span data-stu-id="46746-182">The <xref:Microsoft.Win32.SafeHandles.SafeRegistryHandle> class, for registry keys.</span></span>  
  
* <span data-ttu-id="46746-183">대기 핸들에 대한 <xref:Microsoft.Win32.SafeHandles.SafeWaitHandle> 클래스</span><span class="sxs-lookup"><span data-stu-id="46746-183">The <xref:Microsoft.Win32.SafeHandles.SafeWaitHandle> class, for wait handles.</span></span>  
  
<a name="base"></a>   
## <a name="using-a-safe-handle-to-implement-the-dispose-pattern-for-a-base-class"></a><span data-ttu-id="46746-184">SafeHandle을 사용하여 기본 클래스에 대한 삭제 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="46746-184">Using a safe handle to implement the dispose pattern for a base class</span></span>

<span data-ttu-id="46746-185">다음 예제는 SafeHandle을 사용하여 관리되지 않는 리소스를 캡슐화하는 기본 클래스에 대한 삭제 패턴인 `DisposableStreamResource`를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="46746-185">The following example illustrates the dispose pattern for a base class, `DisposableStreamResource`, that uses a safe handle to encapsulate unmanaged resources.</span></span> <span data-ttu-id="46746-186">이는 `DisposableResource`을 사용하여 열려 있는 파일을 나타내는 <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> 개체를 래핑하는 <xref:System.IO.Stream> 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="46746-186">It defines a `DisposableResource` class that uses a <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> to wrap a <xref:System.IO.Stream> object that represents an open file.</span></span> <span data-ttu-id="46746-187">또한 `DisposableResource` 메서드에는 파일 스트림에서 총 바이트 수를 반환하는 단일 속성인 `Size`도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="46746-187">The `DisposableResource` method also includes a single property, `Size`, that returns the total number of bytes in the file stream.</span></span>  
  
[!code-csharp[Conceptual.Disposable#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/base1.cs#9)]
[!code-vb[Conceptual.Disposable#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/base1.vb#9)]  
  
<a name="derived"></a>   
## <a name="using-a-safe-handle-to-implement-the-dispose-pattern-for-a-derived-class"></a><span data-ttu-id="46746-188">SafeHandle을 사용하여 파생된 클래스에 대한 삭제 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="46746-188">Using a safe handle to implement the dispose pattern for a derived class</span></span>

<span data-ttu-id="46746-189">다음 예제는 이전 예제에 제공된 `DisposableStreamResource2` 클래스에서 상속되는 파생된 클래스에 대한 삭제 패턴인 `DisposableStreamResource`를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="46746-189">The following example illustrates the dispose pattern for a derived class, `DisposableStreamResource2`, that inherits from the `DisposableStreamResource` class presented in the previous example.</span></span> <span data-ttu-id="46746-190">클래스에서 추가 메서드인 `WriteFileInfo`를 추가하고 <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> 개체를 사용하여 쓰기 가능 파일의 핸들을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="46746-190">The class adds an additional method, `WriteFileInfo`, and uses a <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> object to wrap the handle of the writable file.</span></span>  
  
[!code-csharp[Conceptual.Disposable#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/derived1.cs#10)]
[!code-vb[Conceptual.Disposable#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/derived1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="46746-191">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46746-191">See also</span></span>

<xref:System.GC.SuppressFinalize%2A>   
<xref:System.IDisposable>   
<xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>   
<xref:Microsoft.Win32.SafeHandles>   
<xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>   
<xref:System.Object.Finalize%2A?displayProperty=nameWithType>   
<span data-ttu-id="46746-192">[방법: 클래스 및 구조체 정의 및 사용(C++/CLI)](/cpp/dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli) </span><span class="sxs-lookup"><span data-stu-id="46746-192">[How to: Define and Consume Classes and Structs (C++/CLI)](/cpp/dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli) </span></span>  
[<span data-ttu-id="46746-193">삭제 패턴</span><span class="sxs-lookup"><span data-stu-id="46746-193">Dispose Pattern</span></span>](../../../docs/standard/design-guidelines/dispose-pattern.md)
