---
title: "ASSEMBLY_INFO 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ASSEMBLY_INFO
api_location: fusion.dll
api_type: COM
f1_keywords: ASSEMBLY_INFO
helpviewer_keywords: ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 215d80c3d207c2f50cfbd74386915b0467692b57
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="assemblyinfo-structure"></a>ASSEMBLY_INFO 구조체
전역 어셈블리 캐시에 등록 되어 있는 어셈블리에 대 한 정보를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`cbAssemblyInfo`|구조체의 바이트 크기입니다. 이 필드는 다음 버전의 확장에 대 한 예약 되어 있습니다.|  
|`dwAssemblyFlags`|어셈블리에 대 한 설치 세부 정보를 나타내는 플래그입니다. 다음 값이 지원 됩니다.<br /><br /> -ASSEMBLYINFO_FLAG_INSTALLED 나타내는 값을 어셈블리가 설치 됩니다. 현재 버전의.NET Framework 항상 설정 `dwAssemblyFlags` 이 값으로.<br />-ASSEMBLYINFO_FLAG_PAYLOADRESIDENT 값, 상주 페이로드 어셈블리 임을 나타냅니다. 현재 버전의.NET Framework를 설정 하지 `dwAssemblyFlags` 이 값으로.|  
|`uliAssemblySizeInKB`|(킬로바이트) 어셈블리에 포함 되어 있는 파일의 총 크기입니다.|  
|`pszCurrentAssemblyPathBuf`|매니페스트 파일에는 현재 경로 보유 하는 문자열 버퍼에 대 한 포인터입니다. 경로 null 문자로 종료 해야 합니다.|  
|`cchBuf`|Null 종결자를 포함 하는 와이드 문자의 수를 `pszCurrentAssemblyPathBuf` 포함 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Fusion.h  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Fusion 구조체](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [전역 어셈블리 캐시](../../../../docs/framework/app-domains/gac.md)
