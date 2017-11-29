---
title: "ICorPublish::GetProcess 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublish.GetProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4c5fd66fb3ba5eba1b01451b77472a94bc16dfef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishgetprocess-method"></a>ICorPublish::GetProcess 메서드
가져옵니다는 [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) 지정한 식별자를 가진 프로세스를 나타내는 인스턴스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetProcess(  
    [in] unsigned              pid,   
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pid`  
 [in] 프로세스의 식별자입니다.  
  
 `ppProcess`  
 [out] 주소에 대 한 포인터는 `ICorPublishProcess` 프로세스를 나타내는 인스턴스입니다.  
  
## <a name="remarks"></a>설명  
 `GetProcess`프로세스가 존재 하지 않거나 현재 사용자가 디버깅할 수 있는 관리 되는 프로세스가 실패 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorPub.idl, CorPub.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorPublish 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
