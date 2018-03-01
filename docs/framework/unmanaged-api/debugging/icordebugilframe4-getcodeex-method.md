---
title: "ICorDebugILFrame4::GetCodeEx 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetLocalVariableEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aeda0e42-29ee-4ca8-9f21-ac4641677a62
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e5d1d480014e90d3fea9790b10e0dace5a0847ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframe4getcodeex-method"></a>ICorDebugILFrame4::GetCodeEx 메서드
[.NET Framework 4.5.2 이상 버전에서 지원됨]  
  
 이 스택 프레임에서 실행 중인 코드에 대한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `flags`  
 [in] [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) 프로파일러 ReJIT 요청에 의해 정의 된 중간 언어 (IL) 프레임에 포함 되는지 여부를 지정 하는 열거형 멤버입니다.  
  
 `ppCode`  
 [out] 이 스택 프레임이 실행 되는 코드를 나타내는 "ICorDebugCode" 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 비슷합니다는 [icordebugframe:: Getcode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) 메서드를 필요에 따라 프로파일러 ReJIT 요청에 의해 정의 된 코드를 액세스 한다는 점을 제외 하 고 있습니다. 이 메서드를 호출할는 `flags` 값 `ILCODE_ORIGINAL_IL` 호출 하는 것과 같습니다 [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)메서드가 계측 되는 경우 해당 IL에 액세스할 수 없습니다. `ILCODE_REJIT_IL`을 사용하는 경우 디버거가 프로파일러 ReJIT 요청에 의해 정의된 IL에 액세스할 수 있습니다. IL이 계측 되지 않는 경우 `ppCode` 은 **null**, 메서드가 반환 하 고 `S_OK`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugILFrame4 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [방법 가이드는 ReJIT:](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
