---
title: "ICorProfilerInfo::SetILInstrumentedCodeMap 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.SetILInstrumentedCodeMap
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetILInstrumentedCodeMap method [.NET Framework profiling]
ms.assetid: bce1dcf8-b4ec-4e73-a917-f2df1ad49c8a
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 35c87b98a8e0c02ab6f4bca7a4f7a16ff6839c6b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a>ICorProfilerInfo::SetILInstrumentedCodeMap 메서드
지정한 Microsoft MSIL (intermediate language) 맵 엔트리를 사용 하 여 지정된 된 함수에 대 한 코드 맵을 설정 합니다.  
  
> [!NOTE]
>  .NET framework 버전 2.0에서는 호출 `SetILInstrumentedCodeMap` 에 `FunctionID` 제네릭 특정 응용 프로그램 도메인에서 함수를 나타내는 응용 프로그램 도메인에서 해당 함수의 모든 인스턴스의 영향을 줍니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetILInstrumentedCodeMap(  
    [in]  FunctionID functionId,  
    [in]  BOOL       fStartJit,  
    [in]  ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `functionId`  
 [in] 코드 맵을 설정 하려는 함수의 ID입니다.  
  
 `fStartJit`  
 [in] 나타내는 부울 값 여부에 대 한 호출에서 `SetILInstrumentedCodeMap` 메서드는 특정 작업에 대해 첫 번째 `FunctionID`합니다. 설정 `fStartJit` 를 `true` 첫 번째 호출에서 `SetILInstrumentedCodeMap` 에 대 한는 주어진 `FunctionID`, 및 `false` 이후에 합니다.  
  
 `cILMapEntries`  
 [in] 에 있는 요소의 수는 `cILMapEntries` 배열입니다.  
  
 `rgILMapEntries`  
 [in] MSIL 오프셋을 지정 하며 각 COR_IL_MAP 구조체의 배열입니다.  
  
## <a name="remarks"></a>설명  
 프로파일러 (예: 지정 된 소스 줄에 도달할 때 알릴) 계측을 위해 메서드의 소스 코드 내에서 문을 삽입 하는 경우가 있습니다. `SetILInstrumentedCodeMap`프로파일러를 원래 MSIL 명령을 새 위치에 매핑할 수 있습니다. 프로파일러를 사용할 수는 [icorprofilerinfo:: Getiltonativemapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) 메서드를 지정된 된 네이티브 오프셋 위치에 대 한 원래 MSIL 오프셋을 가져옵니다.  
  
 디버거는 각 이전 오프셋 MSIL 원래, 수정 되지 않은 MSIL 코드 내에서 오프셋을 나타내며 각 새 오프셋 새로운, 계측 된 코드 내에서 MSIL 오프셋을 참조 한다고 가정 합니다. 지도 오름차순으로 정렬 되어야 합니다. 단계별 코드 실행이 제대로 작동 하려면, 다음이 지침을 따르십시오.  
  
-   계측 된 MSIL 코드 순서를 변경 하지 마십시오.  
  
-   원래 MSIL 코드를 제거 하지 마십시오.  
  
-   지도에 프로그램 데이터베이스 (PDB) 파일에서 모든 시퀀스 위치에 대 한 항목을 포함 합니다. 지도 누락 된 항목 보간 하지 않습니다. 따라서 다음과 같은 맵을 가정합니다.  
  
     (0, 오래 된 0 새)  
  
     (5, 이전 10 새)  
  
     (9, 이전 20 새)  
  
    -   0, 1, 2, 3 또는 4 이전 오프셋 새 오프셋 0에 매핑됩니다.  
  
    -   5, 6, 7 또는 8 이전 오프셋 10 새 오프셋에 매핑됩니다.  
  
    -   9 이상을 이전 오프셋 20 새 오프셋에 매핑됩니다.  
  
    -   새 오프셋 0, 1, 2, 3, 4, 5, 6, 7, 8 또는 9 이전 오프셋 0에 매핑됩니다.  
  
    -   10, 11, 12, 13, 14, 15, 16, 17, 18 또는 19 새 오프셋 5 이전 오프셋에 매핑됩니다.  
  
    -   20 이상의 새 오프셋 9 이전 오프셋에 매핑됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
