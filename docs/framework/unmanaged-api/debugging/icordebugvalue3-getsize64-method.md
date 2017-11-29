---
title: "ICorDebugValue3::GetSize64 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue3::GetSize64
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue3::GetSize64
helpviewer_keywords:
- GetSize64 method, ICorDebugValue3 interface [.NET Framework debugging]
- ICorDebugValue3::GetSize64 method [.NET Framework debugging]
ms.assetid: fee56a29-3154-4192-958d-71da2ced3740
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b129ebe666972052775c2c3e44e38bb6a25a176e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvalue3getsize64-method"></a><span data-ttu-id="02a55-102">ICorDebugValue3::GetSize64 메서드</span><span class="sxs-lookup"><span data-stu-id="02a55-102">ICorDebugValue3::GetSize64 Method</span></span>
<span data-ttu-id="02a55-103">이 바이트 단위로 크기를 가져옵니다 [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="02a55-103">Gets the size, in bytes, of this [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02a55-104">구문</span><span class="sxs-lookup"><span data-stu-id="02a55-104">Syntax</span></span>  
  
```  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="02a55-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="02a55-105">Parameters</span></span>  
 <span data-ttu-id="02a55-106">pSize</span><span class="sxs-lookup"><span data-stu-id="02a55-106">pSize</span></span>  
 <span data-ttu-id="02a55-107">[out] 이 개체를 바이트 단위로 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="02a55-107">[out] A pointer to the size, in bytes, of this object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02a55-108">설명</span><span class="sxs-lookup"><span data-stu-id="02a55-108">Remarks</span></span>  
 <span data-ttu-id="02a55-109">이 값 형식이 참조 형식인 경우이 메서드는 개체의 크기 보다는 포인터의 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="02a55-109">If this value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="02a55-110">`ICorDebugValue3::GetSize` 에서 다른 메서드는 [icordebugvalue:: Getsize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) 해당 출력 매개 변수 형식에서 메서드.</span><span class="sxs-lookup"><span data-stu-id="02a55-110">The `ICorDebugValue3::GetSize` method differs from the [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) method in the type of its output parameter.</span></span> <span data-ttu-id="02a55-111">[icordebugvalue:: Getsize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), 출력 매개 변수는 `ULONG32`, `ICorDebugValue3::GetSize`, 이기는 `ULONG64`합니다.</span><span class="sxs-lookup"><span data-stu-id="02a55-111">In [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), the output parameter is a `ULONG32`; in `ICorDebugValue3::GetSize`, it is a `ULONG64`.</span></span> <span data-ttu-id="02a55-112">이 통해는 [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) 인터페이스를 2GB를 초과 하는 배열의 크기를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="02a55-112">This enables the [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) interface to report the size of arrays that exceed 2GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02a55-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02a55-113">Requirements</span></span>  
 <span data-ttu-id="02a55-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="02a55-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02a55-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02a55-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02a55-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02a55-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02a55-117">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02a55-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02a55-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02a55-118">See Also</span></span>  
 [<span data-ttu-id="02a55-119">ICorDebugValue3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02a55-119">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 [<span data-ttu-id="02a55-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02a55-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
