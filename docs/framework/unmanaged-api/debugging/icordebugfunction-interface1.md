---
title: ICorDebugFunction Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction
helpviewer_keywords:
- ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 783faea9-8083-41c1-b04a-51a81ac4c8f3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bd0dbe1304d85c856880c989312afb11d3b554c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunction-interface1"></a>ICorDebugFunction Interface1
관리되는 함수 또는 메서드를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CreateBreakpoint 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|이 함수의 시작 부분에 중단점을 만듭니다.|  
|[GetClass 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|이 함수는 멤버의 클래스를 나타내는 ICorDebugClass 개체를 가져옵니다.|  
|[GetCurrentVersionNumber 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|이 함수에 대 한 최신 편집의 버전 번호를 가져옵니다.|  
|[GetILCode 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|이 함수에 대 한 Microsoft의 MSIL (intermediate language) 코드를 가져옵니다.|  
|[GetLocalVarSigToken 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|이 표시 되는 함수의 로컬 변수 서명에 대 한 메타 데이터 토큰을 가져옵니다 `ICorDebugFunction` 인스턴스.|  
|[GetModule 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|이 함수가 정의 된 모듈을 가져옵니다.|  
|[GetNativeCode 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|이 함수에 대 한 네이티브 코드를 가져옵니다.|  
|[GetToken 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|이 함수에 대 한 메타 데이터를 토큰을 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 `ICorDebugFunction` 인터페이스는 제네릭 형식 매개 변수가 있는 함수를 나타내지 않습니다. 예를 들어 한 `ICorDebugFunction` 인스턴스 나타내더라도 `Func<T>` 아닌 `Func<string>`합니다. 호출 [icordebugilframe2:: Enumeratetypeparameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) 제네릭 형식 매개 변수를 가져오려면 합니다.  
  
 메서드의 메타 데이터 토큰, 간의 관계 `mdMethodDef`, 및 메서드의 `ICorDebugFunction` 개체 편집 하며 계속 하기는 함수에 수 있는지 여부에 따라 달라 집니다.  
  
-   사이 한 일 관계가 있습니다 편집 하며 계속 하기는 함수에 허용 되지 않는 경우는 `ICorDebugFunction` 개체 및 `mdMethodDef` 토큰입니다. 함수에, 즉 `ICorDebugFunction` 개체 개와 `mdMethodDef` 토큰입니다.  
  
-   사이 일 대 다 관계가 편집 하며 계속 하기는 함수에 허용 되는 경우는 `ICorDebugFunction` 개체 및 `mdMethodDef` 토큰입니다. 즉, 함수 인스턴스가 많은 보고서의 있을 `ICorDebugFunction`는 함수의 각 버전에 대 한 있지만 한 `mdMethodDef` 토큰입니다.  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
