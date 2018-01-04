---
title: "ICorDebugProcess6::GetExportStepInfo 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d3c69bbc904f54636e56be6d235d1070b9fecf1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess6getexportstepinfo-method"></a>ICorDebugProcess6::GetExportStepInfo 메서드
관리 코드를 단계별로 실행할 수 있도록 런타임에 내보낸 함수에 대한 정보를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,   
    [out] CorDebugCodeInvokeKind* pInvokeKind,   
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pszExportName  
 [in] PE 내보내기 테이블에 기록된 런타임 내보내기 함수의 이름입니다.  
  
 invokeKind  
 [out] 멤버에 대 한 포인터는 [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) 내보낸된 함수가 관리 코드를 호출할 방법을 설명 하는 열거형입니다.  
  
 invokePurpose  
 [out] 멤버에 대 한 포인터는 [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) 내보낸된 함수가 관리 코드를 호출 하는 이유를 설명 하는 열거형입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음 표에 나와 있는 값을 반환할 수 있습니다.  
  
|반환 값|설명|  
|------------------|-----------------|  
|`S_OK`|메서드 호출이 성공했습니다.|  
|`E_POINTER`|`pInvokeKind`또는 `pInvokePurpose` 은 **null**합니다.|  
|기타 오류 `HRESULT` 값입니다.|상황에 따라 적절하게 설정됩니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugProcess6 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
