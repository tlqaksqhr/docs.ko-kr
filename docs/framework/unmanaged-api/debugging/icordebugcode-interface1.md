---
title: ICorDebugCode Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode
helpviewer_keywords: ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7bd14fb6-8b54-4484-a891-e3c21859c019
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 86659b624ef01922b6c5d1db9b3ae3697d0128b3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcode-interface1"></a>ICorDebugCode Interface1
MSIL(Microsoft Intermediate Language) 코드나 네이티브 코드의 세그먼트를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CreateBreakpoint 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|지정된 된 오프셋에 중단점을 만듭니다.|  
|[GetAddress 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|코드 세그먼트의 상대 가상 주소 (RVA)을 가져옵니다이 `ICorDebugCode` 나타냅니다.|  
|[GetCode 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|디스어셈블리로 설정 된 지정된 된 함수에 대 한 모든 코드를 가져옵니다. 이 메서드는 더 이상 사용 되지 않습니다. 사용 하 여 [icordebugcode2:: Getcodechunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) 대신 합니다.|  
|[GetEnCRemapSequencePoints 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|구현되지 않았습니다.|  
|[GetFunction 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|이 연결 된 "ICorDebugFunction" 가져옵니다 `ICorDebugCode`합니다.|  
|[GetILToNativeMapping 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|MSIL 오프셋에서 네이티브 오프셋 간의 매핑을 나타내는 "COR_DEBUG_IL_TO_NATIVE_MAP" 인스턴스의 배열을 가져옵니다.|  
|[GetSize 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|이 표시 되는 이진 코드를 바이트 단위로 크기를 가져옵니다 `ICorDebugCode`합니다.|  
|[GetVersionNumber 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|코드의 버전을 식별 하는 1부터 번호를 가져옵니다이 `ICorDebugCode` 나타냅니다.|  
|[IsIL 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|나타내는 값을 가져옵니다 여부이 `ICorDebugCode` MSIL에 컴파일된 합니다.|  
  
## <a name="remarks"></a>설명  
 `ICorDebugCode`MSIL 또는 네이티브 코드를 나타낼 수 있습니다. MSIL 코드를 나타내는 "ICorDebugFunction" 개체는 0 이나 1 점이 `ICorDebugCode` 관련 된 개체입니다. 네이티브 코드를 나타내는 "ICorDebugFunction" 개체 개수에 관계 없이 점이 `ICorDebugCode` 관련 된 개체입니다.  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
    
 [ICorDebugCode3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
