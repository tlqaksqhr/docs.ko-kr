---
title: "ICorProfilerInfo::IsArrayClass 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.IsArrayClass
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::IsArrayClass
helpviewer_keywords:
- IsArrayClass method [.NET Framework profiling]
- ICorProfilerInfo::IsArrayClass method [.NET Framework profiling]
ms.assetid: 7f230961-23a6-4d56-ad2d-7a876d65705f
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cd07541095158d17b80333b83015d6b1f33a5dcc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfoisarrayclass-method"></a>ICorProfilerInfo::IsArrayClass 메서드
지정된 된 클래스 배열 클래스 인지 확인 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `classId`  
 [in] 검사 하는 클래스의 ID입니다.  
  
 `pBaseElemType`  
 [out] 배열 요소의 형식을 나타내는 CorElementType 열거형의 값에 대 한 포인터입니다.  
  
 `pBaseClassId`  
 [out] 사용 가능한 경우 배열 요소의 클래스 ID에 대 한 포인터입니다.  
  
 `pcRank`  
 [out] 배열 차수 (즉, 차원의 수)를 나타내는 정수에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 클래스가 있는 경우 지정 된 배열 클래스는 `IsArrayClass` 메서드는 s_ok이 고 HRESULT와 모든 null이 아닌 출력 매개 변수 값을 반환 합니다. 이렇게 하지 않으면 S_FALSE를 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
