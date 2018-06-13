---
title: PreBindAssemblyEx 함수
ms.date: 03/30/2017
api_name:
- PreBindAssemblyEx
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- PreBindAssemblyEx
helpviewer_keywords:
- PreBindAssemblyEx function [.NET Framework fusion]
ms.assetid: bd285233-a4a2-4b52-bbca-0025a60e4864
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d3e2535851d39be642de56a86b78c328ecaf446
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432003"
---
# <a name="prebindassemblyex-function"></a>PreBindAssemblyEx 함수
어셈블리에 대 한 사후 정책 표시 이름을 가져옵니다.  
  
 이 함수는.NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT PreBindAssemblyEx (  
    [in]  IApplicationContext *pAppCtx,  
    [in]  IAssemblyName       *pName,  
    [in]  IAssembly           *pAsmParent,  
    [in]  LPCWSTR             pwzRuntimeVersion,  
    [out] IAssemblyName       **ppNamePostPolicy,  
    [in]  LPVOID              pvReserved  
 );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pAppCtx`  
 [in] 응용 프로그램 컨텍스트를 식별합니다.  
  
 `pName`  
 [in] 어셈블리 이름을 식별합니다.  
  
 `pAsmParent`  
 [in] 부모 어셈블리를 식별합니다. 이 매개 변수는 무시됩니다.  
  
 `pwzRuntimeVersion`  
 [in] 런타임 버전을 식별합니다.  
  
 `ppNamePostPolicy`  
 [out] 사후 정책 표시 이름을 포함합니다.  
  
 `pvReserved`  
 [in] 다음 버전의 확장에 대 한 예약 되어 있습니다. `pvReserved` null 참조 여야 합니다.  
  
## <a name="remarks"></a>설명  
 `ppNamePostPolicy` 함수 FUSION_E_REF_DEF_MISMATCH HRESULT를 반환 하는 경우에 출력 매개 변수가 설정 됩니다. 그렇지 않으면 null입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Fusion.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Fusion 전역 정적 함수](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
