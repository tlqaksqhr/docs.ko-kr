---
title: CorpubPublish Coclass
ms.date: 03/30/2017
api_name:
- CorpubPublish Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorpubPublish
helpviewer_keywords:
- CorpubPublish coclass [.NET Framework debugging]
ms.assetid: 191015da-f54a-4bac-a28a-1de7ab3c3428
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9941a9be7d9f68255636b405db29a623be8d37e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406440"
---
# <a name="corpubpublish-coclass"></a>CorpubPublish Coclass
응용 프로그램 도메인 및 프로세스에 대한 정보를 게시하기 위한 인터페이스를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a>인터페이스  
  
|인터페이스|설명|  
|---------------|-----------------|  
|[ICorPublish 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)|해당 프로세스의 프로세스 및 응용 프로그램 도메인에 대 한 정보를 게시 하기 위한 메서드를 제공 합니다.|  
|[ICorPublishAppDomain 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)|를 나타내고 프로세스에서 응용 프로그램 도메인에 대해 설명 합니다.|  
|[ICorPublishAppDomainEnum 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)|프로세스 내에서 현재 존재 하는 응용 프로그램 도메인의 컬렉션을 이동 하는 메서드를 제공 합니다.|  
|[ICorPublishProcess 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)|컴퓨터에서 실행 되는 프로세스를 나타냅니다.|  
|[ICorPublishProcessEnum 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)|컴퓨터에서 실행 되는 프로세스의 컬렉션을 이동 하는 메서드를 제공 합니다.|  
  
## <a name="remarks"></a>설명  
 일반적인 게시 시나리오에는 응용 프로그램 도메인 내의 컴퓨터에서 실행 되는 관리 되는 코드를 디버깅 하려는 개발자가 포함 됩니다. 호스팅 환경에서 프로세스 내에서 둘 이상의 응용 프로그램 도메인을 실행할 수 있습니다. 개발자의 모든 컴퓨터에서 실행 되는 프로세스를 나열 하는 그래픽 사용자 인터페이스 또는 다른 방법을 사용 하 고 특정 프로세스를 선택 하고자 합니다. 관리 코드를 실행 하는 프로세스 내의 응용 프로그램 도메인의 모든 목록에 포함 되어야 합니다. 다음 개발자 특정 응용 프로그램 도메인을 식별 하 고 해당 도메인에 디버거를 연결할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorPub.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
