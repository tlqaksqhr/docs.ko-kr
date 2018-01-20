---
title: "ResolveTypeLib 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ResolveTypeLib
api_location: tlbref.dll
f1_keywords: ResolveTypeLib
helpviewer_keywords:
- ITypeLibResolver::ResolveTypeLib method [.NET Framework]
- ResolveTypeLib method [.NET Framework]
ms.assetid: 95d2aa0d-8eeb-4a9f-a216-5249f7e2c167
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 72d1cedbfc1a1ec6c3588a7b0be9cf657d7369fd
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="resolvetypelib-method"></a>ResolveTypeLib 메서드
정규화 된 경로 반환 하 여 형식 라이브러리의 단순한 이름을 확인 합니다.  
  
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
 [in] A [BSTR](http://msdn.microsoft.com/library/1b2d7d2c-47af-4389-a6b6-b01b7e915228) 형식 라이브러리의 단순한 이름을 포함 하 합니다.  
  
 `tlbid`  
 [in] 레지스트리에서 형식 라이브러리에 할당 된 GUID입니다.  
  
 `lcid`  
 [in] 형식 라이브러리의 지역화 ID입니다.  
  
 `wMajorVersion`  
 [in] 형식 라이브러리의 주 버전 번호입니다. 버전에 대 한 예를 들어 *x.y*, 주 버전 번호는 *x*합니다.  
  
 `wMinorVersion`  
 [in] 형식 라이브러리의 부 버전 번호입니다. 버전에 대 한 예를 들어 *x.y*, 부 버전 번호는 *y*합니다.  
  
 `syskind`  
 [in] A [SYSKIND](http://msdn.microsoft.com/library/662048b2-59a8-48ca-9e4f-2f9a5306faa1) 운영 환경을 식별 하는 플래그입니다. 일반적인 값은 SYS_WIN32 및 SYS_WIN64입니다.  
  
 `pbstrResolvedTlbName`  
 [out] 에 대 한 포인터는 [BSTR](http://msdn.microsoft.com/library/1b2d7d2c-47af-4389-a6b6-b01b7e915228) 에 명명 된 형식 라이브러리의 전체 경로 포함 하는 `bstrSimpleName` 매개 변수입니다.  
  
## <a name="remarks"></a>설명  
 `ResolveTypeLib` 메서드는 [LoadTypeLibWithResolver 함수](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) 중 [Tlbexp.exe (형식 라이브러리 내보내기)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) 처리 합니다.  
  
 이 인터페이스의 사용자 지정 구현을 반환 해야 합니다는 [BSTR](http://msdn.microsoft.com/library/1b2d7d2c-47af-4389-a6b6-b01b7e915228) 에 명명 된 형식 라이브러리의 전체 경로 포함 하는 `bstrSimpleName` 매개 변수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **Header:** TlbRef.idl, TlbRef.h  
  
 **라이브러리:** TlbRef.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Tlbexp 도우미 함수](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [LoadTypeLibEx](http://msdn.microsoft.com/library/56a7f9e1-810b-4a42-aa4d-691f4304f5ef)
