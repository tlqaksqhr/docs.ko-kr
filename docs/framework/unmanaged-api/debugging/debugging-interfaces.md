---
title: 디버깅 인터페이스
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 991e333c53101a2be2a8a19d3960c3d0879619be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33409934"
---
# <a name="debugging-interfaces"></a><span data-ttu-id="904e2-102">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-102">Debugging Interfaces</span></span>
<span data-ttu-id="904e2-103">이 단원에서는 CLR(공용 언어 런타임)에서 실행되는 프로그램의 디버깅을 처리하는 관리되지 않는 인터페이스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-103">This section describes the unmanaged interfaces that handle the debugging of a program that is executing in the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="904e2-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="904e2-104">In This Section</span></span>  
 [<span data-ttu-id="904e2-105">ICLRDataEnumMemoryRegions 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-105">ICLRDataEnumMemoryRegions Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)  
 <span data-ttu-id="904e2-106">호출자가 지정하는 메모리 영역을 열거하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-106">Provides a method to enumerate regions of memory that are specified by callers.</span></span>  
  
 [<span data-ttu-id="904e2-107">ICLRDataEnumMemoryRegionsCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-107">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)  
 <span data-ttu-id="904e2-108">지정된 메모리 영역을 열거하려고 시도한 결과를 디버거에 보고하는 콜백 메서드를 `EnumMemoryRegions`에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-108">Provides a callback method for `EnumMemoryRegions` to report to the debugger, the result of an attempt to enumerate a specified region of memory.</span></span>  
  
 [<span data-ttu-id="904e2-109">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-109">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)  
 <span data-ttu-id="904e2-110">대상 CLR 프로세스와 상호 작용하기 위한 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-110">Provides methods for interaction with a target CLR process.</span></span>  
  
 [<span data-ttu-id="904e2-111">ICLRDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-111">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 <span data-ttu-id="904e2-112">데이터 액세스 서비스 계층에서 대상 프로세스의 가상 메모리 영역을 조작하는 데 사용하는 `ICLRDataTarget`의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-112">A subclass of `ICLRDataTarget` that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
 [<span data-ttu-id="904e2-113">ICLRDataTarget3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-113">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 <span data-ttu-id="904e2-114">서브 클래스 [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) 예외 정보에 대 한 액세스를 제공 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-114">A subclass of [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
 [<span data-ttu-id="904e2-115">ICLRDebugging 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-115">ICLRDebugging Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md)  
 <span data-ttu-id="904e2-116">디버깅을 위해 모듈을 로드 및 언로드하는 작업을 처리하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-116">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
 [<span data-ttu-id="904e2-117">ICLRDebuggingLibraryProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-117">ICLRDebuggingLibraryProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md)  
 <span data-ttu-id="904e2-118">에 포함 되어는 [ProvideLibrary 메서드](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) 메서드 라이브러리 공급자 콜백 인터페이스 공용 언어 런타임 버전별 디버깅 라이브러리를 찾아서에 로드할 요청 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-118">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
 [<span data-ttu-id="904e2-119">ICLRMetadataLocator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-119">ICLRMetadataLocator Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)  
 <span data-ttu-id="904e2-120">데이터 액세스 서비스 계층에서 대상 프로세스의 어셈블리 메타데이터를 찾는 데 사용되는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-120">Interface used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
 [<span data-ttu-id="904e2-121">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-121">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 <span data-ttu-id="904e2-122">개발자가 CLR 환경에서 응용 프로그램을 디버깅하는 데 사용할 수 있는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-122">Provides methods that allow developers to debug applications in the CLR environment.</span></span>  
  
 [<span data-ttu-id="904e2-123">ICorDebugAppDomain Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-123">ICorDebugAppDomain Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md)  
 <span data-ttu-id="904e2-124">응용 프로그램 도메인 디버깅에 사용하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-124">Provides methods for debugging application domains.</span></span>  
  
 [<span data-ttu-id="904e2-125">ICorDebugAppDomain2 Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-125">ICorDebugAppDomain2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-interface.md)  
 <span data-ttu-id="904e2-126">배열, 포인터, 함수 포인터 및 ByRef 형식에 사용할 수 있는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-126">Provides methods to work with arrays, pointers, function pointers, and ByRef types.</span></span> <span data-ttu-id="904e2-127">이 인터페이스는 `ICorDebugAppDomain` 인터페이스의 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-127">This interface is an extension of the `ICorDebugAppDomain` interface.</span></span>  
  
 [<span data-ttu-id="904e2-128">ICorDebugAppDomain3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-128">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)  
 <span data-ttu-id="904e2-129">응용 프로그램 도메인에서 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 형식으로 작동하기 위한 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-129">Provides methods to work with the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain.</span></span> <span data-ttu-id="904e2-130">이 인터페이스는 `ICorDebugAppDomain` 및 `ICorDebugAppDomain2` 인터페이스의 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-130">This interface is an extension of the `ICorDebugAppDomain` and `ICorDebugAppDomain2` interfaces.</span></span>  
  
 [<span data-ttu-id="904e2-131">ICorDebugAppDomain4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-131">ICorDebugAppDomain4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)  
 <span data-ttu-id="904e2-132">논리적으로 확장 된 [ICorDebugAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md) 인터페이스를 COM 호출 가능 래퍼에서 관리 되는 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-132">Logically extends the [ICorDebugAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md) interface to get a managed object from a COM callable wrapper.</span></span>  
  
 [<span data-ttu-id="904e2-133">ICorDebugAppDomainEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-133">ICorDebugAppDomainEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md)  
 <span data-ttu-id="904e2-134">열거형의 다음 위치에서 시작하여 지정된 수만큼 `ICorDebugAppDomain` 값을 반환하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-134">Provides a method that returns a specified number of `ICorDebugAppDomain` values starting at the next location in the enumeration.</span></span>  
  
 [<span data-ttu-id="904e2-135">ICorDebugArrayValue Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-135">ICorDebugArrayValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-interface.md)  
 <span data-ttu-id="904e2-136">1차원 배열이나 다차원 배열을 나타내는 `ICorDebugHeapValue`의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-136">A subclass of `ICorDebugHeapValue` that represents a single-dimensional or multi-dimensional array.</span></span>  
  
 [<span data-ttu-id="904e2-137">ICorDebugAssembly Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-137">ICorDebugAssembly Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md)  
 <span data-ttu-id="904e2-138">어셈블리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-138">Represents an assembly.</span></span>  
  
 [<span data-ttu-id="904e2-139">ICorDebugAssembly2 Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-139">ICorDebugAssembly2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly2-interface.md)  
 <span data-ttu-id="904e2-140">어셈블리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-140">Represents an assembly.</span></span> <span data-ttu-id="904e2-141">이 인터페이스는 `ICorDebugAssembly` 인터페이스의 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-141">This interface is an extension of the `ICorDebugAssembly` interface.</span></span>  
  
 [<span data-ttu-id="904e2-142">ICorDebugAssembly3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-142">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 <span data-ttu-id="904e2-143">논리적으로 확장 된 [ICorDebugAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md) 컨테이너 어셈블리 및 해당 포함 된에 대 한 지원을 제공 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-143">Logically extends the [ICorDebugAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md) interface to provide support for container assemblies and their contained assemblies.</span></span> <span data-ttu-id="904e2-144">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="904e2-144">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="904e2-145">ICorDebugAssemblyEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-145">ICorDebugAssemblyEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassemblyenum-interface.md)  
 <span data-ttu-id="904e2-146">`ICorDebugEnum` 메서드를 구현하고 `ICorDebugAssembly` 배열을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-146">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugAssembly` arrays.</span></span>  
  
 [<span data-ttu-id="904e2-147">ICorDebugBlockingObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-147">ICorDebugBlockingObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
 <span data-ttu-id="904e2-148">목록에 대 한 열거자를 제공 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-148">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
 [<span data-ttu-id="904e2-149">ICorDebugBoxValue Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-149">ICorDebugBoxValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-interface.md)  
 <span data-ttu-id="904e2-150">boxed 값 클래스 개체를 나타내는 `ICorDebugHeapValue`의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-150">A subclass of `ICorDebugHeapValue` that represents a boxed value class object.</span></span>  
  
 [<span data-ttu-id="904e2-151">ICorDebugBreakpoint Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-151">ICorDebugBreakpoint Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-interface.md)  
 <span data-ttu-id="904e2-152">함수의 중단점 또는 값에 대한 조사식 위치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-152">Represents a breakpoint in a function or a watch point on a value.</span></span>  
  
 [<span data-ttu-id="904e2-153">ICorDebugBreakpointEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-153">ICorDebugBreakpointEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-interface.md)  
 <span data-ttu-id="904e2-154">`ICorDebugEnum` 메서드를 구현하고 `ICorDebugBreakpoint` 배열을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-154">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugBreakpoint` arrays.</span></span>  
  
 [<span data-ttu-id="904e2-155">ICorDebugChain Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-155">ICorDebugChain Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md)  
 <span data-ttu-id="904e2-156">실제 또는 논리 호출 스택의 세그먼트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-156">Represents a segment of a physical or logical call stack.</span></span>  
  
 [<span data-ttu-id="904e2-157">ICorDebugChainEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-157">ICorDebugChainEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchainenum-interface.md)  
 <span data-ttu-id="904e2-158">`ICorDebugEnum` 메서드를 구현하고 `ICorDebugChain` 배열을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-158">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugChain` arrays.</span></span>  
  
 [<span data-ttu-id="904e2-159">ICorDebugClass Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-159">ICorDebugClass Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)  
 <span data-ttu-id="904e2-160">기본 또는 복합(즉, 사용자 정의) 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-160">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="904e2-161">형식이 제네릭이면 `ICorDebugClass`는 인스턴스화되지 않은 제네릭 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-161">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
 [<span data-ttu-id="904e2-162">ICorDebugClass2 Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-162">ICorDebugClass2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-interface.md)  
 <span data-ttu-id="904e2-163">제네릭 클래스나 <xref:System.Type> 형식의 메서드 매개 변수를 사용하는 클래스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-163">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="904e2-164">이 인터페이스는 `ICorDebugClass`를 확장한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-164">This interface extends `ICorDebugClass`.</span></span>  
  
 [<span data-ttu-id="904e2-165">ICorDebugCode Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-165">ICorDebugCode Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)  
 <span data-ttu-id="904e2-166">MSIL(Microsoft Intermediate Language) 코드나 네이티브 코드의 세그먼트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-166">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
 [<span data-ttu-id="904e2-167">ICorDebugCode2 Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-167">ICorDebugCode2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md)  
 <span data-ttu-id="904e2-168">`ICorDebugCode`의 기능을 확장하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-168">Provides methods that extend the capabilities of `ICorDebugCode`.</span></span>  
  
 [<span data-ttu-id="904e2-169">ICorDebugCode3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-169">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 <span data-ttu-id="904e2-170">확장 하는 메서드를 제공 [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md) 및 [ICorDebugCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md) 관리 되는 반환 값에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-170">Provides a method that extends [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md) and [ICorDebugCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md) to provide information about a managed return value.</span></span>  
  
 [<span data-ttu-id="904e2-171">ICorDebugCode4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-171">ICorDebugCode4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)  
 <span data-ttu-id="904e2-172">디버거를 지역 변수 및 함수에 인수를 열거 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-172">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
 [<span data-ttu-id="904e2-173">ICorDebugCodeEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-173">ICorDebugCodeEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-interface.md)  
 <span data-ttu-id="904e2-174">`ICorDebugEnum` 메서드를 구현하고 `ICorDebugCode` 배열을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-174">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugCode` arrays.</span></span>  
  
 [<span data-ttu-id="904e2-175">ICorDebugComObjectValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-175">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)  
 <span data-ttu-id="904e2-176">캐시된 인터페이스 개체를 검색하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-176">Provides methods to retrieve cached interface objects.</span></span>  
  
 [<span data-ttu-id="904e2-177">ICorDebugContext Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-177">ICorDebugContext Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontext-interface.md)  
 <span data-ttu-id="904e2-178">컨텍스트 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-178">Represents a context object.</span></span> <span data-ttu-id="904e2-179">이 인터페이스는 아직 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-179">This interface has not been implemented yet.</span></span>  
  
 [<span data-ttu-id="904e2-180">ICorDebugController Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-180">ICorDebugController Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-interface.md)  
 <span data-ttu-id="904e2-181"><xref:System.Diagnostics.Process>나 <xref:System.AppDomain> 같이 코드 실행 컨텍스트를 제어할 수 있는 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-181">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
 [<span data-ttu-id="904e2-182">ICorDebugDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-182">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 <span data-ttu-id="904e2-183">특정 대상 프로세스에 대한 액세스를 제공하는 콜백 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-183">Provides a callback interface that provides access to a particular target process.</span></span>  
  
 [<span data-ttu-id="904e2-184">ICorDebugDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-184">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 <span data-ttu-id="904e2-185">논리적으로 확장 된 [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-185">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="904e2-186">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="904e2-186">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="904e2-187">ICorDebugDataTarget3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-187">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)  
 <span data-ttu-id="904e2-188">논리적으로 확장 된 [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) 로드 된 모듈에 대 한 정보를 제공 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-188">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span> <span data-ttu-id="904e2-189">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="904e2-189">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="904e2-190">ICorDebugDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-190">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 <span data-ttu-id="904e2-191">모든 `ICorDebug` 디버그 이벤트가 파생되는 기본 인터페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-191">Defines the base interface from which all `ICorDebug` debug events derive.</span></span> <span data-ttu-id="904e2-192">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="904e2-192">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="904e2-193">ICorDebugEditAndContinueErrorInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-193">ICorDebugEditAndContinueErrorInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinueerrorinfo-interface.md)  
 <span data-ttu-id="904e2-194">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-194">Obsolete.</span></span> <span data-ttu-id="904e2-195">이 인터페이스를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="904e2-195">Do not use this interface.</span></span>  
  
 [<span data-ttu-id="904e2-196">ICorDebugEditAndContinueSnapshot Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-196">ICorDebugEditAndContinueSnapshot Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinuesnapshot-interface.md)  
 <span data-ttu-id="904e2-197">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-197">Obsolete.</span></span> <span data-ttu-id="904e2-198">이 인터페이스를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="904e2-198">Do not use this interface.</span></span>  
  
 [<span data-ttu-id="904e2-199">ICorDebugEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-199">ICorDebugEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)  
 <span data-ttu-id="904e2-200">열거자를 디버깅할 수 있는 추상 기본 인터페이스로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-200">Serves as the abstract base interface for debugging enumerators.</span></span>  
  
 [<span data-ttu-id="904e2-201">ICorDebugErrorInfoEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-201">ICorDebugErrorInfoEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugerrorinfoenum-interface.md)  
 <span data-ttu-id="904e2-202">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-202">Obsolete.</span></span> <span data-ttu-id="904e2-203">이 인터페이스를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="904e2-203">Do not use this interface.</span></span>  
  
 [<span data-ttu-id="904e2-204">ICorDebugEval Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-204">ICorDebugEval Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-interface.md)  
 <span data-ttu-id="904e2-205">디버깅 중인 코드의 컨텍스트 내에서 디버거가 코드를 실행할 수 있도록 하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-205">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
 [<span data-ttu-id="904e2-206">ICorDebugEval2 Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-206">ICorDebugEval2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-interface.md)  
 <span data-ttu-id="904e2-207">제네릭 형식을 지원하도록 `ICorDebugEval`을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-207">Extends `ICorDebugEval` to provide support for generic types.</span></span>  
  
 [<span data-ttu-id="904e2-208">ICorDebugExceptionDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-208">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 <span data-ttu-id="904e2-209">확장 된 [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) 예외 이벤트를 지 원하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-209">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support exception events.</span></span> <span data-ttu-id="904e2-210">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="904e2-210">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="904e2-211">ICorDebugExceptionObjectCallStackEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-211">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
 <span data-ttu-id="904e2-212">예외 개체에 포함된 호출 스택 정보에 대한 열거자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-212">Provides an enumerator for call stack information that is embedded in an exception object.</span></span>  
  
 [<span data-ttu-id="904e2-213">ICorDebugExceptionObjectValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-213">ICorDebugExceptionObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)  
 <span data-ttu-id="904e2-214">확장 된 [ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md) 인터페이스는 관리 되는 예외 개체에서 스택 추적 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-214">Extends the [ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md) interface to provide stack trace information from a managed exception object.</span></span>  
  
 [<span data-ttu-id="904e2-215">ICorDebugFrame Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-215">ICorDebugFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md)  
 <span data-ttu-id="904e2-216">현재 스택의 프레임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-216">Represents a frame on the current stack.</span></span>  
  
 [<span data-ttu-id="904e2-217">ICorDebugFrameEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-217">ICorDebugFrameEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframeenum-interface.md)  
 <span data-ttu-id="904e2-218">`ICorDebugEnum` 메서드를 구현하고 `ICorDebugFrame` 배열을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-218">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugFrame` arrays.</span></span>  
  
 [<span data-ttu-id="904e2-219">ICorDebugFunction Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-219">ICorDebugFunction Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md)  
 <span data-ttu-id="904e2-220">관리되는 함수 또는 메서드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-220">Represents a managed function or method.</span></span>  
  
 [<span data-ttu-id="904e2-221">ICorDebugFunction2 Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-221">ICorDebugFunction2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-interface.md)  
 <span data-ttu-id="904e2-222">`ICorDebugFunction`의 기능을 논리적으로 확장하여 "내 코드만" 단계별 실행 디버깅을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-222">Logically extends `ICorDebugFunction` to provide support for Just My Code step-through debugging.</span></span>  
  
 [<span data-ttu-id="904e2-223">ICorDebugFunction3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-223">ICorDebugFunction3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-interface.md)  
 <span data-ttu-id="904e2-224">논리적으로 확장 된 [ICorDebugFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md) ReJIT 요청의 코드에 대 한 액세스를 제공 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-224">Logically extends the [ICorDebugFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md) interface to provide access to code from a ReJIT request.</span></span>  
  
 [<span data-ttu-id="904e2-225">ICorDebugFunctionBreakpoint Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-225">ICorDebugFunctionBreakpoint Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-interface.md)  
 <span data-ttu-id="904e2-226">함수에서 중단점을 지원하기 위해 `ICorDebugBreakpoint`를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-226">Extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
 [<span data-ttu-id="904e2-227">ICorDebugGCReferenceEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-227">ICorDebugGCReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
 <span data-ttu-id="904e2-228">가비지 수집되는 개체에 대한 열거자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-228">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
 [<span data-ttu-id="904e2-229">ICorDebugGenericValue Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-229">ICorDebugGenericValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-interface.md)  
 <span data-ttu-id="904e2-230">모든 값에 적용되는 `ICorDebugValue`의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-230">A subclass of `ICorDebugValue` that applies to all values.</span></span> <span data-ttu-id="904e2-231">이 인터페이스에서는 값의 Get 및 Set 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-231">This interface provides Get and Set methods for the value.</span></span>  
  
 [<span data-ttu-id="904e2-232">ICorDebugGuidToTypeEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-232">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
 <span data-ttu-id="904e2-233">GUID를 매핑하는 개체와 그에 해당하는 `ICorDebugType` 개체에 대한 열거자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-233">Provides an enumerator for an object that maps GUIDs and their corresponding `ICorDebugType` objects.</span></span>  
  
 [<span data-ttu-id="904e2-234">ICorDebugHandleValue Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-234">ICorDebugHandleValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-interface.md)  
 <span data-ttu-id="904e2-235">디버거에서 가비지 수집을 위해 핸들을 만든 대상 참조 값을 나타내는 `ICorDebugReferenceValue`의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-235">A subclass of `ICorDebugReferenceValue` that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
 [<span data-ttu-id="904e2-236">ICorDebugHeapEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-236">ICorDebugHeapEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
 <span data-ttu-id="904e2-237">관리되는 힙의 개체에 대한 열거자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-237">Provides an enumerator for objects on the managed heap.</span></span>  
  
 [<span data-ttu-id="904e2-238">ICorDebugHeapSegmentEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-238">ICorDebugHeapSegmentEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
 <span data-ttu-id="904e2-239">관리되는 힙 메모리 영역에 대한 열거자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-239">Provides an enumerator for the memory regions of the managed heap.</span></span>  
  
 [<span data-ttu-id="904e2-240">ICorDebugHeapValue Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-240">ICorDebugHeapValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-interface.md)  
 <span data-ttu-id="904e2-241">CLR 가비지 수집기에서 수집한 개체를 나타내는 `ICorDebugValue`의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-241">A subclass of `ICorDebugValue` that represents an object that has been collected by the CLR garbage collector.</span></span>  
  
 [<span data-ttu-id="904e2-242">ICorDebugHeapValue2 Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-242">ICorDebugHeapValue2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue2-interface1.md)  
 <span data-ttu-id="904e2-243">런타임 핸들에 대한 지원을 제공하는 `ICorDebugHeapValue`의 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-243">An extension of `ICorDebugHeapValue` that provides support for runtime handles.</span></span>  
  
 [<span data-ttu-id="904e2-244">ICorDebugHeapValue3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-244">ICorDebugHeapValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md)  
 <span data-ttu-id="904e2-245">개체의 모니터 잠금 속성을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-245">Exposes the monitor lock properties of objects.</span></span>  
  
 [<span data-ttu-id="904e2-246">ICorDebugILCode 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-246">ICorDebugILCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)  
 <span data-ttu-id="904e2-247">IL(중간 언어) 코드 세그먼트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-247">Represents a segment of intermediate language (IL) code.</span></span>  
  
 [<span data-ttu-id="904e2-248">ICorDebugILCode2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-248">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 <span data-ttu-id="904e2-249">논리적으로 확장 된 [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) 함수의 로컬 변수 서명에 대해 토큰을 반환 하 고 프로파일러의 계측 된 IL (중간 언어)를 매핑하는 메서드를 제공 하는 인터페이스 원래 메서드 IL 오프셋 오프셋 합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-249">Logically extends the [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
 [<span data-ttu-id="904e2-250">ICorDebugILFrame Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-250">ICorDebugILFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-interface.md)  
 <span data-ttu-id="904e2-251">MSIL 코드의 스택 프레임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-251">Represents a stack frame of MSIL code.</span></span>  
  
 [<span data-ttu-id="904e2-252">ICorDebugILFrame2 Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-252">ICorDebugILFrame2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-interface.md)  
 <span data-ttu-id="904e2-253">`ICorDebugILFrame`에서 논리적으로 확장된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-253">A logical extension of `ICorDebugILFrame`.</span></span>  
  
 [<span data-ttu-id="904e2-254">ICorDebugILFrame3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-254">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)  
 <span data-ttu-id="904e2-255">함수의 반환 값을 캡슐화하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-255">Provides a method that encapsulates the return value of a function.</span></span>  
  
 [<span data-ttu-id="904e2-256">ICorDebugILFrame4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-256">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 <span data-ttu-id="904e2-257">IL(중간 언어) 코드의 스택 프레임에서 로컬 변수 및 코드에 액세스하는 데 사용할 수 있는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-257">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="904e2-258">디버거가 프로파일러 ReJIT 계측에 추가된 변수와 코드에 액세스할 수 있는지는 매개 변수를 통해 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-258">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
 [<span data-ttu-id="904e2-259">ICorDebugInstanceFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-259">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 <span data-ttu-id="904e2-260">인스턴스 필드에 대한 디버그 기호 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-260">Represents the debug symbol information for an instance field.</span></span> <span data-ttu-id="904e2-261">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="904e2-261">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="904e2-262">ICorDebugInternalFrame Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-262">ICorDebugInternalFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-interface.md)  
 <span data-ttu-id="904e2-263">디버거의 프레임 형식을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-263">Identifies frame types for the debugger.</span></span>  
  
 [<span data-ttu-id="904e2-264">ICorDebugInternalFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-264">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 <span data-ttu-id="904e2-265">스택 주소 및 위치와 관련 하 여 내부 프레임에 대 한 정보를 제공 [ICorDebugFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-265">Provides information about internal frames, including stack address and position in relation to [ICorDebugFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md) objects.</span></span>  
  
 [<span data-ttu-id="904e2-266">ICorDebugLoadedModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-266">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 <span data-ttu-id="904e2-267">로드된 모듈에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-267">Provides information about a loaded module.</span></span> <span data-ttu-id="904e2-268">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="904e2-268">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="904e2-269">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-269">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)  
 <span data-ttu-id="904e2-270">디버거 콜백을 처리하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-270">Provides methods to process debugger callbacks.</span></span>  
  
 [<span data-ttu-id="904e2-271">ICorDebugManagedCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-271">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 <span data-ttu-id="904e2-272">디버거 예외 처리 및 MDA(관리 디버깅 도우미)를 지원하기 위한 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-272">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="904e2-273">`ICorDebugManagedCallback2`은 `ICorDebugManagedCallback`에서 논리적으로 확장된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-273">`ICorDebugManagedCallback2` is a logical extension of `ICorDebugManagedCallback`.</span></span>  
  
 [<span data-ttu-id="904e2-274">ICorDebugManagedCallback3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-274">ICorDebugManagedCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-interface.md)  
 <span data-ttu-id="904e2-275">활성화된 사용자 지정 디버거 알림이 발생했음을 나타내는 콜백 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-275">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
 [<span data-ttu-id="904e2-276">ICorDebugMDA 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-276">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 <span data-ttu-id="904e2-277">MDA(관리 디버깅 도우미) 메시지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-277">Represents a managed debugging assistant (MDA) message.</span></span>  
  
 [<span data-ttu-id="904e2-278">ICorDebugMemoryBuffer 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-278">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 <span data-ttu-id="904e2-279">메모리 내 버퍼를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-279">Represents an in-memory buffer.</span></span> <span data-ttu-id="904e2-280">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="904e2-280">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="904e2-281">ICorDebugMergedAssemblyRecord 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-281">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 <span data-ttu-id="904e2-282">병합된 어셈블리에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-282">Provides information about a merged assembly.</span></span> <span data-ttu-id="904e2-283">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="904e2-283">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="904e2-284">ICorDebugMetaDataLocator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-284">ICorDebugMetaDataLocator Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-interface.md)  
 <span data-ttu-id="904e2-285">디버거에 메타데이터 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-285">Provides metadata information to the debugger.</span></span>  
  
 [<span data-ttu-id="904e2-286">ICorDebugModule Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-286">ICorDebugModule Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-interface.md)  
 <span data-ttu-id="904e2-287">실행 파일이나 DLL(동적 연결 라이브러리)인 CLR 모듈을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-287">Represents a CLR module, which is either an executable or a dynamic-link library (DLL).</span></span>  
  
 [<span data-ttu-id="904e2-288">ICorDebugModule2 Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-288">ICorDebugModule2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-interface.md)  
 <span data-ttu-id="904e2-289">`ICorDebugModule`에서 논리적으로 확장된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-289">Serves as a logical extension to `ICorDebugModule`.</span></span>  
  
 [<span data-ttu-id="904e2-290">ICorDebugModule3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-290">ICorDebugModule3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-interface.md)  
 <span data-ttu-id="904e2-291">동적 모듈에 대한 기호 판독기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-291">Creates a symbol reader for a dynamic module.</span></span>  
  
 [<span data-ttu-id="904e2-292">ICorDebugModuleBreakpoint Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-292">ICorDebugModuleBreakpoint Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-interface.md)  
 <span data-ttu-id="904e2-293">특정 모듈에 액세스할 수 있도록 `ICorDebugBreakpoint`를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-293">Extends `ICorDebugBreakpoint` to provide access to specific modules.</span></span>  
  
 [<span data-ttu-id="904e2-294">ICorDebugModuleDebugEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-294">ICorDebugModuleDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
 <span data-ttu-id="904e2-295">확장 된 [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) 모듈 수준 이벤트를 지 원하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-295">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span> <span data-ttu-id="904e2-296">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="904e2-296">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="904e2-297">ICorDebugModuleEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-297">ICorDebugModuleEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-interface.md)  
 <span data-ttu-id="904e2-298">`ICorDebugEnum` 메서드를 구현하고 `ICorDebugModule` 배열을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-298">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugModule` arrays.</span></span>  
  
 [<span data-ttu-id="904e2-299">ICorDebugMutableDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-299">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 <span data-ttu-id="904e2-300">확장 된 [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) 인터페이스를 변경할 수 있는 데이터 대상을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-300">Extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
 [<span data-ttu-id="904e2-301">ICorDebugNativeFrame Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-301">ICorDebugNativeFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-interface.md)  
 <span data-ttu-id="904e2-302">네이티브 프레임에 사용되는 특수화된 `ICorDebugFrame` 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-302">A specialized implementation of `ICorDebugFrame` used for native frames.</span></span>  
  
 [<span data-ttu-id="904e2-303">ICorDebugNativeFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-303">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 <span data-ttu-id="904e2-304">자식 및 부모 프레임 관계를 테스트하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-304">Provides methods that test for child and parent frame relationships.</span></span>  
  
 [<span data-ttu-id="904e2-305">ICorDebugObjectEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-305">ICorDebugObjectEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-interface.md)  
 <span data-ttu-id="904e2-306">`ICorDebugEnum` 메서드를 구현하고 RVA(Relative Virtual Address)로 개체의 배열을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-306">Implements `ICorDebugEnum` methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
 [<span data-ttu-id="904e2-307">ICorDebugObjectValue Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-307">ICorDebugObjectValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md)  
 <span data-ttu-id="904e2-308">개체가 들어 있는 값을 나타내는 `ICorDebugValue`의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-308">A subclass of `ICorDebugValue` that represents a value that contains an object.</span></span>  
  
 [<span data-ttu-id="904e2-309">ICorDebugObjectValue2 Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-309">ICorDebugObjectValue2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue2-interface.md)  
 <span data-ttu-id="904e2-310">상속 및 재정의 기능을 지원하도록 `ICorDebugObjectValue`를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-310">Extends `ICorDebugObjectValue` to support inheritance and overrides.</span></span>  
  
 [<span data-ttu-id="904e2-311">ICorDebugProcess Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-311">ICorDebugProcess Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md)  
 <span data-ttu-id="904e2-312">관리 코드를 실행하는 프로세스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-312">Represents a process that is executing managed code.</span></span>  
  
 [<span data-ttu-id="904e2-313">ICorDebugProcess2 Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-313">ICorDebugProcess2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-interface1.md)  
 <span data-ttu-id="904e2-314">`ICorDebugProcess`에서 논리적으로 확장된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-314">A logical extension of `ICorDebugProcess`.</span></span>  
  
 [<span data-ttu-id="904e2-315">ICorDebugProcess3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-315">ICorDebugProcess3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)  
 <span data-ttu-id="904e2-316">사용자 지정 디버거 알림을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-316">Controls custom debugger notifications.</span></span>  
  
 [<span data-ttu-id="904e2-317">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-317">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 <span data-ttu-id="904e2-318">확장 된 [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) 관리 되는 개체의 가비지 수집에 대 한 정보를 제공 하 고 디버거가 응용 프로그램에서 이미지를 로드 하는지 여부를 결정 하는 관리 되는 힙에 대 한 액세스를 지원 하기 위해 인터페이스의 로컬 네이티브 이미지 캐시 합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-318">Extends the [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application's local native image cache.</span></span>  
  
 [<span data-ttu-id="904e2-319">ICorDebugProcess6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-319">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 <span data-ttu-id="904e2-320">논리적으로 확장 된 [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) 가상 모듈 분할 및 네이티브 예외 디버그 이벤트에서 인코딩 되는 관리 되는 디버그 이벤트 디코딩 등의 기능을 활성화 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-320">Logically extends the [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span> <span data-ttu-id="904e2-321">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="904e2-321">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="904e2-322">ICorDebugProcess7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-322">ICorDebugProcess7 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)  
 <span data-ttu-id="904e2-323">대상 프로세스에서 디버거가 메모리 내 메타데이터 업데이트를 처리하도록 구성하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-323">Provides a method that configures the debugger to handle in-memory metadata updates in the target process.</span></span>  
  
 [<span data-ttu-id="904e2-324">ICorDebugProcess8 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-324">ICorDebugProcess8 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)  
 <span data-ttu-id="904e2-325">논리적으로 확장 된 [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) 인터페이스를 특정 유형의 사용할지 [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) 예외 콜백을 합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-325">Logically extends the [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interface to enable or disable certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
 [<span data-ttu-id="904e2-326">ICorDebugProcessEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-326">ICorDebugProcessEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocessenum-interface.md)  
 <span data-ttu-id="904e2-327">`ICorDebugEnum` 메서드를 구현하고 `ICorDebugProcess` 배열을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-327">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugProcess` arrays.</span></span>  
  
 [<span data-ttu-id="904e2-328">ICorDebugReferenceValue Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-328">ICorDebugReferenceValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-interface.md)  
 <span data-ttu-id="904e2-329">참조 형식을 지원하는 `ICorDebugValue`의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-329">A subclass of `ICorDebugValue` that supports reference types.</span></span>  
  
 [<span data-ttu-id="904e2-330">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-330">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 <span data-ttu-id="904e2-331">코드가 실행되고 있는 컴퓨터에서 사용할 수 있는 레지스터 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-331">Represents the set of registers available on the machine that is currently executing code.</span></span>  
  
 [<span data-ttu-id="904e2-332">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-332">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 <span data-ttu-id="904e2-333">64개 이상의 레지스터가 있는 하드웨어 플랫폼의 `ICorDebugRegisterSet` 기능을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-333">Extends the capabilities of `ICorDebugRegisterSet` for hardware platforms that have more than 64 registers.</span></span>  
  
 [<span data-ttu-id="904e2-334">ICorDebugRemote 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-334">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 <span data-ttu-id="904e2-335">시작할 수 있거나 원격 대상 프로세스에 관리되는 디버거를 연결할 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-335">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
 [<span data-ttu-id="904e2-336">ICorDebugRemoteTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-336">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 <span data-ttu-id="904e2-337">CLR 환경에서 Silverlight 기반 응용 프로그램을 디버깅하는 데 사용할 수 있는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-337">Provides methods that enable you to debug Silverlight-based applications in the CLR environment.</span></span>  
  
 [<span data-ttu-id="904e2-338">ICorDebugRuntimeUnwindableFrame 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-338">ICorDebugRuntimeUnwindableFrame Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugruntimeunwindableframe-interface.md)  
 <span data-ttu-id="904e2-339">프레임을 해제하는 데 CLR(공용 언어 런타임)을 필요로 하는 관리되지 않는 메서드에 대한 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-339">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
 [<span data-ttu-id="904e2-340">ICorDebugStackWalk 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-340">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)  
 <span data-ttu-id="904e2-341">스레드 스택에서 관리되는 메서드나 프레임을 가져오기 위한 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-341">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
 [<span data-ttu-id="904e2-342">ICorDebugStaticFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-342">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 <span data-ttu-id="904e2-343">정적 필드에 대한 디버그 기호 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-343">Represents the debug symbol information for a static field.</span></span> <span data-ttu-id="904e2-344">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="904e2-344">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="904e2-345">ICorDebugStepper Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-345">ICorDebugStepper Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-interface.md)  
 <span data-ttu-id="904e2-346">디버거에서 수행하는 코드 실행 단계를 나타내며, 명령의 실행/완료를 구분하는 식별자로 사용되고, 단계를 취소하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-346">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
 [<span data-ttu-id="904e2-347">ICorDebugStepper2 Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-347">ICorDebugStepper2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper2-interface1.md)  
 <span data-ttu-id="904e2-348">JMC(내 코드만) 디버깅을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-348">Provides support for Just My Code (JMC) debugging.</span></span>  
  
 [<span data-ttu-id="904e2-349">ICorDebugStepperEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-349">ICorDebugStepperEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-interface.md)  
 <span data-ttu-id="904e2-350">`ICorDebugEnum` 메서드를 구현하고 `ICorDebugStepper` 배열을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-350">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugStepper` arrays.</span></span>  
  
 [<span data-ttu-id="904e2-351">ICorDebugStringValue Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-351">ICorDebugStringValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-interface.md)  
 <span data-ttu-id="904e2-352">문자열 값에 적용되는 `ICorDebugHeapValue`의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-352">A subclass of `ICorDebugHeapValue` that applies to string values.</span></span>  
  
 [<span data-ttu-id="904e2-353">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-353">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 <span data-ttu-id="904e2-354">디버그 기호 정보를 검색하는 데 사용할 수 있는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-354">Provides methods that can be used to retrieve debug symbol information.</span></span> <span data-ttu-id="904e2-355">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="904e2-355">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="904e2-356">ICorDebugSymbolProvider2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-356">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)  
 <span data-ttu-id="904e2-357">논리적으로 확장 된 [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) 추가 디버그 기호 정보를 검색 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-357">Logically extends the [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span> <span data-ttu-id="904e2-358">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="904e2-358">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="904e2-359">ICorDebugThread Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-359">ICorDebugThread Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-interface.md)  
 <span data-ttu-id="904e2-360">프로세스의 스레드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-360">Represents a thread in a process.</span></span> <span data-ttu-id="904e2-361">`ICorDebugThread` 인스턴스의 수명은 이 인스턴스가 나타내는 스레드의 수명과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-361">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
 [<span data-ttu-id="904e2-362">ICorDebugThread2 Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-362">ICorDebugThread2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interface.md)  
 <span data-ttu-id="904e2-363">`ICorDebugThread`에서 논리적으로 확장된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-363">Serves as a logical extension to `ICorDebugThread`.</span></span>  
  
 [<span data-ttu-id="904e2-364">ICorDebugThread3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-364">ICorDebugThread3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md)  
 <span data-ttu-id="904e2-365">진입점을 제공 된 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) 및 해당 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-365">Provides the entry point to the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
 [<span data-ttu-id="904e2-366">ICorDebugThread4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-366">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 <span data-ttu-id="904e2-367">스레드 차단 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-367">Provides thread blocking information.</span></span>  
  
 [<span data-ttu-id="904e2-368">ICorDebugThreadEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-368">ICorDebugThreadEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-interface1.md)  
 <span data-ttu-id="904e2-369">`ICorDebugEnum` 메서드를 구현하고 `ICorDebugThread` 배열을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-369">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugThread` arrays.</span></span>  
  
 [<span data-ttu-id="904e2-370">ICorDebugType Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-370">ICorDebugType Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md)  
 <span data-ttu-id="904e2-371">기본 또는 복합(즉, 사용자 정의) 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-371">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="904e2-372">형식이 제네릭이면 `ICorDebugType`는 인스턴스화된 제네릭 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-372">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
 [<span data-ttu-id="904e2-373">ICorDebugType2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-373">ICorDebugType2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)  
 <span data-ttu-id="904e2-374">확장 된 [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) 기본 형식 또는 복합 (사용자 정의) 형식을의 형식 식별자를 검색 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-374">Extends the [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
 [<span data-ttu-id="904e2-375">ICorDebugTypeEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="904e2-375">ICorDebugTypeEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtypeenum-interface.md)  
 <span data-ttu-id="904e2-376">`ICorDebugEnum` 메서드를 구현하고 `ICorDebugType` 배열을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-376">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugType` arrays.</span></span>  
  
 [<span data-ttu-id="904e2-377">ICorDebugUnmanagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-377">ICorDebugUnmanagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)  
 <span data-ttu-id="904e2-378">CLR에 직접적으로 관련되지 않은 네이티브 이벤트에 대한 알림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-378">Provides notification of native events that are not directly related to the CLR.</span></span>  
  
 <span data-ttu-id="904e2-379">"ICorDebugValue"</span><span class="sxs-lookup"><span data-stu-id="904e2-379">"ICorDebugValue"</span></span>  
 <span data-ttu-id="904e2-380">디버깅 중인 프로세스의 읽기 또는 쓰기 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-380">Represents a read or write value in the process being debugged.</span></span>  
  
 <span data-ttu-id="904e2-381">"ICorDebugValue2"</span><span class="sxs-lookup"><span data-stu-id="904e2-381">"ICorDebugValue2"</span></span>  
 <span data-ttu-id="904e2-382">`ICorDebugValue`을 지원하기 위해 `ICorDebugType`에서 확장된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-382">Extends `ICorDebugValue` to provide support for `ICorDebugType`.</span></span>  
  
 [<span data-ttu-id="904e2-383">ICorDebugValue3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-383">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 <span data-ttu-id="904e2-384">2GB 보다 큰 배열에 대 한 지원을 제공 하는 "ICorDebugValue" 및 "ICorDebugValue2" 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-384">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
 <span data-ttu-id="904e2-385">"ICorDebugValueBreakpoint"</span><span class="sxs-lookup"><span data-stu-id="904e2-385">"ICorDebugValueBreakpoint"</span></span>  
 <span data-ttu-id="904e2-386">특정 값에 액세스할 수 있도록 `ICorDebugBreakpoint`를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-386">Extends `ICorDebugBreakpoint` to provide access to specific values.</span></span>  
  
 <span data-ttu-id="904e2-387">"ICorDebugValueEnum"</span><span class="sxs-lookup"><span data-stu-id="904e2-387">"ICorDebugValueEnum"</span></span>  
 <span data-ttu-id="904e2-388">`ICorDebugEnum` 메서드를 구현하고 `ICorDebugValue` 배열을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-388">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugValue` arrays.</span></span>  
  
 [<span data-ttu-id="904e2-389">ICorDebugVariableHome 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-389">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 <span data-ttu-id="904e2-390">지역 변수 또는 함수 '의 인수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-390">Represents a local variable or argument of a function.</span></span>  
  
 [<span data-ttu-id="904e2-391">ICorDebugVariableHomeEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-391">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
 <span data-ttu-id="904e2-392">지역 변수 및 함수에 인수에는 열거자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-392">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
 [<span data-ttu-id="904e2-393">ICorDebugVariableSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-393">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 <span data-ttu-id="904e2-394">변수에 대한 디버그 기호 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-394">Retrieves the debug symbol information for a variable.</span></span> <span data-ttu-id="904e2-395">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="904e2-395">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="904e2-396">ICorDebugVirtualUnwinder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-396">ICorDebugVirtualUnwinder Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-interface.md)  
 <span data-ttu-id="904e2-397">스택 해제에 도움이 되는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-397">Provides methods to help in stack unwinding.</span></span> <span data-ttu-id="904e2-398">**.NET 네이티브 에서만 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="904e2-398">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="904e2-399">ICorPublish 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-399">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)  
 <span data-ttu-id="904e2-400">게시 프로세스에 대한 일반적인 인터페이스로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-400">Serves as the general interface for the publishing processes.</span></span>  
  
 [<span data-ttu-id="904e2-401">ICorPublishAppDomain 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-401">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)  
 <span data-ttu-id="904e2-402">응용 프로그램 도메인을 나타내고 응용 프로그램 도메인에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-402">Represents and provides information about an application domain.</span></span>  
  
 [<span data-ttu-id="904e2-403">ICorPublishAppDomainEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-403">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
 <span data-ttu-id="904e2-404">프로세스 내에 현재 있는 `ICorPublishAppDomain` 개체의 컬렉션을 이동하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-404">Provides methods that traverse a collection of `ICorPublishAppDomain` objects that currently exist within a process.</span></span>  
  
 [<span data-ttu-id="904e2-405">ICorPublishEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-405">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)  
 <span data-ttu-id="904e2-406">열거자를 게시하기 위한 추상 기본 열거형으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-406">Serves as the abstract base for publishing enumerators.</span></span>  
  
 [<span data-ttu-id="904e2-407">ICorPublishProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-407">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)  
 <span data-ttu-id="904e2-408">프로세스에 대한 정보에 액세스하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-408">Provides methods that access information about a process.</span></span>  
  
 [<span data-ttu-id="904e2-409">ICorPublishProcessEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="904e2-409">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
 <span data-ttu-id="904e2-410">`ICorPublishProcess` 개체의 컬렉션을 이동하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="904e2-410">Provides methods that traverse a collection of `ICorPublishProcess` objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="904e2-411">관련 단원</span><span class="sxs-lookup"><span data-stu-id="904e2-411">Related Sections</span></span>  
 [<span data-ttu-id="904e2-412">디버깅 Coclass</span><span class="sxs-lookup"><span data-stu-id="904e2-412">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="904e2-413">디버깅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="904e2-413">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [<span data-ttu-id="904e2-414">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="904e2-414">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [<span data-ttu-id="904e2-415">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="904e2-415">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
