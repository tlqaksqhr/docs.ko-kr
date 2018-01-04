---
title: "ICorDebugProcess5::EnableNGENPolicy 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5::EnableNGenPolicy
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::EnableNGENPolicy
helpviewer_keywords:
- ICorDebugProcess5::EnableNGENPolicy method [.NET Framework debugging]
- EnableNGENPolicy method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 3b8e15ca-3c72-4685-a937-da4c739cb9e9
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dca0df7b0be643d53bb5b9a03bd3abbb186d69dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5enablengenpolicy-method"></a><span data-ttu-id="5ee8b-102">ICorDebugProcess5::EnableNGENPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="5ee8b-102">ICorDebugProcess5::EnableNGENPolicy Method</span></span>
<span data-ttu-id="5ee8b-103">응용 프로그램에서 관리 되는 디버거가 실행 되는 동안 네이티브 이미지를 로드 하는 방식을 결정 하는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee8b-103">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ee8b-104">구문</span><span class="sxs-lookup"><span data-stu-id="5ee8b-104">Syntax</span></span>  
  
```  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5ee8b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5ee8b-105">Parameters</span></span>  
 `ePolicy`  
 <span data-ttu-id="5ee8b-106">[in] A [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) 응용 프로그램에서 관리 되는 디버거가 실행 되는 동안 네이티브 이미지를 로드 하는 방식을 결정 하는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="5ee8b-106">[in] A [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) constant that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ee8b-107">설명</span><span class="sxs-lookup"><span data-stu-id="5ee8b-107">Remarks</span></span>  
 <span data-ttu-id="5ee8b-108">메서드가 반환 하는 경우에 정책이 성공적으로 설정 되 면 `S_OK`합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee8b-108">If the policy is set successfully, the method returns `S_OK`.</span></span> <span data-ttu-id="5ee8b-109">경우 `ePolicy` 으로 정의 된 열거 값의 범위 밖에 [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md), 메서드가 반환 `E_INVALIDARG` 메서드 호출이 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee8b-109">If `ePolicy` is outside the range of the enumerated values defined by [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md), the method returns `E_INVALIDARG` and the method call has no effect.</span></span> <span data-ttu-id="5ee8b-110">메서드가 반환 하는 경우 네이티브 이미지 생성기 (Ngen.exe)의 정책을 업데이트할 수 없습니다, `E_FAIL`합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee8b-110">If the policy of the Native Image Generator (Ngen.exe) cannot be updated, the method returns `E_FAIL`.</span></span>  
  
 <span data-ttu-id="5ee8b-111">`ICorDebugProcess5::EnableNGenPolicy` 프로세스의 수명 동안 언제 든 지 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee8b-111">The `ICorDebugProcess5::EnableNGenPolicy` method can be called at any time during the lifetime of the process.</span></span> <span data-ttu-id="5ee8b-112">정책이 정책 설정 된 후 로드 되는 모든 모듈에 대 한 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ee8b-112">The policy is in effect for any modules that are loaded after the policy is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ee8b-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5ee8b-113">Requirements</span></span>  
 <span data-ttu-id="5ee8b-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee8b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ee8b-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ee8b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ee8b-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ee8b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ee8b-117">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ee8b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ee8b-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ee8b-118">See Also</span></span>  
 [<span data-ttu-id="5ee8b-119">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ee8b-119">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="5ee8b-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ee8b-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="5ee8b-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="5ee8b-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
