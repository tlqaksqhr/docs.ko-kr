---
title: "ICorProfilerInfo2::GetStringLayout 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo2.GetStringLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStringLayout
helpviewer_keywords:
- GetStringLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetStringLayout method [.NET Framework profiling]
ms.assetid: 43189651-a535-4803-a1d1-f1c427ace2ca
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1ad91829fab31b47a1dd51bb6cc9118c2ebe4c3a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getstringlayout-method"></a>ICorProfilerInfo2::GetStringLayout 메서드
문자열 개체의 레이아웃 정보를 가져옵니다. 이 메서드는 사용 되지 않습니다는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], 않으며로 대체는 [icorprofilerinfo3:: Getstringlayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) 메서드.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pBufferLengthOffset`  
 [out] 에 대 한 상대 위치 오프셋에 대 한 포인터는 `ObjectID` 문자열의 길이 저장 하는 포인터입니다. 로 저장 되는 `DWORD`합니다.  
  
> [!NOTE]
>  이 매개 변수 버퍼의 길이가 아닌 문자열 자체의 길이 반환합니다. 버퍼의 길이 더 이상 사용할 수 없습니다.  
  
 `PStringLengthOffset`  
 [out] 에 대 한 상대 위치 오프셋에 대 한 포인터는 `ObjectID` 문자열 자체의 길이 저장 하는 포인터입니다. 로 저장 되는 `DWORD`합니다.  
  
 `pBufferOffset`  
 [out] 에 대 한 상대 버퍼의 오프셋에 대 한 포인터는 `ObjectID` 와이드 문자의 문자열을 저장 하는 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `GetStringLayout` 메서드 상대적으로 오프셋을 가져옵니다는 `ObjectID` 포인터의 다음 저장 된 위치:  
  
-   문자열의 버퍼의 길이입니다.  
  
-   문자열 자체의 길이입니다.  
  
-   와이드 문자의 실제 문자열을 포함 하는 버퍼입니다.  
  
 Null로 끝나는 문자열 될 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
