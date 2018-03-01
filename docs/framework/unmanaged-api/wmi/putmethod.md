---
title: "PutMethod 함수 (관리 되지 않는 API 참조)"
description: "PutMethod 함수는 메서드를 만듭니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- PutMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutMethod
helpviewer_keywords:
- PutMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7e97ffcf44a738234f67d9736382c46c42e5b61e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="putmethod-function"></a>PutMethod 함수
메서드를 만듭니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>구문  
  
```  
HRESULT PutMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*  ptr, 
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
[in] 이 매개 변수를 사용 하지 않습니다.

`ptr`  
[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.

`wszName`  
[in] 만드는 방법의 이름입니다. 

`lFlags`  
[in] 예약 되어 있습니다. 이 매개 변수는 0 이어야 합니다.

`pSignatureIn`  
[in] 복사본에 대 한 포인터는 [__Parameters 시스템 클래스](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) 를 포함 하는 `in` 메서드의 매개 변수입니다. 이 매개 변수는 설정 `null`합니다.  

`pSignatureOut`  
[in]  복사본에 대 한 포인터는 [__Parameters 시스템 클래스](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) 를 포함 하는 `out` 메서드의 매개 변수입니다. 이 매개 변수는 설정 `null`합니다.
 

## <a name="return-value"></a>반환 값

이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | 하나 이상의 매개 변수가 올바르지 않습니다. |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | 0x80041043 | `[in, out]` 모두에 지정 된 메서드 매개 변수는 *pInSignature* 및 *pOutSignature* 개체에는 다른 한정자입니다.
| `WBEM_E_MISSING_PARAMETER_ID` | 0x80041036 | 메서드 매개 변수의 사양이 없습니다는 **ID** 한정자입니다. |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | 0x80041038 | 메서드 매개 변수에 할당 된 ID 시리즈 연속 되었거나 0으로 시작 되지 않습니다. |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | 0x80041039 | 메서드에 대 한 반환 값에는 **ID** 한정자입니다. |
| `WBEM_E_PROPAGATED_METHOD` | 0x80041034 | 부모 클래스에서 기존 메서드 이름을 다시 사용 하려고 했습니다 및 서명이 일치 하지 않습니다. |
| `WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다. |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx) 메서드.

이 메서드를 호출 하는 경우만 지원 됩니다 `ptr` CIM 클래스 정의입니다. 조작 메서드를 사용할 수 없기 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) CIM 인스턴스를 가리키는 포인터입니다.

사용자가 시작 또는 밑줄로 끝나야 하는 이름을 가진 메서드를 만들 수 없습니다. 이 시스템 클래스 및 속성에 대해 예약 됩니다.

메서드에 대 한는 `in` 및 `out` 매개 변수에서 속성으로 설명 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) 개체입니다.

`[in/out]` 가리키는 두 개체 모두에 동일한 속성을 추가 하 여 매개 변수를 정의할 수 있습니다는 `pInSignature` 및 `pOutSignature` 매개 변수입니다. 이 경우 속성 공유 동일한 **ID** 한정자 값입니다.

각 속성에는 [__Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) 개체 이외의 클래스 `ReturnValue` 있어야는 **ID** 한정자, 매개 변수가 나타나는 순서를 식별 하는 숫자 값을 0부터 시작 합니다. 동일한 두 개의 매개 변수가 없는 가질 수 있습니다 **ID** 값 및 아니요 **ID** 값을 건너뛸 수 있습니다. 두 조건 중 하나가 발생 하는 경우는 `PutMethod` 함수에서 반환 `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`합니다.

## <a name="example"></a>예

예를 들어 참조는 [IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx) 메서드.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
