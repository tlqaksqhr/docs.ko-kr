---
title: "ICorDebugModule2::SetJITCompilerFlags 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule2.SetJITCompilerFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule2::SetJITCompilerFlags
helpviewer_keywords:
- ICorDebugModule2::SetJITCompilerFlags method [.NET Framework debugging]
- SetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: ea574c84-c622-4589-9a14-b55771af5e06
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cfc25e9ce15996360cd0e3c68805d3707b325f79
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a>ICorDebugModule2::SetJITCompilerFlags 메서드
이 ICorDebugModule2의 컴파일 타임 JIT ()를 제어 하는 플래그를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwFlags`  
 [in] 비트 조합 된 [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) 열거형 값입니다.  
  
## <a name="remarks"></a>설명  
 경우는 `dwFlags` 값 유효 하지 않을 경우는 `SetJITCompilerFlags` 메서드가 실패 합니다.  
  
 `SetJITCompilerFlags` 메서드 내 에서만 호출할 수 있습니다는 [icordebugmanagedcallback:: Loadmodule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) 이 모듈에 대 한 콜백입니다. 후에 메서드를 호출 하려고는 `ICorDebugManagedCallback::LoadModule` 콜백이 전달 된 실패 합니다.  
  
 편집 하며 계속 하기 64 비트 또는 Win9x 플랫폼에서 지원 되지 않습니다. 따라서 호출 하는 경우는 `SetJITCompilerFlags` CORDEBUG_JIT_ENABLE_ENC 플래그가 설정이 두 플랫폼 중 하나에 메서드 `dwFlags`, `SetJITCompilerFlags` 메서드 및 특정 모든 메서드를 편집 하 여 계속와 같은 [ICorDebugModule2:: ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md), 실패 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
