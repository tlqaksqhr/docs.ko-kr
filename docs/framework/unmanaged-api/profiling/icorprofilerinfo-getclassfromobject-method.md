---
title: ICorProfilerInfo::GetClassFromObject 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromObject
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromObject
helpviewer_keywords:
- GetClassFromObject method [.NET Framework profiling]
- ICorProfilerInfo::GetClassFromObject method [.NET Framework profiling]
ms.assetid: b97493fb-713e-49d5-a73e-5688b2ad0700
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 104dfcaa4120d72f3aa758b66134050f178fef75
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453423"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a>ICorProfilerInfo::GetClassFromObject 메서드
가져옵니다는 `ClassID` 지정 된 개체의 해당 `ObjectID`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `objectId`  
 [in] 가져올 개체의 ID는 `ClassID`합니다.  
  
 `pClassId`  
 [out] 반환 된에 대 한 포인터 `ClassID`합니다.  
  
## <a name="remarks"></a>설명  
 Null `pClassId` 나타냅니다 `objectId` 언로드되고 형식이 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
