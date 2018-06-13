---
title: CorDebugInterfaceVersion 열거형
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fac90699cf217aff926003aa545b9cceb11bf58d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33410009"
---
# <a name="cordebuginterfaceversion-enumeration"></a><span data-ttu-id="deddf-102">CorDebugInterfaceVersion 열거형</span><span class="sxs-lookup"><span data-stu-id="deddf-102">CorDebugInterfaceVersion Enumeration</span></span>
<span data-ttu-id="deddf-103">인터페이스, 특정 .NET Framework 버전 또는 인터페이스가 적용된 .NET Framework 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="deddf-103">Specifies an interface, a version of the .NET Framework, or a version of the .NET Framework in which an interface was introduced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="deddf-104">구문</span><span class="sxs-lookup"><span data-stu-id="deddf-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="deddf-105">멤버</span><span class="sxs-lookup"><span data-stu-id="deddf-105">Members</span></span>  
 <span data-ttu-id="deddf-106">다음 테이블에는 각 열거형 값에서 해당 인터페이스의 링크와</span><span class="sxs-lookup"><span data-stu-id="deddf-106">The following table provides links from each enumeration value to the corresponding interface.</span></span> <span data-ttu-id="deddf-107">인터페이스가 지원되는 첫 번째.NET Framework 버전이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="deddf-107">In addition, the table indicates the first version of the .NET Framework that the interface was supported in.</span></span>  
  
