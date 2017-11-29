---
title: "ICorDebugThread::CreateStepper 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.CreateStepper
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::CreateStepper
helpviewer_keywords:
- ICorDebugThread::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 4657443f-dd12-431b-a648-175c23f13c83
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b66c3e536104a46b65c92fe038fb5a92d79db299
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadcreatestepper-method"></a>ICorDebugThread::CreateStepper 메서드
ICorDebugStepper이이 ICorDebugThread의 활성 프레임을 단계별로 수 있는 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppStepper`  
 [out] 주소에 대 한 포인터는 `ICorDebugStepper` 이 스레드의 활성 프레임을 단계별로 실행 하는 사용할 수 있는 개체입니다.  
  
## <a name="remarks"></a>설명  
 활성 프레임에는 관리 되지 않는 코드 일 수 있습니다.  
  
 `ICorDebugStepper` 인터페이스는 실제 단계별 실행을 수행 하는 데 사용 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
