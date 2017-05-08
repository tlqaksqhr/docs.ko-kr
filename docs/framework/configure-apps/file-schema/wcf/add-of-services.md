---
title: "&lt;services&gt;의 &lt;add&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;services&gt;의 &lt;add&gt;
워크플로 기반 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 서비스를 호스트하기 위해 <xref:System.Workflow.Runtime.WorkflowRuntime>의 인스턴스에 대한 설정을 지정합니다.  이 요소는 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> 형식입니다.  
  
## 구문  
  
```  
  
<workflowRuntime>  
   <services>  
      <add type="String"/>  
   </services>  
</workflowRuntime>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|형식|초기화할 서비스의 정규화된 어셈블리 형식 이름을 지정하는 문자열입니다.  지정된 서비스는 생성자의 시그니처에 대한 특정 규칙을 따라야 합니다.  자세한 내용은 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>를 참조하세요.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<services\>](../../../../../docs/framework/configure-apps/file-schema/wcf/services-of-workflowruntime.md)|<xref:System.Workflow.Runtime.WorkflowRuntime> 엔진에 추가할 서비스 컬렉션입니다.  요소는 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> 형식입니다.  컬렉션에 지정된 서비스는 워크플로 런타임 엔진에 의해 초기화되며 해당 <xref:System.Workflow.Runtime.WorkflowRuntime> 생성자를 호출할 때 서비스에 추가됩니다.  따라서 컬렉션에 지정된 서비스는 생성자의 시그니처에 대한 특정 규칙을 따라야 합니다.  자세한 내용은 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>를 참조하세요.|  
  
## 설명  
 이 요소에 지정된 서비스는 워크플로 런타임 엔진에 의해 초기화되며 해당 <xref:System.Workflow.Runtime.WorkflowRuntime> 생성자를 호출할 때 서비스에 추가됩니다.  따라서 지정된 서비스는 생성자의 시그니처에 대한 특정 규칙을 따라야 합니다.  자세한 내용은 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>를 참조하세요.  
  
## 예제  
  
```  
<serviceBehaviors>  
   <behavior name="ServiceBehavior">  
      <workflowRuntime name="WorkflowServiceHostRuntime"  
                       validateOnCreate="true"  
                       enablePerformanceCounters="true">  
         <services>  
             <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common"/>  
         </services>  
      </workflowRuntime>  
   </behavior>  
</serviceBehaviors>  
```  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>   
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>   
 <xref:System.Workflow.Runtime.WorkflowRuntime>   
 [Workflow Configuration Files](http://msdn.microsoft.com/ko-kr/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)