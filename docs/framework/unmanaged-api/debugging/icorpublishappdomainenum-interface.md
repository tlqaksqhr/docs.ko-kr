---
title: "ICorPublishAppDomainEnum 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishAppDomainEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishAppDomainEnum
helpviewer_keywords: ICorPublishAppDomainEnum interface [.NET Framework debugging]
ms.assetid: bb798c56-042e-475d-a245-b6fac36d0c07
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f84a93053744f059eb3fdd06e2fb69e098e24ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishappdomainenum-interface"></a>ICorPublishAppDomainEnum 인터페이스
서브 클래스는 [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) 의 컬렉션을 이동 하는 메서드를 제공 하는 인터페이스 [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) 프로세스 내에서 현재 존재 하는 개체입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Next 메서드](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-next-method.md)|지정된 된 수의 가져옵니다 `ICorPublishAppDomain` 현재 위치부터 시작 하 고 컬렉션에서 인스턴스.|  
  
## <a name="remarks"></a>설명  
 `ICorPublishAppDomainEnum` 추상 인터페이스의 메서드를 구현 하는 인터페이스 [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorPub.idl, CorPub.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [CorpubPublish Coclass](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
