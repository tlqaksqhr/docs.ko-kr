---
title: ICorProfilerAssemblyReferenceProvider::AddAssemblyReference 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerAssemblyReferenceProvider.AddAssemblyReference
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 3d5af8e7-c337-48f4-9fa6-97c83878b9b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 33430db8f83f446bab21b1fc86a5c165aecef2af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452366"
---
# <a name="icorprofilerassemblyreferenceprovideraddassemblyreference-method"></a>ICorProfilerAssemblyReferenceProvider::AddAssemblyReference 메서드
[.NET Framework 4.5.2 이상 버전에서 지원됨]  
  
 프로파일러가에 추가 하는 어셈블리 참조의 공용 언어 런타임 (CLR) 알립니다는 [icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 콜백 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT AddAssemblyReference(  
        const COR_PRF_ASSEMBLY_REFERENCE_INFO* pAssemblyRefInfo  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pAssemblyRefInfo  
 에 대 한 포인터는 [COR_PRF_ASSEMBLY_REFERENCE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md) CLR 어셈블리 참조 closure 워커를 수행할 때 고려해 야 하는 어셈블리 참조에 대 한 정보를 제공 하는 구조입니다.  
  
## <a name="remarks"></a>설명  
 에 지정 된 어셈블리에서 참조 하려는 각 대상 어셈블리에 대해이 메서드를 호출 하는 프로파일러는 `wszAssemblyPath` 의 인수는 [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) 콜백 합니다. [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) 인터페이스를 전달 하는 프로파일러 [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) 콜백 함께 어셈블리 경로 및 이름에는 `wszAssemblyPath` 인수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerAssemblyReferenceProvider 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)  
 [GetAssemblyReferences 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)  
 [ModuleLoadFinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
