---
title: ICorProfilerCallback::ModuleAttachedToAssembly 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleAttachedToAssembly
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly
helpviewer_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly method [.NET Framework profiling]
- ModuleAttachedToAssembly method [.NET Framework profiling]
ms.assetid: b595798a-5d40-4cac-ab4f-911c61d2c5d2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e6b5281e30c48471131fa12e5106f7d0a6826e1b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452561"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a>ICorProfilerCallback::ModuleAttachedToAssembly 메서드
모듈 부모 어셈블리에 연결 되는 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `moduleId`  
 [in] 연결 되는 모듈의 ID입니다.  
  
 `AssemblyId`  
 [in] 모듈을 연결할 부모 어셈블리의 ID입니다.  
  
## <a name="remarks"></a>설명  
 호출을 통해 가져오기 주소 테이블 (IAT)을 통해 모듈을 로드할 수 있습니다 `LoadLibrary`, 또는 메타 데이터 참조를 통해. 결과적으로, 공용 언어 런타임 (CLR) 로더 모듈 거주 하는 어셈블리를 확인 하기 위한 여러 코드 경로 있습니다. 따라서, 후 [icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 호출, 모듈에 어셈블리를 알 수 없습니다에 이며 부모 어셈블리 ID를 가져오는 것은 가능 하지 않습니다. `ModuleAttachedToAssembly` 메서드는 모듈 부모 어셈블리 ID를 가져올 수 부모 어셈블리에 연결 될 때 호출 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
