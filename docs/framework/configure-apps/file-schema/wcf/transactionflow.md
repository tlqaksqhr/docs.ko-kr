---
title: "&lt;transactionFlow&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# &lt;transactionFlow&gt;
사용자 지정 바인딩에 대한 트랜잭션 흐름 지원을 지정합니다.  
  
## 구문  
  
```  
  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|transactionProtocol|사용할 트랜잭션 프로토콜을 지정합니다.  유효한 값은 다음과 같습니다.<br /><br /> -   OleTransactions<br />-   WSAtomicTransactionOctober2004<br /><br /> 기본값은 OleTransactions입니다.<br /><br /> 이 특성은 <xref:System.ServiceModel.TransactionProtocol> 형식입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<binding\>](../../../../../docs/framework/misc/binding.md)|사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.|  
  
## 설명  
 이 요소를 사용하면 끝점의 바인딩 설정에 들어오는 트랜잭션 흐름을 사용하거나 사용하지 않도록 설정할 수 있을 뿐 아니라 들어오는 트랜잭션에 대해 원하는 프로토콜 형식을 지정할 수 있습니다.  이 구성 요소 사용에 대한 자세한 내용은 [ServiceModel 트랜잭션 구성](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) 및 [트랜잭션 흐름 사용](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)을 참조하세요.  
  
> [!CAUTION]
>  `OleTransactions` 프로토콜을 사용하여 끝점 간에 트랜잭션을 전달할 경우 대상 끝점에서 `OleTransactions` 이외의 프로토콜을 사용하여 트랜잭션을 다시 전달하려고 하면 트랜잭션 시간 제한이 상실될 수 있습니다.  따라서 OleTransactions 홉 뒤의 모든 하위 수준 노드가 예상보다 늦게 시간이 초과될 수 있습니다.  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.TransactionFlowElement>   
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [ServiceModel 트랜잭션 구성](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)   
 [트랜잭션 흐름 사용](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)   
 [바인딩](../../../../../docs/framework/wcf/bindings.md)   
 [바인딩 확장](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [사용자 지정 바인딩](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)