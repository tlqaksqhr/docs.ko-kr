---
title: COR_PRF_CODEGEN_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_CODEGEN_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODEGEN_FLAGS
helpviewer_keywords:
- COR_PRF_CODEGEN_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 3e184022-0247-4824-a23d-6b29593d8d01
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ab5612a2bb48b2cc93e0150f45107e474a4e6217
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452119"
---
# <a name="corprfcodegenflags-enumeration"></a>COR_PRF_CODEGEN_FLAGS 열거형
으로 설정할 수 있는 코드 생성 플래그를 정의 고 [icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) 메서드.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|함수가 없는이 함수 본문으로 인라인 처리 되지 않습니다. 그러나 함수 자체의 호출자에 인라인 처리할 수 있습니다.|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|이 함수 본문에 대 한 모든 최적화를 비활성화 됩니다. 그러나 함수 자체 수 여전히 인라인 처리할 수의 호출자에 있습니다.|  
  
## <a name="remarks"></a>설명  
 `COR_PRF_CODEGEN_FLAGS` 열거형에서 사용 되는 [icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) 메서드 프로파일러는 JIT 다시 컴파일된 함수에 대 한 코드 생성을 제어를 사용할 수 있도록 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [프로파일링 열거형](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
