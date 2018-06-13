---
title: ValidatorFlags 열거형
ms.date: 03/30/2017
api_name:
- ValidatorFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ValidatorFlags
helpviewer_keywords:
- ValidatorFlags enumeration [.NET Framework hosting]
ms.assetid: a3f5c266-3fcc-4ad1-aaf5-4cdbe26304ad
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20ce52108c1024ad3e07051b226aa65612580e2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441392"
---
# <a name="validatorflags-enumeration"></a>ValidatorFlags 열거형
에 대 한 호출에서 수행 해야 하는 유효성 검사의 유형을 나타내는 값이 포함 되어는 [iclrvalidator:: Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) 메서드.  
  
## <a name="syntax"></a>구문  
  
```  
enum ValidatorFlags {  
    VALIDATOR_EXTRA_VERBOSE =       0x00000001,  
    VALIDATOR_SHOW_SOURCE_LINES =   0x00000002,  
    VALIDATOR_CHECK_ILONLY =        0x00000004,  
    VALIDATOR_CHECK_PEFORMAT_ONLY = 0x00000008,  
    VALIDATOR_NOCHECK_PEFORMAT =    0x00000010,  
};  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`VALIDATOR_CHECK_ILONLY`|만 Microsoft intermediate language (MSIL)에서 실행 파일을 검사 하도록 지정 합니다.|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|실행 파일의 형식에만 검사 하도록 지정 합니다.|  
|`VALIDATOR_EXTRA_VERBOSE`|모든 유형의 유효성 검사 수행 및 보고를 지정 합니다.|  
|`VALIDATOR_NOCHECK_PEFORMAT`|실행 파일의 형식을 확인 하지 않음을 지정 합니다.|  
|`VALIDATOR_SHOW_SOURCE_LINES`|유효성 검사 오류 메시지 유효성 검사 오류가 발생 하는 소스 코드의 줄에 포함 되도록 지정 합니다. 필드 값이.NET Framework 버전 2.0에서에서 올바르지 않습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** IValidator.idl, IValidator.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRErrorReportingManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [호스팅 열거형](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
