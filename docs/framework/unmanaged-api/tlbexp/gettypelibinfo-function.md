---
title: GetTypeLibInfo 함수
ms.date: 03/30/2017
api_name:
- GetTypeLibInfo
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- GetTypeLibInfo
helpviewer_keywords:
- GetTypeLibInfo function [.NET Framework]
ms.assetid: a1c4d165-9bdc-4ca8-940e-292d4ffcc338
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 56a9b97f37240e385dbd1788bafea62578d687a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457870"
---
# <a name="gettypelibinfo-function"></a>GetTypeLibInfo 함수
검사 하 여 지정된 된 형식 라이브러리에 대 한 정보를 반환 합니다. 해당 [>TLIBATTR](https://msdn.microsoft.com/library/ms221376\(v=vs.85\).aspx) 구조입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `szFile`  
 [in] 형식 라이브러리의 파일 이름입니다.  
  
 `pTypeLibID`  
 [out] 형식 라이브러리의 GUID입니다.  
  
 `pTypeLibLCID`  
 [out] 형식 라이브러리의 지역화 ID입니다.  
  
 `pTypeLibPlatform`  
 [out] A [SYSKIND](https://msdn.microsoft.com/library/ms221272\(v=vs.85\).aspx) 형식 라이브러리에 대 한 대상 운영 체제를 식별 하는 플래그입니다. 일반적인 값은 SYS_WIN32 및 SYS_WIN64입니다.  
  
 `pTypeLibMajorVer`  
 [out] 형식 라이브러리의 주 버전 번호입니다. 버전에 대 한 예를 들어 *x.y*, 주 버전 번호는 *x*합니다.  
  
 `pTypeLibMinorVer`  
 [out] 형식 라이브러리의 부 버전 번호입니다. 버전에 대 한 예를 들어 *x.y*, 부 버전 번호는 *y*합니다.  
  
## <a name="remarks"></a>설명  
 `GetTypeLibInfo` 함수 호출 됩니다는 [Tlbexp.exe (형식 라이브러리 내보내기)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)합니다. 이 도구는 공용 언어 런타임 (CLR) 어셈블리의 형식을 설명 하는 형식 라이브러리를 생성 합니다.  
  
 함수 반환 하는 경우 매개 변수가 null 이면는 `HRESULT` 의 `E_POINTER`합니다. 그 외의 경우 `S_OK`를 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** TlbRef.h  
  
 **라이브러리:** TlbRef.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Tlbexp 도우미 함수](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [LoadTypeLibEx 함수](https://msdn.microsoft.com/library/ms221249\(v=vs.85\).aspx)
