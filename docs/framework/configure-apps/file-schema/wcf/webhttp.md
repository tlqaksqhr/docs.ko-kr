---
title: "&lt;webHttp&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;webHttp&gt;
이 요소는 구성을 통해 끝점에서 <xref:System.ServiceModel.Description.WebHttpBehavior>를 지정합니다.  이 동작을 [\<webHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) 표준 바인딩과 함께 사용할 경우 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 서비스에서 웹 프로그래밍 모델을 사용할 수 있습니다.  
  
## 구문  
  
```  
  
<webHttp />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|automaticFormatSelectionEnabled|이 속성이 `true`로 설정되면 WCF 인프라가 사용할 가장 적절한 형식을 결정합니다.  기본적으로 자동 형식 선택은 이전 버전과의 호환성을 위해 사용되지 않습니다.  자동 형식 선택은 프로그래밍 방식이나 구성을 통해 사용하도록 설정할 수 있습니다.|  
|defaultBodyStyle|반환된 메시지의 기본 본문 스타일을 지정합니다.  [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)] <xref:System.ServiceModel.Web.WebMessageBodyStyle>와 [WCF 웹 HTTP 형식 지정](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)을 참조하세요.|  
|defaultOutgoingResponseFormat|메시지의 나가는 기본 응답 형식을 지정합니다.  [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)] 자세한 내용은 [WCF 웹 HTTP 형식 지정](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)을 참조하세요.|  
|faultExceptionEnabled|내부 서버 오류\(HTTP 상태 코드: 500\)가 발생할 때 FaultException이 생성되는지 여부를 지정하는 플래그를 가져오거나 설정합니다.|  
|helpEnabled|도움말 페이지를 사용할 수 있는지 여부를 결정하는 값을 가져오거나 설정합니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<behavior\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|끝점 동작 집합을 지정합니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.WebHttpElement>   
 <xref:System.ServiceModel.Description.WebHttpBehavior>   
 [AJAX 통합 및 JSON 지원](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)   
 [\<webHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)