|<span data-ttu-id="deddf-108">멤버</span><span class="sxs-lookup"><span data-stu-id="deddf-108">Member</span></span>|<span data-ttu-id="deddf-109">설명</span><span class="sxs-lookup"><span data-stu-id="deddf-109">Specifies</span></span>|<span data-ttu-id="deddf-110">.NET Framework 버전</span><span class="sxs-lookup"><span data-stu-id="deddf-110">.NET Framework version</span></span>|  
|------------|---------------|----------------------------|  
|`CorDebugInvalidVersion`|<span data-ttu-id="deddf-111">.NET Framework 버전이 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="deddf-111">The version of the .NET Framework is invalid.</span></span>|-|  
|`CorDebugVersion_1_0`|<span data-ttu-id="deddf-112">모든 서비스 팩을 포함한 .NET Framework 버전이 1.0입니다.</span><span class="sxs-lookup"><span data-stu-id="deddf-112">The version of the .NET Framework, including all its service packs, is 1.0.</span></span>|<span data-ttu-id="deddf-113">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-113">1.0</span></span>|  
|`CorDebugVersion_1_1`|<span data-ttu-id="deddf-114">모든 서비스 팩을 포함한 .NET Framework 버전이 1.1입니다.</span><span class="sxs-lookup"><span data-stu-id="deddf-114">The version of the .NET Framework, including all service packs, is 1.1.</span></span>|<span data-ttu-id="deddf-115">1.1</span><span class="sxs-lookup"><span data-stu-id="deddf-115">1.1</span></span>|  
|`CorDebugVersion_2_0`|<span data-ttu-id="deddf-116">모든 서비스 팩을 포함한 .NET Framework 버전이 2.0입니다.</span><span class="sxs-lookup"><span data-stu-id="deddf-116">The version of the .NET Framework, including all service packs, is 2.0.</span></span>|<span data-ttu-id="deddf-117">2.0</span><span class="sxs-lookup"><span data-stu-id="deddf-117">2.0</span></span>|  
|`CorDebugVersion_4_0`|<span data-ttu-id="deddf-118">모든 서비스 팩을 포함한 .NET Framework 버전이 4입니다.</span><span class="sxs-lookup"><span data-stu-id="deddf-118">The version of the .NET Framework, including all service packs, is 4.</span></span>|<span data-ttu-id="deddf-119">4</span><span class="sxs-lookup"><span data-stu-id="deddf-119">4</span></span>|  
|`CorDebugVersion_4_5`|<span data-ttu-id="deddf-120">모든 서비스 팩을 포함한 .NET Framework 버전이 4.5입니다.</span><span class="sxs-lookup"><span data-stu-id="deddf-120">The version of the .NET Framework, including all service packs, is 4.5.</span></span>|<span data-ttu-id="deddf-121">4.5</span><span class="sxs-lookup"><span data-stu-id="deddf-121">4.5</span></span>|  
|`ver_ICorDebugManagedCallback`|[<span data-ttu-id="deddf-122">ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="deddf-122">ICorDebugManagedCallback</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)|<span data-ttu-id="deddf-123">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-123">1.0</span></span>|  
|`ver_ICorDebugUnmanagedCallback`|[<span data-ttu-id="deddf-124">ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="deddf-124">ICorDebugUnmanagedCallback</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)|<span data-ttu-id="deddf-125">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-125">1.0</span></span>|  
|`ver_ICorDebug`|[<span data-ttu-id="deddf-126">ICorDebug</span><span class="sxs-lookup"><span data-stu-id="deddf-126">ICorDebug</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)|<span data-ttu-id="deddf-127">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-127">1.0</span></span>|  
|`ver_ICorDebugController`|[<span data-ttu-id="deddf-128">ICorDebugController</span><span class="sxs-lookup"><span data-stu-id="deddf-128">ICorDebugController</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-interface.md)|<span data-ttu-id="deddf-129">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-129">1.0</span></span>|  
|`ver_ICorDebugAppDomain`|[<span data-ttu-id="deddf-130">ICorDebugAppDomain</span><span class="sxs-lookup"><span data-stu-id="deddf-130">ICorDebugAppDomain</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md)|<span data-ttu-id="deddf-131">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-131">1.0</span></span>|  
|`ver_ICorDebugAssembly`|[<span data-ttu-id="deddf-132">ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="deddf-132">ICorDebugAssembly</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md)|<span data-ttu-id="deddf-133">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-133">1.0</span></span>|  
|`ver_ICorDebugProcess`|[<span data-ttu-id="deddf-134">ICorDebugProcess</span><span class="sxs-lookup"><span data-stu-id="deddf-134">ICorDebugProcess</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md)|<span data-ttu-id="deddf-135">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-135">1.0</span></span>|  
|`ver_ICorDebugBreakpoint`|[<span data-ttu-id="deddf-136">ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="deddf-136">ICorDebugBreakpoint</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-interface.md)|<span data-ttu-id="deddf-137">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-137">1.0</span></span>|  
|`ver_ICorDebugFunctionBreakpoint`|[<span data-ttu-id="deddf-138">ICorDebugFunctionBreakpoint</span><span class="sxs-lookup"><span data-stu-id="deddf-138">ICorDebugFunctionBreakpoint</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-interface.md)|<span data-ttu-id="deddf-139">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-139">1.0</span></span>|  
|`ver_ICorDebugModuleBreakpoint`|[<span data-ttu-id="deddf-140">ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="deddf-140">ICorDebugModuleBreakpoint</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-interface.md)|<span data-ttu-id="deddf-141">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-141">1.0</span></span>|  
|`ver_ICorDebugValueBreakpoint`|[<span data-ttu-id="deddf-142">ICorDebugValueBreakpoint</span><span class="sxs-lookup"><span data-stu-id="deddf-142">ICorDebugValueBreakpoint</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-interface.md)|<span data-ttu-id="deddf-143">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-143">1.0</span></span>|  
|`ver_ICorDebugStepper`|[<span data-ttu-id="deddf-144">ICorDebugStepper</span><span class="sxs-lookup"><span data-stu-id="deddf-144">ICorDebugStepper</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-interface.md)|<span data-ttu-id="deddf-145">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-145">1.0</span></span>|  
|`ver_ICorDebugRegisterSet`|[<span data-ttu-id="deddf-146">ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="deddf-146">ICorDebugRegisterSet</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)|<span data-ttu-id="deddf-147">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-147">1.0</span></span>|  
|`ver_ICorDebugThread`|[<span data-ttu-id="deddf-148">ICorDebugThread</span><span class="sxs-lookup"><span data-stu-id="deddf-148">ICorDebugThread</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-interface.md)|<span data-ttu-id="deddf-149">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-149">1.0</span></span>|  
|`ver_ICorDebugChain`|[<span data-ttu-id="deddf-150">ICorDebugChain</span><span class="sxs-lookup"><span data-stu-id="deddf-150">ICorDebugChain</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md)|<span data-ttu-id="deddf-151">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-151">1.0</span></span>|  
|`ver_ICorDebugFrame`|[<span data-ttu-id="deddf-152">ICorDebugFrame</span><span class="sxs-lookup"><span data-stu-id="deddf-152">ICorDebugFrame</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md)|<span data-ttu-id="deddf-153">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-153">1.0</span></span>|  
|`ver_ICorDebugILFrame`|[<span data-ttu-id="deddf-154">ICorDebugILFrame</span><span class="sxs-lookup"><span data-stu-id="deddf-154">ICorDebugILFrame</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-interface.md)|<span data-ttu-id="deddf-155">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-155">1.0</span></span>|  
|`ver_ICorDebugNativeFrame`|[<span data-ttu-id="deddf-156">ICorDebugNativeFrame</span><span class="sxs-lookup"><span data-stu-id="deddf-156">ICorDebugNativeFrame</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-interface.md)|<span data-ttu-id="deddf-157">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-157">1.0</span></span>|  
|`ver_ICorDebugModule`|[<span data-ttu-id="deddf-158">ICorDebugModule</span><span class="sxs-lookup"><span data-stu-id="deddf-158">ICorDebugModule</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-interface.md)|<span data-ttu-id="deddf-159">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-159">1.0</span></span>|  
|`ver_ICorDebugFunction`|[<span data-ttu-id="deddf-160">ICorDebugFunction</span><span class="sxs-lookup"><span data-stu-id="deddf-160">ICorDebugFunction</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md)|<span data-ttu-id="deddf-161">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-161">1.0</span></span>|  
|`ver_ICorDebugCode`|[<span data-ttu-id="deddf-162">ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="deddf-162">ICorDebugCode</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)|<span data-ttu-id="deddf-163">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-163">1.0</span></span>|  
|`ver_ICorDebugClass`|[<span data-ttu-id="deddf-164">ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="deddf-164">ICorDebugClass</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)|<span data-ttu-id="deddf-165">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-165">1.0</span></span>|  
|`ver_ICorDebugEval`|[<span data-ttu-id="deddf-166">ICorDebugEval</span><span class="sxs-lookup"><span data-stu-id="deddf-166">ICorDebugEval</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-interface.md)|<span data-ttu-id="deddf-167">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-167">1.0</span></span>|  
|`ver_ICorDebugValue`|[<span data-ttu-id="deddf-168">ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="deddf-168">ICorDebugValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md)|<span data-ttu-id="deddf-169">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-169">1.0</span></span>|  
|`ver_ICorDebugGenericValue`|[<span data-ttu-id="deddf-170">ICorDebugGenericValue</span><span class="sxs-lookup"><span data-stu-id="deddf-170">ICorDebugGenericValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-interface.md)|<span data-ttu-id="deddf-171">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-171">1.0</span></span>|  
|`ver_ICorDebugReferenceValue`|[<span data-ttu-id="deddf-172">ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="deddf-172">ICorDebugReferenceValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-interface.md)|<span data-ttu-id="deddf-173">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-173">1.0</span></span>|  
|`ver_ICorDebugHeapValue`|[<span data-ttu-id="deddf-174">ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="deddf-174">ICorDebugHeapValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-interface.md)|<span data-ttu-id="deddf-175">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-175">1.0</span></span>|  
|`ver_ICorDebugObjectValue`|[<span data-ttu-id="deddf-176">ICorDebugObjectValue</span><span class="sxs-lookup"><span data-stu-id="deddf-176">ICorDebugObjectValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md)|<span data-ttu-id="deddf-177">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-177">1.0</span></span>|  
|`ver_ICorDebugBoxValue`|[<span data-ttu-id="deddf-178">ICorDebugBoxValue</span><span class="sxs-lookup"><span data-stu-id="deddf-178">ICorDebugBoxValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-interface.md)|<span data-ttu-id="deddf-179">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-179">1.0</span></span>|  
|`ver_ICorDebugStringValue`|[<span data-ttu-id="deddf-180">ICorDebugStringValue</span><span class="sxs-lookup"><span data-stu-id="deddf-180">ICorDebugStringValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-interface.md)|<span data-ttu-id="deddf-181">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-181">1.0</span></span>|  
|`ver_ICorDebugArrayValue`|[<span data-ttu-id="deddf-182">ICorDebugArrayValue</span><span class="sxs-lookup"><span data-stu-id="deddf-182">ICorDebugArrayValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-interface.md)|<span data-ttu-id="deddf-183">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-183">1.0</span></span>|  
|`ver_ICorDebugContext`|[<span data-ttu-id="deddf-184">ICorDebugContext</span><span class="sxs-lookup"><span data-stu-id="deddf-184">ICorDebugContext</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontext-interface.md)|<span data-ttu-id="deddf-185">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-185">1.0</span></span>|  
|`ver_ICorDebugEnum`|[<span data-ttu-id="deddf-186">ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="deddf-186">ICorDebugEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)|<span data-ttu-id="deddf-187">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-187">1.0</span></span>|  
|`ver_ICorDebugObjectEnum`|[<span data-ttu-id="deddf-188">ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="deddf-188">ICorDebugObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-interface.md)|<span data-ttu-id="deddf-189">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-189">1.0</span></span>|  
|`ver_ICorDebugBreakpointEnum`|[<span data-ttu-id="deddf-190">ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="deddf-190">ICorDebugBreakpointEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-interface.md)|<span data-ttu-id="deddf-191">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-191">1.0</span></span>|  
|`ver_ICorDebugStepperEnum`|[<span data-ttu-id="deddf-192">ICorDebugStepperEnum</span><span class="sxs-lookup"><span data-stu-id="deddf-192">ICorDebugStepperEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-interface.md)|<span data-ttu-id="deddf-193">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-193">1.0</span></span>|  
|`ver_ICorDebugProcessEnum`|[<span data-ttu-id="deddf-194">ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="deddf-194">ICorDebugProcessEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocessenum-interface.md)|<span data-ttu-id="deddf-195">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-195">1.0</span></span>|  
|`ver_ICorDebugThreadEnum`|[<span data-ttu-id="deddf-196">ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="deddf-196">ICorDebugThreadEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-interface1.md)|<span data-ttu-id="deddf-197">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-197">1.0</span></span>|  
|`ver_ICorDebugFrameEnum`|[<span data-ttu-id="deddf-198">ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="deddf-198">ICorDebugFrameEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframeenum-interface.md)|<span data-ttu-id="deddf-199">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-199">1.0</span></span>|  
|`ver_ICorDebugChainEnum`|[<span data-ttu-id="deddf-200">ICorDebugChainEnum</span><span class="sxs-lookup"><span data-stu-id="deddf-200">ICorDebugChainEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchainenum-interface.md)|<span data-ttu-id="deddf-201">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-201">1.0</span></span>|  
|`ver_ICorDebugModuleEnum`|[<span data-ttu-id="deddf-202">ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="deddf-202">ICorDebugModuleEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-interface.md)|<span data-ttu-id="deddf-203">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-203">1.0</span></span>|  
|`ver_ICorDebugValueEnum`|[<span data-ttu-id="deddf-204">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="deddf-204">ICorDebugValueEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalueenum-interface.md)|<span data-ttu-id="deddf-205">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-205">1.0</span></span>|  
|`ver_ICorDebugCodeEnum`|[<span data-ttu-id="deddf-206">ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="deddf-206">ICorDebugCodeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-interface.md)|<span data-ttu-id="deddf-207">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-207">1.0</span></span>|  
|`ver_ICorDebugTypeEnum`|[<span data-ttu-id="deddf-208">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="deddf-208">ICorDebugTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtypeenum-interface.md)|<span data-ttu-id="deddf-209">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-209">1.0</span></span>|  
|`ver_ICorDebugErrorInfoEnum`|[<span data-ttu-id="deddf-210">ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="deddf-210">ICorDebugErrorInfoEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugerrorinfoenum-interface.md)|<span data-ttu-id="deddf-211">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-211">1.0</span></span>|  
|`ver_ICorDebugAppDomainEnum`|[<span data-ttu-id="deddf-212">ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="deddf-212">ICorDebugAppDomainEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md)|<span data-ttu-id="deddf-213">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-213">1.0</span></span>|  
|`ver_ICorDebugAssemblyEnum`|[<span data-ttu-id="deddf-214">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="deddf-214">ICorDebugAssemblyEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassemblyenum-interface.md)|<span data-ttu-id="deddf-215">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-215">1.0</span></span>|  
|`ver_ICorDebugEditAndContinueErrorInfo`|[<span data-ttu-id="deddf-216">ICorDebugEditAndContinueErrorInfo</span><span class="sxs-lookup"><span data-stu-id="deddf-216">ICorDebugEditAndContinueErrorInfo</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinueerrorinfo-interface.md)|<span data-ttu-id="deddf-217">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-217">1.0</span></span>|  
|`ver_ICorDebugEditAndContinueSnapshot`|[<span data-ttu-id="deddf-218">ICorDebugEditAndContinueSnapshot</span><span class="sxs-lookup"><span data-stu-id="deddf-218">ICorDebugEditAndContinueSnapshot</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinuesnapshot-interface.md)|<span data-ttu-id="deddf-219">1.0</span><span class="sxs-lookup"><span data-stu-id="deddf-219">1.0</span></span>|  
|`ver_ICorDebugManagedCallback2`|[<span data-ttu-id="deddf-220">ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="deddf-220">ICorDebugManagedCallback2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)|<span data-ttu-id="deddf-221">2.0</span><span class="sxs-lookup"><span data-stu-id="deddf-221">2.0</span></span>|  
|`ver_ICorDebugAppDomain2`|[<span data-ttu-id="deddf-222">ICorDebugAppDomain2</span><span class="sxs-lookup"><span data-stu-id="deddf-222">ICorDebugAppDomain2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-interface.md)|<span data-ttu-id="deddf-223">2.0</span><span class="sxs-lookup"><span data-stu-id="deddf-223">2.0</span></span>|  
|`ver_ICorDebugProcess2`|[<span data-ttu-id="deddf-224">ICorDebugProcess2</span><span class="sxs-lookup"><span data-stu-id="deddf-224">ICorDebugProcess2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-interface1.md)|<span data-ttu-id="deddf-225">2.0</span><span class="sxs-lookup"><span data-stu-id="deddf-225">2.0</span></span>|  
|`ver_ICorDebugStepper2`|[<span data-ttu-id="deddf-226">ICorDebugStepper2</span><span class="sxs-lookup"><span data-stu-id="deddf-226">ICorDebugStepper2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper2-interface1.md)|<span data-ttu-id="deddf-227">2.0</span><span class="sxs-lookup"><span data-stu-id="deddf-227">2.0</span></span>|  
|`ver_ICorDebugRegisterSet2`|[<span data-ttu-id="deddf-228">ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="deddf-228">ICorDebugRegisterSet2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)|<span data-ttu-id="deddf-229">2.0</span><span class="sxs-lookup"><span data-stu-id="deddf-229">2.0</span></span>|  
|`ver_ICorDebugThread2`|[<span data-ttu-id="deddf-230">ICorDebugThread2</span><span class="sxs-lookup"><span data-stu-id="deddf-230">ICorDebugThread2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interface.md)|<span data-ttu-id="deddf-231">2.0</span><span class="sxs-lookup"><span data-stu-id="deddf-231">2.0</span></span>|  
|`ver_ICorDebugILFrame2`|[<span data-ttu-id="deddf-232">ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="deddf-232">ICorDebugILFrame2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-interface.md)|<span data-ttu-id="deddf-233">2.0</span><span class="sxs-lookup"><span data-stu-id="deddf-233">2.0</span></span>|  
|`ver_ICorDebugModule2`|[<span data-ttu-id="deddf-234">ICorDebugModule2</span><span class="sxs-lookup"><span data-stu-id="deddf-234">ICorDebugModule2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-interface.md)|<span data-ttu-id="deddf-235">2.0</span><span class="sxs-lookup"><span data-stu-id="deddf-235">2.0</span></span>|  
|`ver_ICorDebugFunction2`|[<span data-ttu-id="deddf-236">ICorDebugFunction2</span><span class="sxs-lookup"><span data-stu-id="deddf-236">ICorDebugFunction2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-interface.md)|<span data-ttu-id="deddf-237">2.0</span><span class="sxs-lookup"><span data-stu-id="deddf-237">2.0</span></span>|  
|`ver_ICorDebugCode2`|[<span data-ttu-id="deddf-238">ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="deddf-238">ICorDebugCode2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md)|<span data-ttu-id="deddf-239">2.0</span><span class="sxs-lookup"><span data-stu-id="deddf-239">2.0</span></span>|  
|`ver_ICorDebugClass2`|<span data-ttu-id="deddf-240">"ICorDebugClass2"</span><span class="sxs-lookup"><span data-stu-id="deddf-240">"ICorDebugClass2"</span></span>|<span data-ttu-id="deddf-241">2.0</span><span class="sxs-lookup"><span data-stu-id="deddf-241">2.0</span></span>|  
|`ver_ICorDebugValue2`|<span data-ttu-id="deddf-242">"ICorDebugValue2"</span><span class="sxs-lookup"><span data-stu-id="deddf-242">"ICorDebugValue2"</span></span>|<span data-ttu-id="deddf-243">2.0</span><span class="sxs-lookup"><span data-stu-id="deddf-243">2.0</span></span>|  
|`ver_ICorDebugEval2`|<span data-ttu-id="deddf-244">"ICorDebugEval2"입니다.</span><span class="sxs-lookup"><span data-stu-id="deddf-244">The "ICorDebugEval2".</span></span>|<span data-ttu-id="deddf-245">2.0</span><span class="sxs-lookup"><span data-stu-id="deddf-245">2.0</span></span>|  
|`ver_ICorDebugObjectValue2`|<span data-ttu-id="deddf-246">"ICorDebugObjectValue2"</span><span class="sxs-lookup"><span data-stu-id="deddf-246">"ICorDebugObjectValue2"</span></span>|<span data-ttu-id="deddf-247">2.0</span><span class="sxs-lookup"><span data-stu-id="deddf-247">2.0</span></span>|  
|`ver_ICorDebugThread3`|[<span data-ttu-id="deddf-248">ICorDebugThread3</span><span class="sxs-lookup"><span data-stu-id="deddf-248">ICorDebugThread3</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md)|<span data-ttu-id="deddf-249">4</span><span class="sxs-lookup"><span data-stu-id="deddf-249">4</span></span>|  
|`ver_ICorDebugThread4`|[<span data-ttu-id="deddf-250">ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="deddf-250">ICorDebugThread4</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)|<span data-ttu-id="deddf-251">4</span><span class="sxs-lookup"><span data-stu-id="deddf-251">4</span></span>|  
|`ver_ICorDebugStackWalk`|[<span data-ttu-id="deddf-252">ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="deddf-252">ICorDebugStackWalk</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)|<span data-ttu-id="deddf-253">4</span><span class="sxs-lookup"><span data-stu-id="deddf-253">4</span></span>|  
|`ver_ICorDebugNativeFrame2`|[<span data-ttu-id="deddf-254">ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="deddf-254">ICorDebugNativeFrame2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)|<span data-ttu-id="deddf-255">4</span><span class="sxs-lookup"><span data-stu-id="deddf-255">4</span></span>|  
|`ver_ICorDebugInternalFrame2`|[<span data-ttu-id="deddf-256">ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="deddf-256">ICorDebugInternalFrame2</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)|<span data-ttu-id="deddf-257">4</span><span class="sxs-lookup"><span data-stu-id="deddf-257">4</span></span>|  
|`ver_ICorDebugRuntimeUnwindableFrame`|[<span data-ttu-id="deddf-258">ICorDebugRuntimeUnwindableFrame</span><span class="sxs-lookup"><span data-stu-id="deddf-258">ICorDebugRuntimeUnwindableFrame</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugruntimeunwindableframe-interface.md)|<span data-ttu-id="deddf-259">4</span><span class="sxs-lookup"><span data-stu-id="deddf-259">4</span></span>|  
|`ver_ICorDebugHeapValue3`|[<span data-ttu-id="deddf-260">ICorDebugHeapValue3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="deddf-260">ICorDebugHeapValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md)|<span data-ttu-id="deddf-261">4</span><span class="sxs-lookup"><span data-stu-id="deddf-261">4</span></span>|  
|`ver_ICorDebugBlockingObjectEnum`|[<span data-ttu-id="deddf-262">ICorDebugBlockingObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="deddf-262">ICorDebugBlockingObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)|<span data-ttu-id="deddf-263">4</span><span class="sxs-lookup"><span data-stu-id="deddf-263">4</span></span>|  
|`ver_ICorDebugValue3`|[<span data-ttu-id="deddf-264">ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="deddf-264">ICorDebugValue3</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)|<span data-ttu-id="deddf-265">4</span><span class="sxs-lookup"><span data-stu-id="deddf-265">4</span></span>|  
|`ver_ICorDebugComObjectValue`|[<span data-ttu-id="deddf-266">ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="deddf-266">ICorDebugComObjectValue</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)|<span data-ttu-id="deddf-267">4.5</span><span class="sxs-lookup"><span data-stu-id="deddf-267">4.5</span></span>|  
|`ver_ICorDebugAppDomain3`|[<span data-ttu-id="deddf-268">ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="deddf-268">ICorDebugAppDomain3</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)|<span data-ttu-id="deddf-269">4.5</span><span class="sxs-lookup"><span data-stu-id="deddf-269">4.5</span></span>|  
|`ver_ICorDebugCode3`|[<span data-ttu-id="deddf-270">ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="deddf-270">ICorDebugCode3</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)|<span data-ttu-id="deddf-271">4.5</span><span class="sxs-lookup"><span data-stu-id="deddf-271">4.5</span></span>|  
|`ver_ICorDebugILFrame3`|[<span data-ttu-id="deddf-272">ICorDebugILFrame3</span><span class="sxs-lookup"><span data-stu-id="deddf-272">ICorDebugILFrame3</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)|<span data-ttu-id="deddf-273">4.5</span><span class="sxs-lookup"><span data-stu-id="deddf-273">4.5</span></span>|  
|`CorDebugLatestVersion`|<span data-ttu-id="deddf-274">모든 서비스 팩을 포함한 .NET Framework 버전이 최신 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="deddf-274">The version of the .NET Framework, including all of its service packs, is the latest version.</span></span>|-|  
  
