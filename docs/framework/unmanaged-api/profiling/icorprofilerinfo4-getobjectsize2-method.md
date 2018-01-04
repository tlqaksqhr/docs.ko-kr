---
title: "ICorProfilerInfo4::GetObjectSize2 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4.GetObjectSize2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4::GetObjectSize2
helpviewer_keywords:
- GetObjectSize2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetObjectSize2 method [.NET Framework profiling]
ms.assetid: 4a3e43ed-3ee3-4395-ab14-f78b903be13e
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0aa13a056929c9cb4f63c52f1e993f110cfca7be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo4getobjectsize2-method"></a>ICorProfilerInfo4::GetObjectSize2 메서드
지정된 된 개체의 크기를 반환합니다. 대체는 [icorprofilerinfo:: Getobjectsize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md) 으로 표현 될 수 있는 보다 큰 개체의 크기를 보고 하 여 메서드는 `ULONG`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetObjectSize2(  
    [in]  ObjectID objectId,  
    [out] SIZE_T *pcSize);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `objectId`  
 [in] 개체의 ID입니다.  
  
 `pcSize`  
 [out] 개체의 크기 (바이트)에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 동일한 형식의 다른 개체에는 크기가 있는 경우가 많습니다. 그러나 배열 또는 문자열 등의 일부 형식에는 각 개체에 대해 다른 크기가 있을 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerInfo4 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
