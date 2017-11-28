---
title: "ICorDebugProcess::GetHelperThreadID 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.GetHelperThreadID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::GetHelperThreadID
helpviewer_keywords:
- GetHelperThreadID method [.NET Framework debugging]
- ICorDebugProcess::GetHelperThreadID method [.NET Framework debugging]
ms.assetid: 84e1e605-37c1-49a5-8e12-35db85654622
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 092e99cb1d5534cee56db08b5a2eedaaa2fc4724
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocessgethelperthreadid-method"></a>ICorDebugProcess::GetHelperThreadID 메서드
디버거의 내부 도우미 스레드가의 운영 체제 (OS) 스레드 ID를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pThreadID`  
 [out] 운영 체제에 대 한 포인터 스레드 디버거의 내부 도우미 스레드가의 ID입니다.  
  
## <a name="remarks"></a>설명  
 관리 되는 관리 되지 않는 디버깅 하는 동안는 디버거의 배치 디버거가 중단점에 도달할 경우 지정한 ID 가진 스레드가 계속 실행 되도록 합니다. 디버거가이 스레드는 사용자 로부터 숨길 수도 있습니다. 도우미 스레드가 아직 프로세스에 있는 경우는 `GetHelperThreadID` 메서드에 0을 반환 합니다 *`pThreadID`합니다.  
  
 시간이 지남에 따라 변경 될 수 있으므로 도우미 스레드의 스레드 ID를 캐시할 수 없습니다. 모든 중지 이벤트에서 스레드 ID를 다시 쿼리해야 합니다.  
  
 디버거 도우미 스레드의 스레드 ID에 수정 될 모든 관리 되지 않는 [icordebugmanagedcallback:: Createthread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) 이벤트, 디버거 도우미 스레드에서의 스레드 ID를 확인 하 고 사용자 로부터 숨길 수 있도록 합니다. 관리 되지 않는 동안 도우미 스레드로 식별 되는 스레드 `ICorDebugManagedCallback::CreateThread` 이벤트 관리 되는 사용자 코드를 실행 하지 것입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl 합니다. CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
