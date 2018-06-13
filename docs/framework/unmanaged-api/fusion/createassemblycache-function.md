---
title: CreateAssemblyCache 함수
ms.date: 03/30/2017
api_name:
- CreateAssemblyCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyCache
helpviewer_keywords:
- CreateAssemblyCache function [.NET Framework fusion]
ms.assetid: 348c7c8c-8578-46ae-97cf-480d6015c3c6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ba4259ad9cdf4f56fd4c00b5c7e9ebfa8b7fe1ff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429581"
---
# <a name="createassemblycache-function"></a>CreateAssemblyCache 함수
새에 대 한 포인터를 가져옵니다 [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) 전역 어셈블리 캐시를 나타내는 인스턴스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppAsmCache`  
 [out] 반환 된 `IAssemblyCache` 포인터입니다.  
  
 `dwReserved`  
 [in] 다음 버전의 확장에 대 한 예약 되어 있습니다. `dwReserved` 0 (영) 이어야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Fusion.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IAssemblyCache 인터페이스](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 [Fusion 전역 정적 함수](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
 [전역 어셈블리 캐시](../../../../docs/framework/app-domains/gac.md)
