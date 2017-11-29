---
title: "ICorDebugILFrame::SetIP 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame.SetIP
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame::SetIP
helpviewer_keywords:
- SetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::SetIP method [.NET Framework debugging]
ms.assetid: 23f38dc1-85e4-4263-9235-2d05bbb6a833
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b92dc50777d55ba6bfa1a0559ab198dd69114ade
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframesetip-method"></a>ICorDebugILFrame::SetIP 메서드
Microsoft MSIL (intermediate language) 코드에서 지정된 된 오프셋된 위치를 명령 포인터를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nOffset`  
 MSIL 코드 내의 오프셋된 위치입니다.  
  
## <a name="remarks"></a>설명  
 에 대 한 호출이 `SetIP` 즉시 모든 프레임 및 현재 스레드에 대 한 체인을 무효화 합니다. 디버거를 호출한 후 프레임 정보가 필요한 경우 `SetIP`, 새 스택 추적을 수행 해야 합니다.  
  
 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 스택 프레임을 유효한 상태로 유지 하려고 합니다. 그러나 경우에 프레임 유효한 상태, 초기화 되지 않은 지역 변수와 같은 문제가 발생할 수 있습니다. 호출자가 실행 중인 프로그램의 일관성이 유지 되도록 합니다.  
  
 64 비트 플랫폼에서 명령 포인터 없습니다에서 이동할 수는 `catch` 또는 `finally` 블록입니다. 경우 `SetIP` 호출 되는 64 비트 플랫폼에서 이러한 이동 되도록 오류를 나타내는 HRESULT 반환 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
