---
title: "ICLRDataTarget2::AllocVirtual 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget2.AllocVirtual
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget2::AllocVirtual
helpviewer_keywords:
- ICLRDataTarget2::AllocVirtual method [.NET Framework debugging]
- AllocVirtual method [.NET Framework debugging]
ms.assetid: e3226230-964b-47fb-9f53-d6fdbeda1e9e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e61b27ae7dcda8cc5e14d9c0f72f74c8bda13169
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdatatarget2allocvirtual-method"></a>ICLRDataTarget2::AllocVirtual 메서드
이 대상 프로세스의 주소 공간에 메모리를 할당할는 공용 언어 런타임 (CLR) 데이터 액세스 서비스에서 호출 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `addr`  
 [in] A `CLRDATA_ADDRESS` 할당할 메모리의 요청 된 시작 주소를 지정 하는 값입니다.  
  
 `size`  
 [in] 에 할당할 메모리의 바이트 크기입니다.  
  
 `typeFlags`  
 [in] 메모리의 할당을 제어 하는 플래그입니다. Win32 참조 `VirtualAlloc` 함수입니다.  
  
 `protectFlags`  
 [in] 할당된 된 메모리에 대 한 보호 특성입니다. Win32 참조 `VirtualAlloc` 함수입니다.  
  
 `virt`  
 [out] 에 대 한 포인터는 `CLRDATA_ADDRESS` 할당된 된 메모리의 실제 시작 주소를 지정 하는 값입니다.  
  
## <a name="remarks"></a>설명  
 `AllocVirtual` 메서드 래퍼 역할을 논리는 win32 `VirtualAlloc` 함수입니다.  
  
 이 메서드는 디버깅 응용 프로그램의 작성자가 구현합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** ClrData.idl, ClrData.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRDataTarget2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [FreeVirtual 메서드](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)
