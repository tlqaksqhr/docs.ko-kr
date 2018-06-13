---
title: COR_PRF_GC_ROOT_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_FLAGS
helpviewer_keywords:
- COR_PRF_GC_ROOT_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 4611ee6f-0f05-4d84-91e1-e83d5e7dd7e4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2d5dcb089074b52fc87a0bb83c7e062e7ef07b46
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450403"
---
# <a name="corprfgcrootflags-enumeration"></a>COR_PRF_GC_ROOT_FLAGS 열거형
가비지 수집 루트의 속성을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|루트 개체를 이동에서 가비지 수집을 방지 합니다.|  
|`COR_PRF_GC_ROOT_WEAKREF`|루트는 가비지 수집을 방해 되지는 않습니다.|  
|`COR_PRF_GC_ROOT_INTERIOR`|루트 개체 자체가 아니라 개체의 필드를 참조 합니다.|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|루트 개체의 참조 횟수 특정 값이 있으면 가비지 수집을 방지 합니다.|  
  
## <a name="remarks"></a>설명  
 `COR_PRF_GC_ROOT_FLAGS` 특수 루트에 대 한 추가 정보를 제공 하는 비트 마스크가입니다. 그러나 일부 루트는 특별 합니다. 예를 들어 일부 루트는 약한 참조를 내부 포인터, 고정 또는 참조 횟수가 계산 되지 않습니다. 이러한 루트 전달할 플래그가 있습니다. 따라서 등이 열거형을 사용 하는 메서드는 [icorprofilercallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) 메서드를 모든 플래그를 나타내는 플래그 비트 마스크에 대 한 송신 0은 해제 되어 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [프로파일링 열거형](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
