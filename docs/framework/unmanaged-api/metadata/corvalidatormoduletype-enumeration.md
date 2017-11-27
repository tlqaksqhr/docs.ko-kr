---
title: "CorValidatorModuleType 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorValidatorModuleType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorValidatorModuleType
helpviewer_keywords: CorValidatorModuleType enumeration [.NET Framework metadata]
ms.assetid: 748f1ab2-fbcb-4f55-89ec-8d23d81ebc80
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: fa7ca08398358dcf00a986c356de365e9caafc4f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="corvalidatormoduletype-enumeration"></a>CorValidatorModuleType 열거형
모듈의 형식을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum  
{  
    ValidatorModuleTypeInvalid  = 0x0,  
    ValidatorModuleTypeMin      = 0x00000001,  
    ValidatorModuleTypePE       = 0x00000001,  
    ValidatorModuleTypeObj      = 0x00000002,  
    ValidatorModuleTypeEnc      = 0x00000003,  
    ValidatorModuleTypeIncr     = 0x00000004,  
    ValidatorModuleTypeMax      = 0x00000004  
} CorValidatorModuleType;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|모듈에 잘못 된 형식입니다.|  
|`ValidatorModuleTypeMin`|최소 값은 `CorValidatorModuleType` 열거형입니다.|  
|`ValidatorModuleTypePE`|모듈에는 이식 가능한 실행 (PE) 파일입니다.|  
|`ValidatorModuleTypeObj`|모듈은.obj 파일.|  
|`ValidatorModuleTypeEnc`|모듈은는 편집 하며 계속 하기 디버거 세션입니다.|  
|`ValidatorModuleTypeIncr`|모듈은 증분 빌드할입니다.|  
|`ValidatorModuleTypeMax`|최대값은 `CorValidatorModuleType` 열거형입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타 데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