## <a name="remarks"></a><span data-ttu-id="deddf-275">설명</span><span class="sxs-lookup"><span data-stu-id="deddf-275">Remarks</span></span>  
 <span data-ttu-id="deddf-276">디버거에서 사용할 수는 `CorDebugInterfaceVersion` 열거형에는 [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) 디버거가 지 원하는.NET Framework의 가장 높은 버전을 지정 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="deddf-276">A debugger can use the `CorDebugInterfaceVersion` enumeration in the [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) function to specify the highest version of the .NET Framework that the debugger supports.</span></span>  
  
## <a name="interface-names"></a><span data-ttu-id="deddf-277">인터페이스 이름</span><span class="sxs-lookup"><span data-stu-id="deddf-277">Interface Names</span></span>  
 <span data-ttu-id="deddf-278">디버깅 API에서 인터페이스 이름 끝에 표시되는 숫자(예: `ICorDebugThread3`의 경우 "3")는 .NET Framework의 버전이 아닌 인터페이스의 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="deddf-278">The number that appears at the end of the interface names in the debugging API (for example, the "3" in `ICorDebugThread3`) specifies the version of the interface, not the version of the .NET Framework.</span></span> <span data-ttu-id="deddf-279">.NET Framework 버전 1에 처음 도입된 인터페이스를 제외하면 디버깅 API의 모든 인터페이스 이름에는 버전 번호가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="deddf-279">All interface names in the debugging API include version numbers except for interfaces that were introduced in the .NET Framework version 1.</span></span> <span data-ttu-id="deddf-280">인터페이스 버전 번호와 .NET Framework 버전 번호가 일치하는 경우 단순히 우연적인 일입니다.</span><span class="sxs-lookup"><span data-stu-id="deddf-280">Any correspondence between interface version numbers and.NET Framework version numbers are coincidental.</span></span>  
  
