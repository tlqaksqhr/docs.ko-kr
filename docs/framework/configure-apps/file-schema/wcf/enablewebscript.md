---
title: "&lt;enableWebScript&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;enableWebScript&gt;
이 요소는 ASP.NET AJAX 웹 페이지에서 서비스를 사용할 수 있게 하는 끝점 동작을 설정합니다.  
  
## 구문  
  
```  
  
<enableWebScript />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<behavior\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|끝점 동작 집합을 지정합니다.|  
  
## 설명  
 이 동작은 [\<webHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) 표준 바인딩 또는 [\<webMessageEncoding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) 바인딩 요소와 함께 사용해야 합니다.  이 동작에 대한 자세한 내용은 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>를 참조하세요.  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>   
 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>   
 [AJAX 통합 및 JSON 지원](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)   
 [\<webHttp\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)