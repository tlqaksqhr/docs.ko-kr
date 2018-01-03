---
title: "ICLRDataTarget 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget
helpviewer_keywords: ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: e2f05155-9bef-4e11-b703-7f05890665ca
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 73966ffe89f0e84d5a516f20962472d900332faa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatarget-interface"></a>ICLRDataTarget 인터페이스
공용 언어 런타임 (CLR)의 대상 항목과 상호 작용 하기 위한 메서드를 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetCurrentThreadID 메서드](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getcurrentthreadid-method.md)|현재 스레드에 대 한 운영 체제 식별자를 가져옵니다.|  
|[GetImageBase 메서드](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getimagebase-method.md)|지정된 된 이미지에 대 한 기본 메모리 주소를 가져옵니다.|  
|[GetMachineType 메서드](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getmachinetype-method.md)|대상 프로세스를 사용 하는 명령 집합의 종류에 대 한 식별자를 가져옵니다.|  
|[GetPointerSize 메서드](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getpointersize-method.md)|현재 대상에 대 한 포인터를 바이트 단위로 크기를 가져옵니다.|  
|[GetThreadContext 메서드](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getthreadcontext-method.md)|지정한 식별자를 가진 스레드 컨텍스트에 대 한 포인터를 가져옵니다.|  
|[GetTLSValue 메서드](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-gettlsvalue-method.md)|스레드 로컬 저장소 (TLS)에 지정 된 스레드에 대 한 지정된 된 인덱스에 값을 가져옵니다.|  
|[ReadVirtual 메서드](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-readvirtual-method.md)|지정된 된 버퍼에 지정 된 가상 메모리 주소에서 데이터를 읽습니다.|  
|[Request 메서드](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-request-method.md)|구현에 의해 정의 된 대로 작업을 요청 하는 공용 언어 런타임 (CLR) 데이터 액세스 서비스에서 호출 됩니다.|  
|[SetThreadContext 메서드](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-setthreadcontext-method.md)|대상 프로세스에서 지정 된 스레드의 현재 컨텍스트를 설정합니다.|  
|[SetTLSValue 메서드](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-settlsvalue-method.md)|대상 프로세스에서 지정 된 스레드의 스레드 로컬 저장소 (TLS)에 값을 설정합니다.|  
|[WriteVirtual 메서드](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-writevirtual-method.md)|지정 된 가상 메모리 주소에 지정된 된 버퍼에서 데이터를 씁니다.|  
  
## <a name="remarks"></a>설명  
 API 클라이언트 (즉, 디버거)에서는 특정 대상 항목에 따라이 인터페이스를 구현 해야 합니다. 예를 들어 활성 프로세스의 구현은 메모리 덤프의 구현과는 다릅니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** ClrData.idl, ClrData.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRDataTarget2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
