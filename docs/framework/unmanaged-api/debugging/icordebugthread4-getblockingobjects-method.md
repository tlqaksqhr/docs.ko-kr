---
title: "ICorDebugThread4::GetBlockingObjects 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread4.GetBlockingObjects Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread4::GetBlockingObjects
helpviewer_keywords:
- GetBlockingObjects method [.NET Framework debugging]
- ICorDebugThread4::GetBlockingObjects method [.NET Framework debugging]
ms.assetid: a7e6c54e-7be9-4e52-bbb4-95f52458e8e4
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 006535885868ef2778146f86e5395ea1f7605d6f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread4getblockingobjects-method"></a><span data-ttu-id="5815b-102">ICorDebugThread4::GetBlockingObjects 메서드</span><span class="sxs-lookup"><span data-stu-id="5815b-102">ICorDebugThread4::GetBlockingObjects Method</span></span>
<span data-ttu-id="5815b-103">순서가 지정 된 열거형을 제공 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 스레드 차단 정보를 제공 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="5815b-103">Provides an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5815b-104">구문</span><span class="sxs-lookup"><span data-stu-id="5815b-104">Syntax</span></span>  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5815b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5815b-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="5815b-106">[out] 순서가 지정 된 열거형에 대 한 포인터 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="5815b-106">[out] A pointer to an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5815b-107">설명</span><span class="sxs-lookup"><span data-stu-id="5815b-107">Remarks</span></span>  
 <span data-ttu-id="5815b-108">반환된 된 열거형의 첫 번째 요소는 스레드를 차단 하는 첫 번째 구조체에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5815b-108">The first element in the returned enumeration corresponds to the first structure that is blocking the thread.</span></span> <span data-ttu-id="5815b-109">두 번째 요소는 첫 번째, 및 등을 차단 하는 경우 비동기 프로시저 호출 (APC)를 실행 하는 동안 발생 하는 차단 항목에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5815b-109">The second element corresponds to a blocking item that is encountered while running an asynchronous procedure call (APC) when blocked on the first, and so on.</span></span>  
  
 <span data-ttu-id="5815b-110">열거형은 현재 동기화 된 상태의 기간에만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="5815b-110">The enumeration is valid only for the duration of the current synchronized state.</span></span>  
  
 <span data-ttu-id="5815b-111">동기화 된 상태가 되는 동안이 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5815b-111">This method must be called while the debuggee is in a synchronized state.</span></span>  
  
 <span data-ttu-id="5815b-112">경우 `ppBlockingObjectEnum` 가 유효한 포인터가 아닌 결과가 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5815b-112">If `ppBlockingObjectEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="5815b-113">스레드가 차단 되 고 오류를 확인할 수 없어 실패를 나타내는 HRESULT를 반환 하는 경우 그렇지 않으면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5815b-113">If a thread is blocked and the error cannot be determined, the method returns an HRESULT that indicates failure; otherwise, it returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5815b-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5815b-114">Requirements</span></span>  
 <span data-ttu-id="5815b-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5815b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5815b-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5815b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5815b-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5815b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5815b-118">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5815b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5815b-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5815b-119">See Also</span></span>  
 [<span data-ttu-id="5815b-120">ICorDebugThread4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5815b-120">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 [<span data-ttu-id="5815b-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5815b-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="5815b-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="5815b-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
