---
title: "ICorProfilerInfo2::GetArrayObjectInfo 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetArrayObjectInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetArrayObjectInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo method [.NET Framework profiling]
- GetArrayObjectInfo method [.NET Framework profiling]
ms.assetid: bda75017-739f-4ce5-9000-f3b526e8473c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b20530081f7c9ad32f4702099abacc78e052ebd9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a>ICorProfilerInfo2::GetArrayObjectInfo 메서드
배열 개체에 대 한 자세한 정보를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `objectId`  
 [in] 유효한 배열 개체의 ID입니다.  
  
 `cDimensions`  
 [in] 배열 차수 (차원 수)입니다.  
  
 `pDimensionSizes`  
 [out] 각각 배열의 차원 크기를 나타내는 정수를 포함 하는 배열입니다.  
  
 `pDimensionLowerBounds`  
 [out] 배열 차원의 바인딩된 각각 더 작은 값을 나타내는 정수를 포함 하는 배열입니다.  
  
 `ppData`  
 [out] C + + 규칙에 따라 배치 되는 배열에 대 한 원시 버퍼의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `pDimensionSizes` 및 `pDimensionLowerBounds` 하므로 각 배열에 있는 동일한 인덱스에 있는 요소는 동일한 엔터티의 특성에는 병렬 배열입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
