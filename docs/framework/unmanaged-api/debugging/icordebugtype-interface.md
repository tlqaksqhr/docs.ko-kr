---
title: ICorDebugType Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType
helpviewer_keywords: ICorDebugType interface [.NET Framework debugging]
ms.assetid: 94e02e31-67ea-4b00-8148-a46740a4571d
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 503d0debef2ec1bebd674234051db8101dcb0de2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugtype-interface1"></a>ICorDebugType Interface1
형식을, 기본 또는 복합 (즉, 사용자 정의)를 나타냅니다. 형식이 제네릭이면 `ICorDebugType`는 인스턴스화된 제네릭 형식을 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[EnumerateTypeParameters 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|제네릭 참조 하는 ICorDebugTypeEnum에 대 한 인터페이스 포인터를 가져옵니다 <xref:System.Type> 이 참조 하는 클래스의 매개 변수 `ICorDebugType`합니다.|  
|[GetBase 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|한 인터페이스 포인터를 가져옵니다는 `ICorDebugType` 이 참조 하는 클래스의 기본 클래스를 참조 하는 `ICorDebugType`있는 경우.|  
|[GetClass 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|이 형식의 생성자를 참조 하는 ICorDebugClass에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugType`합니다.|  
|[GetFirstTypeParameter 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|한 인터페이스 포인터를 가져옵니다는 `ICorDebugType` 첫 번째 제네릭을 참조 하는 <xref:System.Type> 이 참조 하는 클래스의 생성자에 대 한 매개 변수 `ICorDebugType`합니다.|  
|[GetRank 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|배열 형식에서 차원 수를 가져옵니다.|  
|[GetStaticFieldValue 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|토큰을 지정 된 스택 프레임에 지정 된 필드에서 참조 하는 정적 필드의 값이 포함 된 ICorDebugValue에 인터페이스 포인터를 가져옵니다.|  
|[GetType 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|공용 언어 런타임의 네이티브 형식을 설명 하는 CorElementType 값을 가져옵니다 <xref:System.Type> 받았습니다 참조 `ICorDebugType`합니다.|  
  
## <a name="remarks"></a>설명  
 형식이 제네릭인 경우 `ICorDebugClass` 는 인스턴스화되지 않은 형식입니다. `ICorDebugType` 인터페이스는 인스턴스화된 제네릭 형식을 나타냅니다. 예를 들어 Hashtable\<K, V >을 표시 `ICorDebugClass`반면, 해시 테이블\<Int32, String >을 표시 `ICorDebugType`합니다.  
  
 제네릭이 아닌 형식은 둘 다로 표현 됩니다 `ICorDebugClass` 및 `ICorDebugType`합니다. 두 번째 인터페이스 형식 인스턴스화 처리 하는.NET Framework 버전 2.0에서에서 도입 되었습니다.  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
