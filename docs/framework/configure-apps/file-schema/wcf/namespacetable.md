---
title: "&lt;namespaceTable&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;namespaceTable&gt;
매핑을 앞에 붙인 다음 XPath 필터에서 라우팅에 사용할 수 있는 네임스페이스를 포함하는 요소 집합을 정의하기 위한 구성 섹션을 나타냅니다.  
  
## 구문  
  
```vb  
  
<routing>  
   <namespaceTable>  
     <add namespace="String" prefix="String" />   
   </namespaceTable>  
</routing>  
  
```  
  
```csharp  
  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)|XPath 식에 사용되는 네임스페이스 접두사 매핑을 정의합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<routing\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|들어오는 메시지 및 필터가 일치할 때 메시지를 보낼 대상 끝점을 정의하는 라우팅 테이블을 평가할 때 사용되는 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> 형식을 결정하는 라우팅 필터 집합을 정의하기 위한 구성 섹션을 나타냅니다.|  
  
## 참고 항목  
 [System.ServiceModel.Routing.Configuration.NamespaceElementCollection](assetId:///System.ServiceModel.Routing.Configuration.NamespaceElementCollection?qualifyHint=False&amp;autoUpgrade=True)