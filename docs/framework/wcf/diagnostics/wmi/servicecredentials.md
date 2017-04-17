---
title: "ServiceCredentials | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# ServiceCredentials
ServiceCredentials  
  
## 구문  
  
```  
class ServiceCredentials : Behavior  
{  
  string ClientCertificate;  
  string IssuedTokenAuthentication;  
  string Peer;  
  string SecureConversationAuthentication;  
  string ServiceCertificate;  
  string UserNameAuthentication;  
  string WindowsAuthentication;  
};  
```  
  
## 메서드  
 ServiceCredentials 클래스는 메서드를 정의하지 않습니다.  
  
## 속성  
 ServiceCredentials 클래스에는 다음과 같은 속성이 있습니다.  
  
### ClientCertificate  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 이 서비스에 대한 클라이언트 인증서 인증 및 구축 설정입니다.  
  
### IssuedTokenAuthentication  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 이 서비스에 대해 현재 발급된 토큰 인증 설정입니다.  
  
### Peer  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 피어 전송 끝점이 사용하는 현재 자격 증명 인증 및 구축 설정입니다.  
  
### SecureConversationAuthentication  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 현재 보안 대화 설정을 지정합니다.  
  
### ServiceCertificate  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 이 서비스와 연관된 인증서입니다.  
  
### UserNameAuthentication  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 이 서비스에 대한 사용자 이름\/암호 설정입니다.  
  
### WindowsAuthentication  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 이 서비스에 대한 Windows 인증 설정입니다.  
  
## 요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|----------------------------------|  
|네임스페이스|root\\ServiceModel에 정의되어 있습니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Description.ServiceCredentials>