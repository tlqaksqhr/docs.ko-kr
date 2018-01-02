---
title: '&lt;webHttp&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6b488d4e4884f92b107b2b6be71827a2f8b4cdbf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltwebhttpgt"></a>&lt;webHttp&gt;
이 요소는 구성을 통해 끝점에서 <xref:System.ServiceModel.Description.WebHttpBehavior>를 지정합니다. 이 동작을 함께 사용 하는 경우는 [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) 표준 바인딩 웹 프로그래밍 모델을 사용 하면 한 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 서비스입니다.  
  
 \<시스템입니다. ServiceModel >  
\<동작 >  
\<endpointBehaviors >  
\<동작 >  
\<webHttp >  
  
## <a name="syntax"></a>구문  
  
```xml  
<webHttp />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|automaticFormatSelectionEnabled|이 속성이 `true`로 설정되면 WCF 인프라가 사용할 가장 적절한 형식을 결정합니다. 기본적으로 자동 형식 선택은 이전 버전과의 호환성을 위해 사용되지 않습니다. 자동 형식 선택은 프로그래밍 방식이나 구성을 통해 사용하도록 설정할 수 있습니다.|  
|defaultBodyStyle|반환된 메시지의 기본 본문 스타일을 지정합니다. [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)]<xref:System.ServiceModel.Web.WebMessageBodyStyle> 및 [WCF 웹 HTTP 형식 지정](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)합니다.|  
|defaultOutgoingResponseFormat|메시지의 나가는 기본 응답 형식을 지정합니다. [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)][WCF 웹 HTTP 형식 지정](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)합니다.|  
|faultExceptionEnabled|내부 서버 오류(HTTP 상태 코드: 500)가 발생할 때 FaultException이 생성되는지 여부를 지정하는 플래그를 가져오거나 설정합니다.|  
|helpEnabled|도움말 페이지를 사용할 수 있는지 여부를 결정하는 값을 가져오거나 설정합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<동작 >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|끝점 동작 집합을 지정합니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.WebHttpElement>  
 <xref:System.ServiceModel.Description.WebHttpBehavior>  
 [AJAX 통합 및 JSON 지원](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [\<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)
