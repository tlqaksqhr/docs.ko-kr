---
title: "OneWayBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# OneWayBindingElement
OneWayBindingElement  
  
## 구문  
  
```  
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## 메서드  
 OneWayBindingElement 클래스는 메서드를 정의하지 않습니다.  
  
## 속성  
 OneWayBindingElement 클래스에는 다음과 같은 속성이 있습니다.  
  
### ChannelPoolSettings  
 데이터 형식: ChannelPoolSettings  
  
 액세스 형식: 읽기 전용  
  
 채널 풀 설정입니다.  
  
### MaxAcceptedChannels  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 허용되는 최대 채널 수입니다.  
  
### PacketRoutable  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 패킷을 라우팅할 수 있는지 여부를 나타내는 값입니다.  
  
## 요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|----------------------------------|  
|네임스페이스|root\\ServiceModel에 정의되어 있습니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>