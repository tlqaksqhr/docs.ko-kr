---
title: "ICLRRuntimeHost::ExecuteInDefaultAppDomain 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.ExecuteInDefaultAppDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::ExecuteInDefaultAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain method [.NET Framework hosting]
- ExecuteInDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 30b5cf9a-a762-4bd4-be12-d6c1442b78b1
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ae0e006cdaa983fd7a3c9f650b61d4579aeaf0ed
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a>ICLRRuntimeHost::ExecuteInDefaultAppDomain 메서드
지정된 된 관리 되는 어셈블리에 지정 된 형식의 지정된 된 메서드를 호출합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,   
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pwzAssemblyPath`  
 [in] 에 대 한 경로 <xref:System.Reflection.Assembly> 정의 하는 <xref:System.Type> 호출 방법은 합니다.  
  
 `pwzTypeName`  
 [in] 이름에서 <xref:System.Type> 호출할 메서드를 정의 하는 합니다.  
  
 `pwzMethodName`  
 [in] 호출할 메서드의 이름입니다.  
  
 `pwzArgument`  
 [in] 메서드에 전달할 문자열 매개 변수입니다.  
  
 `pReturnValue`  
 [out] 호출 된 메서드에서 반환 된 정수 값입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`ExecuteInDefaultAppDomain`성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자에 게 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 CRL을 프로세스 내에서 사용할 수 없습니다. 호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 호출 된 메서드에 다음 서명이 있어야 합니다.  
  
```  
static int pwzMethodName (String pwzArgument)  
```  
  
 여기서 `pwzMethodName` 호출 된 메서드의 이름을 나타내는 및 `pwzArgument` 해당 메서드에 매개 변수로 전달 된 문자열 값을 나타냅니다. HRESULT 값 s_ok이 고에 설정 된 경우 `pReturnValue` 호출 된 메서드에서 반환 된 정수 값으로 설정 됩니다. 그렇지 않으면 `pReturnValue` 설정 되지 않았습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRRuntimeHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
