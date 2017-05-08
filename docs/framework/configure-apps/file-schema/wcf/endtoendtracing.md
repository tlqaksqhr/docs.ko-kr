---
title: "&lt;endToEndTracing&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;endToEndTracing&gt;
서비스 응용 프로그램 실행 중에 종단 간 추적의 다양한 측면을 사용하거나 사용하지 않도록 설정할 수 있는 구성 요소입니다.  
  
## 구문  
  
```  
  
<system.serviceModel>  
   <diagnostics>  
       <endToEndTracing activityTracing="Boolean"  
          messageFlowTracing="Boolean"  
          propagateActivity="Boolean" />  
   </diagnostics>  
</system.serviceModel>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`activityTracing`|활동 추적 사용 여부를 지정하는 부울 값입니다.|  
|`messageFlowTracing`|메시지 흐름 추적 사용 여부를 지정하는 부울 값입니다.|  
|`propagateActivity`|propagate 특성을 true로 설정할지 여부를 지정하는 부울 값입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<diagnostics\>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|관리자의 런타임 검사 및 제어를 위한 WCF 설정을 정의합니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>   
 <xref:System.ServiceModel.Diagnostics>   
 <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>   
 <xref:System.ServiceModel.Configuration.EndToEndTracingElement>   
 [종단 간 추적](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)