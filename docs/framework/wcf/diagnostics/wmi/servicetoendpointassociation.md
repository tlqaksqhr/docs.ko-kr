---
title: "ServiceToEndpointAssociation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# ServiceToEndpointAssociation
서비스를 끝점에 매핑합니다.  
  
## 구문  
  
```  
class ServiceToEndpointAssociation  
{  
  Service ref;  
  Endpoint ref;  
};  
```  
  
## 메서드  
 ServiceToEndpointAssociation 클래스는 메서드를 정의하지 않습니다.  
  
## 속성  
 ServiceToEndpointAssociation 클래스에는 다음과 같은 속성이 있습니다.  
  
### ref  
 데이터 형식: Service  
  
 액세스 형식: 읽기 전용  
한정자: Key  
  
 끝점과 연결된 서비스입니다.  
  
### ref  
 데이터 형식: Endpoint  
  
 액세스 형식: 읽기 전용  
한정자: Key  
  
 서비스와 연결된 끝점입니다.  
  
## 요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|----------------------------------|  
|네임스페이스|root\\ServiceModel에 정의되어 있습니다.|