---
title: ICorDebugProcess::EnableLogMessages 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.EnableLogMessages
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::EnableLogMessages
helpviewer_keywords:
- ICorDebugProcess::EnableLogMessages method [.NET Framework debugging]
- EnableLogMessages method [.NET Framework debugging]
ms.assetid: 14a4e5a3-3eaf-4f53-9dd1-762726963a23
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0dbac6570fc0af0452a0e44f838124afbf6a4fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419886"
---
# <a name="icordebugprocessenablelogmessages-method"></a><span data-ttu-id="7695b-102">ICorDebugProcess::EnableLogMessages 메서드</span><span class="sxs-lookup"><span data-stu-id="7695b-102">ICorDebugProcess::EnableLogMessages Method</span></span>
<span data-ttu-id="7695b-103">사용 하도록 설정 하 고 디버거를 로그 메시지의 전송을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="7695b-103">Enables and disables the transmission of log messages to the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7695b-104">구문</span><span class="sxs-lookup"><span data-stu-id="7695b-104">Syntax</span></span>  
  
```  
HRESULT EnableLogMessages([in]BOOL fOnOff);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7695b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7695b-105">Parameters</span></span>  
 `fOnOff`  
 <span data-ttu-id="7695b-106">[in] `true` ; 로그 메시지의 전송을 사용 하도록 설정 `false` 전송을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7695b-106">[in] `true` enables the transmission of log messages; `false` disables the transmission.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7695b-107">설명</span><span class="sxs-lookup"><span data-stu-id="7695b-107">Remarks</span></span>  
 <span data-ttu-id="7695b-108">이 메서드는 한 후에 유효는 [icordebugmanagedcallback:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) 콜백이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="7695b-108">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback occurs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7695b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7695b-109">Requirements</span></span>  
 <span data-ttu-id="7695b-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7695b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7695b-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7695b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7695b-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7695b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7695b-113">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7695b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
