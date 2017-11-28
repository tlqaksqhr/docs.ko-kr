---
title: "&lt;synchronousReceive&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b630f5ad2fbf5e3f20667e0bd1b7ae711992dc18
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltsynchronousreceivegt-element"></a>&lt;synchronousReceive&gt; 요소
이 구성 요소는 서비스 또는 클라이언트 응용 프로그램에서 메시지 수신을 위한 런타임 동작을 지정하는 데 사용됩니다. 이 구성 요소에는 특성이나 자식 요소가 없습니다.  
  
 \<시스템입니다. ServiceModel >  
\<동작 >  
\<endpointBehaviors >  
\<동작 >  
\<synchronousReceive >  
  
## <a name="syntax"></a>구문  
  
```xml  
<synchronousReceive />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<동작 >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|끝점 동작을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 채널 수신기에 기본값(비동기) 대신 동기 수신을 사용하도록 지시하려면 이 동작을 사용합니다. [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]는 수락된 각 채널에 대해 공급할 새 스레드를 발급합니다. 채널이 많은 경우 스레드가 부족할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>  
 <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
