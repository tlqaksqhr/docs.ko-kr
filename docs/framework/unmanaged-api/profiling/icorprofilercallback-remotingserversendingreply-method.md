---
title: "ICorProfilerCallback::RemotingServerSendingReply 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingServerSendingReply
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingServerSendingReply
helpviewer_keywords:
- RemotingServerSendingReply method [.NET Framework profiling]
- ICorProfilerCallback::RemotingServerSendingReply method [.NET Framework profiling]
ms.assetid: dfe84a19-2e03-4be2-8b25-f02bad38e4a9
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4f8fa5a81231c8181e0d0257a1bbfdb4a1f0a7a0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a>ICorProfilerCallback::RemotingServerSendingReply 메서드
프로세스에서 원격 메서드 호출 요청 처리를 완료 하 고 채널을 통해 회신을 전송 하려고 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pCookie`  
 [in] 에 제공 된 값과 일치 하는 GUID에 대 한 포인터 [icorprofilercallback:: Remotingclientreceivingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) 이러한 조건:  
  
-   원격 GUID 쿠키가 활성화 되어 있습니다.  
  
-   채널에서 메시지를 전송 하는 데 성공 합니다.  
  
-   GUID 쿠키는 클라이언트 프로세스에서 활성 상태입니다.  
  
 이렇게 하면 원격 호출 및 논리 호출 스택의 만드는 쉽게 쌍 있습니다.  
  
 `fIsAsync`  
 [in] 값을 `true` 는 호출이 고, 그렇지 않으면 비동기 경우 `false`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
