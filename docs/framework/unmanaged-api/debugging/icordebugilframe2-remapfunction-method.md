---
title: "ICorDebugILFrame2::RemapFunction 메서드"
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
- ICorDebugILFrame2.RemapFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::RemapFunction
helpviewer_keywords:
- ICorDebugILFrame2::RemapFunction method [.NET Framework debugging]
- RemapFunction method [.NET Framework debugging]
ms.assetid: dd639ba0-f77b-426d-9ff6-f92706840348
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a9fed4759576d1b6d2fec1a5e9c1e36019e5944c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframe2remapfunction-method"></a>ICorDebugILFrame2::RemapFunction 메서드
새 Microsoft MSIL (intermediate language) 오프셋을 지정 하 여 편집된 된 함수를 다시 매핑합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `newILOffset`  
 [in] 스택 프레임의 새로운 MSIL 오프셋 명령 포인터를 배치할입니다. 이 값은 시퀀스 위치 여야 합니다.  
  
 호출자의이 값의 유효성을 검사 합니다. 예를 들어 MSIL 오프셋 함수 범위 바깥쪽 올바르지 않습니다.  
  
## <a name="remarks"></a>설명  
 프레임의 함수가 편집 되어, 디버거를 호출할 수는 `RemapFunction` 메서드를 실행할 수 있도록 최신 버전의 프레임의 함수에서 바꿀 수 있습니다. 코드 실행은 지정된 된 MSIL 오프셋에서 시작 됩니다.  
  
> [!NOTE]
>  호출 `RemapFunction`처럼 호출 [icordebugilframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), 관련 된 스레드에 대 한 스택 추적을 생성 하는 모든 디버깅 인터페이스를 즉시 무효화 됩니다. 이러한 인터페이스 [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame, 및 ICorDebugNativeFrame 합니다.  
  
 `RemapFunction` 메서드는 현재 프레임의 컨텍스트에서 하 고 하나는 다음과 같은 경우에만 호출할 수 있습니다.  
  
-   받은 후는 [icordebugmanagedcallback2:: Functionremapopportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) 계속 하지 아직 콜백입니다.  
  
-   때문에 코드 실행을 중지 하는 동안는 [icordebugmanagedcallback:: Editandcontinueremap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) 이 프레임에 대 한 이벤트입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
