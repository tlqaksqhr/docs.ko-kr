---
title: "SecurityBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# SecurityBindingElement
SecurityBindingElement  
  
## 구문  
  
```  
class SecurityBindingElement : BindingElement  
{  
  string DefaultAlgorithmSuite;  
  boolean IncludeTimestamp;  
  string KeyEntropyMode;  
  LocalServiceSecuritySettings LocalServiceSecuritySettings;  
  string MessageSecurityVersion;  
  string SecurityHeaderLayout;  
};  
```  
  
## 메서드  
 SecurityBindingElement 클래스는 메서드를 정의하지 않습니다.  
  
## 속성  
 SecurityBindingElement 클래스에는 다음과 같은 속성이 있습니다.  
  
### DefaultAlgorithmSuite  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 바인딩과 함께 사용할 알고리즘을 지정합니다.  
  
### IncludeTimestamp  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 각 메시지에 타임스탬프가 포함되는지 여부를 지정하는 부울 값입니다.  
  
### KeyEntropyMode  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 키를 만드는 데 사용되는 엔트로피의 소스입니다.  
  
### LocalServiceSecuritySettings  
 데이터 형식: LocalServiceSecuritySettings  
  
 액세스 형식: 읽기 전용  
  
 로컬 서비스에 대한 바인딩 특정 보안 속성입니다.  
  
### MessageSecurityVersion  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 메시지 보안에 사용된 버전입니다.  
  
### SecurityHeaderLayout  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 이 바인딩의 보안 헤더에 있는 요소의 순서입니다.  
  
## 요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|----------------------------------|  
|네임스페이스|root\\ServiceModel에 정의되어 있습니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>