---
title: "AssemblyComparisonResult 열거형"
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
- AssemblyComparisonResult
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- AssemblyComparisonResult
helpviewer_keywords:
- AssemblyComparisonResult enumeration [.NET Framework fusion]
ms.assetid: bd042f89-10b1-40ca-946e-46da082f5263
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f2c38561a804a331df102a600d4b0b0f6312aaa6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="assemblycomparisonresult-enumeration"></a>AssemblyComparisonResult 열거형
상응 하는 두 개의 어셈블리 id 기준으로 나타냅니다는 [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) 함수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum _tagAssemblyComparisonResult {  
    ACR_Unknown,   
    ACR_EquivalentFullMatch,  
    ACR_EquivalentWeakNamed,  
    ACR_EquivalentFXUnified,  
    ACR_EquivalentUnified,    
    ACR_NonEquivalentVersion,  
    ACR_NonEquivalent,      
    ACR_EquivalentPartialMatch,  
    ACR_EquivalentPartialWeakNamed,    
    ACR_EquivalentPartialUnified,  
    ACR_EquivalentPartialFXUnified,  
    ACR_NonEquivalentPartialVersion    
} AssemblyComparisonResult;  
```  
  
## <a name="members"></a>멤버  
  
|멤버 이름|설명|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|모든 어셈블리 비교 일치 하는 필드가 있는지를 나타냅니다.|  
|`ACR_EquivalentFXUnified`|어셈블리 동일 하다 고 간주.NET Framework 버전 2.0에서에서 어셈블리 버전 번호의 공용 언어 런타임 (CLR) 버전 통합에 따라 나타냅니다.|  
|`ACR_EquivalentPartialFXUnified`|.NET Framework 2.0에서 어셈블리 버전 번호의 CLR 통합에 따라 어셈블리가 부분적으로 일치를 나타냅니다.|  
|`ACR_EquivalentPartialMatch`|어셈블리의 부분 일치를 나타냅니다.|  
|`ACR_EquivalentPartialUnified`|버전 번호의 레거시 통합에 따라 어셈블리가 부분적으로 일치를 나타냅니다.|  
|`ACR_EquivalentPartialWeakNamed`|간단한 이름의 어셈블리를 부분적으로 일치를 나타냅니다.|  
|`ACR_EquivalentUnified`|어셈블리 동일 하다 고 간주 레거시 버전의.NET Framework 버전 번호의 CLR 통합에 따라 나타냅니다.|  
|`ACR_EquivalentWeakNamed`|해당 버전 번호 내용이 무시 됩니다. 두 명의 간단한 이름의 어셈블리가 일치 함을 나타냅니다.|  
|`ACR_NonEquivalent`|일치 항목이 없는 두 어셈블리가 발생 했음을 나타냅니다.|  
|`ACR_NonEquivalentPartialVersion`|두 어셈블리는 부분적 으로만 일치 해당 버전 번호와 일치 함을 나타냅니다.|  
|`ACR_NonEquivalentVersion`|두 어셈블리는 일치 하지 않음을 해당 버전 번호와 일치 함을 나타냅니다.|  
|`ACR_Unknown`|알 수 없는 같지 않은 이유는 나타냅니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Fusion.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [CompareAssemblyIdentity 함수](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)  
 [Fusion 열거형](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
