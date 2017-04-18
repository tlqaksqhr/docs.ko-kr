---
title: "&lt;webScriptEndpoint&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;webScriptEndpoint&gt;
이 구성 요소는 [\<enableWebScript\>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) 동작을 자동으로 추가하는 고정 [\<webHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) 바인딩을 사용하여 표준 끝점을 정의합니다.  ASP.NET AJAX 응용 프로그램에서 호출되는 서비스를 기록할 때 이 끝점을 사용합니다.  
  
## 구문  
  
```  
  
<system.serviceModel>  
    <standardEndpoints>  
       <webScriptEndpoint>   
          <standardEndpoint  
             webEndpointType=”String”/>        
       </webScriptEndpoint>   
    </standardEndpoints>  
</system.serviceModel>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|webEndpointType|끝점의 형식을 지정하는 문자열입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<standardEndpoints\>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|하나 이상의 속성\(주소, 바인딩, 계약\)이 고정된 미리 정의된 끝점인 표준 끝점의 컬렉션입니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Description.WebScriptEndpoint>   
 <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>