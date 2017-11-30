---
title: "ICorDebugThread::GetDebugState 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetDebugState
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetDebugState
helpviewer_keywords:
- GetDebugState method [.NET Framework debugging]
- ICorDebugThread::GetDebugState method [.NET Framework debugging]
ms.assetid: 9be27b0c-1d99-4722-b0d4-40cf6753ce5c
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4e66cc976be59c519e48d7ef9285963e5109d848
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="34a48-102">ICorDebugThread::GetDebugState 메서드</span><span class="sxs-lookup"><span data-stu-id="34a48-102">ICorDebugThread::GetDebugState Method</span></span>
<span data-ttu-id="34a48-103">이 ICorDebugThread 개체의 현재 디버그 상태를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="34a48-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34a48-104">구문</span><span class="sxs-lookup"><span data-stu-id="34a48-104">Syntax</span></span>  
  
```  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="34a48-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="34a48-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="34a48-106">[out] 이 스레드의 현재 디버그 상태를 설명 하는 CorDebugThreadState 열거형 값의 비트 조합에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="34a48-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34a48-107">설명</span><span class="sxs-lookup"><span data-stu-id="34a48-107">Remarks</span></span>  
 <span data-ttu-id="34a48-108">프로세스가 현재 중지 된 `pState` 프로세스가 계속 될이 스레드의 현재 실제 상태가 아니라 경우이 스레드에 대해 존재 하는 디버그 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="34a48-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34a48-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="34a48-109">Requirements</span></span>  
 <span data-ttu-id="34a48-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="34a48-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34a48-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34a48-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34a48-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34a48-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34a48-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34a48-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
