---
title: ICorDebugThread::GetHandle 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetHandle method [.NET Framework debugging]
ms.assetid: 172ef8c4-2ead-4cfc-bd2e-dee4fb7191cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 358597edc9fbc5203e5c00a5fb4d04019281060d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418274"
---
# <a name="icordebugthreadgethandle-method"></a>ICorDebugThread::GetHandle 메서드
이 ICorDebugThread의 활성 부분에 대 한 현재 핸들을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `phThreadHandle`  
 [out] 이 스레드의 활성 부분 핸들 인 HTHREAD에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 핸들은 프로세스는 실행 되 고 스레드의 다른 부분에 대해 다를 수 있습니다 변경 될 수 있습니다.  
  
 디버깅 API에서이 핸들을 소유 합니다. 디버거 사용 하기 전에 복제 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
