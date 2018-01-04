---
title: "ICorPublishProcess 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcess
helpviewer_keywords: ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 765be4e0ae7657d169ea561bc6a36bcf8cc11153
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishprocess-interface"></a>ICorPublishProcess 인터페이스
액세스 하는 프로세스에 대 한 정보를 표시 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[EnumAppDomains 메서드](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|가져옵니다는 [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) 이 참조 하는 프로세스의 응용 프로그램 도메인을 포함 하는 인스턴스 `ICorPublishProcess`합니다.|  
|[GetDisplayName 메서드](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|이 참조 하는 프로세스에 대 한 실행 파일의 전체 경로 가져옵니다 `ICorPublishProcess`합니다.|  
|[GetProcessID 메서드](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|이 참조 하는 프로세스에 대 한 운영 체제 식별자를 가져옵니다 `ICorPublishProcess`합니다.|  
|[IsManaged 메서드](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|이 프로세스를 참조 하는지 여부를 나타내는 값을 가져옵니다 `ICorPublishProcess` 관리 되는 코드가 실행 될 것으로 알려져 있습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorPub.idl, CorPub.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [CorpubPublish Coclass](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
