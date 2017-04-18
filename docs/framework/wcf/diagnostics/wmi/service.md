---
title: "서비스 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# 서비스
서비스  
  
## 구문  
  
```  
class Service  
{  
  string BaseAddresses[];  
  Behavior Behaviors[];  
  string ConfigurationName;  
  string CounterInstanceName;  
  string DistinguishedName;  
  string Extensions[];  
  string Metadata[];  
  string Name;  
  string Namespace;  
  datetime Opened;  
  Channel OutgoingChannels[];  
  sint32 ProcessId;  
};  
```  
  
## 메서드  
 Service 클래스는 메서드를 정의하지 않습니다.  
  
## 속성  
 Service 클래스에는 다음과 같은 속성이 있습니다.  
  
### BaseAddresses  
 데이터 형식: string array  
  
 액세스 형식: 읽기 전용  
  
 서비스가 사용하는 기본 주소입니다.  
  
### Behaviors  
 데이터 형식: Behavior array  
  
 액세스 형식: 읽기 전용  
  
 이 서비스와 연관된 동작입니다.  
  
### ConfigurationName  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 ServiceElement\_BehaviorConfiguration  
  
### CounterInstanceName  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 서비스의 성능 카운터 인스턴스의 인스턴스 이름입니다.  
  
### DistinguishedName  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 주소의 서비스 이름입니다.  
  
### Extensions  
 데이터 형식: string array  
  
 액세스 형식: 읽기 전용  
  
 서비스 인스턴스의 확장에 대한 인스턴스 컨텍스트입니다.  
  
### Metadata  
 데이터 형식: string array  
  
 액세스 형식: 읽기 전용  
  
 서비스 메타데이터 설정입니다.  
  
### Name  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 이 서비스의 고유한 이름입니다.  
  
### 네임스페이스  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 서비스의 네임스페이스입니다.  
  
### Opened  
 데이터 형식: datetime  
  
 액세스 형식: 읽기 전용  
  
 서비스가 열린 시간입니다.  
  
### OutgoingChannels  
 데이터 형식: Channel array  
  
 액세스 형식: 읽기 전용  
  
 서비스 인스턴스에서 보내는 채널입니다.  
  
### ProcessId  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 서비스를 호스팅하는 프로세스의 프로세스 ID입니다.  
  
## 요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|----------------------------------|  
|네임스페이스|root\\ServiceModel에 정의되어 있습니다.|