---
title: ServiceThrottlingBehavior
ms.date: 03/30/2017
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
ms.openlocfilehash: 9a7fbf93dbdbf1a6debcf865b4883b5784e2ff4a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33487609"
---
# <a name="servicethrottlingbehavior"></a>ServiceThrottlingBehavior
ServiceThrottlingBehavior  
  
## <a name="syntax"></a>구문  
  
```  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a>메서드  
 ServiceThrottlingBehavior 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  
 ServiceThrottlingBehavior 클래스에는 다음과 같은 속성이 있습니다.  
  
### <a name="maxconcurrentcalls"></a>MaxConcurrentCalls  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 ServiceHost의 모든 디스패처 개체에서 동시에 처리하는 최대 메시지 수입니다.  
  
### <a name="maxconcurrentinstances"></a>MaxConcurrentInstances  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 한 번에 실행할 수 있는 최대 서비스 개체 수입니다.  
  
### <a name="maxconcurrentsessions"></a>MaxConcurrentSessions  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 호스트가 한 번에 수락할 수 있는 최대 세션 수입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
