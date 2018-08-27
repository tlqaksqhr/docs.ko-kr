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
ms.openlocfilehash: 0ec28c581b8e6e0aff3a2765720b6e9795be931b
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42931706"
---
# <a name="gettypelibinfo-function"></a>GetTypeLibInfo 함수
검사 하 여 지정된 된 형식 라이브러리에 대 한 정보를 반환 합니다. 해당 [>TLIBATTR](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagtlibattr) 구조입니다.  
  
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
 [out] 지역화 ID 형식 라이브러리입니다.  
  
 `pTypeLibPlatform`  
 [out] A [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) 형식 라이브러리에 대 한 대상 운영 체제를 식별 하는 플래그입니다. 일반적인 값은 SYS_WIN32 SYS_WIN64입니다.  
  
 `pTypeLibMajorVer`  
 [out] 형식 라이브러리의 주 버전 번호입니다. 예를 들어 버전용 *x.y*, 주 버전 번호는 *x*합니다.  
  
 `pTypeLibMinorVer`  
 [out] 형식 라이브러리의 부 버전 번호입니다. 버전에 대 한 예를 들어 *x.y*, 부 버전 번호가 *y*합니다.  
  
## <a name="remarks"></a>설명  
 합니다 `GetTypeLibInfo` 의해 함수가 호출 되는 [Tlbexp.exe (형식 라이브러리 내보내기)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)합니다. 이 도구는 공용 언어 런타임 (CLR) 어셈블리에서 형식을 설명 하는 형식 라이브러리를 생성 합니다.  
  
 함수를 반환 하는 경우 모든 매개 변수를는 `HRESULT` 의 `E_POINTER`합니다. 그 외의 경우 `S_OK`를 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** TlbRef.h  
  
 **라이브러리:** TlbRef.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Tlbexp 도우미 함수](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [LoadTypeLibEx 함수](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
