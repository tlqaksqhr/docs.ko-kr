---
title: "ICorDebugThread2::GetConnectionID 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugThread2.GetConnectionID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetConnectionID
helpviewer_keywords:
- ICorDebugThread2::GetConnectionID method [.NET Framework debugging]
- GetConnectionID method [.NET Framework debugging]
ms.assetid: 9c76b587-f941-4fa1-8b86-f3494fb10c8e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 28fa949de768191061bd747034a5c951a03b8596
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread2getconnectionid-method"></a>ICorDebugThread2::GetConnectionID 메서드
이 ICorDebugThread2 개체에 대 한 연결 식별자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetConnectionID (  
    [out] CONNID *pdwConnectionId  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdwConnectionId`  
 [out] A `CONNID` 연결 식별자를 나타내는입니다.  
  
## <a name="remarks"></a>설명  
 `GetConnectionID` 변수에 0을 반환 하는 메서드는 `pdwConnectionId` 매개 변수를이 스레드는 연결의 일부가 아닌 경우.  
  
 이 스레드가의 Microsoft SQL Server 2005 Analysis Services (SSAS), 인스턴스에 연결 되어 있는 경우는 `CONNID` 서버 프로세스 식별자 (SPID)에 매핑됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
