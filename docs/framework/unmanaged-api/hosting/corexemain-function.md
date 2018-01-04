---
title: "_CorExeMain 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _CorExeMain
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: _CorExeMain
helpviewer_keywords: _CorExeMain function [.NET Framework hosting]
ms.assetid: 898f76e2-16f4-4a63-b7d9-dad2d3824d8a
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5f5c0909db10c7bf8e15a7af998b78e0a193a908
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corexemain-function"></a>_CorExeMain 함수
공용 언어 런타임 (CLR)을 초기화 하 고 실행 가능한 어셈블리의 CLR 헤더의 관리 되는 진입점을 찾고 실행을 시작 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a>설명  
 이 함수는 관리 되는 실행 가능한 어셈블리에서 만든 프로세스에서 로더에 의해 호출 됩니다. 로더가 DLL 어셈블리에 대 한 호출에서 [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) 함수를 대신 합니다.  
  
 운영 체제 로더는 이미지 파일에 지정 된 진입점에 관계 없이이 메서드를 호출 합니다.  
  
 Windows 98, Windows ME, Windows NT 및 Windows 2000에는 `_CorExeMain` 함수 운영 체제 로더에서 수정을 통해 간접적으로 호출 됩니다. 다른 모든 버전의 Windows에서는 운영 체제 로더에 의해 직접 호출 됩니다.  
  
 자세한 내용은의 주의 섹션을 참조 하십시오.는 [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) 항목입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 전역 정적 함수](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
