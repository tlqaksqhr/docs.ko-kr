---
title: "ClientCredentials | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# ClientCredentials
ClientCredentials  
  
## 구문  
  
```  
class ClientCredentials : Behavior  
{  
  string ClientCertificate;  
  string HttpDigest;  
  string IssuedToken;  
  string Peer;  
  string ServiceCertificate;  
  boolean SupportInteractive;  
  string UserName;  
  string Windows;  
};  
```  
  
## 메서드  
 ClientCredentials 클래스는 메서드를 정의하지 않습니다.  
  
## 속성  
 ClientCredentials 클래스에는 다음과 같은 속성이 있습니다.  
  
### ClientCertificate  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 서비스를 인증하는 데 클라이언트가 사용하는 X.509 인증서입니다.  
  
### HttpDigest  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 현재 Http Digest 자격 증명입니다.  
  
### IssuedToken  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 로컬 보안 토큰 서비스에 연결하기 위해 사용되는 끝점 주소 및 바인딩입니다.  
  
### Peer  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 메시의 다른 노드에게 자신을 인증하기 위해 피어 노드가 사용하는 자격 증명입니다.  
  
### ServiceCertificate  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 서비스의 X.509 인증서입니다.  
  
### SupportInteractive  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 자격 증명이 대화형 협상을 지원하는지 여부를 지정하는 부울 값입니다.  
  
### UserName  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 서비스에게 자신을 인증하기 위해 클라이언트가 사용하는 사용자 이름 및 암호입니다.  
  
### Windows  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 서비스에게 자신을 인증하기 위해 클라이언트가 사용하는 Windows 자격 증명입니다.  
  
## 요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|----------------------------------|  
|네임스페이스|root\\ServiceModel에 정의되어 있습니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Description.ClientCredentials>