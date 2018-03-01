---
title: "CorDebugInterfaceVersion 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorDebugInterfaceVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugInterfaceVersion
helpviewer_keywords:
- CorDebugInterfaceVersion enumeration [.NET Framework debugging]
ms.assetid: 7d1e6cd9-2a15-41c6-9b68-008705a4ed90
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2b5d28e6def34c9263d519c2eeb9cc432656bd1a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cordebuginterfaceversion-enumeration"></a><span data-ttu-id="3d142-102">CorDebugInterfaceVersion 열거형</span><span class="sxs-lookup"><span data-stu-id="3d142-102">CorDebugInterfaceVersion Enumeration</span></span>
<span data-ttu-id="3d142-103">인터페이스, 특정 .NET Framework 버전 또는 인터페이스가 적용된 .NET Framework 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3d142-103">Specifies an interface, a version of the .NET Framework, or a version of the .NET Framework in which an interface was introduced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d142-104">구문</span><span class="sxs-lookup"><span data-stu-id="3d142-104">Syntax</span></span>  
  
```  
typedef enum CorDebugInterfaceVersion {  
  
    CorDebugInvalidVersion            = 0,  
    CorDebugVersion_1_0               = CorDebugInvalidVersion + 1,  
  
    ver_ICorDebugManagedCallback      = CorDebugVersion_1_0,  
    ver_ICorDebugUnmanagedCallback    = CorDebugVersion_1_0,  
    ver_ICorDebug                     = CorDebugVersion_1_0,  
    ver_ICorDebugController           = CorDebugVersion_1_0,  
    ver_ICorDebugAppDomain            = CorDebugVersion_1_0,  
    ver_ICorDebugAssembly             = CorDebugVersion_1_0,  
    ver_ICorDebugProcess              = CorDebugVersion_1_0,  
    ver_ICorDebugBreakpoint           = CorDebugVersion_1_0,  
    ver_ICorDebugFunctionBreakpoint   = CorDebugVersion_1_0,  
    ver_ICorDebugModuleBreakpoint     = CorDebugVersion_1_0,  
    ver_ICorDebugValueBreakpoint      = CorDebugVersion_1_0,  
    ver_ICorDebugStepper              = CorDebugVersion_1_0,  
    ver_ICorDebugRegisterSet          = CorDebugVersion_1_0,  
    ver_ICorDebugThread               = CorDebugVersion_1_0,  
    ver_ICorDebugChain                = CorDebugVersion_1_0,  
    ver_ICorDebugFrame                = CorDebugVersion_1_0,  
    ver_ICorDebugILFrame              = CorDebugVersion_1_0,  
    ver_ICorDebugNativeFrame          = CorDebugVersion_1_0,  
    ver_ICorDebugModule               = CorDebugVersion_1_0,  
    ver_ICorDebugFunction             = CorDebugVersion_1_0,  
    ver_ICorDebugCode                 = CorDebugVersion_1_0,  
    ver_ICorDebugClass                = CorDebugVersion_1_0,  
    ver_ICorDebugEval                 = CorDebugVersion_1_0,  
    ver_ICorDebugValue                = CorDebugVersion_1_0,  
    ver_ICorDebugGenericValue         = CorDebugVersion_1_0,  
    ver_ICorDebugReferenceValue       = CorDebugVersion_1_0,  
    ver_ICorDebugHeapValue            = CorDebugVersion_1_0,  
    ver_ICorDebugObjectValue          = CorDebugVersion_1_0,  
    ver_ICorDebugBoxValue             = CorDebugVersion_1_0,  
    ver_ICorDebugStringValue          = CorDebugVersion_1_0,  
    ver_ICorDebugArrayValue           = CorDebugVersion_1_0,  
    ver_ICorDebugContext              = CorDebugVersion_1_0,  
    ver_ICorDebugEnum                 = CorDebugVersion_1_0,  
    ver_ICorDebugObjectEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugBreakpointEnum       = CorDebugVersion_1_0,  
    ver_ICorDebugStepperEnum          = CorDebugVersion_1_0,  
    ver_ICorDebugProcessEnum          = CorDebugVersion_1_0,  
    ver_ICorDebugThreadEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugFrameEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugChainEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugModuleEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugValueEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugCodeEnum             = CorDebugVersion_1_0,  
    ver_ICorDebugTypeEnum             = CorDebugVersion_1_0,  
    ver_ICorDebugErrorInfoEnum        = CorDebugVersion_1_0,  
    ver_ICorDebugAppDomainEnum        = CorDebugVersion_1_0,  
    ver_ICorDebugAssemblyEnum         = CorDebugVersion_1_0,  
    ver_ICorDebugEditAndContinueErrorInfo   
                                      = CorDebugVersion_1_0,  
    ver_ICorDebugEditAndContinueSnapshot   
                                      = CorDebugVersion_1_0,  
  
    CorDebugVersion_1_1               = CorDebugVersion_1_0 + 1,  
    // No interface definitions in version 1.1.  
  
    CorDebugVersion_2_0 = CorDebugVersion_1_1 + 1,  
  
    ver_ICorDebugManagedCallback2    = CorDebugVersion_2_0,  
    ver_ICorDebugAppDomain2          = CorDebugVersion_2_0,  
    ver_ICorDebugProcess2            = CorDebugVersion_2_0,  
    ver_ICorDebugStepper2            = CorDebugVersion_2_0,  
    ver_ICorDebugRegisterSet2        = CorDebugVersion_2_0,  
    ver_ICorDebugThread2             = CorDebugVersion_2_0,  
    ver_ICorDebugILFrame2            = CorDebugVersion_2_0,  
    ver_ICorDebugModule2             = CorDebugVersion_2_0,  
    ver_ICorDebugFunction2           = CorDebugVersion_2_0,  
    ver_ICorDebugCode2               = CorDebugVersion_2_0,  
    ver_ICorDebugClass2              = CorDebugVersion_2_0,  
    ver_ICorDebugValue2              = CorDebugVersion_2_0,  
    ver_ICorDebugEval2               = CorDebugVersion_2_0,  
    ver_ICorDebugObjectValue2        = CorDebugVersion_2_0,  
  
    // CLR v4 - next major CLR version after CLR v2  
    // Includes Silverlight 4  
    CorDebugVersion_4_0 = CorDebugVersion_2_0 + 1,  
  
    ver_ICorDebugThread3             = CorDebugVersion_4_0,  
    ver_ICorDebugThread4             = CorDebugVersion_4_0,  
    ver_ICorDebugStackWalk           = CorDebugVersion_4_0,  
    ver_ICorDebugNativeFrame2        = CorDebugVersion_4_0,  
    ver_ICorDebugInternalFrame2      = CorDebugVersion_4_0,  
    ver_ICorDebugRuntimeUnwindableFrame = CorDebugVersion_4_0,  
    ver_ICorDebugHeapValue3          = CorDebugVersion_4_0,  
    ver_ICorDebugBlockingObjectEnum  = CorDebugVersion_4_0,  
    ver_ICorDebugValue3 = CorDebugVersion_4_0,  
  
    CorDebugVersion_4_5 = CorDebugVersion_4_0 + 1,  
  
    ver_ICorDebugComObjectValue = CorDebugVersion_4_5,  
    ver_ICorDebugAppDomain3 = CorDebugVersion_4_5,  
    ver_ICorDebugCode3 = CorDebugVersion_4_5,  
    ver_ICorDebugILFrame3 = CorDebugVersion_4_5,  
  
    CorDebugLatestVersion = CorDebugVersion_4_5  
  
} CorDebugInterfaceVersion;  
```  
  
