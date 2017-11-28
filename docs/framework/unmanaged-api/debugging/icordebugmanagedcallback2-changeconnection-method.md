---
title: "ICorDebugManagedCallback2::ChangeConnection 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.ChangeConnection
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::ChangeConnection
helpviewer_keywords:
- ICorDebugManagedCallback2::ChangeConnection method [.NET Framework debugging]
- ChangeConnection method [.NET Framework debugging]
ms.assetid: 7263f9a9-4c0b-4d82-a181-288873fb2b18
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7c62859cb6a3e61af9670834db169410cecb6787
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a>ICorDebugManagedCallback2::ChangeConnection 메서드
지정 된 연결과 관련 된 작업 집합이 변경 된 디버거에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pProcess`  
 [in] 변경 된 연결을 포함 하는 프로세스를 나타내는 "ICorDebugProcess" 개체에 대 한 포인터입니다.  
  
 `dwConnectionId`  
 [in] 변경 하는 연결의 ID입니다.  
  
## <a name="remarks"></a>설명  
 A `ChangeConnection` 콜백 중 한 가지는 다음과 같은 경우에 발생 합니다.  
  
-   때 연결을 포함 하는 프로세스에 디버거 연결 합니다. 이 경우 런타임에 생성 되며 발송 한 [icordebugmanagedcallback2:: Createconnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) 이벤트 및 `ChangeConnection` 프로세스에서 각 연결에 대 한 이벤트입니다. A `ChangeConnection` 만들어진 이후 해당 연결의 작업 집합이 변경 된 여부에 관계 없이 모든 기존 연결에 대해 이벤트가 생성 됩니다.  
  
-   호스트를 호출 하는 경우 [iclrdebugmanager:: Setconnectiontasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) 에 [호스팅 API](../../../../docs/framework/unmanaged-api/hosting/index.md)합니다.  
  
 디버거에서 새 변경 내용을 적용할 프로세스의 모든 스레드를 검색 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugManagedCallback2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [ICorDebugManagedCallback 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
