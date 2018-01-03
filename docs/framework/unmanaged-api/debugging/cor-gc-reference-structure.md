---
title: "COR_GC_REFERENCE 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_GC_REFERENCE
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_GC_REFERENCE
helpviewer_keywords: COR_GC_REFERENCE structure [.NET Framework debugging]
ms.assetid: 162e8179-0cd4-4110-8f06-5f387698bd62
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a86604febb7641eef147608e564a27883fdc4bec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corgcreference-structure"></a>COR_GC_REFERENCE 구조체
가비지 수집할 개체에 대한 정보를 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;   
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`domain`|핸들 또는 개체가 속해 있는 응용 프로그램 도메인에 대 한 포인터입니다. 해당 값이 경우도 `null`합니다.|  
|`location`|ICorDebugValue 또는 가비지 수집 될 개체에 해당 하는 ICorDebugReferenceValue 인터페이스입니다.|  
|`type`|A [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) 루트에서 제공 하는 위치를 나타내는 열거형 값입니다. 자세한 내용은 설명 섹션을 참조하세요.|  
|`extraData`|가비지 수집 될 개체에 대 한 추가 데이터입니다. 에 표시 된 대로이 정보는 개체의 원본에 종속 된 `type` 필드입니다. 자세한 내용은 설명 섹션을 참조하세요.|  
  
## <a name="remarks"></a>설명  
 `type` 필드는 한 [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) 참조에서 제공 하는 위치를 나타내는 열거형 값입니다. 특정 `COR_GC_REFERENCE` 값에는 다음과 같은 종류의 관리 되는 개체를 반영할 수 있습니다.  
  
-   모든 관리 되는 스택 개체 (`CorGCReferenceType.CorReferenceStack`). 여기 공용 언어 런타임에서 생성 된 개체를 비롯 하 여 관리 코드에 대 한 라이브 참조가 포함 됩니다.  
  
-   개체 핸들 테이블의 (`CorGCReferenceType.CorHandle*`). 이 강력한 참조를 포함 (`HNDTYPE_STRONG` 및 `HNDTYPE_REFCOUNT`) 및 모듈의 정적 변수.  
  
-   종료자 큐에서 개체 (`CorGCReferenceType.CorReferenceFinalizer`). 종료자 큐는 종료 자가 실행 될 때까지 개체 루트입니다.  
  
 `extraData` 필드 참조의 소스 (또는 유형)에 따라 추가 데이터를 포함 합니다. 가능한 값은 다음과 같습니다.  
  
-   `DependentSource`. 경우는 `type` 은 `CorGCREferenceType.CorHandleStrongDependent`,이 필드는 연결을 유지 하는 경우 루트 개체에서 가비지 수집 되도록 하는 개체 `COR_GC_REFERENCE.Location`합니다.  
  
-   `RefCount`. 경우는 `type` 은 `CorGCREferenceType.CorHandleStrongRefCount`,이 필드는 핸들의 참조 횟수입니다.  
  
-   `Size`. 경우는 `type` 은 `CorGCREferenceType.CorHandleStrongSizedByref`,이 필드는 가비지 수집기가 개체 루트의 경우 계산 되는 개체 트리의 마지막 크기입니다. 이 계산은 반드시 최신 인지 확인 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 구조체](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
