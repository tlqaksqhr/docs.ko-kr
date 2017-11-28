---
title: "ICorDebugCode::GetCode 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.GetCode
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::GetCode
helpviewer_keywords:
- ICorDebugCode::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7137e3d1-1dad-48d8-8c37-16ac816534d3
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 12820d0be725c92754640aaa4eebca56bbc33ab6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcodegetcode-method"></a>ICorDebugCode::GetCode 메서드
디스어셈블리로 설정 된 지정된 된 함수에 대 한 모든 코드를 가져옵니다. 이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 합니다. 사용 하 여 [icordebugcode2:: Getcodechunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetCode (  
    [in] ULONG32     startOffset,   
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `startOffset`  
 [in] 오프셋은 함수의 시작 부분입니다.  
  
 `endOffset`  
 [in] 함수의 끝의 오프셋입니다.  
  
 `cBufferAlloc`  
 [in] 크기는 `buffer` 배열에 코드가 반환 됩니다.  
  
 `buffer`  
 [out] 코드가 반환 하는 배열입니다.  
  
 `pcBufferSize`  
 [out] 반환 된 바이트 수입니다.  
  
## <a name="remarks"></a>설명  
 여러 개의 청크로 나뉘어진 함수의 코드, 네이티브 오프셋의 오름차순에 연결 되며 됩니다. 명령 경계를 확인 하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** 1.0, 1.1  
  
## <a name="see-also"></a>참고 항목  
 [GetCodeChunks 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)  
 
