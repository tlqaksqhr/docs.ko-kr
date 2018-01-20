---
title: "기본 마샬링 동작"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interop marshaling, default
- interoperation with unmanaged code, marshaling
- marshaling behavior
ms.assetid: c0a9bcdf-3df8-4db3-b1b6-abbdb2af809a
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0e66caf800fd49b4822ee22326b8a5cf712d99bb
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="default-marshaling-behavior"></a><span data-ttu-id="b7683-102">기본 마샬링 동작</span><span class="sxs-lookup"><span data-stu-id="b7683-102">Default Marshaling Behavior</span></span>
<span data-ttu-id="b7683-103">Interop 마샬링은 메서드 매개 변수와 연결된 데이터가 관리되는 메모리와 관리되지 않는 메모리 간에 전달될 때 동작하는 방식을 제어하는 규칙에 따라 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-103">Interop marshaling operates on rules that dictate how data associated with method parameters behaves as it passes between managed and unmanaged memory.</span></span> <span data-ttu-id="b7683-104">이러한 기본 제공 규칙은 데이터 형식 변환, 호출 수신자가 전달된 데이터를 변경하고 해당 변경 내용을 호출자에게 반환할 수 있는지 여부 및 마샬러가 성능 최적화를 제공하는 상황과 같은 마샬링 작업을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-104">These built-in rules control such marshaling activities as data type transformations, whether a callee can change data passed to it and return those changes to the caller, and under which circumstances the marshaler provides performance optimizations.</span></span>  
  
 <span data-ttu-id="b7683-105">이 섹션에서는 interop 마샬링 서비스의 기본 동작 특성을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-105">This section identifies the default behavioral characteristics of the interop marshaling service.</span></span> <span data-ttu-id="b7683-106">배열, 부울 형식, char 형식, 대리자, 클래스, 개체, 문자열 및 구조체 마샬링에 대한 자세한 정보를 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-106">It presents detailed information on marshaling arrays, Boolean types, char types, delegates, classes, objects, strings, and structures.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7683-107">제네릭 형식의 마샬링은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-107">Marshaling of generic types is not supported.</span></span> <span data-ttu-id="b7683-108">자세한 내용은 [제네릭 형식을 통한 상호 운용](http://msdn.microsoft.com/library/26b88e03-085b-4b53-94ba-a5a9c709ce58)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7683-108">For more information see, [Interoperating Using Generic Types](http://msdn.microsoft.com/library/26b88e03-085b-4b53-94ba-a5a9c709ce58).</span></span>  
  
## <a name="memory-management-with-the-interop-marshaler"></a><span data-ttu-id="b7683-109">Interop 마샬러를 사용한 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="b7683-109">Memory management with the interop marshaler</span></span>  
 <span data-ttu-id="b7683-110">Interop 마샬러는 항상 비관리 코드에 의해 할당된 메모리를 해제하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-110">The interop marshaler always attempts to free memory allocated by unmanaged code.</span></span> <span data-ttu-id="b7683-111">이 동작은 COM 메모리 관리 규칙을 준수하지만 네이티브 C++를 제어하는 규칙과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-111">This behavior complies with COM memory management rules, but differs from the rules that govern native C++.</span></span>  
  
 <span data-ttu-id="b7683-112">포인터에 대한 메모리를 자동으로 해제하는 플랫폼 호출을 사용하는 경우 네이티브 C++ 동작(메모리 해제 안 함)을 예상하면 혼란이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-112">Confusion can arise if you anticipate native C++ behavior (no memory freeing) when using platform invoke, which automatically frees memory for pointers.</span></span> <span data-ttu-id="b7683-113">예를 들어 C++ DLL에서 다음 관리되지 않는 메서드를 호출하는 경우 메모리가 자동으로 해제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-113">For example, calling the following unmanaged method from a C++ DLL does not automatically free any memory.</span></span>  
  
### <a name="unmanaged-signature"></a><span data-ttu-id="b7683-114">관리되지 않는 서명</span><span class="sxs-lookup"><span data-stu-id="b7683-114">Unmanaged signature</span></span>  
  
```  
BSTR MethodOne (BSTR b) {  
     return b;  
}  
```  
  
 <span data-ttu-id="b7683-115">그러나 메서드를 플랫폼 호출 프로토타입으로 정의하고, 각 **BSTR** 형식을 <xref:System.String> 형식으로 바꾼 다음 `MethodOne`을 호출하는 경우 공용 언어 런타임에서 `b`를 해제하려고 두 번 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-115">However, if you define the method as a platform invoke prototype, replace each **BSTR** type with a <xref:System.String> type, and call `MethodOne`, the common language runtime attempts to free `b` twice.</span></span> <span data-ttu-id="b7683-116">**String** 형식보다 <xref:System.IntPtr> 형식을 사용하여 마샬링 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-116">You can change the marshaling behavior by using <xref:System.IntPtr> types rather than **String** types.</span></span>  
  
 <span data-ttu-id="b7683-117">런타임은 항상 **CoTaskMemFree** 메서드를 사용하여 메모리를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-117">The runtime always uses the **CoTaskMemFree** method to free memory.</span></span> <span data-ttu-id="b7683-118">사용하는 메모리가 **CoTaskMemAlloc** 메서드를 통해 할당되지 않은 경우 **IntPtr**을 사용하고 적절한 메서드를 통해 수동으로 메모리를 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-118">If the memory you are working with was not allocated with the **CoTaskMemAlloc** method, you must use an **IntPtr** and free the memory manually using the appropriate method.</span></span> <span data-ttu-id="b7683-119">마찬가지로, 커널 메모리에 대한 포인터를 반환하는 Kernel32.dll의 **GetCommandLine** 함수를 사용하는 경우와 같이 메모리가 해제되지 않아야 하는 상황에서는 자동 메모리 해제를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-119">Similarly, you can avoid automatic memory freeing in situations where memory should never be freed, such as when using the **GetCommandLine** function from Kernel32.dll, which returns a pointer to kernel memory.</span></span> <span data-ttu-id="b7683-120">수동으로 메모리를 해제하는 방법에 대한 자세한 내용은 [Buffers 샘플](http://msdn.microsoft.com/library/e30d36e8-d7c4-4936-916a-8fdbe4d9ffd5)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7683-120">For details on manually freeing memory, see the [Buffers Sample](http://msdn.microsoft.com/library/e30d36e8-d7c4-4936-916a-8fdbe4d9ffd5).</span></span>  
  
## <a name="default-marshaling-for-classes"></a><span data-ttu-id="b7683-121">클래스에 대한 기본 마샬링</span><span class="sxs-lookup"><span data-stu-id="b7683-121">Default marshaling for classes</span></span>  
 <span data-ttu-id="b7683-122">클래스는 COM interop에 의해서만 마샬링될 수 있으며 항상 인터페이스로 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-122">Classes can be marshaled only by COM interop and are always marshaled as interfaces.</span></span> <span data-ttu-id="b7683-123">클래스를 마샬링하는 데 사용되는 인터페이스를 클래스 인터페이스라고 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-123">In some cases the interface used to marshal the class is known as the class interface.</span></span> <span data-ttu-id="b7683-124">선택한 인터페이스로 클래스 인터페이스를 재정의하는 방법에 대한 자세한 내용은 [클래스 인터페이스 소개](http://msdn.microsoft.com/library/733c0dd2-12e5-46e6-8de1-39d5b25df024)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7683-124">For information about overriding the class interface with an interface of your choice, see [Introducing the Class Interface](http://msdn.microsoft.com/library/733c0dd2-12e5-46e6-8de1-39d5b25df024).</span></span>  
  
### <a name="passing-classes-to-com"></a><span data-ttu-id="b7683-125">COM에 클래스 전달</span><span class="sxs-lookup"><span data-stu-id="b7683-125">Passing Classes to COM</span></span>  
 <span data-ttu-id="b7683-126">관리되는 클래스를 COM에 전달하면 interop 마샬러가 자동으로 클래스를 COM 프록시로 래핑하고 프록시에 의해 생성된 클래스 인터페이스를 COM 메서드 호출에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-126">When a managed class is passed to COM, the interop marshaler automatically wraps the class with a COM proxy and passes the class interface produced by the proxy to the COM method call.</span></span> <span data-ttu-id="b7683-127">그런 다음 프록시는 클래스 인터페이스에 대한 모든 호출을 관리되는 개체에 다시 위임합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-127">The proxy then delegates all calls on the class interface back to the managed object.</span></span> <span data-ttu-id="b7683-128">또한 프록시는 클래스에 의해 명시적으로 구현되지 않은 다른 인터페이스를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-128">The proxy also exposes other interfaces that are not explicitly implemented by the class.</span></span> <span data-ttu-id="b7683-129">프록시는 클래스를 대신하여 **IUnknown** 및 **IDispatch**와 같은 인터페이스를 자동으로 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-129">The proxy automatically implements interfaces such as **IUnknown** and **IDispatch** on behalf of the class.</span></span>  
  
### <a name="passing-classes-to-net-code"></a><span data-ttu-id="b7683-130">.NET 코드에 클래스 전달</span><span class="sxs-lookup"><span data-stu-id="b7683-130">Passing Classes to .NET Code</span></span>  
 <span data-ttu-id="b7683-131">Coclass는 대개 COM에서 메서드 인수로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-131">Coclasses are not typically used as method arguments in COM.</span></span> <span data-ttu-id="b7683-132">대신, 일반적으로 기본 인터페이스가 coclass 대신 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-132">Instead, a default interface is usually passed in place of the coclass.</span></span>  
  
 <span data-ttu-id="b7683-133">인터페이스가 관리 코드에 전달되는 경우 interop 마샬러가 인터페이스를 적절한 래퍼로 래핑하고 관리되는 메서드에 래퍼를 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-133">When an interface is passed into managed code, the interop marshaler is responsible for wrapping the interface with the proper wrapper and passing the wrapper to the managed method.</span></span> <span data-ttu-id="b7683-134">사용할 래퍼를 결정하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-134">Determining which wrapper to use can be difficult.</span></span> <span data-ttu-id="b7683-135">COM 개체의 모든 인스턴스에는 개체가 구현하는 인터페이스 수에 관계없이 하나의 고유한 래퍼가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-135">Every instance of a COM object has a single, unique wrapper, no matter how many interfaces the object implements.</span></span> <span data-ttu-id="b7683-136">예를 들어 서로 다른 인터페이스 5개를 구현하는 단일 COM 개체에는 하나의 래퍼만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-136">For example, a single COM object that implements five distinct interfaces has only one wrapper.</span></span> <span data-ttu-id="b7683-137">동일한 래퍼가 5개 인터페이스를 모두 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-137">The same wrapper exposes all five interfaces.</span></span> <span data-ttu-id="b7683-138">COM 개체 인스턴스를 2개 만들면 래퍼 인스턴스도 2개 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-138">If two instances of the COM object are created, then two instances of the wrapper are created.</span></span>  
  
 <span data-ttu-id="b7683-139">래퍼가 전체 수명 동안 동일한 형식을 유지하려면 개체에 의해 노출된 인터페이스가 마샬러를 통해 처음 전달될 때 interop 마샬러가 올바른 래퍼를 식별해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-139">For the wrapper to maintain the same type throughout its lifetime, the interop marshaler must identify the correct wrapper the first time an interface exposed by the object is passed through the marshaler.</span></span> <span data-ttu-id="b7683-140">마샬러는 개체가 구현하는 인터페이스 중 하나를 확인하여 개체를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-140">The marshaler identifies the object by looking at one of the interfaces the object implements.</span></span>  
  
 <span data-ttu-id="b7683-141">예를 들어 마샬러는 클래스 래퍼를 사용하여 관리 코드에 전달된 인터페이스를 래핑해야 한다고 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-141">For example, the marshaler determines that the class wrapper should be used to wrap the interface that was passed into managed code.</span></span> <span data-ttu-id="b7683-142">인터페이스는 마샬러를 통해 처음 전달될 때 마샬러는 인터페이스가 알려진 개체에서 제공되는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-142">When the interface is first passed through the marshaler, the marshaler checks whether the interface is coming from a known object.</span></span> <span data-ttu-id="b7683-143">이 검사는 다음 두 가지 상황에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-143">This check occurs in two situations:</span></span>  
  
-   <span data-ttu-id="b7683-144">다른 곳에서 COM에 전달된 다른 관리되는 개체에 의해 인터페이스가 구현되는 경우.</span><span class="sxs-lookup"><span data-stu-id="b7683-144">An interface is being implemented by another managed object that was passed to COM elsewhere.</span></span> <span data-ttu-id="b7683-145">마샬러는 관리되는 개체에 의해 노출된 인터페이스를 쉽게 식별할 수 있으며, 구현을 제공하는 관리되는 개체와 인터페이스를 일치시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-145">The marshaler can readily identify interfaces exposed by managed objects and is able to match the interface with the managed object that provides the implementation.</span></span> <span data-ttu-id="b7683-146">그런 다음 관리되는 개체가 메서드에 전달되며 래퍼는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-146">The managed object is then passed to the method and no wrapper is needed.</span></span>  
  
-   <span data-ttu-id="b7683-147">이미 래핑된 개체가 인터페이스를 구현하는 경우.</span><span class="sxs-lookup"><span data-stu-id="b7683-147">An object that has already been wrapped is implementing the interface.</span></span> <span data-ttu-id="b7683-148">이러한 경우인지 확인하기 위해 마샬러는 해당 **IUnknown** 인터페이스에 대해 개체를 쿼리하고 반환된 인터페이스를 이미 래핑된 다른 개체의 인터페이스와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-148">To determine whether this is the case, the marshaler queries the object for its **IUnknown** interface and compares the returned interface to the interfaces of other objects that are already wrapped.</span></span> <span data-ttu-id="b7683-149">인터페이스가 다른 래퍼의 인터페이스와 같으면 개체 ID가 동일하고 기존 래퍼가 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-149">If the interface is the same as that of another wrapper, the objects have the same identity and the existing wrapper is passed to the method.</span></span>  
  
 <span data-ttu-id="b7683-150">알려진 개체의 인터페이스가 아닌 경우 마샬러는 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-150">If an interface is not from a known object, the marshaler does the following:</span></span>  
  
1.  <span data-ttu-id="b7683-151">마샬러가 **IProvideClassInfo2** 인터페이스에 대해 개체를 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-151">The marshaler queries the object for the **IProvideClassInfo2** interface.</span></span> <span data-ttu-id="b7683-152">제공되면 마샬러가 **IProvideClassInfo2.GetGUID**에서 반환된 CLSID를 사용하여 인터페이스를 제공하는 coclass를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-152">If provided, the marshaler uses the CLSID returned from **IProvideClassInfo2.GetGUID** to identify the coclass providing the interface.</span></span> <span data-ttu-id="b7683-153">CLSID를 통해 마샬러는 어셈블리가 이전에 등록된 경우 레지스트리에서 래퍼를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-153">With the CLSID, the marshaler can locate the wrapper from the registry if the assembly has previously been registered.</span></span>  
  
2.  <span data-ttu-id="b7683-154">마샬러가 **IProvideClassInfo** 인터페이스에 대해 인터페이스를 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-154">The marshaler queries the interface for the **IProvideClassInfo** interface.</span></span> <span data-ttu-id="b7683-155">제공되면 마샬러가 **IProvideClassInfo.GetClassinfo**에서 반환된 **ITypeInfo**를 사용하여 인터페이스를 노출하는 클래스의 CLSID를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-155">If provided, the marshaler uses the **ITypeInfo** returned from **IProvideClassInfo.GetClassinfo** to determine the CLSID of the class exposing the interface.</span></span> <span data-ttu-id="b7683-156">마샬러는 CLSID를 사용하여 래퍼에 대한 메타데이터를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-156">The marshaler can use the CLSID to locate the metadata for the wrapper.</span></span>  
  
3.  <span data-ttu-id="b7683-157">마샬러가 여전히 클래스를 식별할 수 없는 경우 **System.__ComObject**라는 제네릭 래퍼 클래스로 인터페이스를 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-157">If the marshaler still cannot identify the class, it wraps the interface with a generic wrapper class called **System.__ComObject**.</span></span>  
  
## <a name="default-marshaling-for-delegates"></a><span data-ttu-id="b7683-158">대리자에 대한 기본 마샬링</span><span class="sxs-lookup"><span data-stu-id="b7683-158">Default marshaling for delegates</span></span>  
 <span data-ttu-id="b7683-159">관리되는 대리자는 호출 메커니즘에 따라 COM 인터페이스 또는 함수 포인터로 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-159">A managed delegate is marshaled as a COM interface or as a function pointer, based on the calling mechanism:</span></span>  
  
-   <span data-ttu-id="b7683-160">플랫폼 호출의 경우 대리자는 기본적으로 관리되지 않는 함수 포인터로 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-160">For platform invoke, a delegate is marshaled as an unmanaged function pointer by default.</span></span>  
  
-   <span data-ttu-id="b7683-161">COM interop의 경우 대리자는 기본적으로 **_Delegate** 형식의 COM 인터페이스로 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-161">For COM interop, a delegate is marshaled as a COM interface of type **_Delegate** by default.</span></span> <span data-ttu-id="b7683-162">**_Delegate** 인터페이스는 Mscorlib.tlb 형식 라이브러리에서 정의되며 대리자가 참조하는 메서드를 호출할 수 있게 해주는 <xref:System.Delegate.DynamicInvoke%2A?displayProperty=nameWithType> 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-162">The **_Delegate** interface is defined in the Mscorlib.tlb type library and contains the <xref:System.Delegate.DynamicInvoke%2A?displayProperty=nameWithType> method, which enables you to call the method that the delegate references.</span></span>  
  
 <span data-ttu-id="b7683-163">다음 표에서는 관리되는 대리자 데이터 형식에 대한 마샬링 옵션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-163">The following table shows the marshaling options for the managed delegate data type.</span></span> <span data-ttu-id="b7683-164"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성은 대리자를 마샬링하기 위한 여러 <xref:System.Runtime.InteropServices.UnmanagedType> 열거형 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-164">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal delegates.</span></span>  
  
|<span data-ttu-id="b7683-165">열거형 형식</span><span class="sxs-lookup"><span data-stu-id="b7683-165">Enumeration type</span></span>|<span data-ttu-id="b7683-166">관리되지 않는 형식에 대한 설명</span><span class="sxs-lookup"><span data-stu-id="b7683-166">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|<span data-ttu-id="b7683-167">**UnmanagedType.FunctionPtr**</span><span class="sxs-lookup"><span data-stu-id="b7683-167">**UnmanagedType.FunctionPtr**</span></span>|<span data-ttu-id="b7683-168">관리되지 않는 함수 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-168">An unmanaged function pointer.</span></span>|  
|<span data-ttu-id="b7683-169">**UnmanagedType.Interface**</span><span class="sxs-lookup"><span data-stu-id="b7683-169">**UnmanagedType.Interface**</span></span>|<span data-ttu-id="b7683-170">Mscorlib.tlb에서 정의된 **_Delegate** 형식의 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-170">An interface of type **_Delegate**, as defined in Mscorlib.tlb.</span></span>|  
  
 <span data-ttu-id="b7683-171">`DelegateTestInterface`의 메서드를 COM 형식 라이브러리로 내보내는 다음 예제 코드를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="b7683-171">Consider the following example code in which the methods of `DelegateTestInterface` are exported to a COM type library.</span></span> <span data-ttu-id="b7683-172">**ref**(또는 **ByRef**) 키워드로 표시된 대리자만 In/Out 매개 변수로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-172">Notice that only delegates marked with the **ref** (or **ByRef**) keyword are passed as In/Out parameters.</span></span>  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
  
public interface DelegateTest {  
void m1(Delegate d);  
void m2([MarshalAs(UnmanagedType.Interface)] Delegate d);     
void m3([MarshalAs(UnmanagedType.Interface)] ref Delegate d);    
void m4([MarshalAs(UnmanagedType.FunctionPtr)] Delegate d);   
void m5([MarshalAs(UnmanagedType.FunctionPtr)] ref Delegate d);     
}  
```  
  
### <a name="type-library-representation"></a><span data-ttu-id="b7683-173">형식 라이브러리 표현</span><span class="sxs-lookup"><span data-stu-id="b7683-173">Type library representation</span></span>  
  
```  
importlib("mscorlib.tlb");  
interface DelegateTest : IDispatch {  
[id(…)] HRESULT m1([in] _Delegate* d);  
[id(…)] HRESULT m2([in] _Delegate* d);  
[id(…)] HRESULT m3([in, out] _Delegate** d);  
[id()] HRESULT m4([in] int d);  
[id()] HRESULT m5([in, out] int *d);  
   };  
```  
  
 <span data-ttu-id="b7683-174">다른 모든 관리되지 않는 함수 포인터를 역참조할 수 있는 것과 마찬가지로 함수 포인터도 역참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-174">A function pointer can be dereferenced, just as any other unmanaged function pointer can be dereferenced.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7683-175">비관리 코드에서 보유한 관리되는 대리자에 대한 함수 포인터 참조는 공용 언어 런타임이 관리되는 개체에서 가비지 수집을 수행할 수 없도록 차단하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-175">A reference to the function pointer to a managed delegate held by unmanaged code does not prevent the common language runtime from performing garbage collection on the managed object.</span></span>  
  
 <span data-ttu-id="b7683-176">예를 들어 다음 코드는 `SetChangeHandler` 메서드에 전달된 `cb` 개체 참조가 `Test` 메서드의 수명을 초과하여 `cb` 연결을 유지하지 않으므로 잘못된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-176">For example, the following code is incorrect because the reference to the `cb` object, passed to the `SetChangeHandler` method, does not keep `cb` alive beyond the life of the `Test` method.</span></span> <span data-ttu-id="b7683-177">`cb` 개체가 가비지 수집되고 나면 `SetChangeHandler`에 전달된 함수 포인터가 더이상 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-177">Once the `cb` object is garbage collected, the function pointer passed to `SetChangeHandler` is no longer valid.</span></span>  
  
```csharp  
public class ExternalAPI {  
   [DllImport("External.dll")]  
   public static extern void SetChangeHandler(  
      [MarshalAs(UnmanagedType.FunctionPtr)]ChangeDelegate d);  
}  
public delegate bool ChangeDelegate([MarshalAs(UnmanagedType.LPWStr) string S);  
public class CallBackClass {  
   public bool OnChange(string S){ return true;}  
}  
internal class DelegateTest {  
   public static void Test() {  
      CallBackClass cb = new CallBackClass();  
      // Caution: The following reference on the cb object does not keep the   
      // object from being garbage collected after the Main method   
      // executes.  
      ExternalAPI.SetChangeHandler(new ChangeDelegate(cb.OnChange));     
   }  
}  
```  
  
 <span data-ttu-id="b7683-178">예기치 않은 가비지 수집을 보완하기 위해 호출자는 관리되지 않는 함수 포인터가 사용되는 한 `cb` 개체 연결이 유지되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-178">To compensate for unexpected garbage collection, the caller must ensure that the `cb` object is kept alive as long as the unmanaged function pointer is in use.</span></span> <span data-ttu-id="b7683-179">필요에 따라 다음 예제와 같이 함수 포인터가 더 이상 필요하지 않을 때 비관리 코드에서 관리 코드에 알리도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-179">Optionally, you can have the unmanaged code notify the managed code when the function pointer is no longer needed, as the following example shows.</span></span>  
  
```csharp  
internal class DelegateTest {  
   CallBackClass cb;  
   // Called before ever using the callback function.  
   public static void SetChangeHandler() {  
      cb = new CallBackClass();  
      ExternalAPI.SetChangeHandler(new ChangeDelegate(cb.OnChange));  
   }  
   // Called after using the callback function for the last time.  
   public static void RemoveChangeHandler() {  
      // The cb object can be collected now. The unmanaged code is   
      // finished with the callback function.  
      cb = null;  
   }  
}  
```  
  
## <a name="default-marshaling-for-value-types"></a><span data-ttu-id="b7683-180">값 형식에 대한 기본 마샬링</span><span class="sxs-lookup"><span data-stu-id="b7683-180">Default marshaling for value types</span></span>  
 <span data-ttu-id="b7683-181">정수 및 부동 소수점 숫자와 같은 대부분의 값 형식은 [blittable](../../../docs/framework/interop/blittable-and-non-blittable-types.md)이며 마샬링할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-181">Most value types, such as integers and floating-point numbers, are [blittable](../../../docs/framework/interop/blittable-and-non-blittable-types.md) and do not require marshaling.</span></span> <span data-ttu-id="b7683-182">다른 [비 blittable](../../../docs/framework/interop/blittable-and-non-blittable-types.md) 형식은 관리되는 메모리와 관리되지 않는 메모리에서 서로 다르게 표현되므로 마샬링해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-182">Other [non-blittable](../../../docs/framework/interop/blittable-and-non-blittable-types.md) types have dissimilar representations in managed and unmanaged memory and do require marshaling.</span></span> <span data-ttu-id="b7683-183">다른 형식은 상호 운용 경계 간에 명시적 형식 지정도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-183">Still other types require explicit formatting across the interoperation boundary.</span></span>  
  
 <span data-ttu-id="b7683-184">이 항목에서는 형식이 지정된 값 형식에 대한 다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-184">This topic provides the follow information on formatted value types:</span></span>  
  
-   [<span data-ttu-id="b7683-185">플랫폼 호출에서 사용되는 값 형식</span><span class="sxs-lookup"><span data-stu-id="b7683-185">Value Types Used in Platform Invoke</span></span>](#cpcondefaultmarshalingforvaluetypesanchor2)  
  
-   [<span data-ttu-id="b7683-186">COM Interop에서 사용되는 값 형식</span><span class="sxs-lookup"><span data-stu-id="b7683-186">Value Types Used in COM Interop</span></span>](#cpcondefaultmarshalingforvaluetypesanchor3)  
  
 <span data-ttu-id="b7683-187">이 항목에서는 형식이 지정된 형식을 설명할 뿐 아니라 특별한 마샬링 동작이 있는 [시스템 값 형식](#cpcondefaultmarshalingforvaluetypesanchor1)을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-187">In addition to describing formatted types, this topic identifies [System Value Types](#cpcondefaultmarshalingforvaluetypesanchor1) that have unusual marshaling behavior.</span></span>  
  
 <span data-ttu-id="b7683-188">형식이 지정된 형식은 메모리에서 해당 멤버의 레이아웃을 명시적으로 제어하는 정보가 포함된 복합 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-188">A formatted type is a complex type that contains information that explicitly controls the layout of its members in memory.</span></span> <span data-ttu-id="b7683-189">멤버 레이아웃 정보는 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성을 사용하여 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-189">The member layout information is provided using the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute.</span></span> <span data-ttu-id="b7683-190">레이아웃은 다음 <xref:System.Runtime.InteropServices.LayoutKind> 열거형 값 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-190">The layout can be one of the following <xref:System.Runtime.InteropServices.LayoutKind> enumeration values:</span></span>  
  
-   <span data-ttu-id="b7683-191">**LayoutKind.Automatic**</span><span class="sxs-lookup"><span data-stu-id="b7683-191">**LayoutKind.Automatic**</span></span>  
  
     <span data-ttu-id="b7683-192">공용 언어 런타임이 효율성을 위해 형식의 멤버 순서를 자유롭게 조정할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-192">Indicates that the common language runtime is free to reorder the members of the type for efficiency.</span></span> <span data-ttu-id="b7683-193">그러나 값 형식이 비관리 코드에 전달될 때는 멤버의 레이아웃을 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-193">However, when a value type is passed to unmanaged code, the layout of the members is predictable.</span></span> <span data-ttu-id="b7683-194">이러한 구조체를 자동으로 마샬링하려고 하면 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-194">An attempt to marshal such a structure automatically causes an exception.</span></span>  
  
-   <span data-ttu-id="b7683-195">**LayoutKind.Sequential**</span><span class="sxs-lookup"><span data-stu-id="b7683-195">**LayoutKind.Sequential**</span></span>  
  
     <span data-ttu-id="b7683-196">형식의 멤버가 관리되는 형식 정의에 나타나는 순서대로 관리되지 않는 메모리에 배치됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-196">Indicates that the members of the type are to be laid out in unmanaged memory in the same order in which they appear in the managed type definition.</span></span>  
  
-   <span data-ttu-id="b7683-197">**LayoutKind.Explicit**</span><span class="sxs-lookup"><span data-stu-id="b7683-197">**LayoutKind.Explicit**</span></span>  
  
     <span data-ttu-id="b7683-198">각 필드에 제공된 <xref:System.Runtime.InteropServices.FieldOffsetAttribute>에 따라 멤버가 배치됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-198">Indicates that the members are laid out according to the <xref:System.Runtime.InteropServices.FieldOffsetAttribute> supplied with each field.</span></span>  
  
<a name="cpcondefaultmarshalingforvaluetypesanchor2"></a>   
### <a name="value-types-used-in-platform-invoke"></a><span data-ttu-id="b7683-199">플랫폼 호출에서 사용되는 값 형식</span><span class="sxs-lookup"><span data-stu-id="b7683-199">Value Types Used in Platform Invoke</span></span>  
 <span data-ttu-id="b7683-200">다음 예제에서 `Point` 및 `Rect` 형식은 **StructLayoutAttribute**를 사용하여 멤버 레이아웃 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-200">In the following example the `Point` and `Rect` types provide member layout information using the **StructLayoutAttribute**.</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
<StructLayout(LayoutKind.Sequential)> Public Structure Point  
   Public x As Integer  
   Public y As Integer  
End Structure  
<StructLayout(LayoutKind.Explicit)> Public Structure Rect  
   <FieldOffset(0)> Public left As Integer  
   <FieldOffset(4)> Public top As Integer  
   <FieldOffset(8)> Public right As Integer  
   <FieldOffset(12)> Public bottom As Integer  
End Structure  
```  
  
```csharp  
using System.Runtime.InteropServices;  
[StructLayout(LayoutKind.Sequential)]  
public struct Point {  
   public int x;  
   public int y;  
}     
  
[StructLayout(LayoutKind.Explicit)]  
public struct Rect {  
   [FieldOffset(0)] public int left;  
   [FieldOffset(4)] public int top;  
   [FieldOffset(8)] public int right;  
   [FieldOffset(12)] public int bottom;  
}  
```  
  
 <span data-ttu-id="b7683-201">비관리 코드로 마샬링된 경우 이러한 형식이 지정된 형식은 C 스타일 구조체로 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-201">When marshaled to unmanaged code, these formatted types are marshaled as C-style structures.</span></span> <span data-ttu-id="b7683-202">이렇게 하면 구조체 인수가 있는 관리되지 않는 API를 쉽게 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-202">This provides an easy way of calling an unmanaged API that has structure arguments.</span></span> <span data-ttu-id="b7683-203">예를 들어 Microsoft Win32 API **PtInRect** 함수에 `POINT` 및 `RECT` 구조체를 다음과 같이 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-203">For example, the `POINT` and `RECT` structures can be passed to the Microsoft Win32 API **PtInRect** function as follows:</span></span>  
  
```  
BOOL PtInRect(const RECT *lprc, POINT pt);  
```  
  
 <span data-ttu-id="b7683-204">다음과 같은 플랫폼 호출 정의를 사용하여 구조체를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-204">You can pass structures using the following platform invoke definition:</span></span>  
  
```vb  
Class Win32API      
   Declare Auto Function PtInRect Lib "User32.dll" _  
    (ByRef r As Rect, p As Point) As Boolean  
End Class  
```  
  
```csharp  
class Win32API {  
   [DllImport("User32.dll")]  
   public static extern Bool PtInRect(ref Rect r, Point p);  
}  
```  
  
 <span data-ttu-id="b7683-205">관리되지 않는 API는 `RECT`에 대한 포인터가 함수에 전달될 것으로 예상하기 때문에 `Rect` 값 형식은 참조로 전달되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-205">The `Rect` value type must be passed by reference because the unmanaged API is expecting a pointer to a `RECT` to be passed to the function.</span></span> <span data-ttu-id="b7683-206">관리되지 않는 API는 `POINT`가 스택에서 전달될 것으로 예상하기 때문에 `Point` 값 형식은 값으로 전달되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-206">The `Point` value type is passed by value because the unmanaged API expects the `POINT` to be passed on the stack.</span></span> <span data-ttu-id="b7683-207">이러한 미묘한 차이가 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-207">This subtle difference is very important.</span></span> <span data-ttu-id="b7683-208">참조는 비관리 코드에 포인터로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-208">References are passed to unmanaged code as pointers.</span></span> <span data-ttu-id="b7683-209">값은 스택에서 비관리 코드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-209">Values are passed to unmanaged code on the stack.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7683-210">형식이 지정된 형식이 구조체로 마샬링된 경우 형식 내의 필드에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-210">When a formatted type is marshaled as a structure, only the fields within the type are accessible.</span></span> <span data-ttu-id="b7683-211">형식에 메서드, 속성 또는 이벤트가 있는 경우 비관리 코드에서 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-211">If the type has methods, properties, or events, they are inaccessible from unmanaged code.</span></span>  
  
 <span data-ttu-id="b7683-212">고정된 멤버 레이아웃이 있는 경우 클래스를 비관리 코드에 C 스타일 구조체로 마샬링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-212">Classes can also be marshaled to unmanaged code as C-style structures, provided they have fixed member layout.</span></span> <span data-ttu-id="b7683-213">클래스에 대한 멤버 레이아웃 정보도 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성을 통해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-213">The member layout information for a class is also provided with the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute.</span></span> <span data-ttu-id="b7683-214">고정 레이아웃의 값 형식과 고정 레이아웃의 클래스 간에 주요 차이점은 비관리 코드로 마샬링되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-214">The main difference between value types with fixed layout and classes with fixed layout is the way in which they are marshaled to unmanaged code.</span></span> <span data-ttu-id="b7683-215">값 형식은 스택에서 값으로 전달되므로 호출 수신자가 형식의 멤버를 변경해도 변경 내용이 호출자에게 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-215">Value types are passed by value (on the stack) and consequently any changes made to the members of the type by the callee are not seen by the caller.</span></span> <span data-ttu-id="b7683-216">참조 형식은 참조로 전달되므로(스택에서 형식에 대한 참조가 전달됨) 호출 수신자가 형식의 blittable 형식 멤버를 변경할 경우 모든 변경 내용이 호출자에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-216">Reference types are passed by reference (a reference to the type is passed on the stack); consequently, all changes made to blittable-type members of a type by the callee are seen by the caller.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7683-217">참조 형식에 non-blittable 형식 멤버가 있을 경우 변환이 두 번 필요합니다. 첫 번째는 인수가 관리되지 않는 쪽에 전달될 때이고 두 번째는 호출에서 반환될 때입니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-217">If a reference type has members of non-blittable types, conversion is required twice: the first time when an argument is passed to the unmanaged side and the second time on return from the call.</span></span> <span data-ttu-id="b7683-218">이러한 추가 오버헤드로 인해 호출자가 호출 수신자에 의한 변경 내용을 보려는 경우 In/Out 매개 변수를 인수에 명시적으로 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-218">Due to this added overhead, In/Out parameters must be explicitly applied to an argument if the caller wants to see changes made by the callee.</span></span>  
  
 <span data-ttu-id="b7683-219">다음 예제에서 `SystemTime` 클래스는 순차적 멤버 레이아웃을 사용하며 Win32 API **GetSystemTime** 함수에 전달될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-219">In the following example, the `SystemTime` class has sequential member layout and can be passed to the Win32 API **GetSystemTime** function.</span></span>  
  
```vb  
<StructLayout(LayoutKind.Sequential)> Public Class SystemTime  
   Public wYear As System.UInt16  
   Public wMonth As System.UInt16  
   Public wDayOfWeek As System.UInt16  
   Public wDay As System.UInt16  
   Public wHour As System.UInt16  
   Public wMinute As System.UInt16  
   Public wSecond As System.UInt16  
   Public wMilliseconds As System.UInt16  
End Class  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
   public class SystemTime {  
   public ushort wYear;   
   public ushort wMonth;  
   public ushort wDayOfWeek;   
   public ushort wDay;   
   public ushort wHour;   
   public ushort wMinute;   
   public ushort wSecond;   
   public ushort wMilliseconds;   
}  
```  
  
 <span data-ttu-id="b7683-220">**GetSystemTime** 함수는 다음과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-220">The **GetSystemTime** function is defined as follows:</span></span>  
  
```  
void GetSystemTime(SYSTEMTIME* SystemTime);  
```  
  
 <span data-ttu-id="b7683-221">**GetSystemTime**에 해당하는 플랫폼 호출 정의는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-221">The equivalent platform invoke definition for **GetSystemTime** is as follows:</span></span>  
  
```vb  
Public Class Win32  
   Declare Auto Sub GetSystemTime Lib "Kernel32.dll" (ByVal sysTime _  
   As SystemTime)  
End Class  
```  
  
```csharp  
class Win32API {  
   [DllImport("Kernel32.dll", CharSet=CharSet.Auto)]  
   public static extern void GetSystemTime(SystemTime st);  
}  
```  
  
 <span data-ttu-id="b7683-222">`SystemTime`이 값 형식이 아니라 클래스이기 때문에 `SystemTime` 인수는 참조 인수로 형식화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-222">Notice that the `SystemTime` argument is not typed as a reference argument because `SystemTime` is a class, not a value type.</span></span> <span data-ttu-id="b7683-223">값 형식과 달리 클래스는 항상 참조로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-223">Unlike value types, classes are always passed by reference.</span></span>  
  
 <span data-ttu-id="b7683-224">다음 코드 예제에서는 `SetXY`라는 메서드가 있는 다른 `Point` 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-224">The following code example shows a different `Point` class that has a method called `SetXY`.</span></span> <span data-ttu-id="b7683-225">형식이 순차적 레이아웃을 사용하므로 비관리 코드에 전달되고 구조체로 마샬링될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-225">Because the type has sequential layout, it can be passed to unmanaged code and marshaled as a structure.</span></span> <span data-ttu-id="b7683-226">그러나 개체가 참조로 전달되는 경우에도 `SetXY` 멤버는 비관리 코드에서 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-226">However, the `SetXY` member is not callable from unmanaged code, even though the object is passed by reference.</span></span>  
  
```vb  
<StructLayout(LayoutKind.Sequential)> Public Class Point  
   Private x, y As Integer  
   Public Sub SetXY(x As Integer, y As Integer)  
      Me.x = x  
      Me.y = y  
   End Sub  
End Class  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public class Point {  
   int x, y;  
   public void SetXY(int x, int y){   
      this.x = x;  
      this.y = y;  
   }  
}  
```  
  
<a name="cpcondefaultmarshalingforvaluetypesanchor3"></a>   
### <a name="value-types-used-in-com-interop"></a><span data-ttu-id="b7683-227">COM Interop에서 사용되는 값 형식</span><span class="sxs-lookup"><span data-stu-id="b7683-227">Value Types Used in COM Interop</span></span>  
 <span data-ttu-id="b7683-228">형식이 지정된 형식을 COM interop 메서드 호출에 전달할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-228">Formatted types can also be passed to COM interop method calls.</span></span> <span data-ttu-id="b7683-229">실제로 형식 라이브러리로 내보내는 경우 값 형식이 자동으로 구조체로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-229">In fact, when exported to a type library, value types are automatically converted to structures.</span></span> <span data-ttu-id="b7683-230">다음 예제에서 볼 수 있듯이, `Point` 값 형식은 이름이 `Point`인 형식 정의(typedef)가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-230">As the following example shows, the `Point` value type becomes a type definition (typedef) with the name `Point`.</span></span> <span data-ttu-id="b7683-231">형식 라이브러리의 다른 위치에 있는 `Point` 값 형식에 대한 모든 참조가 `Point` typedef로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-231">All references to the `Point` value type elsewhere in the type library are replaced with the `Point` typedef.</span></span>  
  
 <span data-ttu-id="b7683-232">**형식 라이브러리 표현**</span><span class="sxs-lookup"><span data-stu-id="b7683-232">**Type library representation**</span></span>  
  
```  
typedef struct tagPoint {  
   int x;  
   int y;  
} Point;  
interface _Graphics {  
   …  
   HRESULT SetPoint ([in] Point p)  
   HRESULT SetPointRef ([in,out] Point *p)  
   HRESULT GetPoint ([out,retval] Point *p)  
}  
```  
  
 <span data-ttu-id="b7683-233">값과 참조를 플랫폼 호출로 마샬링하는 데 사용되는 것과 동일한 규칙이 COM 인터페이스를 통해 마샬링할 때도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-233">The same rules used to marshal values and references to platform invoke calls are used when marshaling through COM interfaces.</span></span> <span data-ttu-id="b7683-234">예를 들어 `Point` 값 형식의 인스턴스가 .NET Framework에서 COM으로 전달되는 경우 `Point`가 값으로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-234">For example, when an instance of the `Point` value type is passed from the .NET Framework to COM, the `Point` is passed by value.</span></span> <span data-ttu-id="b7683-235">`Point` 값 형식이 참조로 전달되는 경우에는 `Point`에 대한 포인터가 스택에서 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-235">If the `Point` value type is passed by reference, a pointer to a `Point` is passed on the stack.</span></span> <span data-ttu-id="b7683-236">interop 마샬러는 두 방향에서 모두 더 높은 수준의 간접 참조(**Point \*\***)를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-236">The interop marshaler does not support higher levels of indirection (**Point \*\***) in either direction.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7683-237">내보낸 형식 라이브러리에서 명시적 레이아웃을 표현할 수 없기 때문에 <xref:System.Runtime.InteropServices.LayoutKind> 열거형 값이 **Explicit**로 설정된 구조체는 COM interop에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-237">Structures having the <xref:System.Runtime.InteropServices.LayoutKind> enumeration value set to **Explicit** cannot be used in COM interop because the exported type library cannot express an explicit layout.</span></span>  
  
<a name="cpcondefaultmarshalingforvaluetypesanchor1"></a>   
### <a name="system-value-types"></a><span data-ttu-id="b7683-238">시스템 값 형식</span><span class="sxs-lookup"><span data-stu-id="b7683-238">System Value Types</span></span>  
 <span data-ttu-id="b7683-239"><xref:System> 네임스페이스에는 런타임 기본 형식의 boxed 형식을 나타내는 여러 개의 값 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-239">The <xref:System> namespace has several value types that represent the boxed form of the runtime primitive types.</span></span> <span data-ttu-id="b7683-240">예를 들어 값 형식 <xref:System.Int32?displayProperty=nameWithType> 구조체는 **ELEMENT_TYPE_I4**의 boxed 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-240">For example, the value type <xref:System.Int32?displayProperty=nameWithType> structure represents the boxed form of **ELEMENT_TYPE_I4**.</span></span> <span data-ttu-id="b7683-241">다른 형식이 지정된 형식처럼 이러한 형식을 구조체로 마샬링하는 대신 boxing하는 기본 형식과 동일한 방식으로 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-241">Instead of marshaling these types as structures, as other formatted types are, you marshal them in the same way as the primitive types they box.</span></span> <span data-ttu-id="b7683-242">따라서 **System.Int32**는 **long** 형식의 단일 멤버를 포함하는 구조체가 아니라 **ELEMENT_TYPE_I4**로 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-242">**System.Int32** is therefore marshaled as **ELEMENT_TYPE_I4** instead of as a structure containing a single member of type **long**.</span></span> <span data-ttu-id="b7683-243">다음 표에는 기본 형식의 boxed 표현인 **System** 네임스페이스의 값 형식 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-243">The following table contains a list of the value types in the **System** namespace that are boxed representations of primitive types.</span></span>  
  
|<span data-ttu-id="b7683-244">시스템 값 형식</span><span class="sxs-lookup"><span data-stu-id="b7683-244">System value type</span></span>|<span data-ttu-id="b7683-245">요소 형식</span><span class="sxs-lookup"><span data-stu-id="b7683-245">Element type</span></span>|  
|-----------------------|------------------|  
|<xref:System.Boolean?displayProperty=nameWithType>|<span data-ttu-id="b7683-246">**ELEMENT_TYPE_BOOLEAN**</span><span class="sxs-lookup"><span data-stu-id="b7683-246">**ELEMENT_TYPE_BOOLEAN**</span></span>|  
|<xref:System.SByte?displayProperty=nameWithType>|<span data-ttu-id="b7683-247">**ELEMENT_TYPE_I1**</span><span class="sxs-lookup"><span data-stu-id="b7683-247">**ELEMENT_TYPE_I1**</span></span>|  
|<xref:System.Byte?displayProperty=nameWithType>|<span data-ttu-id="b7683-248">**ELEMENT_TYPE_UI1**</span><span class="sxs-lookup"><span data-stu-id="b7683-248">**ELEMENT_TYPE_UI1**</span></span>|  
|<xref:System.Char?displayProperty=nameWithType>|<span data-ttu-id="b7683-249">**ELEMENT_TYPE_CHAR**</span><span class="sxs-lookup"><span data-stu-id="b7683-249">**ELEMENT_TYPE_CHAR**</span></span>|  
|<xref:System.Int16?displayProperty=nameWithType>|<span data-ttu-id="b7683-250">**ELEMENT_TYPE_I2**</span><span class="sxs-lookup"><span data-stu-id="b7683-250">**ELEMENT_TYPE_I2**</span></span>|  
|<xref:System.UInt16?displayProperty=nameWithType>|<span data-ttu-id="b7683-251">**ELEMENT_TYPE_U2**</span><span class="sxs-lookup"><span data-stu-id="b7683-251">**ELEMENT_TYPE_U2**</span></span>|  
|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="b7683-252">**ELEMENT_TYPE_I4**</span><span class="sxs-lookup"><span data-stu-id="b7683-252">**ELEMENT_TYPE_I4**</span></span>|  
|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="b7683-253">**ELEMENT_TYPE_U4**</span><span class="sxs-lookup"><span data-stu-id="b7683-253">**ELEMENT_TYPE_U4**</span></span>|  
|<xref:System.Int64?displayProperty=nameWithType>|<span data-ttu-id="b7683-254">**ELEMENT_TYPE_I8**</span><span class="sxs-lookup"><span data-stu-id="b7683-254">**ELEMENT_TYPE_I8**</span></span>|  
|<xref:System.UInt64?displayProperty=nameWithType>|<span data-ttu-id="b7683-255">**ELEMENT_TYPE_U8**</span><span class="sxs-lookup"><span data-stu-id="b7683-255">**ELEMENT_TYPE_U8**</span></span>|  
|<xref:System.Single?displayProperty=nameWithType>|<span data-ttu-id="b7683-256">**ELEMENT_TYPE_R4**</span><span class="sxs-lookup"><span data-stu-id="b7683-256">**ELEMENT_TYPE_R4**</span></span>|  
|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="b7683-257">**ELEMENT_TYPE_R8**</span><span class="sxs-lookup"><span data-stu-id="b7683-257">**ELEMENT_TYPE_R8**</span></span>|  
|<xref:System.String?displayProperty=nameWithType>|<span data-ttu-id="b7683-258">**ELEMENT_TYPE_STRING**</span><span class="sxs-lookup"><span data-stu-id="b7683-258">**ELEMENT_TYPE_STRING**</span></span>|  
|<xref:System.IntPtr?displayProperty=nameWithType>|<span data-ttu-id="b7683-259">**ELEMENT_TYPE_I**</span><span class="sxs-lookup"><span data-stu-id="b7683-259">**ELEMENT_TYPE_I**</span></span>|  
|<xref:System.UIntPtr?displayProperty=nameWithType>|<span data-ttu-id="b7683-260">**ELEMENT_TYPE_U**</span><span class="sxs-lookup"><span data-stu-id="b7683-260">**ELEMENT_TYPE_U**</span></span>|  
  
 <span data-ttu-id="b7683-261">**System** 네임스페이스의 다른 값 형식은 다르게 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-261">Some other value types in the **System** namespace are handled differently.</span></span> <span data-ttu-id="b7683-262">비관리 코드에는 이러한 형식에 대해 잘 설정된 형식이 이미 있으므로 마샬러에 특수 마샬링 규칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-262">Because the unmanaged code already has well-established formats for these types, the marshaler has special rules for marshaling them.</span></span> <span data-ttu-id="b7683-263">다음 표에서는 **System** 네임스페이스의 특수 값 형식과 마샬링되는 관리되지 않는 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-263">The following table lists the special value types in the **System** namespace, as well as the unmanaged type they are marshaled to.</span></span>  
  
|<span data-ttu-id="b7683-264">시스템 값 형식</span><span class="sxs-lookup"><span data-stu-id="b7683-264">System value type</span></span>|<span data-ttu-id="b7683-265">IDL 형식</span><span class="sxs-lookup"><span data-stu-id="b7683-265">IDL type</span></span>|  
|-----------------------|--------------|  
|<xref:System.DateTime?displayProperty=nameWithType>|<span data-ttu-id="b7683-266">**DATE**</span><span class="sxs-lookup"><span data-stu-id="b7683-266">**DATE**</span></span>|  
|<xref:System.Decimal?displayProperty=nameWithType>|<span data-ttu-id="b7683-267">**DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="b7683-267">**DECIMAL**</span></span>|  
|<xref:System.Guid?displayProperty=nameWithType>|<span data-ttu-id="b7683-268">**GUID**</span><span class="sxs-lookup"><span data-stu-id="b7683-268">**GUID**</span></span>|  
|<xref:System.Drawing.Color?displayProperty=nameWithType>|<span data-ttu-id="b7683-269">**OLE_COLOR**</span><span class="sxs-lookup"><span data-stu-id="b7683-269">**OLE_COLOR**</span></span>|  
  
 <span data-ttu-id="b7683-270">다음 코드에서는 Stdole2 형식 라이브러리에 있는 관리되지 않는 형식 **DATE**, **GUID**, **DECIMAL** 및 **OLE_COLOR**의 정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-270">The following code shows the definition of the unmanaged types **DATE**, **GUID**, **DECIMAL**, and **OLE_COLOR** in the Stdole2 type library.</span></span>  
  
#### <a name="type-library-representation"></a><span data-ttu-id="b7683-271">형식 라이브러리 표현</span><span class="sxs-lookup"><span data-stu-id="b7683-271">Type library representation</span></span>  
  
```  
typedef double DATE;  
typedef DWORD OLE_COLOR;  
  
typedef struct tagDEC {  
    USHORT    wReserved;  
    BYTE      scale;  
    BYTE      sign;  
    ULONG     Hi32;  
    ULONGLONG Lo64;  
} DECIMAL;  
  
typedef struct tagGUID {  
    DWORD Data1;  
    WORD  Data2;  
    WORD  Data3;  
    BYTE  Data4[ 8 ];  
} GUID;  
```  
  
 <span data-ttu-id="b7683-272">다음 코드에서는 관리되는 `IValueTypes` 인터페이스의 해당 정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b7683-272">The following code shows the corresponding definitions in the managed `IValueTypes` interface.</span></span>  
  
```vb  
Public Interface IValueTypes  
   Sub M1(d As System.DateTime)  
   Sub M2(d As System.Guid)  
   Sub M3(d As System.Decimal)  
   Sub M4(d As System.Drawing.Color)  
End Interface  
```  
  
```csharp  
public interface IValueTypes {  
   void M1(System.DateTime d);  
   void M2(System.Guid d);  
   void M3(System.Decimal d);  
   void M4(System.Drawing.Color d);  
}  
```  
  
#### <a name="type-library-representation"></a><span data-ttu-id="b7683-273">형식 라이브러리 표현</span><span class="sxs-lookup"><span data-stu-id="b7683-273">Type library representation</span></span>  
  
```  
[…]  
interface IValueTypes : IDispatch {  
   HRESULT M1([in] DATE d);  
   HRESULT M2([in] GUID d);  
   HRESULT M3([in] DECIMAL d);  
   HRESULT M4([in] OLE_COLOR d);  
};  
```  
  
## <a name="see-also"></a><span data-ttu-id="b7683-274">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7683-274">See Also</span></span>  
 [<span data-ttu-id="b7683-275">Blittable 형식 및 비 Blittable 형식</span><span class="sxs-lookup"><span data-stu-id="b7683-275">Blittable and Non-Blittable Types</span></span>](../../../docs/framework/interop/blittable-and-non-blittable-types.md)  
 [<span data-ttu-id="b7683-276">복사 및 고정</span><span class="sxs-lookup"><span data-stu-id="b7683-276">Copying and Pinning</span></span>](../../../docs/framework/interop/copying-and-pinning.md)  
 [<span data-ttu-id="b7683-277">배열에 대한 기본 마샬링</span><span class="sxs-lookup"><span data-stu-id="b7683-277">Default Marshaling for Arrays</span></span>](../../../docs/framework/interop/default-marshaling-for-arrays.md)  
 [<span data-ttu-id="b7683-278">개체에 대한 마샬링</span><span class="sxs-lookup"><span data-stu-id="b7683-278">Default Marshaling for Objects</span></span>](../../../docs/framework/interop/default-marshaling-for-objects.md)  
 [<span data-ttu-id="b7683-279">문자열에 대한 기본 마샬링</span><span class="sxs-lookup"><span data-stu-id="b7683-279">Default Marshaling for Strings</span></span>](../../../docs/framework/interop/default-marshaling-for-strings.md)
