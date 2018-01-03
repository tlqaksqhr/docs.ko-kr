---
title: "ICorDebugDataTarget::GetThreadContext 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugDataTarget.GetThreadContext Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 44543ca3546827b38643cab0e047032a96be9ea6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a>ICorDebugDataTarget::GetThreadContext 메서드
지정된 된 스레드에 대 한 현재 스레드 컨텍스트를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwThreadID`  
 [in] 식별자를 검색할 수 있는 컨텍스트는 스레드입니다. 식별자가 운영 체제에 의해 정의 되었습니다.  
  
 `contextFlags`  
 [in] 컨텍스트의 어떤 부분 읽도록 나타내는 플랫폼에 관계 없이 플래그의 비트 조합입니다.  
  
 `contextSize`  
 [in] `pContext`의 크기입니다.  
  
 `pContext`  
 [out] 스레드 컨텍스트를 저장할 버퍼입니다.  
  
## <a name="remarks"></a>설명  
 Windows 플랫폼에서 `pContext` 이어야 합니다는 `CONTEXT` (WinNT.h에 정의 됨)로 지정 된 컴퓨터 종류에 적합 한는 구조는 [icordebugdatatarget:: Getplatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) 메서드. `contextFlags`동일한 값으로 있어야 합니다.는 `ContextFlags` 필드는 `CONTEXT` 구조입니다. `CONTEXT` 구조는 특정 프로세서 관련; 대 한 자세한 내용은 WinNT.h 파일을 참조 하십시오.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugDataTarget 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
