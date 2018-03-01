---
title: "COR_PRF_ASSEMBLY_REFERENCE_INFO 구조"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- cpp
ms.assetid: c8c1d916-8d1a-4f82-8128-9fd3732383fc
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4b5889f8e0b0dc8faab76f637e2fcf03853709bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corprfassemblyreferenceinfo-structure"></a>COR_PRF_ASSEMBLY_REFERENCE_INFO 구조
[.NET Framework 4.5.2 이상 버전에서 지원됨]  
  
 어셈블리 참조 closure 워커를 수행할 때 고려해야 하는 어셈블리 참조에 대한 정보를 공용 언어 런타임에 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _COR_PRF_ASSEMBLY_REFERENCE_INFO {  
    void* pbPublicKeyOrToken;  
    ULONG cbPublicKeyOrToken;  
    LPCWSTR szName;  
    ASSEMBLYMETADATA* pMetaData;  
    void* pbHashValue;  
    ULONG cbHashValue;  
    DWORD dwAssemblyRefFlags;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`pbPublicKeyOrToken`|어셈블리의 공개 키 또는 토큰에 대한 포인터입니다.|  
|`cbPublicKeyOrToken`|공개 키 또는 토큰의 바이트 수입니다.|  
|`szName`|참조되는 어셈블리의 이름입니다.|  
|`pMetaData`|어셈블리의 메타데이터에 대한 포인터입니다.|  
|`pbHashValue`|해시 BLOB(Binary Large Object)에 대한 포인터입니다.|  
|`cbHashValue`|해시 BLOB의 바이트 수입니다.|  
|`dwAssemblyRefFlags`|어셈블리의 플래그입니다.|  
  
## <a name="remarks"></a>설명  
 프로파일러는 어셈블리 참조 closure 워커를 수행할 때 공용 언어 런타임이 고려해야 하는 추가 어셈블리 참조를 선언할 때 `COR_PRF_EX_CLAUSE_INFO` 구조체를 채웁니다.  
  
 프로파일러에 대 한 등록 하는 경우는 [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) 콜백 메서드는 런타임에서 전달에 대 한 포인터와 함께 로드할된 어셈블리의 이름과 경로 [ ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) 해당 메서드로 인터페이스 개체입니다. 프로파일러를 호출할 수는 [icorprofilerassemblyreferenceprovider:: Addassemblyreference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) 메서드는 `COR_PRF_ASSEMBLY_REFERENCE_INFO` 에 지정 된 어셈블리에서 참조 하려는 각 대상 어셈블리에 대 한 개체는 [ Icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) 콜백 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [프로파일링 구조체](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)  
 [GetAssemblyReferences 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)  
 [AddAssemblyReference 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)