## <a name="members"></a><span data-ttu-id="3d142-105">멤버</span><span class="sxs-lookup"><span data-stu-id="3d142-105">Members</span></span>  
 <span data-ttu-id="3d142-106">다음 테이블에는 각 열거형 값에서 해당 인터페이스의 링크와</span><span class="sxs-lookup"><span data-stu-id="3d142-106">The following table provides links from each enumeration value to the corresponding interface.</span></span> <span data-ttu-id="3d142-107">인터페이스가 지원되는 첫 번째.NET Framework 버전이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d142-107">In addition, the table indicates the first version of the .NET Framework that the interface was supported in.</span></span>  
  
|<span data-ttu-id="3d142-108">멤버</span><span class="sxs-lookup"><span data-stu-id="3d142-108">Member</span></span>|<span data-ttu-id="3d142-109">설명</span><span class="sxs-lookup"><span data-stu-id="3d142-109">Specifies</span></span>|<span data-ttu-id="3d142-110">.NET Framework 버전</span><span class="sxs-lookup"><span data-stu-id="3d142-110">.NET Framework version</span></span>|  
|------------|---------------|----------------------------|  
|`CorDebugInvalidVersion`|<span data-ttu-id="3d142-111">.NET Framework 버전이 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3d142-111">The version of the .NET Framework is invalid.</span></span>|-|  
|`CorDebugVersion_1_0`|<span data-ttu-id="3d142-112">모든 서비스 팩을 포함한 .NET Framework 버전이 1.0입니다.</span><span class="sxs-lookup"><span data-stu-id="3d142-112">The version of the .NET Framework, including all its service packs, is 1.0.</span></span>|<span data-ttu-id="3d142-113">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-113">1.0</span></span>|  
|`CorDebugVersion_1_1`|<span data-ttu-id="3d142-114">모든 서비스 팩을 포함한 .NET Framework 버전이 1.1입니다.</span><span class="sxs-lookup"><span data-stu-id="3d142-114">The version of the .NET Framework, including all service packs, is 1.1.</span></span>|<span data-ttu-id="3d142-115">1.1</span><span class="sxs-lookup"><span data-stu-id="3d142-115">1.1</span></span>|  
|`CorDebugVersion_2_0`|<span data-ttu-id="3d142-116">모든 서비스 팩을 포함한 .NET Framework 버전이 2.0입니다.</span><span class="sxs-lookup"><span data-stu-id="3d142-116">The version of the .NET Framework, including all service packs, is 2.0.</span></span>|<span data-ttu-id="3d142-117">2.0</span><span class="sxs-lookup"><span data-stu-id="3d142-117">2.0</span></span>|  
|`CorDebugVersion_4_0`|<span data-ttu-id="3d142-118">모든 서비스 팩을 포함한 .NET Framework 버전이 4입니다.</span><span class="sxs-lookup"><span data-stu-id="3d142-118">The version of the .NET Framework, including all service packs, is 4.</span></span>|<span data-ttu-id="3d142-119">4</span><span class="sxs-lookup"><span data-stu-id="3d142-119">4</span></span>|  
|`CorDebugVersion_4_5`|<span data-ttu-id="3d142-120">모든 서비스 팩을 포함한 .NET Framework 버전이 4.5입니다.</span><span class="sxs-lookup"><span data-stu-id="3d142-120">The version of the .NET Framework, including all service packs, is 4.5.</span></span>|<span data-ttu-id="3d142-121">4.5</span><span class="sxs-lookup"><span data-stu-id="3d142-121">4.5</span></span>|  
|`ver_ICorDebugManagedCallback`|[<span data-ttu-id="3d142-122">ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="3d142-122">ICorDebugManagedCallback</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)|<span data-ttu-id="3d142-123">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-123">1.0</span></span>|  
|`ver_ICorDebugUnmanagedCallback`|[<span data-ttu-id="3d142-124">ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="3d142-124">ICorDebugUnmanagedCallback</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)|<span data-ttu-id="3d142-125">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-125">1.0</span></span>|  
|`ver_ICorDebug`|[<span data-ttu-id="3d142-126">ICorDebug</span><span class="sxs-lookup"><span data-stu-id="3d142-126">ICorDebug</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)|<span data-ttu-id="3d142-127">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-127">1.0</span></span>|  
|`ver_ICorDebugController`|[<span data-ttu-id="3d142-128">ICorDebugController</span><span class="sxs-lookup"><span data-stu-id="3d142-128">ICorDebugController</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-interface.md)|<span data-ttu-id="3d142-129">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-129">1.0</span></span>|  
|`ver_ICorDebugAppDomain`|[<span data-ttu-id="3d142-130">ICorDebugAppDomain</span><span class="sxs-lookup"><span data-stu-id="3d142-130">ICorDebugAppDomain</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md)|<span data-ttu-id="3d142-131">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-131">1.0</span></span>|  
|`ver_ICorDebugAssembly`|[<span data-ttu-id="3d142-132">ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="3d142-132">ICorDebugAssembly</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md)|<span data-ttu-id="3d142-133">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-133">1.0</span></span>|  
|`ver_ICorDebugProcess`|[<span data-ttu-id="3d142-134">ICorDebugProcess</span><span class="sxs-lookup"><span data-stu-id="3d142-134">ICorDebugProcess</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md)|<span data-ttu-id="3d142-135">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-135">1.0</span></span>|  
|`ver_ICorDebugBreakpoint`|[<span data-ttu-id="3d142-136">ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="3d142-136">ICorDebugBreakpoint</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-interface.md)|<span data-ttu-id="3d142-137">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-137">1.0</span></span>|  
|`ver_ICorDebugFunctionBreakpoint`|[<span data-ttu-id="3d142-138">ICorDebugFunctionBreakpoint</span><span class="sxs-lookup"><span data-stu-id="3d142-138">ICorDebugFunctionBreakpoint</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-interface.md)|<span data-ttu-id="3d142-139">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-139">1.0</span></span>|  
|`ver_ICorDebugModuleBreakpoint`|[<span data-ttu-id="3d142-140">ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="3d142-140">ICorDebugModuleBreakpoint</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-interface.md)|<span data-ttu-id="3d142-141">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-141">1.0</span></span>|  
|`ver_ICorDebugValueBreakpoint`|[<span data-ttu-id="3d142-142">ICorDebugValueBreakpoint</span><span class="sxs-lookup"><span data-stu-id="3d142-142">ICorDebugValueBreakpoint</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-interface.md)|<span data-ttu-id="3d142-143">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-143">1.0</span></span>|  
|`ver_ICorDebugStepper`|[<span data-ttu-id="3d142-144">ICorDebugStepper</span><span class="sxs-lookup"><span data-stu-id="3d142-144">ICorDebugStepper</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-interface.md)|<span data-ttu-id="3d142-145">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-145">1.0</span></span>|  
|`ver_ICorDebugRegisterSet`|[<span data-ttu-id="3d142-146">ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="3d142-146">ICorDebugRegisterSet</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)|<span data-ttu-id="3d142-147">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-147">1.0</span></span>|  
|`ver_ICorDebugThread`|[<span data-ttu-id="3d142-148">ICorDebugThread</span><span class="sxs-lookup"><span data-stu-id="3d142-148">ICorDebugThread</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-interface.md)|<span data-ttu-id="3d142-149">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-149">1.0</span></span>|  
|`ver_ICorDebugChain`|[<span data-ttu-id="3d142-150">ICorDebugChain</span><span class="sxs-lookup"><span data-stu-id="3d142-150">ICorDebugChain</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md)|<span data-ttu-id="3d142-151">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-151">1.0</span></span>|  
|`ver_ICorDebugFrame`|[<span data-ttu-id="3d142-152">ICorDebugFrame</span><span class="sxs-lookup"><span data-stu-id="3d142-152">ICorDebugFrame</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md)|<span data-ttu-id="3d142-153">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-153">1.0</span></span>|  
|`ver_ICorDebugILFrame`|[<span data-ttu-id="3d142-154">ICorDebugILFrame</span><span class="sxs-lookup"><span data-stu-id="3d142-154">ICorDebugILFrame</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-interface.md)|<span data-ttu-id="3d142-155">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-155">1.0</span></span>|  
|`ver_ICorDebugNativeFrame`|[<span data-ttu-id="3d142-156">ICorDebugNativeFrame</span><span class="sxs-lookup"><span data-stu-id="3d142-156">ICorDebugNativeFrame</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-interface.md)|<span data-ttu-id="3d142-157">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-157">1.0</span></span>|  
|`ver_ICorDebugModule`|[<span data-ttu-id="3d142-158">ICorDebugModule</span><span class="sxs-lookup"><span data-stu-id="3d142-158">ICorDebugModule</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-interface.md)|<span data-ttu-id="3d142-159">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-159">1.0</span></span>|  
|`ver_ICorDebugFunction`|[<span data-ttu-id="3d142-160">ICorDebugFunction</span><span class="sxs-lookup"><span data-stu-id="3d142-160">ICorDebugFunction</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md)|<span data-ttu-id="3d142-161">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-161">1.0</span></span>|  
|`ver_ICorDebugCode`|[<span data-ttu-id="3d142-162">ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="3d142-162">ICorDebugCode</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)|<span data-ttu-id="3d142-163">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-163">1.0</span></span>|  
|`ver_ICorDebugClass`|[<span data-ttu-id="3d142-164">ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="3d142-164">ICorDebugClass</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)|<span data-ttu-id="3d142-165">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-165">1.0</span></span>|  
|`ver_ICorDebugEval`|[<span data-ttu-id="3d142-166">ICorDebugEval</span><span class="sxs-lookup"><span data-stu-id="3d142-166">ICorDebugEval</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-interface.md)|<span data-ttu-id="3d142-167">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-167">1.0</span></span>|  
|`ver_ICorDebugValue`|[<span data-ttu-id="3d142-168">ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="3d142-168">ICorDebugValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md)|<span data-ttu-id="3d142-169">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-169">1.0</span></span>|  
|`ver_ICorDebugGenericValue`|[<span data-ttu-id="3d142-170">ICorDebugGenericValue</span><span class="sxs-lookup"><span data-stu-id="3d142-170">ICorDebugGenericValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-interface.md)|<span data-ttu-id="3d142-171">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-171">1.0</span></span>|  
|`ver_ICorDebugReferenceValue`|[<span data-ttu-id="3d142-172">ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="3d142-172">ICorDebugReferenceValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-interface.md)|<span data-ttu-id="3d142-173">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-173">1.0</span></span>|  
|`ver_ICorDebugHeapValue`|[<span data-ttu-id="3d142-174">ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="3d142-174">ICorDebugHeapValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-interface.md)|<span data-ttu-id="3d142-175">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-175">1.0</span></span>|  
|`ver_ICorDebugObjectValue`|[<span data-ttu-id="3d142-176">ICorDebugObjectValue</span><span class="sxs-lookup"><span data-stu-id="3d142-176">ICorDebugObjectValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md)|<span data-ttu-id="3d142-177">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-177">1.0</span></span>|  
|`ver_ICorDebugBoxValue`|[<span data-ttu-id="3d142-178">ICorDebugBoxValue</span><span class="sxs-lookup"><span data-stu-id="3d142-178">ICorDebugBoxValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-interface.md)|<span data-ttu-id="3d142-179">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-179">1.0</span></span>|  
|`ver_ICorDebugStringValue`|[<span data-ttu-id="3d142-180">ICorDebugStringValue</span><span class="sxs-lookup"><span data-stu-id="3d142-180">ICorDebugStringValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-interface.md)|<span data-ttu-id="3d142-181">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-181">1.0</span></span>|  
|`ver_ICorDebugArrayValue`|[<span data-ttu-id="3d142-182">ICorDebugArrayValue</span><span class="sxs-lookup"><span data-stu-id="3d142-182">ICorDebugArrayValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-interface.md)|<span data-ttu-id="3d142-183">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-183">1.0</span></span>|  
|`ver_ICorDebugContext`|[<span data-ttu-id="3d142-184">ICorDebugContext</span><span class="sxs-lookup"><span data-stu-id="3d142-184">ICorDebugContext</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontext-interface.md)|<span data-ttu-id="3d142-185">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-185">1.0</span></span>|  
|`ver_ICorDebugEnum`|[<span data-ttu-id="3d142-186">ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="3d142-186">ICorDebugEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)|<span data-ttu-id="3d142-187">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-187">1.0</span></span>|  
|`ver_ICorDebugObjectEnum`|[<span data-ttu-id="3d142-188">ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="3d142-188">ICorDebugObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-interface.md)|<span data-ttu-id="3d142-189">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-189">1.0</span></span>|  
|`ver_ICorDebugBreakpointEnum`|[<span data-ttu-id="3d142-190">ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="3d142-190">ICorDebugBreakpointEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-interface.md)|<span data-ttu-id="3d142-191">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-191">1.0</span></span>|  
|`ver_ICorDebugStepperEnum`|[<span data-ttu-id="3d142-192">ICorDebugStepperEnum</span><span class="sxs-lookup"><span data-stu-id="3d142-192">ICorDebugStepperEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-interface.md)|<span data-ttu-id="3d142-193">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-193">1.0</span></span>|  
|`ver_ICorDebugProcessEnum`|[<span data-ttu-id="3d142-194">ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="3d142-194">ICorDebugProcessEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocessenum-interface.md)|<span data-ttu-id="3d142-195">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-195">1.0</span></span>|  
|`ver_ICorDebugThreadEnum`|[<span data-ttu-id="3d142-196">ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="3d142-196">ICorDebugThreadEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-interface1.md)|<span data-ttu-id="3d142-197">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-197">1.0</span></span>|  
|`ver_ICorDebugFrameEnum`|[<span data-ttu-id="3d142-198">ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="3d142-198">ICorDebugFrameEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframeenum-interface.md)|<span data-ttu-id="3d142-199">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-199">1.0</span></span>|  
|`ver_ICorDebugChainEnum`|[<span data-ttu-id="3d142-200">ICorDebugChainEnum</span><span class="sxs-lookup"><span data-stu-id="3d142-200">ICorDebugChainEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchainenum-interface.md)|<span data-ttu-id="3d142-201">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-201">1.0</span></span>|  
|`ver_ICorDebugModuleEnum`|[<span data-ttu-id="3d142-202">ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="3d142-202">ICorDebugModuleEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-interface.md)|<span data-ttu-id="3d142-203">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-203">1.0</span></span>|  
|`ver_ICorDebugValueEnum`|[<span data-ttu-id="3d142-204">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="3d142-204">ICorDebugValueEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalueenum-interface.md)|<span data-ttu-id="3d142-205">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-205">1.0</span></span>|  
|`ver_ICorDebugCodeEnum`|[<span data-ttu-id="3d142-206">ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="3d142-206">ICorDebugCodeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-interface.md)|<span data-ttu-id="3d142-207">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-207">1.0</span></span>|  
|`ver_ICorDebugTypeEnum`|[<span data-ttu-id="3d142-208">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="3d142-208">ICorDebugTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtypeenum-interface.md)|<span data-ttu-id="3d142-209">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-209">1.0</span></span>|  
|`ver_ICorDebugErrorInfoEnum`|[<span data-ttu-id="3d142-210">ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="3d142-210">ICorDebugErrorInfoEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugerrorinfoenum-interface.md)|<span data-ttu-id="3d142-211">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-211">1.0</span></span>|  
|`ver_ICorDebugAppDomainEnum`|[<span data-ttu-id="3d142-212">ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="3d142-212">ICorDebugAppDomainEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md)|<span data-ttu-id="3d142-213">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-213">1.0</span></span>|  
|`ver_ICorDebugAssemblyEnum`|[<span data-ttu-id="3d142-214">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="3d142-214">ICorDebugAssemblyEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassemblyenum-interface.md)|<span data-ttu-id="3d142-215">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-215">1.0</span></span>|  
|`ver_ICorDebugEditAndContinueErrorInfo`|[<span data-ttu-id="3d142-216">ICorDebugEditAndContinueErrorInfo</span><span class="sxs-lookup"><span data-stu-id="3d142-216">ICorDebugEditAndContinueErrorInfo</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinueerrorinfo-interface.md)|<span data-ttu-id="3d142-217">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-217">1.0</span></span>|  
|`ver_ICorDebugEditAndContinueSnapshot`|[<span data-ttu-id="3d142-218">ICorDebugEditAndContinueSnapshot</span><span class="sxs-lookup"><span data-stu-id="3d142-218">ICorDebugEditAndContinueSnapshot</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinuesnapshot-interface.md)|<span data-ttu-id="3d142-219">1.0</span><span class="sxs-lookup"><span data-stu-id="3d142-219">1.0</span></span>|  
|`ver_ICorDebugManagedCallback2`|[<span data-ttu-id="3d142-220">ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="3d142-220">ICorDebugManagedCallback2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)|<span data-ttu-id="3d142-221">2.0</span><span class="sxs-lookup"><span data-stu-id="3d142-221">2.0</span></span>|  
|`ver_ICorDebugAppDomain2`|[<span data-ttu-id="3d142-222">ICorDebugAppDomain2</span><span class="sxs-lookup"><span data-stu-id="3d142-222">ICorDebugAppDomain2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-interface.md)|<span data-ttu-id="3d142-223">2.0</span><span class="sxs-lookup"><span data-stu-id="3d142-223">2.0</span></span>|  
|`ver_ICorDebugProcess2`|[<span data-ttu-id="3d142-224">ICorDebugProcess2</span><span class="sxs-lookup"><span data-stu-id="3d142-224">ICorDebugProcess2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-interface1.md)|<span data-ttu-id="3d142-225">2.0</span><span class="sxs-lookup"><span data-stu-id="3d142-225">2.0</span></span>|  
|`ver_ICorDebugStepper2`|[<span data-ttu-id="3d142-226">ICorDebugStepper2</span><span class="sxs-lookup"><span data-stu-id="3d142-226">ICorDebugStepper2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper2-interface1.md)|<span data-ttu-id="3d142-227">2.0</span><span class="sxs-lookup"><span data-stu-id="3d142-227">2.0</span></span>|  
|`ver_ICorDebugRegisterSet2`|[<span data-ttu-id="3d142-228">ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="3d142-228">ICorDebugRegisterSet2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)|<span data-ttu-id="3d142-229">2.0</span><span class="sxs-lookup"><span data-stu-id="3d142-229">2.0</span></span>|  
|`ver_ICorDebugThread2`|[<span data-ttu-id="3d142-230">ICorDebugThread2</span><span class="sxs-lookup"><span data-stu-id="3d142-230">ICorDebugThread2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interface.md)|<span data-ttu-id="3d142-231">2.0</span><span class="sxs-lookup"><span data-stu-id="3d142-231">2.0</span></span>|  
|`ver_ICorDebugILFrame2`|[<span data-ttu-id="3d142-232">ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="3d142-232">ICorDebugILFrame2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-interface.md)|<span data-ttu-id="3d142-233">2.0</span><span class="sxs-lookup"><span data-stu-id="3d142-233">2.0</span></span>|  
|`ver_ICorDebugModule2`|[<span data-ttu-id="3d142-234">ICorDebugModule2</span><span class="sxs-lookup"><span data-stu-id="3d142-234">ICorDebugModule2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-interface.md)|<span data-ttu-id="3d142-235">2.0</span><span class="sxs-lookup"><span data-stu-id="3d142-235">2.0</span></span>|  
|`ver_ICorDebugFunction2`|[<span data-ttu-id="3d142-236">ICorDebugFunction2</span><span class="sxs-lookup"><span data-stu-id="3d142-236">ICorDebugFunction2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-interface.md)|<span data-ttu-id="3d142-237">2.0</span><span class="sxs-lookup"><span data-stu-id="3d142-237">2.0</span></span>|  
|`ver_ICorDebugCode2`|[<span data-ttu-id="3d142-238">ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="3d142-238">ICorDebugCode2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md)|<span data-ttu-id="3d142-239">2.0</span><span class="sxs-lookup"><span data-stu-id="3d142-239">2.0</span></span>|  
|`ver_ICorDebugClass2`|<span data-ttu-id="3d142-240">"ICorDebugClass2"</span><span class="sxs-lookup"><span data-stu-id="3d142-240">"ICorDebugClass2"</span></span>|<span data-ttu-id="3d142-241">2.0</span><span class="sxs-lookup"><span data-stu-id="3d142-241">2.0</span></span>|  
|`ver_ICorDebugValue2`|<span data-ttu-id="3d142-242">"ICorDebugValue2"</span><span class="sxs-lookup"><span data-stu-id="3d142-242">"ICorDebugValue2"</span></span>|<span data-ttu-id="3d142-243">2.0</span><span class="sxs-lookup"><span data-stu-id="3d142-243">2.0</span></span>|  
|`ver_ICorDebugEval2`|<span data-ttu-id="3d142-244">"ICorDebugEval2"입니다.</span><span class="sxs-lookup"><span data-stu-id="3d142-244">The "ICorDebugEval2".</span></span>|<span data-ttu-id="3d142-245">2.0</span><span class="sxs-lookup"><span data-stu-id="3d142-245">2.0</span></span>|  
|`ver_ICorDebugObjectValue2`|<span data-ttu-id="3d142-246">"ICorDebugObjectValue2"</span><span class="sxs-lookup"><span data-stu-id="3d142-246">"ICorDebugObjectValue2"</span></span>|<span data-ttu-id="3d142-247">2.0</span><span class="sxs-lookup"><span data-stu-id="3d142-247">2.0</span></span>|  
|`ver_ICorDebugThread3`|[<span data-ttu-id="3d142-248">ICorDebugThread3</span><span class="sxs-lookup"><span data-stu-id="3d142-248">ICorDebugThread3</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md)|<span data-ttu-id="3d142-249">4</span><span class="sxs-lookup"><span data-stu-id="3d142-249">4</span></span>|  
|`ver_ICorDebugThread4`|[<span data-ttu-id="3d142-250">ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="3d142-250">ICorDebugThread4</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)|<span data-ttu-id="3d142-251">4</span><span class="sxs-lookup"><span data-stu-id="3d142-251">4</span></span>|  
|`ver_ICorDebugStackWalk`|[<span data-ttu-id="3d142-252">ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="3d142-252">ICorDebugStackWalk</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)|<span data-ttu-id="3d142-253">4</span><span class="sxs-lookup"><span data-stu-id="3d142-253">4</span></span>|  
|`ver_ICorDebugNativeFrame2`|[<span data-ttu-id="3d142-254">ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="3d142-254">ICorDebugNativeFrame2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)|<span data-ttu-id="3d142-255">4</span><span class="sxs-lookup"><span data-stu-id="3d142-255">4</span></span>|  
|`ver_ICorDebugInternalFrame2`|[<span data-ttu-id="3d142-256">ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="3d142-256">ICorDebugInternalFrame2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)|<span data-ttu-id="3d142-257">4</span><span class="sxs-lookup"><span data-stu-id="3d142-257">4</span></span>|  
|`ver_ICorDebugRuntimeUnwindableFrame`|[<span data-ttu-id="3d142-258">ICorDebugRuntimeUnwindableFrame</span><span class="sxs-lookup"><span data-stu-id="3d142-258">ICorDebugRuntimeUnwindableFrame</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugruntimeunwindableframe-interface.md)|<span data-ttu-id="3d142-259">4</span><span class="sxs-lookup"><span data-stu-id="3d142-259">4</span></span>|  
|`ver_ICorDebugHeapValue3`|[<span data-ttu-id="3d142-260">ICorDebugHeapValue3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3d142-260">ICorDebugHeapValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md)|<span data-ttu-id="3d142-261">4</span><span class="sxs-lookup"><span data-stu-id="3d142-261">4</span></span>|  
|`ver_ICorDebugBlockingObjectEnum`|[<span data-ttu-id="3d142-262">ICorDebugBlockingObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3d142-262">ICorDebugBlockingObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)|<span data-ttu-id="3d142-263">4</span><span class="sxs-lookup"><span data-stu-id="3d142-263">4</span></span>|  
|`ver_ICorDebugValue3`|[<span data-ttu-id="3d142-264">ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="3d142-264">ICorDebugValue3</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)|<span data-ttu-id="3d142-265">4</span><span class="sxs-lookup"><span data-stu-id="3d142-265">4</span></span>|  
|`ver_ICorDebugComObjectValue`|[<span data-ttu-id="3d142-266">ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="3d142-266">ICorDebugComObjectValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)|<span data-ttu-id="3d142-267">4.5</span><span class="sxs-lookup"><span data-stu-id="3d142-267">4.5</span></span>|  
|`ver_ICorDebugAppDomain3`|[<span data-ttu-id="3d142-268">ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="3d142-268">ICorDebugAppDomain3</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)|<span data-ttu-id="3d142-269">4.5</span><span class="sxs-lookup"><span data-stu-id="3d142-269">4.5</span></span>|  
|`ver_ICorDebugCode3`|[<span data-ttu-id="3d142-270">ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="3d142-270">ICorDebugCode3</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)|<span data-ttu-id="3d142-271">4.5</span><span class="sxs-lookup"><span data-stu-id="3d142-271">4.5</span></span>|  
|`ver_ICorDebugILFrame3`|[<span data-ttu-id="3d142-272">ICorDebugILFrame3</span><span class="sxs-lookup"><span data-stu-id="3d142-272">ICorDebugILFrame3</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)|<span data-ttu-id="3d142-273">4.5</span><span class="sxs-lookup"><span data-stu-id="3d142-273">4.5</span></span>|  
|`CorDebugLatestVersion`|<span data-ttu-id="3d142-274">모든 서비스 팩을 포함한 .NET Framework 버전이 최신 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="3d142-274">The version of the .NET Framework, including all of its service packs, is the latest version.</span></span>|-|  
  
## <a name="remarks"></a><span data-ttu-id="3d142-275">설명</span><span class="sxs-lookup"><span data-stu-id="3d142-275">Remarks</span></span>  
 <span data-ttu-id="3d142-276">디버거에서 사용할 수는 `CorDebugInterfaceVersion` 열거형에는 [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) 디버거가 지 원하는.NET Framework의 가장 높은 버전을 지정 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="3d142-276">A debugger can use the `CorDebugInterfaceVersion` enumeration in the [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) function to specify the highest version of the .NET Framework that the debugger supports.</span></span>  
  
## <a name="interface-names"></a><span data-ttu-id="3d142-277">인터페이스 이름</span><span class="sxs-lookup"><span data-stu-id="3d142-277">Interface Names</span></span>  
 <span data-ttu-id="3d142-278">디버깅 API에서 인터페이스 이름 끝에 표시되는 숫자(예: `ICorDebugThread3`의 경우 "3")는 .NET Framework의 버전이 아닌 인터페이스의 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3d142-278">The number that appears at the end of the interface names in the debugging API (for example, the "3" in `ICorDebugThread3`) specifies the version of the interface, not the version of the .NET Framework.</span></span> <span data-ttu-id="3d142-279">.NET Framework 버전 1에 처음 도입된 인터페이스를 제외하면 디버깅 API의 모든 인터페이스 이름에는 버전 번호가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d142-279">All interface names in the debugging API include version numbers except for interfaces that were introduced in the .NET Framework version 1.</span></span> <span data-ttu-id="3d142-280">인터페이스 버전 번호와 .NET Framework 버전 번호가 일치하는 경우 단순히 우연적인 일입니다.</span><span class="sxs-lookup"><span data-stu-id="3d142-280">Any correspondence between interface version numbers and.NET Framework version numbers are coincidental.</span></span>  
  
-   <span data-ttu-id="3d142-281">.NET Framework 버전 1.0에 도입된 인터페이스의 경우 모두 암시적으로 버전 1이므로 번호를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d142-281">Interfaces that were introduced in the .NET Framework version 1.0 do not include numbers, because they are all implicitly version 1.</span></span>  
  
-   <span data-ttu-id="3d142-282">.NET Framework 버전 1.1은 버전 1.0 인터페이스를 사용하며 새로운 디버깅 인터페이스는 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d142-282">The .NET Framework version 1.1 uses version 1.0 interfaces, and does not introduce any new debugging interfaces.</span></span>  
  
-   <span data-ttu-id="3d142-283">.NET Framework 버전 2.0에 도입된 14개 디버깅 인터페이스는 버전 1의 해당 인터페이스가 논리적으로 확장된 것이며 이름에 숫자 "2"가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d142-283">The 14 debugging interfaces introduced in the .NET Framework version 2.0 are logical extensions of their version 1 counterparts and include the number "2" in their names.</span></span>  
  
-   <span data-ttu-id="3d142-284">.NET Framework 버전 3.0 및 3.5는 기존 .NET Framework 2.0 인터페이스를 사용하며 새로운 인터페이스는 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d142-284">The .NET Framework versions 3.0 and 3.5 use the existing .NET Framework 2.0 interfaces, and do not introduce any new interfaces.</span></span>  
  
-   <span data-ttu-id="3d142-285">[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] 다양 한 인터페이스 버전이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3d142-285">The [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] introduces a mix of interface versions.</span></span> <span data-ttu-id="3d142-286">예를 들어 `ICorDebugThread3` 및 `ICorDebugThread4`는 모두 `ICorDebugThread` 인터페이스의 3번째/4번째 버전으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d142-286">For example, both `ICorDebugThread3` and `ICorDebugThread4` appear as the third and fourth versions of the `ICorDebugThread` interface.</span></span> <span data-ttu-id="3d142-287">[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 의 첫 번째 버전도 소개는 `ICorDebugStackWalk` 인터페이스와 두 번째 버전의는 `ICorDebugNativeFrame` 인터페이스 (`ICorDebugNativeFrame2`).</span><span class="sxs-lookup"><span data-stu-id="3d142-287">The [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] also introduces the first version of the `ICorDebugStackWalk` interface and the second version of the `ICorDebugNativeFrame` interface (`ICorDebugNativeFrame2`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d142-288">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3d142-288">Requirements</span></span>  
 <span data-ttu-id="3d142-289">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3d142-289">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d142-290">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d142-290">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d142-291">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d142-291">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d142-292">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d142-292">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d142-293">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d142-293">See Also</span></span>  
 [<span data-ttu-id="3d142-294">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="3d142-294">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
