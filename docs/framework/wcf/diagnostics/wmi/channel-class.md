---
title: "Channel 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Channel 클래스
채널  
  
## 구문  
  
```  
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## 메서드  
 Channel 클래스는 메서드를 정의하지 않습니다.  
  
## 속성  
 Channel 클래스에는 다음 속성이 있습니다.  
  
### LocalAddress  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 채널에 대한 로컬 끝점입니다.  
  
### ref  
 데이터 형식: Endpoint  
  
 액세스 형식: 읽기 전용  
  
 채널이 연결되는 끝점에 대한 참조입니다.  
  
### RemoteAddress  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 채널과 연결된 원격 주소입니다.  
  
### SessionId  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 현재 세션 ID\(있는 경우\)입니다.  
  
### 형식  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 채널 형식입니다.  
  
## 요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|----------------------------------|  
|네임스페이스|root\\ServiceModel에 정의되어 있습니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Channels.ChannelBase>