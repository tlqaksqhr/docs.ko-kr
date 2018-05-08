---
title: ICorProfilerInfo2::GetBoxClassLayout 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetBoxClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetBoxClassLayout
helpviewer_keywords:
- GetBoxClassLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetBoxClassLayout method [.NET Framework profiling]
ms.assetid: 624672b5-1189-488a-85d2-3e12b49617c1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f046fb51753bfa79d333d465e8850794ecc73973
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a>ICorProfilerInfo2::GetBoxClassLayout 메서드
지정 된 값 형식의 위치한 box이 된 경우에 대 한 정보를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `classId`  
 [in] Boxed 값 형식을 설명 하는 클래스의 ID입니다.  
  
 `pBufferOffset`  
 [out] 정수는 값 형식의 boxed 개체 ID 포인터를 기준으로 오프셋입니다.  
  
## <a name="remarks"></a>설명  
 `pBufferOffset` 값은 값 형식 상자 내에서 위치입니다. 후 `pBufferOffset` 적용 되는 boxed 개체에 값 형식의 클래스 레이아웃 데 사용할 수 개체의 값을 해석 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
