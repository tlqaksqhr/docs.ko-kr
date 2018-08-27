---
title: ResolveTypeLib 메서드
ms.date: 03/30/2017
api_name:
- ResolveTypeLib
api_location:
- tlbref.dll
f1_keywords:
- ResolveTypeLib
helpviewer_keywords:
- ITypeLibResolver::ResolveTypeLib method [.NET Framework]
- ResolveTypeLib method [.NET Framework]
ms.assetid: 95d2aa0d-8eeb-4a9f-a216-5249f7e2c167
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be2558e760be8519e528baeff438273c8871f320
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2018
ms.locfileid: "42924471"
---
# <a name="resolvetypelib-method"></a>ResolveTypeLib 메서드
해당 정규화 된 경로 반환 하 여 형식 라이브러리의 단순한 이름을 확인 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ResolveTypeLib(  
    [in]  BSTR      bstrSimpleName,  
    [in]  GUID      tlbid,  
    [in]  LCID      lcid,  
    [in]  USHORT    wMajorVersion,  
    [in]  USHORT    wMinorVersion,  
    [in]  SYSKIND   syskind,  
    [out] BSTR     *pbstrResolvedTlbName);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `bstrSimpleName`  
 [in] A [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) 형식 라이브러리의 간단한 이름을 포함 하는 합니다.  
  
 `tlbid`  
 [in] 레지스트리에서 형식 라이브러리에 할당 된 GUID입니다.  
  
 `lcid`  
 [in] 지역화 ID 형식 라이브러리입니다.  
  
 `wMajorVersion`  
 [in] 형식 라이브러리의 주 버전 번호입니다. 예를 들어 버전용 *x.y*, 주 버전 번호는 *x*합니다.  
  
 `wMinorVersion`  
 [in] 형식 라이브러리의 부 버전 번호입니다. 버전에 대 한 예를 들어 *x.y*, 부 버전 번호가 *y*합니다.  
  
 `syskind`  
 [in] A [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) 운영 환경을 식별 하는 플래그입니다. 일반적인 값은 SYS_WIN32 SYS_WIN64입니다.  
  
 `pbstrResolvedTlbName`  
 [out] 에 대 한 포인터를 [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) 에 명명 된 형식 라이브러리의 전체 경로 포함 하는 `bstrSimpleName` 매개 변수입니다.  
  
## <a name="remarks"></a>설명  
 합니다 `ResolveTypeLib` 메서드를 호출 합니다 [LoadTypeLibWithResolver 함수](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) 하는 동안 [Tlbexp.exe (형식 라이브러리 내보내기)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) 처리 합니다.  
  
 이 인터페이스의 사용자 지정 구현을 반환 해야 합니다는 [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) 에 명명 된 형식 라이브러리의 전체 경로 포함 하는 `bstrSimpleName` 매개 변수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** TlbRef.idl, TlbRef.h  
  
 **라이브러리:** TlbRef.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Tlbexp 도우미 함수](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [LoadTypeLibEx](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
