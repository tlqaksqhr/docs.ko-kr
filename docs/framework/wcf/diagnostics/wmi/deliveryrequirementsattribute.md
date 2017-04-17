---
title: "DeliveryRequirementsAttribute | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# DeliveryRequirementsAttribute
DeliveryRequirementsAttribute  
  
## 구문  
  
```  
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## 메서드  
 DeliveryRequirementsAttribute 클래스는 메서드를 정의하지 않습니다.  
  
## 속성  
 DeliveryRequirementsAttribute 클래스에는 다음과 같은 속성이 있습니다.  
  
### QueuedDeliveryRequirements  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 서비스 바인딩이 계약을 지원할지 여부를 지정합니다.  
  
### RequireOrderedDelivery  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 바인딩이 순서가 지정된 메시지를 지원할지 여부를 지정합니다.  
  
### TargetContract  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 적용할 계약입니다.  
  
## 요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|----------------------------------|  
|네임스페이스|root\\ServiceModel에 정의되어 있습니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>