---
title: GetDemultiplexedStub 함수 (관리 되지 않는 API 참조)
description: GetDemultiplexedStub 함수 Windows 관리에서 비동기 호출을 받는 클라이언트를 지원 하기 위해 개체 전달자 싱크를 만듭니다.
ms.date: 11/06/2017
api_name:
- GetDemultiplexedStub
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetDemultiplexedStub
helpviewer_keywords:
- GetDemultiplexedStub function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b195d3a512c537ca409bd2039add9e69abaf4df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="getdemultiplexedstub-function"></a>GetDemultiplexedStub 함수
Windows 관리에서 비동기 호출을 받는 클라이언트를 지원 하기 위해 개체 전달자 싱크를 만듭니다.
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject, 
   [in] boolean      isLocal, 
   [out] IUnknown**  ppObject
); 
```  

## <a name="parameters"></a>매개 변수

`pObject`  
[in] 클라이언트의 프로세스에 구현에 대 한 포인터 [IWbemObjectSink](https://msdn.microsoft.com/library/aa391787(v=vs.85).aspx)합니다.

`isLocal`  
[in] 이벤트가 로컬 인지 여부를 나타내는 플래그 (`true`), 그렇지 않으면 `false`합니다.

`ppObject`  
[out] Windows 관리에서 비동기 호출을 받는 클라이언트를 지원 하기 위해 개체 전달자 싱크.

## <a name="return-value"></a>반환 값

함수가 성공 하면 반환 값은 `S_OK` (0).

함수가 실패 하면 반환 값은 0이 아닌 오류 코드입니다. 확장 정보를 가져오려면 오류를 호출 하는 [GetErrorInfo](geterrorinfo.md) 함수입니다.
    
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
