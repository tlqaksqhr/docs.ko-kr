---
title: ICorDebugCode2 Interface1
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
- ICorDebugCode2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2
helpviewer_keywords:
- ICorDebugCode2 interface [.NET Framework debugging]
ms.assetid: 9321903b-7dea-40d8-ba32-99016c00cc46
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 54cada8e8211b3837e30f3d058d54af1eaf96a83
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcode2-interface1"></a>ICorDebugCode2 Interface1
"ICorDebugCode"의 기능을 확장 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetCodeChunks 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)|이 코드 개체를 구성 하는 코드 청크를 가져옵니다.|  
|[GetCompilerFlags 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcompilerflags-method.md)|이 코드 개체의 중 하나에서 적시 (JIT)의 컴파일 또는 네이티브 이미지 생성기 (Ngen.exe)를 사용 하 여 생성 되었습니다는 조건을 지정 하는 플래그를 가져옵니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
    
 [ICorDebugCode3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
