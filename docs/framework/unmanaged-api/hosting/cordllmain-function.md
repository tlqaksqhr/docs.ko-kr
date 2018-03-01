---
title: "_CorDllMain 함수"
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
- _CorDllMain
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorDllMain
helpviewer_keywords:
- _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 985f2284026054217671de767c316b1fba35c098
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cordllmain-function"></a>_CorDllMain 함수
공용 언어 런타임 (CLR)을 초기화 하 고 DLL 어셈블리의 CLR 헤더의 관리 되는 진입점을 찾고 실행을 시작 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `hInst`  
 [in] 로드 된 모듈의 인스턴스 핸들입니다.  
  
 `dwReason`  
 [in] DLL 진입점 함수를 호출 하는 이유를 나타냅니다. 이 매개 변수는 다음 값 중 하나일 수 있습니다: DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH, 또는 DLL_PROCESS_DETACH 합니다. 이러한 값의 설명에 대 한 참조는 `DllMain` Platform SDK 설명서입니다.  
  
 `lpReserved`  
 [in] 사용 되지 않습니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드가 반환 `true` 성공 및 `false` 오류가 발생 합니다.  
  
## <a name="remarks"></a>설명  
 이 함수는 DLL 어셈블리에 대 한 운영 체제 로더에 의해 호출 됩니다. 로더 실행 가능 어셈블리에 대 한 호출에서 [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) 함수를 대신 합니다.  
  
 운영 체제 로더는 DLL 파일에 지정 된 진입점에 관계 없이이 메서드를 호출 합니다.  
  
 Windows 98, Windows ME, Windows NT 및 Windows 2000에는 `_CorDllMain` 함수는 간접적으로 호출 된 fixupin를 통해 운영 체제 로더에 합니다. 다른 모든 버전의 Windows에서는 운영 체제 로더에 의해 직접 호출 됩니다.  
  
 자세한 내용은의 주의 섹션을 참조 하십시오.는 [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) 항목입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 전역 정적 함수](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
