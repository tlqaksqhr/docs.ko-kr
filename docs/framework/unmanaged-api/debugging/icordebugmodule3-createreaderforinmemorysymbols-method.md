---
title: ICorDebugModule3::CreateReaderForInMemorySymbols 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule3.CreateReaderForInMemorySymbols
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3::CreateReaderForInMemorySymbols
helpviewer_keywords:
- CreateReaderForInMemorySymbols method, ICorDebugModule3 interface [.NET Framework debugging]
- ICorDebugModule3::CreateReaderForInMemorySymbols method [.NET Framework debugging]
ms.assetid: af317171-d66d-4114-89eb-063554c74940
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 76f7b53f800bc8c5c23f49a0781287a38bf8c959
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a>ICorDebugModule3::CreateReaderForInMemorySymbols 메서드
동적 모듈에 대 한 디버그 기호 판독기를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
#### <a name="parameters"></a>매개 변수  
 riid  
 [in] 반환할 COM 인터페이스의 IID입니다. 이 일반적으로 [ISymUnmanagedReader 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)합니다.  
  
 ppObj  
 [out] 반환 되는 인터페이스에 대 한 포인터에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 S_OK  
 판독기를 성공적으로 만들었습니다.  
  
 CORDBG_E_MODULE_LOADED_FROM_DISK  
 모듈은 메모리 또는 동적 모듈이 아닙니다.  
  
 CORDBG_E_SYMBOLS_NOT_AVAILABLE  
 응용 프로그램에서 지정 되지 않은 기호나 아직 제공 되지 않습니다.  
  
 E_FAIL(또는 다른 E_ 반환 코드)  
 판독기를 만들 수 없습니다.  
  
## <a name="remarks"></a>설명  
 이 메서드도만 될 수 있습니다를 메모리에 있는 (동적이 지 않은) 모듈에 대 한 기호 판독기 개체를 만드는 사용 되는 기호는 사용할 수 있는 먼저 후 (가리키는 [UpdateModuleSymbols 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) 콜백).  
  
 이 메서드가 호출 될 때마다 새 판독기 인스턴스를 반환 (같은 [CComPtrBase::CoCreateInstance](http://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6)). 디버거가 해야 결과 캐시 하 고 기본 데이터 변경 하는 경우에 새 인스턴스를 요청 하는 따라서 (때, 즉는 [LoadClass 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) 콜백을 수신) 합니다.  
  
 동적 모듈의 기호를 사용할 수 있는 권한이 첫 번째 유형은 로드할 때까지 (나타내듯이 [LoadClass 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) 콜백).  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** 4.5, 4, 3.5 SP1  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugRemoteTarget 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [ICorDebug 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
