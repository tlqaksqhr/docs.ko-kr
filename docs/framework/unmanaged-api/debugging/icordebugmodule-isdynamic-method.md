---
title: "ICorDebugModule::IsDynamic 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.IsDynamic
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::IsDynamic
helpviewer_keywords:
- IsDynamic method [.NET Framework debugging]
- ICorDebugModule::IsDynamic method [.NET Framework debugging]
ms.assetid: 5eefe716-5025-4a4c-970c-c823cdc7bb87
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e3583749ddb48015b43d45061d3e4cb10e08016b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmoduleisdynamic-method"></a>ICorDebugModule::IsDynamic 메서드
이 모듈에 동적 인지 여부를 나타내는 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pDynamic`  
 [out] `true` 이 모듈이 고, 그렇지 않으면 동적 경우 `false`합니다.  
  
## <a name="remarks"></a>설명  
 동적 모듈 새 클래스를 추가할 수 있습니다 및 모듈을 로드 한 후에 기존 클래스를 삭제 합니다. [icordebugmanagedcallback:: Loadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) 및 [icordebugmanagedcallback:: Unloadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) 콜백을 클래스 때 추가 또는 삭제 되었음을 디버거에 알리기.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
