---
title: "ICorDebugDataTarget::ReadVirtual 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugDataTarget.ReadVirtual Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugDataTarget::ReadVirtual
helpviewer_keywords:
- ICorDebugDataTarget::ReadVirtual method [.NET Framework debugging]
- ReadVirtual method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: 55e57640-b3d2-413d-b4f4-fbc27fb8e37c
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9b9f0399c05155a9925624e5c9d6bcb6a52f024
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatargetreadvirtual-method"></a>ICorDebugDataTarget::ReadVirtual 메서드
지정된 된 주소에서 시작 하는 인접 한 메모리 블록을 가져오고 제공된 된 버퍼에 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `address`  
 [in] 요청 된 메모리의 시작 주소입니다.  
  
 `pbuffer`  
 [out] 메모리를 저장할 버퍼입니다.  
  
 `bytesRequested`  
 [in] 대상 주소에서 바이트 수입니다.  
  
 `pBytesRead`  
 [out] 바이트 수가 대상 주소에서 실제로 읽는 합니다. 보다 적을 수 있습니다 `bytesRequested`합니다.  
  
## <a name="remarks"></a>설명  
 지정 된 시작 주소) (에서 첫 번째 바이트를 읽을 수 호출 성공 (자체 설명 되는 null로 끝나는 문자열 처럼의 길이와 데이터 구조를 효율적으로 읽을)를 반환 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugDataTarget 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
