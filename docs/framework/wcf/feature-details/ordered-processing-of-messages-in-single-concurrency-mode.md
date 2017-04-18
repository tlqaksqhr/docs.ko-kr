---
title: "단일 동시성 모델에서 메시지의 순서 지정 처리 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a90f5662-a796-46cd-ae33-30a4072838af
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 단일 동시성 모델에서 메시지의 순서 지정 처리
기본 채널에 세션이 있는 경우가 아니면 WCF는 메시지가 처리되는 순서에 대해 보장하지 않습니다. 예를 들어, 세션이 없는 채널인 MsmqInputChannel을 사용하는 WCF 서비스는 메시지를 순서대로 처리하지 못합니다. 개발자가 세션을 사용하지 않으면서 순서에 따른 처리 동작을 원하는 상황이 있습니다.이 항목에서는 서비스가 단일 동시성 모델에서 실행되고 있을 때 이 동작을 구성하는 방법을 설명합니다.  
  
## 순서에 따른 메시지 처리  
 <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A>라는 새 속성이 <xref:System.ServiceModel.ServiceBehaviorAttribute>에 추가되었습니다.<xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A>가 true로 설정되고 <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A>가 <xref:System.ServiceModel.ConcurrencyMode>로 설정되면 서비스에 전송된 메시지는 순서대로 처리됩니다.다음 코드 조각에서는 이러한 특성을 설정하는 방법을 보여 줍니다.  
  
```  
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, EnsureOrderedDispatch = true )]  
    class Service : IService  
    {  
         // ...  
    }  
  
```  
  
 <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A>가 다른 값으로 설정되면 <xref:System.InvalidOperationException>이 throw됩니다.  
  
## 참고 항목  
 [세션, 인스턴스 및 동시성](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)   
 [동시성](../../../../docs/framework/wcf/samples/concurrency.md)