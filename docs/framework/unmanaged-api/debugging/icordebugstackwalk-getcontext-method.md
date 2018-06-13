---
title: ICorDebugStackWalk::GetContext 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetContext
helpviewer_keywords:
- GetContext method, ICorDebugStackWalk interface [.NET Framework debugging]
- ICorDebugStackWalk::GetContext method [.NET Framework debugging]
ms.assetid: 081d1c95-152b-4797-8552-18453eb7b14b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1126842a30f19831cc845bcfccc0e08f4bf5f6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422674"
---
# <a name="icordebugstackwalkgetcontext-method"></a>ICorDebugStackWalk::GetContext 메서드
현재 프레임에 대 한 컨텍스트를 반환 된 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `contextFlags`  
 [in] (WinNT.h에 정의 됨)은 컨텍스트 버퍼의 요청 된 콘텐츠를 나타내는 플래그입니다.  
  
 `contextBufSize`  
 [in] 컨텍스트 버퍼의 할당 된 크기입니다.  
  
 `contextSize`  
 [out] 컨텍스트의 실제 크기입니다. 이 값은 컨텍스트 버퍼의 크기 보다 작거나 이어야 합니다.  
  
 `contextBuf`  
 [out] 상황에 맞는 버퍼입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|현재 프레임에 대 한 컨텍스트가 반환 되었습니다.|  
|E_FAIL|컨텍스트를 반환할 수 없습니다.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)|상황에 맞는 버퍼가 너무 작습니다.|  
|CORDBG_E_PAST_END_OF_STACK|프레임 포인터는 이미; 스택의 끝 따라서 추가 프레임 없음 액세스할 수 있습니다.|  
  
## <a name="exceptions"></a>예외  
  
## <a name="remarks"></a>설명  
 예 비휘발성 레지스터: 레지스터의 하위 집합만 복원 해제 때문에 컨텍스트가 다 레지스터 상태 호출 시.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
