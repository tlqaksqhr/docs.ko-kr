---
title: ICorDebugModule2 Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule2
helpviewer_keywords: ICorDebugModule2 interface [.NET Framework debugging]
ms.assetid: 0847e64f-fdbe-4c96-8168-da20fdc84d80
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 97259783d34babe3f0f229f5d62b3e945c0ac624
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodule2-interface1"></a>ICorDebugModule2 Interface1
ICorDebugModule 인터페이스를 논리적으로 확장으로 사용 됩니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[ApplyChanges 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|실행 중인 프로세스에 메타 데이터의 변경 내용과 Microsoft MSIL (intermediate language) 코드의 변경 내용을 적용합니다.|  
|[GetJITCompilerFlags 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|이 컴파일 타임 JIT ()를 제어 하는 플래그를 가져옵니다 `ICorDebugModule2`합니다.|  
|[ResolveAssembly 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|지정한 메타 데이터 토큰에서 참조 하는 어셈블리를 확인 합니다.|  
|[SetJITCompilerFlags 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|이 대 한 JIT 컴파일을 제어 하는 플래그를 설정 `ICorDebugModule2`합니다.|  
|[SetJMCStatus 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|이 모든 클래스의 모든 메서드의 코드 JMC (내) 상태를 설정 `ICorDebugModule2` 에서 제외 하 고 지정된 된 값으로는 `pTokens` 반대 값을 설정 하는 배열입니다.|  
  
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