-   <span data-ttu-id="deddf-281">.NET Framework 버전 1.0에 도입된 인터페이스의 경우 모두 암시적으로 버전 1이므로 번호를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="deddf-281">Interfaces that were introduced in the .NET Framework version 1.0 do not include numbers, because they are all implicitly version 1.</span></span>  
  
-   <span data-ttu-id="deddf-282">.NET Framework 버전 1.1은 버전 1.0 인터페이스를 사용하며 새로운 디버깅 인터페이스는 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="deddf-282">The .NET Framework version 1.1 uses version 1.0 interfaces, and does not introduce any new debugging interfaces.</span></span>  
  
-   <span data-ttu-id="deddf-283">.NET Framework 버전 2.0에 도입된 14개 디버깅 인터페이스는 버전 1의 해당 인터페이스가 논리적으로 확장된 것이며 이름에 숫자 "2"가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="deddf-283">The 14 debugging interfaces introduced in the .NET Framework version 2.0 are logical extensions of their version 1 counterparts and include the number "2" in their names.</span></span>  
  
-   <span data-ttu-id="deddf-284">.NET Framework 버전 3.0 및 3.5는 기존 .NET Framework 2.0 인터페이스를 사용하며 새로운 인터페이스는 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="deddf-284">The .NET Framework versions 3.0 and 3.5 use the existing .NET Framework 2.0 interfaces, and do not introduce any new interfaces.</span></span>  
  
