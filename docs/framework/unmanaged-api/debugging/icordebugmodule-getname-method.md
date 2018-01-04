---
title: "ICorDebugModule::GetName 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.GetName
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::GetName
helpviewer_keywords:
- ICorDebugModule::GetName method [.NET Framework debugging]
- GetName method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: db499637-7ba9-421e-b8b1-35856995e80b
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 64be936277b0ebe04248ae2913a882b628ee363f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodulegetname-method"></a>ICorDebugModule::GetName 메서드
모듈의 파일 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cchname`  
 [in] `szName` 배열의 크기입니다.  
  
 `pcchName`  
 [in] 반환 된 이름의 길이에 대 한 포인터입니다.  
  
 `szName`  
 [out] 반환된 된 이름을 저장 하는 배열입니다.  
  
## <a name="remarks"></a>설명  
 `GetName` 모듈의 파일 이름에는 디스크에 있는 이름과 일치 하는 경우 메서드가 s_ok이 고 HRESULT를 반환 합니다. `GetName`맞추어진 등을 위해 동적 또는 메모리에 모듈 이름이 S_FALSE HRESULT를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
    
 
