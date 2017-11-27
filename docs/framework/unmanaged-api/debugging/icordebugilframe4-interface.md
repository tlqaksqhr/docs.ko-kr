---
title: "ICorDebugILFrame4 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame4
api_location: mscordbi.dll
api_type: COM
ms.assetid: 1e739183-3e05-49e5-846f-4075256e41de
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80b42a2ed4e93fd5e4c662bab34b111fe0757890
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilframe4-interface"></a><span data-ttu-id="e5332-102">ICorDebugILFrame4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5332-102">ICorDebugILFrame4 Interface</span></span>
<span data-ttu-id="e5332-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="e5332-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="e5332-104">IL(중간 언어) 코드의 스택 프레임에서 로컬 변수 및 코드에 액세스하는 데 사용할 수 있는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e5332-104">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="e5332-105">디버거가 프로파일러 ReJIT 계측에 추가된 변수와 코드에 액세스할 수 있는지는 매개 변수를 통해 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5332-105">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e5332-106">메서드</span><span class="sxs-lookup"><span data-stu-id="e5332-106">Methods</span></span>  
  
|<span data-ttu-id="e5332-107">메서드</span><span class="sxs-lookup"><span data-stu-id="e5332-107">Method</span></span>|<span data-ttu-id="e5332-108">설명</span><span class="sxs-lookup"><span data-stu-id="e5332-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e5332-109">EnumerateLocalVariablesEx 메서드</span><span class="sxs-lookup"><span data-stu-id="e5332-109">EnumerateLocalVariablesEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md)|<span data-ttu-id="e5332-110">현재 프레임에서 사용할 수 있는 로컬 변수 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e5332-110">Returns a list of the local variables available in the current frame.</span></span>|  
|[<span data-ttu-id="e5332-111">GetCodeEx 메서드</span><span class="sxs-lookup"><span data-stu-id="e5332-111">GetCodeEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md)|<span data-ttu-id="e5332-112">이 스택 프레임에서 실행 중인 코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e5332-112">Returns the code that this stack frame is running.</span></span>|  
|[<span data-ttu-id="e5332-113">GetLocalVariableEx 메서드</span><span class="sxs-lookup"><span data-stu-id="e5332-113">GetLocalVariableEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md)|<span data-ttu-id="e5332-114">IL 프레임의 로컬 변수 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e5332-114">Returns the value of a local variable in the IL frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5332-115">설명</span><span class="sxs-lookup"><span data-stu-id="e5332-115">Remarks</span></span>  
 <span data-ttu-id="e5332-116">이외에서 제공 하는 기능을 제공 하는 이러한 메서드는 [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md), [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md), 및 [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="e5332-116">These methods offer functionality in addition to that provided by the [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md), [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md), and [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) methods.</span></span> <span data-ttu-id="e5332-117">각 메서드는 프로파일러 ReJIT 요청에 의해 정의된 추가 로컬 변수나 코드가 표시되는지 여부를 지정하는 `flags` 매개 변수를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e5332-117">Each method includes a `flags` parameter that specifies whether additional local variables or code defined by a profiler's ReJIT request are visible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5332-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5332-118">Requirements</span></span>  
 <span data-ttu-id="e5332-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e5332-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5332-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5332-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5332-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5332-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5332-122">**.NET framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5332-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5332-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5332-123">See Also</span></span>  
 [<span data-ttu-id="e5332-124">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5332-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="e5332-125">디버깅</span><span class="sxs-lookup"><span data-stu-id="e5332-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
