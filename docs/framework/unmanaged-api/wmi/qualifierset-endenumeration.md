---
title: "QualifierSet_EndEnumeration 함수 (관리 되지 않는 API 참조)"
description: "QualifierSet_EndEnumeration 함수는 열거형을 종료 합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_EndEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_EndEnumeration
helpviewer_keywords: QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7868a0c0ba5abb880af201ce73b35f5ffed6f223
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="qualifiersetendenumeration-function"></a>QualifierSet_EndEnumeration 함수
열거형에 대 한 호출을 시작한 종료는 [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) 함수입니다.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
[in] 이 매개 변수를 사용 하지 않습니다.

`ptr`   
[in] 에 대 한 포인터는 [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) 인스턴스.

## <a name="return-value"></a>반환 값

이 함수에서 반환 되는 다음 값에 정의 된 *WbemCli.h* 헤더 파일을 정의할 수는 상수로 코드에서:

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemQualifierSet::EndEnumeration](https://msdn.microsoft.com/library/aa391865(v=vs.85).aspx) 메서드.

이 호출은 권장 되지만 필요 하지 않습니다. 즉시 열거와 연결 된 리소스를 해제 합니다.

## <a name="requirements"></a>요구 사항  

**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
**헤더:** WMINet_Utils.idl  
  
**.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
