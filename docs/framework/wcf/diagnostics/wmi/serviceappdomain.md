---
title: "ServiceAppDomain | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# ServiceAppDomain
서비스를 응용 프로그램 도메인에 매핑합니다.  
  
## 구문  
  
```  
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## 메서드  
 ServiceAppDomain 클래스는 메서드를 정의하지 않습니다.  
  
## 속성  
 ServiceAppDomain 클래스에는 다음 속성이 포함되어 있습니다.  
  
### ref  
 데이터 형식: Service               
 한정자: Key  
  
 액세스 형식: 읽기 전용  
  
 이 응용 프로그램 도메인의 서비스입니다.  
  
### ref  
 데이터 형식: AppDomainInfo               
 한정자: Key  
  
 액세스 형식: 읽기 전용  
  
 응용 프로그램 도메인의 속성을 포함합니다.  
  
## 요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|----------------------------------|  
|네임스페이스|root\\ServiceModel에 정의되어 있습니다.|