-   <span data-ttu-id="deddf-285">[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] 다양 한 인터페이스 버전이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="deddf-285">The [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] introduces a mix of interface versions.</span></span> <span data-ttu-id="deddf-286">예를 들어 `ICorDebugThread3` 및 `ICorDebugThread4`는 모두 `ICorDebugThread` 인터페이스의 3번째/4번째 버전으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="deddf-286">For example, both `ICorDebugThread3` and `ICorDebugThread4` appear as the third and fourth versions of the `ICorDebugThread` interface.</span></span> <span data-ttu-id="deddf-287">[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 의 첫 번째 버전도 소개는 `ICorDebugStackWalk` 인터페이스와 두 번째 버전의는 `ICorDebugNativeFrame` 인터페이스 (`ICorDebugNativeFrame2`).</span><span class="sxs-lookup"><span data-stu-id="deddf-287">The [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] also introduces the first version of the `ICorDebugStackWalk` interface and the second version of the `ICorDebugNativeFrame` interface (`ICorDebugNativeFrame2`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="deddf-288">요구 사항</span><span class="sxs-lookup"><span data-stu-id="deddf-288">Requirements</span></span>  
 <span data-ttu-id="deddf-289">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="deddf-289">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="deddf-290">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="deddf-290">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="deddf-291">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="deddf-291">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="deddf-292">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="deddf-292">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deddf-293">참고 항목</span><span class="sxs-lookup"><span data-stu-id="deddf-293">See Also</span></span>  
 [<span data-ttu-id="deddf-294">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="deddf-294">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
