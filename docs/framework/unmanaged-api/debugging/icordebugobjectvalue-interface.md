---
title: ICorDebugObjectValue Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugObjectValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugObjectValue
helpviewer_keywords: ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 937de6a0-6fbf-4ddc-80ea-a6217b73e62b
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6dfde9f212936b1a0d0f5a6e76eafd4a2e62356c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugobjectvalue-interface1"></a>ICorDebugObjectValue Interface1
개체를 포함 하는 값을 나타내는 "ICorDebugValue"의 하위 클래스입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetClass 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)|공용 언어 런타임 (CLR)에 대 한 인터페이스 포인터를 가져옵니다 <xref:System.Type> 개체의이 `ICorDebugObjectValue` 참조 합니다.|  
|[GetContext 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getcontext-method.md)|구현되지 않았습니다.|  
|[GetFieldValue 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getfieldvalue-method.md)|한 인터페이스 포인터를 가져옵니다는 [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) 지정된 된 클래스의 지정된 된 필드의 값을 나타내는입니다.|  
|[GetManagedCopy 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getmanagedcopy-method.md)|사용되지 않습니다. 이 메서드를 호출 하지 마십시오.|  
|[GetVirtualMethod 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getvirtualmethod-method.md)|구현되지 않았습니다.|  
|[IsValueClass 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-isvalueclass-method.md)|이 참조 하는 개체가 있는지 여부를 나타내는 값을 가져옵니다 `ICorDebugObjectValue` 값 형식이 있습니다.|  
|[SetFromManagedCopy 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-setfrommanagedcopy-method.md)|사용되지 않습니다. 이 메서드를 호출 하지 마십시오.|  
  
## <a name="remarks"></a>설명  
 `ICorDebugObjectValue` 디버깅 중인 프로세스가 계속 될 때까지 유효 합니다.  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 
