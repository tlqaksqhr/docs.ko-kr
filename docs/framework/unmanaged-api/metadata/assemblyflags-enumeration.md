---
title: "AssemblyFlags 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: AssemblyFlags
helpviewer_keywords: AssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: 40f9bd9e-16ec-447e-81b0-168c875e9866
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 605817ef23246f708b6cf46a93072cde3003ab43
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="assemblyflags-enumeration"></a>AssemblyFlags 열거형
어셈블리의 런타임 기능을 설명 하는 값을 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`afImplicitExportedTypes`|내보낸된 형식 정의 어셈블리를 구성 하는 파일 내에서 암시적 되도록 지정 합니다. .NET Framework 버전 1.0 및 1.1에서는이 값은 항상 설정으로 간주 됩니다.|  
|`afImplicitResources`|리소스 정의 어셈블리를 구성 하는 파일 내에서 암시적 되도록 지정 합니다. .NET Framework 1.0 및 1.1이이 값은 항상 설정으로 간주 됩니다.|  
|`afNonSideBySideAppDomain`|동일한 응용 프로그램 도메인에서 어셈블리를 다른 버전과 함께 실행할 수 없습니다 것을 지정 합니다.|  
|`afNonSideBySideProcess`|어셈블리는 같은 프로세스에서 실행 하는 경우 다른 버전과 함께 실행할 수 없습니다 것을 지정 합니다.|  
|`afNonSideBySideMachine`|동일한 컴퓨터에서 어셈블리를 다른 버전과 함께 실행할 수 없습니다 것을 지정 합니다.|  
  
## <a name="remarks"></a>설명  
 0x0010과 0x0070, inclusive, 사이의 값은 참조 된 어셈블리의 side-by-side-호환성 기능을 설명 하는 데 사용 됩니다. 이러한 값을 설정 하 여 병렬 호환 될 어셈블리 가정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MsCorEE.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [IMetaDataAssemblyEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
