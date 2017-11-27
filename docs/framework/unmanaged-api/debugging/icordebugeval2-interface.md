---
title: ICorDebugEval2 Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2
helpviewer_keywords: ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: fce34531-2687-406d-9131-d6ad94f2ce0e
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fbcf36ff7aca84299c55083b4ae135ce0a9ec4f3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugeval2-interface1"></a>ICorDebugEval2 Interface1
"ICorDebugEval" 확장에 제네릭 형식에 대 한 지원을 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CallParameterizedFunction 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)|지정 된 "ICorDebugFunction"의 생성자 형식 매개 변수 또는 형식 매개 변수 자체 지나야 형식 안에 중첩 될 수 있는에 대 한 호출을 설정 합니다.|  
|[CreateValueForType 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)|초기 값이 null 또는 0으로 지정 된 형식의 새 "ICorDebugValue"에 대 한 포인터를 가져옵니다.|  
|[NewParameterizedArray 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md)|지정한 요소 형식 및 차원에 대 한 새 배열을 할당합니다.|  
|[NewParameterizedObject 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)|새 매개 변수가 있는 형식 개체를 인스턴스화하고 개체의 생성자 메서드를 호출 합니다.|  
|[NewParameterizedObjectNoConstructor 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)|생성자 메서드를 호출 하지 않고 지정된 된 클래스의 새 매개 변수가 있는 형식 개체를 인스턴스화합니다.|  
|[NewStringWithLength 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newstringwithlength-method.md)|지정 된 내용으로 지정 된 길이의 새 문자열을 만듭니다.|  
|[RudeAbort 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-rudeabort-method.md)|계산 중단이 `ICorDebugEval2` 현재 수행 합니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
