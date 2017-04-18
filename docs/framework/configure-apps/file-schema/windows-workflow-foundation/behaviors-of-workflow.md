---
title: "워크플로의 &lt;behaviors&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 워크플로의 &lt;behaviors&gt;
이 요소에는 **serviceBehaviors** 컬렉션이 포함됩니다.  컬렉션의 각 요소는 워크플로 서비스에서 사용하는 동작 요소를 정의합니다.  각 동작 요소는 고유한 **name** 특성으로 식별됩니다.  
  
 \<system.ServiceModel\>  
  
## 구문  
  
```  
  
<behaviors>  
   <serviceBehaviors>  
   </serviceBehaviors>  
</behaviors>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<serviceBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|이 구성 섹션은 특정 워크플로 서비스에 정의된 모든 동작을 나타냅니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<system.serviceModel\>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|모든 워크플로 구성 요소의 루트 요소입니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>   
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>   
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>   
 [동작을 사용하여 런타임 구성 및 확장](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)