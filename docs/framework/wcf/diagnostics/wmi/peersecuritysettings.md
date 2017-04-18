---
title: "PeerSecuritySettings | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# PeerSecuritySettings
PeerSecuritySettings  
  
## 구문  
  
```  
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## 메서드  
 PeerSecuritySettings 클래스는 메서드를 정의하지 않습니다.  
  
## 속성  
 PeerSecuritySettings 클래스에는 다음과 같은 속성이 있습니다.  
  
### Mode  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 바인딩으로 구성된 끝점이 메시지 수준 보안을 사용하는지 또는 전송 수준 보안을 사용하는지 여부입니다.  
  
### Transport  
 데이터 형식: PeerTransportSecuritySettings  
  
 액세스 형식: 읽기 전용  
  
 전송 보안 설정입니다.  
  
## 요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|----------------------------------|  
|네임스페이스|root\\ServiceModel에 정의되어 있습니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.PeerSecuritySettings>