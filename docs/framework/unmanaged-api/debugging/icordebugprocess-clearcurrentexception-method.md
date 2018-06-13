---
title: ICorDebugProcess::ClearCurrentException 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ClearCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ClearCurrentException
helpviewer_keywords:
- ClearCurrentException method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::ClearCurrentException method [.NET Framework debugging]
ms.assetid: 9e02ee1a-e495-4578-bfb5-b946274bede7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d2515e21ec00bd656eafd21a092a27304f7b1769
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419018"
---
# <a name="icordebugprocessclearcurrentexception-method"></a><span data-ttu-id="8a600-102">ICorDebugProcess::ClearCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="8a600-102">ICorDebugProcess::ClearCurrentException Method</span></span>
<span data-ttu-id="8a600-103">지정 된 스레드에 대해 현재 관리 되지 않는 예외를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="8a600-103">Clears the current unmanaged exception on the given thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a600-104">구문</span><span class="sxs-lookup"><span data-stu-id="8a600-104">Syntax</span></span>  
  
```  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a600-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8a600-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="8a600-106">[in] 현재 관리 되지 않는 예외는 지워집니다 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8a600-106">[in] The ID of the thread on which the current unmanaged exception will be cleared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a600-107">설명</span><span class="sxs-lookup"><span data-stu-id="8a600-107">Remarks</span></span>  
 <span data-ttu-id="8a600-108">이 메서드를 호출 하기 전에 호출 [icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) 스레드가 디버기에 서 무시 해야 하는 관리 되지 않는 예외에서 보고 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="8a600-108">Call this method before calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) when a thread has reported an unmanaged exception that should be ignored by the debuggee.</span></span> <span data-ttu-id="8a600-109">처리 중인 대역 (IB)와 지정한 스레드에서 밴드의 범위를 벗어난 (OOB) 이벤트를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="8a600-109">This will clear both the outstanding in-band (IB) and out-of-band (OOB) events on the given thread.</span></span> <span data-ttu-id="8a600-110">모든 OOB 중단점 및 단일 단계 예외 자동으로 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="8a600-110">All OOB breakpoints and single-step exceptions are automatically cleared.</span></span>  
  
 <span data-ttu-id="8a600-111">사용 하 여 [icordebugthread2:: Interceptcurrentexception](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) 현재 가로채기 위해 스레드의 예외를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a600-111">Use [ICorDebugThread2::InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) to intercept the current managed exception on a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a600-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8a600-112">Requirements</span></span>  
 <span data-ttu-id="8a600-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8a600-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a600-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a600-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a600-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a600-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a600-116">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a600-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
