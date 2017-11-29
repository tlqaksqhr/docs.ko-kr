---
title: "ASSEMBLYMETADATA 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ASSEMBLYMETADATA
api_location: mscoree.dll
api_type: COM
f1_keywords: ASSEMBLYMETADATA
helpviewer_keywords: ASSEMBLYMETADATA structure [.NET Framework metadata]
ms.assetid: 1af98e57-9145-4d35-bb78-77d1da7c91a5
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5652907abc17868414c554cb5c87b0856d2c5a0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="assemblymetadata-structure"></a>ASSEMBLYMETADATA 구조체
해당 버전 및 로캘, 프로세서, 및 운영 체제에 대 한 지원 수준을 포함 하 여 참조 된 어셈블리에 대 한 정보를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct {  
    USHORT  usMajorVersion;  
    USHORT  usMinorVersion;  
    USHORT  usBuildNumber;  
    USHORT  usRevisionNumber;  
    LPWSTR  szLocale;  
    ULONG   cbLocale;  
    DWORD*  rdwProcessor[];  
    ULONG   ulProcessor  
    OSINFO* rOS[];  
    ULONG   ulOS;  
} ASSEMBLYMETADATA;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`usMajorVersion`|참조 된 어셈블리의 주 버전 번호입니다. 이 값은 0 일 수 없습니다. 하는 경우의 모든 비트가 `usMajorVersion` 주 버전을 지정 하지 않으면 설정 됩니다.|  
|`usMinorVersion`|참조 된 어셈블리의 부 버전 번호입니다. 이 값은 0 일 수 없습니다. 하는 경우의 모든 비트가 `usMinorVersion` 부 버전을 지정 하지 않으면 설정 됩니다.|  
|`usBuildNumber`|참조 된 어셈블리의 빌드 번호입니다. 이 값은 0 일 수 없습니다. 하는 경우의 모든 비트가 `usBuildNumber` 빌드 번호를 지정 하지 않으면 설정 됩니다.|  
|`usRevisionNumber`|참조 된 어셈블리의 수정 번호입니다. 이 값은 0 일 수 없습니다. 하는 경우의 모든 비트가 `usRevisionNumber` 수정 번호를 지정 하지 않으면 설정 됩니다.|  
|`szLocale`|참조 된 어셈블리에서 지원 되는 로캘을 지정 하는 세미콜론으로 구분 하는 RFC1766 사양에 맞는 로캘 이름이의 목록. Null 값에는 로캘과 관련이 없음을 나타냅니다. **참고:** .NET Framework 버전 1.0 둘 이상의 로캘을 지정할 수 없습니다.|  
|`cbLocale`|와이드 문자에서 크기 `szLocale`합니다.|  
|`rdwProcessor`|참조 된 어셈블리에서 지 원하는 프로세서 종류에 대 한 Winnt.h에 정의 된 식별자의 배열입니다. NULL 값에는 프로세서 관련이 없음을 나타냅니다.|  
|`ulProcessor`|길이 `rdwProcessor` 배열입니다.|  
|`rOS`|배열을 [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) 참조 된 어셈블리에서 지원 되는 운영 체제를 지정 하는 인스턴스. NULL 값에는 운영 체제 관련이 없음을 나타냅니다.|  
|`ulOS`|길이 `rOS` 배열입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타 데이터 구조](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [IMetaDataAssemblyEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [OSINFO 구조체](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
