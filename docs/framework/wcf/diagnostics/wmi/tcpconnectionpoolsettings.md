---
title: "TcpConnectionPoolSettings | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# TcpConnectionPoolSettings
TcpConnectionPoolSettings  
  
## 구문  
  
```  
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## 메서드  
 TcpConnectionPoolSettings 클래스는 메서드를 정의하지 않습니다.  
  
## 속성  
 TcpConnectionPoolSettings 클래스에는 다음과 같은 속성이 있습니다.  
  
### GroupName  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 바인딩 요소가 사용하는 연결 풀의 그룹 이름입니다.  
  
### IdleTimeout  
 데이터 형식: datetime  
  
 액세스 형식: 읽기 전용  
  
 연결이 끊어지기 전에 유휴 상태일 수 있는 최대 시간입니다.  
  
### LeaseTimeout  
 데이터 형식: datetime  
  
 액세스 형식: 읽기 전용  
  
 제한 시간을 초과하기 전에 대여 작업을 완료하기 위한 최대 시간입니다.  
  
### MaxOutboundConnectionsPerEndpoint  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 각 끝점에 대한 최대 아웃바운드 연결 수입니다.  
  
## 요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|----------------------------------|  
|네임스페이스|root\\ServiceModel에 정의되어 있습니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>