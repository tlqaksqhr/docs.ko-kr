---
title: "CoEEShutDownCOM 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoEEShutDownCOM
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: CoEEShutDownCOM
helpviewer_keywords: CoEEShutDownCOM function [.NET Framework hosting]
ms.assetid: b634cae2-632f-4737-9be4-92d0652844d7
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8d6d9e3d650f65ef084c63104980bca0ac77f1bd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="coeeshutdowncom-function"></a>CoEEShutDownCOM 함수
공용 언어 런타임 (CLR) 내부 런타임 호출 가능 래퍼 RCW ()를 보유 하는 모든 인터페이스 포인터를 해제 하기 위해를 강제로 수행 합니다. 모든 RCW 캐시 해제 것과 효과가 있습니다. 이 전역 함수에서 사용 되지 않는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다. 대신, 특정 런타임에 대 한 진입점을 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a>설명  
 `CoEEShutDownCOM` 함수 먼저 모든 컨텍스트 및 모든 캐시에서 모든 Rcw를 해제 한 다음 설치 프로그램에 있는 모든 중지 알림을 제거 합니다. DLL 언로드 없습니다 발생합니다.  
  
> [!CAUTION]
>  이 함수에는 프로세스에 로드 되는 모든 런타임에 적용 합니다.  
  
 부터는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], 원하는 특정 런타임에 대해이 함수에 대 한 진입점을 호출 합니다. 진입점을 가져오려면 호출는 [iclrruntimeinfo:: Getprocaddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) 메서드 "CoEEShutDownCOM"를 지정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타 데이터 전역 정적 함수](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
