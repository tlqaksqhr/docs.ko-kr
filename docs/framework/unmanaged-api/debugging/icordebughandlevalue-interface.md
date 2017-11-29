---
title: ICorDebugHandleValue Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHandleValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHandleValue
helpviewer_keywords: ICorDebugHandleValue interface [.NET Framework debugging]
ms.assetid: 66fcd2b8-ac66-414b-83a8-75a925e17772
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b56c23caaaed2bc63c724769db1198fd088f7f1a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebughandlevalue-interface1"></a>ICorDebugHandleValue Interface1
디버거에서 가비지 수집에 대 한 핸들을 만든 참조 값을 나타내는 ICorDebugReferenceValue의 하위 클래스입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Dispose 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|이 참조 하는 핸들을 해제 `ICorDebugHandleValue` 명시적으로 인터페이스 포인터를 해제 하지 않고 개체입니다.|  
|[GetHandleType 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|이 참조 하는 핸들의 종류를 설명 하는 CorDebugHandleType 값을 가져옵니다 `ICorDebugHandleValue`합니다.|  
  
## <a name="remarks"></a>설명  
 `ICorDebugReferenceValue` 개체 디버깅된 되는 코드의 실행이 중단 되 면 무효화 됩니다. `ICorDebugHandleValue` 명시적으로 해제 될 때까지 중단과 continuation, 참조를 유지 합니다.  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
