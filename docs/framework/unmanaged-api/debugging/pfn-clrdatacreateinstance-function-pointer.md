---
title: "PFN_CLRDataCreateInstance 함수 포인터"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: PFN_CLRDataCreateInstance
api_location: mscordbi.dll
api_type: COM
f1_keywords: PFN_CLRDataCreateInstance
helpviewer_keywords: PFN_CLRDataCreateInstance function pointer [.NET Framework debugging]
ms.assetid: 5c66ac57-d751-4de5-af9f-26ceb949af8b
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 98a966434332549d9ceb7f29de81e19fa1b2108f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="pfnclrdatacreateinstance-function-pointer"></a>PFN_CLRDataCreateInstance 함수 포인터
지정 된 대상 항목에 대 한 인터페이스 개체를 만드는 함수를 가리킵니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
    [in]  REFIID           iid,  
    [in]  ICLRDataTarget  *target,  
    [out] void           **iface  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 인스턴스화할 인터페이스의 식별자입니다.  
  
 `target`  
 [in] 사용자가 구현에 대 한 포인터 [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) 인터페이스 개체를 대상 항목을 나타내는 개체입니다.  
  
 `iface`  
 [out] 반환 된 인터페이스 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `ICLRDataTarget` 개체는 디버깅 응용 프로그램의 작성자에 의해 구현 됩니다. 구현에서는 표시 되는 대상 항목의 형식에 따라 달라 집니다. 프로세스, 메모리 덤프, 원격 컴퓨터 및 등 대상 항목 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** ClrData.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 전역 정적 함수](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
