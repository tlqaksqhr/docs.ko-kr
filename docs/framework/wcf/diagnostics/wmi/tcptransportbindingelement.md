---
title: "TcpTransportBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# TcpTransportBindingElement
TcpTransportBindingElement  
  
## 구문  
  
```  
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## 메서드  
 TcpTransportBindingElement 클래스는 메서드를 정의하지 않습니다.  
  
## 속성  
 TcpTransportBindingElement 클래스에는 다음과 같은 속성이 있습니다.  
  
### ConnectionPoolSettings  
 데이터 형식: TcpConnectionPoolSettings  
  
 액세스 형식: 읽기 전용  
  
 연결 풀 설정입니다.  
  
### ListenBacklog  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 보류할 수 있는 최대 대기 중인 연결 요청 수입니다.  
  
### PortSharingEnabled  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 이 연결에서 TCP 포트 공유를 사용하는지 여부를 지정하는 부울 값입니다.  
  
### TeredoEnabled  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 Teredo\(방화벽으로 보호되는 클라이언트의 주소를 지정하는 기술\)의 사용 여부를 지정하는 부울 값입니다.  
  
## 요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|----------------------------------|  
|네임스페이스|root\\ServiceModel에 정의되어 있습니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>