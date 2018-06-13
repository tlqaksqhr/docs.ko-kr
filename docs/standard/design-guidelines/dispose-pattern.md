---
title: 삭제 패턴
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Dispose method
- class library design guidelines [.NET Framework], Dispose method
- class library design guidelines [.NET Framework], Finalize method
- customizing Dispose method name
- Finalize method
ms.assetid: 31a6c13b-d6a2-492b-9a9f-e5238c983bcb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bdcb746ae2d8c2262b0cd0c6c9dcaababb12bd63
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33578991"
---
# <a name="dispose-pattern"></a><span data-ttu-id="987c5-102">삭제 패턴</span><span class="sxs-lookup"><span data-stu-id="987c5-102">Dispose Pattern</span></span>
<span data-ttu-id="987c5-103">모든 프로그램 실행을 사용 하는 동안 메모리, 시스템 핸들 또는 데이터베이스 연결과 같은 하나 이상의 시스템 리소스를 획득합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-103">All programs acquire one or more system resources, such as memory, system handles, or database connections, during the course of their execution.</span></span> <span data-ttu-id="987c5-104">개발자가 직접 획득 고 사용한 후 해제 되어야 합니다 때문에 이러한 시스템 리소스를 사용할 때는 주의 해야 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-104">Developers have to be careful when using such system resources, because they must be released after they have been acquired and used.</span></span>  
  
 <span data-ttu-id="987c5-105">CLR 자동 메모리 관리에 대 한 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-105">The CLR provides support for automatic memory management.</span></span> <span data-ttu-id="987c5-106">관리 되는 메모리 (C# 연산자를 사용 하 여 할당 된 메모리 `new`) 명시적으로 해제 될 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-106">Managed memory (memory allocated using the C# operator `new`) does not need to be explicitly released.</span></span> <span data-ttu-id="987c5-107">가비지 수집기 (GC)에 의해 자동으로 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-107">It is released automatically by the garbage collector (GC).</span></span> <span data-ttu-id="987c5-108">이 개발자의 메모리를 확보 걸리고 어려운 작업에서 해제 하 고 되었으면.NET Framework에서 제공 하는 최고의 생산성에 대 한 주된 이유 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-108">This frees developers from the tedious and difficult task of releasing memory and has been one of the main reasons for the unprecedented productivity afforded by the .NET Framework.</span></span>  
  
 <span data-ttu-id="987c5-109">그러나 관리 되는 메모리는 많은 시스템 리소스 종류 중 하나일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-109">Unfortunately, managed memory is just one of many types of system resources.</span></span> <span data-ttu-id="987c5-110">리소스 관리 되는 메모리는 여전히 명시적으로 해제 해야 하 고 관리 되지 않는 리소스로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-110">Resources other than managed memory still need to be released explicitly and are referred to as unmanaged resources.</span></span> <span data-ttu-id="987c5-111">GC 특별히 설계 되지 않았습니다 같은 관리 되지 않는 리소스를 관리 하는 개발자가 직접 관리 되지 않는 리소스를 관리 하기 위한 책임은는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-111">The GC was specifically not designed to manage such unmanaged resources, which means that the responsibility for managing unmanaged resources lies in the hands of the developers.</span></span>  
  
 <span data-ttu-id="987c5-112">CLR에서 관리 되지 않는 리소스를 해제에 대 한 도움을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-112">The CLR provides some help in releasing unmanaged resources.</span></span> <span data-ttu-id="987c5-113"><xref:System.Object?displayProperty=nameWithType> 가상 메서드를 선언 <xref:System.Object.Finalize%2A> (종료자 라고도 함) GC가 호출 되 해당 개체의 메모리 GC 회수 하 고 관리 되지 않는 리소스를 해제 하기 위해 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-113"><xref:System.Object?displayProperty=nameWithType> declares a virtual method <xref:System.Object.Finalize%2A> (also called the finalizer) that is called by the GC before the object’s memory is reclaimed by the GC and can be overridden to release unmanaged resources.</span></span> <span data-ttu-id="987c5-114">종료자를 재정의 하는 형식 종료 가능 형식으로 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-114">Types that override the finalizer are referred to as finalizable types.</span></span>  
  
 <span data-ttu-id="987c5-115">종료자 일부 정리 시나리오에서는 유효 하지만, 두 가지 중요 한 단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-115">Although finalizers are effective in some cleanup scenarios, they have two significant drawbacks:</span></span>  
  
-   <span data-ttu-id="987c5-116">종료자는 GC 검색 개체 컬렉션에 적합 한 경우 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-116">The finalizer is called when the GC detects that an object is eligible for collection.</span></span> <span data-ttu-id="987c5-117">이 일부 지정 하지 않은 후 일정 시간 동안 리소스가 더 이상 필요 하지 않은 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-117">This happens at some undetermined period of time after the resource is not needed anymore.</span></span> <span data-ttu-id="987c5-118">개발자 수 또는 종료자에서 리소스는 실제로 해제 되는 시점 시간과 리소스를 해제 하려는 경우 사이의 지연 또는 많은 부족 한 리소스 (쉽게 소진 될 수 있는 리소스)를 획득 하는 프로그램에서 사용할 수 수 있습니다. 리소스를 사용 하 여 (예:: 관리 되지 않는 대용량 메모리 버퍼)에 유지 하려면 비용이 많이 드는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-118">The delay between when the developer could or would like to release the resource and the time when the resource is actually released by the finalizer might be unacceptable in programs that acquire many scarce resources (resources that can be easily exhausted) or in cases in which resources are costly to keep in use (e.g., large unmanaged memory buffers).</span></span>  
  
-   <span data-ttu-id="987c5-119">CLR을 종료자를 호출 해야 하는 경우에 다음 가비지 컬렉션 (컬렉션 간에 실행 종료자)의 반올림 될 때까지 개체의 메모리의 컬렉션을 연기 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-119">When the CLR needs to call a finalizer, it must postpone collection of the object’s memory until the next round of garbage collection (the finalizers run between collections).</span></span> <span data-ttu-id="987c5-120">이 해당 개체의 메모리 (및 참조 하는 모든 개체) 긴 시간 동안 해제 되지 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-120">This means that the object’s memory (and all objects it refers to) will not be released for a longer period of time.</span></span>  
  
 <span data-ttu-id="987c5-121">따라서 종료자에만 의존 하지 않을 수 또는 매우 높은 성능의 시나리오에 부족 한 리소스를 처리할 때 가능한 신속 하 게 관리 되지 않는 리소스를 회수 하는 경우 대부분의 시나리오에서 적절 한 추가 된 GC 오버 헤드 종료가 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-121">Therefore, relying exclusively on finalizers might not be appropriate in many scenarios when it is important to reclaim unmanaged resources as quickly as possible, when dealing with scarce resources, or in highly performant scenarios in which the added GC overhead of finalization is unacceptable.</span></span>  
  
 <span data-ttu-id="987c5-122">프레임 워크를 제공는 <xref:System.IDisposable?displayProperty=nameWithType> 인터페이스를 개발자에 게 필요 하지 않은으로 관리 되지 않는 리소스를 해제 하는 수동 방법을 제공 하기 위해 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-122">The Framework provides the <xref:System.IDisposable?displayProperty=nameWithType> interface that should be implemented to provide the developer a manual way to release unmanaged resources as soon as they are not needed.</span></span> <span data-ttu-id="987c5-123">또한 제공 된 <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> 것을 알 수 GC 개체 수동으로 삭제 된 메서드와 경우 개체의 메모리를 회수할 수 이전 종료 더 이상 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-123">It also provides the <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> method that can tell the GC that an object was manually disposed of and does not need to be finalized anymore, in which case the object’s memory can be reclaimed earlier.</span></span> <span data-ttu-id="987c5-124">구현 하는 형식에서 `IDisposable` 인터페이스는 삭제 가능한 형식은 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-124">Types that implement the `IDisposable` interface are referred to as disposable types.</span></span>  
  
 <span data-ttu-id="987c5-125">Dispose 패턴 표준화 사용량과 종료자의 구현 하기 위한 것이 고 `IDisposable` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-125">The Dispose Pattern is intended to standardize the usage and implementation of finalizers and the `IDisposable` interface.</span></span>  
  
 <span data-ttu-id="987c5-126">패턴에 대 한 주요 목표는 구현의 복잡성을 줄이기 위해는 <xref:System.Object.Finalize%2A> 및 <xref:System.IDisposable.Dispose%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="987c5-126">The main motivation for the pattern is to reduce the complexity of the implementation of the <xref:System.Object.Finalize%2A> and the <xref:System.IDisposable.Dispose%2A> methods.</span></span> <span data-ttu-id="987c5-127">메서드 (차이점은 장의 뒷부분에 나오는 설명 참조)에 대 한 일부는 아니지만 일부 코드 경로 공유 하는 사실에서 복잡 한 형태소 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-127">The complexity stems from the fact that the methods share some but not all code paths (the differences are described later in the chapter).</span></span> <span data-ttu-id="987c5-128">또한 결정적 리소스 관리에 대 한 언어 지원의 진화와 관련 된 패턴의 일부 요소에 대 한 이유 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-128">In addition, there are historical reasons for some elements of the pattern related to the evolution of language support for deterministic resource management.</span></span>  
  
 <span data-ttu-id="987c5-129">**✓ 않습니다** 삭제 가능한 형식은의 인스턴스를 포함 하는 형식에 기본 Dispose 패턴을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-129">**✓ DO** implement the Basic Dispose Pattern on types containing instances of disposable types.</span></span> <span data-ttu-id="987c5-130">참조는 [기본 Dispose 패턴](#basic_pattern) 기본 패턴에 대 한 자세한 내용은 섹션.</span><span class="sxs-lookup"><span data-stu-id="987c5-130">See the [Basic Dispose Pattern](#basic_pattern) section for details on the basic pattern.</span></span>  
  
 <span data-ttu-id="987c5-131">형식이 다른 삭제 가능한 개체의 수명을 담당 이면 개발자 너무을 삭제 하는 방법을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-131">If a type is responsible for the lifetime of other disposable objects, developers need a way to dispose of them, too.</span></span> <span data-ttu-id="987c5-132">컨테이너의를 사용 하 여 `Dispose` 메서드는 가능 하도록 하는 편리한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-132">Using the container’s `Dispose` method is a convenient way to make this possible.</span></span>  
  
 <span data-ttu-id="987c5-133">**✓ 않습니다** 기본 Dispose 패턴을 구현 하 고 보유 중인 리소스를 명시적으로 해제 해야 하 고 종료자가 없는 형식에 종료자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-133">**✓ DO** implement the Basic Dispose Pattern and provide a finalizer on types holding resources that need to be freed explicitly and that do not have finalizers.</span></span>  
  
 <span data-ttu-id="987c5-134">예를 들어 관리 되지 않는 메모리 버퍼를 저장 하는 형식에 패턴을 구현 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-134">For example, the pattern should be implemented on types storing unmanaged memory buffers.</span></span> <span data-ttu-id="987c5-135">[종료 가능 형식](#finalizable_types) 섹션 종료자를 구현 하는 데 관련 된 지침에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-135">The [Finalizable Types](#finalizable_types) section discusses guidelines related to implementing finalizers.</span></span>  
  
 <span data-ttu-id="987c5-136">**✓ 고려** 클래스에 직접 저장 하지 않으므로 관리 되지 않는 리소스 또는 삭제 가능한 개체 이지만 수행 하는 하위 종류가 가능성은 기본 Dispose 패턴을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-136">**✓ CONSIDER** implementing the Basic Dispose Pattern on classes that themselves don’t hold unmanaged resources or disposable objects but are likely to have subtypes that do.</span></span>  
  
 <span data-ttu-id="987c5-137">이 예는는 <xref:System.IO.Stream?displayProperty=nameWithType> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-137">A great example of this is the <xref:System.IO.Stream?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="987c5-138">모든 리소스를 차지 하지 않는 하는 추상 기본 클래스는 아니지만 대부분의 하위 클래스 및이 때문에이 패턴 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-138">Although it is an abstract base class that doesn’t hold any resources, most of its subclasses do and because of this, it implements this pattern.</span></span>  
  
<a name="basic_pattern"></a>   
## <a name="basic-dispose-pattern"></a><span data-ttu-id="987c5-139">기본 삭제 패턴</span><span class="sxs-lookup"><span data-stu-id="987c5-139">Basic Dispose Pattern</span></span>  
 <span data-ttu-id="987c5-140">구현 패턴의 기본 구현에서는 `System.IDisposable` 를 선언 하는 인터페이스는 `Dispose(bool)` 를 간에 공유할 수 있는 모든 리소스 정리 논리를 구현 하는 메서드는 `Dispose` 메서드와 선택적 종료 자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-140">The basic implementation of the pattern involves implementing the `System.IDisposable` interface and declaring the `Dispose(bool)` method that implements all resource cleanup logic to be shared between the `Dispose` method and the optional finalizer.</span></span>  
  
 <span data-ttu-id="987c5-141">다음 예제에서는 기본 패턴의 간단한 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-141">The following example shows a simple implementation of the basic pattern:</span></span>  
  
```  
public class DisposableResourceHolder : IDisposable {  
  
    private SafeHandle resource; // handle to a resource  
  
    public DisposableResourceHolder(){  
        this.resource = ... // allocates the resource  
    }  
  
    public void Dispose(){  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
  
    protected virtual void Dispose(bool disposing){  
        if (disposing){  
            if (resource!= null) resource.Dispose();  
        }  
    }  
}  
```  
  
 <span data-ttu-id="987c5-142">부울 매개 변수 `disposing` 에서 메서드가 호출 된 있는지 여부를 나타내는 `IDisposable.Dispose` 구현 또는 종료자에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-142">The Boolean parameter `disposing` indicates whether the method was invoked from the `IDisposable.Dispose` implementation or from the finalizer.</span></span> <span data-ttu-id="987c5-143">`Dispose(bool)` 구현 다른 참조 개체 (예: 앞의 예제에서 리소스 필드)에 액세스 하기 전에 매개 변수를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-143">The `Dispose(bool)` implementation should check the parameter before accessing other reference objects (e.g., the resource field in the preceding sample).</span></span> <span data-ttu-id="987c5-144">이러한 개체에서 메서드를 호출할 때에 액세스 해야는 `IDisposable.Dispose` 구현 (때는 `disposing` 매개 변수는 true).</span><span class="sxs-lookup"><span data-stu-id="987c5-144">Such objects should only be accessed when the method is called from the `IDisposable.Dispose` implementation (when the `disposing` parameter is equal to true).</span></span> <span data-ttu-id="987c5-145">메서드가 종료자를 호출 하는 경우 (`disposing` 은 false), 다른 개체에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-145">If the method is invoked from the finalizer (`disposing` is false), other objects should not be accessed.</span></span> <span data-ttu-id="987c5-146">이유는 개체를 순서에 관계 없이 종료 되므로 또는 해당 종속성 수 이미 종료 되었을 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-146">The reason is that objects are finalized in an unpredictable order and so they, or any of their dependencies, might already have been finalized.</span></span>  
  
 <span data-ttu-id="987c5-147">또한이 섹션으로 이미 Dispose 패턴을 구현 하지 않는 기본 클래스에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-147">Also, this section applies to classes with a base that does not already implement the Dispose Pattern.</span></span> <span data-ttu-id="987c5-148">이미의 패턴을 구현 하는 클래스에서 상속 하는 경우 재정의 하기만 `Dispose(bool)` 메서드를 추가 하는 리소스 정리 논리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-148">If you are inheriting from a class that already implements the pattern, simply override the `Dispose(bool)` method to provide additional resource cleanup logic.</span></span>  
  
 <span data-ttu-id="987c5-149">**✓ 않습니다** 선언는 `protected virtual void Dispose(bool disposing)` 관련 된 모든 논리를 중앙 집중화 메서드 관리 되지 않는 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-149">**✓ DO** declare a `protected virtual void Dispose(bool disposing)` method to centralize all logic related to releasing unmanaged resources.</span></span>  
  
 <span data-ttu-id="987c5-150">이 방법에서는 모든 리소스 정리를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-150">All resource cleanup should occur in this method.</span></span> <span data-ttu-id="987c5-151">메서드는 모두 종료자에서 및 `IDisposable.Dispose` 메서드.</span><span class="sxs-lookup"><span data-stu-id="987c5-151">The method is called from both the finalizer and the `IDisposable.Dispose` method.</span></span> <span data-ttu-id="987c5-152">매개 변수는 종료 자가 내에서 호출 되는 경우 false 됩니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-152">The parameter will be false if being invoked from inside a finalizer.</span></span> <span data-ttu-id="987c5-153">종료 하는 동안 실행 되는 모든 코드에는 다른 종료 가능 개체에 액세스 하는 데 사용할 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-153">It should be used to ensure any code running during finalization is not accessing other finalizable objects.</span></span> <span data-ttu-id="987c5-154">종료자를 구현 세부 정보는 다음 섹션에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-154">Details of implementing finalizers are described in the next section.</span></span>  
  
```  
protected virtual void Dispose(bool disposing){  
    if (disposing){  
        if (resource!= null) resource.Dispose();  
    }  
}  
```  
  
 <span data-ttu-id="987c5-155">**✓ 않습니다** 구현는 `IDisposable` 단순히 호출 하 여 인터페이스 `Dispose(true)` 이어서 `GC.SuppressFinalize(this)`합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-155">**✓ DO** implement the `IDisposable` interface by simply calling `Dispose(true)` followed by `GC.SuppressFinalize(this)`.</span></span>  
  
 <span data-ttu-id="987c5-156">에 대 한 호출 `SuppressFinalize` 경우에 발생 해야 `Dispose(true)` 성공적으로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-156">The call to `SuppressFinalize` should only occur if `Dispose(true)` executes successfully.</span></span>  
  
```  
public void Dispose(){  
    Dispose(true);  
    GC.SuppressFinalize(this);  
}  
```  
  
 <span data-ttu-id="987c5-157">**X 하지 않으면** 매개 변수가 없는 확인 `Dispose` 가상 메서드.</span><span class="sxs-lookup"><span data-stu-id="987c5-157">**X DO NOT** make the parameterless `Dispose` method virtual.</span></span>  
  
 <span data-ttu-id="987c5-158">`Dispose(bool)` 메서드는 서브 클래스에서 재정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-158">The `Dispose(bool)` method is the one that should be overridden by subclasses.</span></span>  
  
```  
// bad design  
public class DisposableResourceHolder : IDisposable {  
    public virtual void Dispose(){ ... }  
    protected virtual void Dispose(bool disposing){ ... }  
}  
  
// good design  
public class DisposableResourceHolder : IDisposable {  
    public void Dispose(){ ... }  
    protected virtual void Dispose(bool disposing){ ... }  
}  
```  
  
 <span data-ttu-id="987c5-159">**X 하지 마십시오** 모든 오버 로드의 선언 된 `Dispose` 이외의 다른 방법 `Dispose()` 및 `Dispose(bool)`합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-159">**X DO NOT** declare any overloads of the `Dispose` method other than `Dispose()` and `Dispose(bool)`.</span></span>  
  
 <span data-ttu-id="987c5-160">`Dispose` 이 패턴을 체계화 하 고 구현자, 사용자 및 컴파일러 간에 혼동을 방지 하려면 예약 된 단어를 고려 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-160">`Dispose` should be considered a reserved word to help codify this pattern and prevent confusion among implementers, users, and compilers.</span></span> <span data-ttu-id="987c5-161">일부 언어 특정 형식에 자동으로이 패턴을 구현 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-161">Some languages might choose to automatically implement this pattern on certain types.</span></span>  
  
 <span data-ttu-id="987c5-162">**✓ 않습니다** 허용 된 `Dispose(bool)` 메서드를 두 번 이상 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-162">**✓ DO** allow the `Dispose(bool)` method to be called more than once.</span></span> <span data-ttu-id="987c5-163">메서드는 아무것도 수행 하지 않는 첫 번째 호출 이후의 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-163">The method might choose to do nothing after the first call.</span></span>  
  
```  
public class DisposableResourceHolder : IDisposable {  
  
    bool disposed = false;  
  
    protected virtual void Dispose(bool disposing){  
        if(disposed) return;  
        // cleanup  
        ...  
        disposed = true;  
    }  
}  
```  
  
 <span data-ttu-id="987c5-164">**하지 말고 X** 내에서 예외를 throw `Dispose(bool)` 포함 하는 프로세스 손상 되어 중요 한 상황에 따라 제외 하 고 (누수, 일치 하지 않는 공유 상태 등.).</span><span class="sxs-lookup"><span data-stu-id="987c5-164">**X AVOID** throwing an exception from within `Dispose(bool)` except under critical situations where the containing process has been corrupted (leaks, inconsistent shared state, etc.).</span></span>  
  
 <span data-ttu-id="987c5-165">사용자가 기대 하는에 대 한 호출 `Dispose` 예외가 발생 하지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-165">Users expect that a call to `Dispose` will not raise an exception.</span></span>  
  
 <span data-ttu-id="987c5-166">경우 `Dispose` 예외를 발생 시킬 수 있습니다, finally 블록 정리 논리를 더 이상 실행 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-166">If `Dispose` could raise an exception, further finally-block cleanup logic will not execute.</span></span> <span data-ttu-id="987c5-167">이 해결 하려면 사용자를 호출할 때마다 래핑할 해야 `Dispose` (내는 finally 블록!) try 블록에 있는 까지로 매우 복잡 한 정리 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-167">To work around this, the user would need to wrap every call to `Dispose` (within the finally block!) in a try block, which leads to very complex cleanup handlers.</span></span> <span data-ttu-id="987c5-168">실행 하는 경우는 `Dispose(bool disposing)` 메서드를 삭제 하는 것이 false 예외가 throw 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-168">If executing a `Dispose(bool disposing)` method, never throw an exception if disposing is false.</span></span> <span data-ttu-id="987c5-169">이렇게 종료자 컨텍스트 내에서 실행 하는 경우 프로세스가 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-169">Doing so will terminate the process if executing inside a finalizer context.</span></span>  
  
 <span data-ttu-id="987c5-170">**✓ 않습니다** throw 한 <xref:System.ObjectDisposedException> 개체의 삭제 된 후에 사용할 수 없는 멤버에서.</span><span class="sxs-lookup"><span data-stu-id="987c5-170">**✓ DO** throw an <xref:System.ObjectDisposedException> from any member that cannot be used after the object has been disposed of.</span></span>  
  
```  
public class DisposableResourceHolder : IDisposable {  
    bool disposed = false;  
    SafeHandle resource; // handle to a resource  
  
    public void DoSomething(){  
           if(disposed) throw new ObjectDisposedException(...);  
        // now call some native methods using the resource   
            ...  
    }  
    protected virtual void Dispose(bool disposing){  
        if(disposed) return;  
        // cleanup  
        ...  
        disposed = true;  
    }  
}  
```  
  
 <span data-ttu-id="987c5-171">**✓ 고려** 메서드를 제공 하 `Close()`, 외에 `Dispose()`, 영역에서 표준 용어 닫기 인지 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-171">**✓ CONSIDER** providing method `Close()`, in addition to the `Dispose()`, if close is standard terminology in the area.</span></span>  
  
 <span data-ttu-id="987c5-172">이렇게 할 경우 반드시 귀하에 게는 `Close` 구현 동일 `Dispose` 구현는 `IDisposable.Dispose` 메서드 명시적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-172">When doing so, it is important that you make the `Close` implementation identical to `Dispose` and consider implementing the `IDisposable.Dispose` method explicitly.</span></span>  
  
```  
public class Stream : IDisposable {  
    IDisposable.Dispose(){  
        Close();  
    }  
    public void Close(){  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
}  
```  
  
<a name="finalizable_types"></a>   
## <a name="finalizable-types"></a><span data-ttu-id="987c5-173">종료 가능 형식</span><span class="sxs-lookup"><span data-stu-id="987c5-173">Finalizable Types</span></span>  
 <span data-ttu-id="987c5-174">종료 가능한 형식은 종료자를 재정의 하 고 종료 코드 경로에서 제공 하 여 기본 Dispose 패턴을 확장 하는 형식을 `Dispose(bool)` 메서드.</span><span class="sxs-lookup"><span data-stu-id="987c5-174">Finalizable types are types that extend the Basic Dispose Pattern by overriding the finalizer and providing finalization code path in the `Dispose(bool)` method.</span></span>  
  
 <span data-ttu-id="987c5-175">종료자는 주로 없기 때문에 시스템의 상태에 대 한 특정 (일반적으로 유효) 가정을 실행 과정을 올바르게 구현 하기 매우 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-175">Finalizers are notoriously difficult to implement correctly, primarily because you cannot make certain (normally valid) assumptions about the state of the system during their execution.</span></span> <span data-ttu-id="987c5-176">다음 지침 신중 하 게 고려를 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-176">The following guidelines should be taken into careful consideration.</span></span>  
  
 <span data-ttu-id="987c5-177">일부 지침 방금에 적용 된 `Finalize` 메서드를 종료자에서 호출 되는 코드에 있지만 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-177">Note that some of the guidelines apply not just to the `Finalize` method, but to any code called from a finalizer.</span></span> <span data-ttu-id="987c5-178">기본적인 Dispose 패턴 이전에 정의 된 경우 내에서 실행 하는 논리 `Dispose(bool disposing)` 때는 `disposing` 매개 변수는 false입니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-178">In the case of the Basic Dispose Pattern previously defined, this means logic that executes inside `Dispose(bool disposing)` when the `disposing` parameter is false.</span></span>  
  
 <span data-ttu-id="987c5-179">재정의 하지 않아야 함 기본 클래스는 이미은 종료 가능 하 고 기본 Dispose 패턴을 구현 경우 `Finalize` 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-179">If the base class already is finalizable and implements the Basic Dispose Pattern, you should not override `Finalize` again.</span></span> <span data-ttu-id="987c5-180">재정의 해야 하는 대신 방금는 `Dispose(bool)` 메서드를 추가 하는 리소스 정리 논리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-180">You should instead just override the `Dispose(bool)` method to provide additional resource cleanup logic.</span></span>  
  
 <span data-ttu-id="987c5-181">다음 코드에서는 종료 가능 형식의 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-181">The following code shows an example of a finalizable type:</span></span>  
  
```  
public class ComplexResourceHolder : IDisposable {  
  
    private IntPtr buffer; // unmanaged memory buffer  
    private SafeHandle resource; // disposable handle to a resource  
  
    public ComplexResourceHolder(){  
        this.buffer = ... // allocates memory  
        this.resource = ... // allocates the resource  
    }  
  
    protected virtual void Dispose(bool disposing){  
            ReleaseBuffer(buffer); // release unmanaged memory  
        if (disposing){ // release other disposable objects  
            if (resource!= null) resource.Dispose();  
        }  
    }  
  
    ~ ComplexResourceHolder(){  
        Dispose(false);  
    }  
  
    public void Dispose(){  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
}  
```  
  
 <span data-ttu-id="987c5-182">**하지 말고 X** 유형을 종료 가능 만드는 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-182">**X AVOID** making types finalizable.</span></span>  
  
 <span data-ttu-id="987c5-183">종료 자가 필요한 생각 하는 모든 경우를 신중히 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-183">Carefully consider any case in which you think a finalizer is needed.</span></span> <span data-ttu-id="987c5-184">실제는 한 성능 및 코드 복잡성 관점에서 종료자를 사용 하 여 인스턴스와 관련 된 비용입니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-184">There is a real cost associated with instances with finalizers, from both a performance and code complexity standpoint.</span></span> <span data-ttu-id="987c5-185">와 같은 리소스 래퍼를 사용 하는 것을 선호 <xref:System.Runtime.InteropServices.SafeHandle> 가능한 경우에 관리 되지 않는 리소스를 캡슐화, 하는 경우 종료자 불필요 하 게 만드는 자체 리소스 정리에 대 한 래퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-185">Prefer using resource wrappers such as <xref:System.Runtime.InteropServices.SafeHandle> to encapsulate unmanaged resources where possible, in which case a finalizer becomes unnecessary because the wrapper is responsible for its own resource cleanup.</span></span>  
  
 <span data-ttu-id="987c5-186">**X 하지 않으면** 값 형식을 개체로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-186">**X DO NOT** make value types finalizable.</span></span>  
  
 <span data-ttu-id="987c5-187">실제로 참조 형식에만 CLR에 의해 종료 가져오기 및 값 형식에 종료자를 배치 하려고 하므로 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-187">Only reference types actually get finalized by the CLR, and thus any attempt to place a finalizer on a value type will be ignored.</span></span> <span data-ttu-id="987c5-188">C# 및 c + + 컴파일러에서이 규칙을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-188">The C# and C++ compilers enforce this rule.</span></span>  
  
 <span data-ttu-id="987c5-189">**✓ 않습니다** 형식이 자체 종료 자가 없는 관리 되지 않는 리소스를 해제 하는 일을 담당 하는 경우 종료 가능 형식을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-189">**✓ DO** make a type finalizable if the type is responsible for releasing an unmanaged resource that does not have its own finalizer.</span></span>  
  
 <span data-ttu-id="987c5-190">종료자를 구현 하는 경우 호출 `Dispose(false)` 내 모든 리소스 정리 논리를 배치 하 고는 `Dispose(bool disposing)` 메서드.</span><span class="sxs-lookup"><span data-stu-id="987c5-190">When implementing the finalizer, simply call `Dispose(false)` and place all resource cleanup logic inside the `Dispose(bool disposing)` method.</span></span>  
  
```  
public class ComplexResourceHolder : IDisposable {  
  
    ~ ComplexResourceHolder(){  
        Dispose(false);  
    }  
  
    protected virtual void Dispose(bool disposing){  
        ...  
    }  
}  
```  
  
 <span data-ttu-id="987c5-191">**✓ 않습니다** 줄어드는 경우 모든 형식에 대해 기본 Dispose 패턴을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-191">**✓ DO** implement the Basic Dispose Pattern on every finalizable type.</span></span>  
  
 <span data-ttu-id="987c5-192">이렇게 하면 형식의 사용자를 명시적으로 종료 자가 담당 이러한 동일한 리소스의 명확한 정리 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-192">This gives users of the type a means to explicitly perform deterministic cleanup of those same resources for which the finalizer is responsible.</span></span>  
  
 <span data-ttu-id="987c5-193">**X 하지 않으면** 는 것은 이미 종료 되었을 상당한 위험 있기 때문에 종료 자가 코드 경로에 추가 된 줄어드는 경우 개체에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-193">**X DO NOT** access any finalizable objects in the finalizer code path, because there is significant risk that they will have already been finalized.</span></span>  
  
 <span data-ttu-id="987c5-194">예를 들어 다른 줄어드는 경우 개체 B에 대 한 참조가 있는 종료 가능 개체가 A 안정적으로에 사용할 수 없습니다 B A의 종료 자가 또는 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-194">For example, a finalizable object A that has a reference to another finalizable object B cannot reliably use B in A’s finalizer, or vice versa.</span></span> <span data-ttu-id="987c5-195">종료자 (보다 짧은 중요 한 종료에 대 한 약한 정렬 보증) 임의의 순서로 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-195">Finalizers are called in a random order (short of a weak ordering guarantee for critical finalization).</span></span>  
  
 <span data-ttu-id="987c5-196">또한, 응용 프로그램 도메인 언로드 동안 또는 프로세스를 종료 하는 동안 정적 변수에 저장 된 개체의 특정 지점에서 수집 가져오기 주의 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-196">Also, be aware that objects stored in static variables will get collected at certain points during an application domain unload or while exiting the process.</span></span> <span data-ttu-id="987c5-197">종료 가능 개체 (또는 정적 변수에 저장 된 값을 사용할 수 있는 정적 메서드 호출)를 참조 하는 정적 변수가 되지 않을 수 있습니다에 액세스할 경우에 안전 하 게 보호 <xref:System.Environment.HasShutdownStarted%2A?displayProperty=nameWithType> true를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-197">Accessing a static variable that refers to a finalizable object (or calling a static method that might use values stored in static variables) might not be safe if <xref:System.Environment.HasShutdownStarted%2A?displayProperty=nameWithType> returns true.</span></span>  
  
 <span data-ttu-id="987c5-198">**✓ 않습니다** 확인 프로그램 `Finalize` 보호 된 메서드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-198">**✓ DO** make your `Finalize` method protected.</span></span>  
  
 <span data-ttu-id="987c5-199">C#, c + +, 및 VB.NET 개발자 필요가 없습니다 이런, 컴파일러는이 지침을 적용 하는 데 도움이 되므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-199">C#, C++, and VB.NET developers do not need to worry about this, because the compilers help to enforce this guideline.</span></span>  
  
 <span data-ttu-id="987c5-200">**X 하지 않으면** 종료자 논리 시스템에 중요 한 오류를 제외 하 고 답변된 예외 이스케이프 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-200">**X DO NOT** let exceptions escape from the finalizer logic, except for system-critical failures.</span></span>  
  
 <span data-ttu-id="987c5-201">예외가 종료자에서를 CLR 종료 됩니다 (현재.NET Framework 버전 2.0)에서는 전체 프로세스를 실행 및 제어 된 방식으로 해제 되지 리소스에서 다른 종료자를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-201">If an exception is thrown from a finalizer, the CLR will shut down the entire process (as of .NET Framework version 2.0), preventing other finalizers from executing and resources from being released in a controlled manner.</span></span>  
  
 <span data-ttu-id="987c5-202">**✓ 고려** 만들고 중요 한 종료 가능 개체를 사용 하 여 (포함 된 형식 계층 구조와 형식을 <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject>)는 종료자 절대적으로 실행 해야 경우에 강제 응용 프로그램 도메인 언로드 및 스레드 상황에 대 한 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="987c5-202">**✓ CONSIDER** creating and using a critical finalizable object (a type with a type hierarchy that contains <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject>) for situations in which a finalizer absolutely must execute even in the face of forced application domain unloads and thread aborts.</span></span>  
  
 <span data-ttu-id="987c5-203">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="987c5-203">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="987c5-204">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="987c5-204">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="987c5-205">참고 항목</span><span class="sxs-lookup"><span data-stu-id="987c5-205">See Also</span></span>  
 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>  
 <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="987c5-206">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="987c5-206">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="987c5-207">일반 디자인 패턴</span><span class="sxs-lookup"><span data-stu-id="987c5-207">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 [<span data-ttu-id="987c5-208">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="987c5-208">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)
