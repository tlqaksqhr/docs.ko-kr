---
title: ICorDebugAppDomain Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain
helpviewer_keywords:
- ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: be7ae711-1217-4a44-be40-166e29641b77
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84a11b6264ac0e241c1975eea5626edbdddce206
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugappdomain-interface1"></a>ICorDebugAppDomain Interface1
응용 프로그램 도메인 디버깅에 사용하는 메서드를 제공합니다. 이 인터페이스는 ICorDebugController의 서브 클래스입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Attach 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-attach-method.md)|응용 프로그램 도메인에서 디버거를 연결합니다.|  
|[EnumerateAssemblies 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|응용 프로그램 도메인에서 어셈블리에 대 한 열거자를 가져옵니다.|  
|[EnumerateBreakpoints 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratebreakpoints-method.md)|응용 프로그램 도메인에서 활성화 된 모든 중단점에 대 한 열거자를 가져옵니다.|  
|[EnumerateSteppers 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratesteppers-method.md)|응용 프로그램 도메인에서 모든 활성 스텝 퍼에 대 한 열거자를 가져옵니다.|  
|[GetId 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getid-method.md)|응용 프로그램 도메인의 고유 ID를 가져옵니다.|  
|[GetModuleFromMetaDataInterface 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getmodulefrommetadatainterface-method.md)|지정 된 메타 데이터 인터페이스 ICorDebugModule 개체를 가져옵니다.|  
|[GetName 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getname-method.md)|응용 프로그램 도메인의 이름을 가져옵니다.|  
|[GetObject 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getobject-method.md)|공용 언어 런타임 (CLR) 응용 프로그램 도메인에 대 한 인터페이스 포인터를 가져옵니다.|  
|[GetProcess 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getprocess-method.md)|응용 프로그램 도메인을 포함 하는 프로세스를 가져옵니다.|  
|[IsAttached 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-isattached-method.md)|디버거에서 응용 프로그램 도메인에 연결 되었는지 여부를 결정 합니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
