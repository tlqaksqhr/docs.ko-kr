---
title: ICLRValidator::Validate 메서드
ms.date: 03/30/2017
api_name:
- ICLRValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator::Validate
helpviewer_keywords:
- Validate method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::Validate method [.NET Framework hosting]
ms.assetid: 0b1b432a-d234-4002-839b-81366c3a8bdc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b2ad9ef473a498804e5b3ac0469b5b68697c49f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439175"
---
# <a name="iclrvalidatorvalidate-method"></a>ICLRValidator::Validate 메서드
Pe (이식 가능) 또는 Microsoft MSIL (intermediate language)에 지정된 된 파일의 유효성을 검사 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Validate (  
    [in] IVEHandler        *veh,  
    [in] unsigned long      ulAppDomainId,  
    [in] unsigned long      ulFlags,  
    [in] unsigned long      ulMaxError,  
    [in] unsigned long      token,  
    [in] LPWSTR             fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long      ulSize  
);      
```  
  
#### <a name="parameters"></a>매개 변수  
 `veh`  
 [in] 에 대 한 포인터는 `IVEHandler` 유효성 검사 오류를 처리 하는 인스턴스입니다.  
  
 `ulAppDomainId`  
 [in] 현재 식별자 <xref:System.AppDomain>합니다.  
  
 `ulFlags`  
 [in] 조합을 [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) 수행 해야 하는 유효성 검사의 종류를 나타내는 값입니다.  
  
 `ulMaxError`  
 [in] 유효성 검사를 종료 하기 전까지 허용 오류의 최대 수입니다.  
  
 `token`  
 [in] 사용 되지 않습니다.  
  
 `fileName`  
 [in] 유효성을 검사할 파일의 이름입니다.  
  
 `pe`  
 [in] 파일 버퍼에 대 한 포인터입니다.  
  
 `ulSize`  
 [in] 유효성을 검사할 파일의 바이트 크기입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`Validate` 성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** IValidator.idl, IValidator.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRValidator 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
