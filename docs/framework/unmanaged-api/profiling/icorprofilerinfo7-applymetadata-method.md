---
title: "Icorprofilerinfo7:: Applymetadata 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: ICorProfilerInfo7.ApplyMetaData
api_location: mscorwks.dll
api_type: COM
ms.assetid: a1bfb649-4584-4d35-b3e6-8fe59b53992a
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2e79d687d3d777895dea9427e4865c2fc866f50d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo7applymetadata-method"></a>Icorprofilerinfo7:: Applymetadata 메서드
[.NET Framework 4.6.1 이상 버전에서 지원됨]  
  
 새로 정의한 메타 데이터에 적용 되는 `IMetadataEmit::Define*` 메서드를 지정된 된 모듈입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `moduleID`  
 [in] 변경 된 메타 데이터가 포함 모듈의 식별자입니다.  
  
## <a name="remarks"></a>설명  
 이후 메타 데이터를 변경 하는 경우는 [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 콜백에서 새 메타 데이터를 사용 하기 전에이 메서드를 호출 해야 합니다.  
  
 `ApplyMetaData`다음과 같은 유형의 메타 데이터를 추가 지원 합니다.  
  
-   `AssemblyRef`호출 하 여 만든는 레코드에는 [imetadataassemblyemit:: Defineassemblyref](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)합니다. 메서드를 재정의합니다.  
  
-   `TypeRef`호출 하 여 만든는 레코드에는 [imetadataemit:: Definetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) 메서드.  
  
-   `TypeSpec`호출 하 여 만든는 레코드에는 [imetadataemit:: Gettokenfromtypespec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) 메서드.  
  
-   `MemberRef`호출 하 여 만든는 레코드에는 [imetadataemit:: Definememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) 메서드.  
  
-   `MemberSpec`호출 하 여 만든는 레코드에는 [imetadataemit2:: Definemethodspec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) 메서드.  
  
-   `UserString`호출 하 여 만든는 레코드에는 [imetadataemit:: Defineuserstring](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerInfo7 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
