---
title: "ICorProfilerInfo3::GetRuntimeInformation 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.GetRuntimeInformation Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::GetRuntimeInformation
helpviewer_keywords:
- GetRuntimeInformation method [.NET Framework profiling]
- ICorProfilerInfo3::GetRuntimeInformation method [.NET Framework profiling]
ms.assetid: 4400fb8c-0407-4791-8557-f011fd2aee51
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5eadd9970d29cc65d8411692407dcae5471e51c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a>ICorProfilerInfo3::GetRuntimeInformation 메서드
프로 파일링 되 고 공용 언어 런타임 (CLR)에 대 한 버전 정보를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetRuntimeInformation(  
       [out] USHORT *pClrInstanceId,  
       [out] COR_PRF_RUNTIME_TYPE *pRuntimeType,  
       [out] USHORT *pMajorVersion,  
       [out] USHORT *pMinorVersion,  
       [out] USHORT *pBuildNumber,  
       [out] USHORT *pQFEVersion,  
       [in]  ULONG  cchVersionString,  
       [out] ULONG  *pcchVersionString,  
       [out, size_is(cchVersionString), length_is(*pcchVersionString)]  
                   WCHAR  szVersionString[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pClrInstanceId`  
 [out] 프로세스에서 실행 중인 CLR 인스턴스의 담당자 ID입니다. 이와 동일는 `ClrInstanceID` 는 ETW (Windows) startup 이벤트 용 이벤트 추적을 보고 합니다.  
  
 `pRuntimeType`  
 [out] 런타임 형식입니다. 이 매개 변수 반환 `COR_PRF_DESKTOP_CLR` CLR의 데스크톱 버전에 대 한 또는 `COR_PRF_CORE_CLR` Silverlight에서 사용 하는 CLR의 핵심 버전에 대 한 합니다.  
  
 `pMajorVersion`  
 [out] CLR의 주 버전 번호입니다.  
  
 `pMinorVersion`  
 [out] CLR의 부 버전 번호입니다.  
  
 `pBuildVersion`  
 [out] Clr 빌드 버전 번호입니다.  
  
 `pQFEVersion`  
 [out] 소프트웨어 업데이트와 관련 된 CLR의 버전 번호입니다.  
  
 `cchVersionString`  
 [in] 버퍼의 문자에서 길이 `szVersionString` 를 가리킵니다.  
  
 `pcchVersionString`  
 [out] 길이 문자의 `szVersionString`합니다.  
  
 `szVersionString`  
 [out] CLR 버전 문자열입니다.  
  
## <a name="remarks"></a>설명  
 매개 변수에 대해 null을 전달할 수 있습니다. 그러나 `pcchVersionString` null 일 수 없습니다 하지 않는 한 `szVersionString` 도 null입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerInfo3 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [프로파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [프로파일링](../../../../docs/framework/unmanaged-api/profiling/index.md)
