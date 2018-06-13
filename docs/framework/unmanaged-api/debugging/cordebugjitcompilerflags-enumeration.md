---
title: CorDebugJITCompilerFlags 열거형
ms.date: 03/30/2017
api_name:
- CorDebugJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugJITCompilerFlags
helpviewer_keywords:
- CorDebugJITCompilerFlags enumeration [.NET Framework debugging]
ms.assetid: c0774f70-5bed-45e8-9922-fdad778c4c33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5835da6ee20673c2662f1166d304a45ca3e9daeb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405322"
---
# <a name="cordebugjitcompilerflags-enumeration"></a>CorDebugJITCompilerFlags 열거형
관리되는 JIT(Just-In-Time) 컴파일러의 동작에 영향을 주는 값을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|컴파일러는 컴파일 데이터 문제를 추적 해야 하 고 최적화를 허용을 지정 합니다.|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|컴파일러가 하지만 최적화는 비활성화 컴파일 데이터를 추적 하도록 지정 합니다.|  
|`CORDEBUG_JIT_ENABLE_ENC`|컴파일러가 최적화를 비활성화 하는 컴파일 데이터를 추적 하도록 및 편집 하며 계속 하기 기술을 지정 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 열거형](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
