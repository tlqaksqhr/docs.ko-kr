---
title: "ICorDebugVariableHome 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: ICorDebugVariableHome
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome
helpviewer_keywords: ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 76f2bf3b-759f-4eed-bce7-119415b25915
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a561360e7ea43945a3e12a73daba5063b3ad02f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablehome-interface"></a>ICorDebugVariableHome 인터페이스
지역 변수 또는 함수 '의 인수를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetArgumentIndex 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getargumentindex-method.md)|함수 인수 인덱스를 가져옵니다.|  
|[GetCode 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getcode-method.md)|이 포함 하는 "ICorDebugCode" 인스턴스로 가져옵니다 `ICorDebugVariableHome` 개체입니다.|  
|[GetLiveRange 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getliverange-method.md)|이 변수는 라이브 기본 범위를 가져옵니다.|  
|[GetLocationType 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md)|변수의 네이티브 위치의 형식을 가져옵니다.|  
|[GetOffset 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getoffset-method.md)|변수에 대 한 기본 레지스터에서 오프셋을 가져옵니다.|  
|[GetRegister 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getregister-method.md)|위치 유형 변수를 포함 하는 레지스터 가져옵니다 `VLT_REGISTER`와의 위치 유형 변수에 대 한 기본 레지스터 `VLT_REGISTER_RELATIVE`합니다.|  
|[GetSlotIndex 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getslotindex-method.md)|지역 변수의 관리 되는 슬롯 인덱스를 가져옵니다.|  
  
## <a name="example"></a>예  
 다음 코드 조각에서는 [ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md) 라는 개체 `pCode4`합니다.  
  
```cpp  
ICorDebugCode4 *pCode4 = NULL;  
pCode->QueryInterface(IID_ICorDebugCode4, &pCode4);  
  
ICorDebugVariableEnum *pVarLocEnum = NULL;  
pCode4->EnumerateVariableHomes(&pVarLocEnum);  
  
// retrieve local variables and arguments  
ULONG celt = 0;  
pVarLocEnum->GetCount(&celt);  
ICorDebugVariableHome **homes = new ICorDebugVariableHome *[celt];  
ULONG celtFetched = 0;  
pVarLocEnum->Next(celt, homes, &celtFetched);  
  
for (int i = 0; i < celtFetched; i++)  
{  
    VariableLocationType locType = VLT_INVALID;  
    homes[i].GetLocationType(&locType);  
    switch (locType)  
    {  
    case VLT_REGISTER:  
        CorDebugRegister register = 0;  
        locals[i].GetRegister(&register);  
        // now we know which register it is in  
        break;  
    case VLT_REGISTER_RELATIVE:  
        CorDebugRegister baseRegister = 0;  
        LONG offset = 0;  
        locals[i].GetRegister(&register);  
        locals[i].GetOffset(&offset);  
        // now we know the register-relative offset  
        break;  
    case VLT_INVALID:  
        // handle case where we can't access the location  
        break;  
    }  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [ICorDebugVariableHomeEnum 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)
