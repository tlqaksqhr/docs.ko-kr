---
title: "MsmqTransportBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# MsmqTransportBindingElement
MsmqTransportBindingElement  
  
## 구문  
  
```  
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## 메서드  
 MsmqTransportBindingElement 클래스는 메서드를 정의하지 않습니다.  
  
## 속성  
 MsmqTransportBindingElement 클래스에는 다음과 같은 속성이 있습니다.  
  
### MaxPoolSize  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 내부 MSMQ 메시지 개체가 포함된 풀의 최대 크기입니다.  
  
### QueueTransferProtocol  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 이 바인딩에서 사용하는 대기 중인 통신 채널 전송을 나타내는 열거형 값입니다.  
  
### UseActiveDirectory  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 Active Directory를 사용하여 큐 주소를 변환해야 하는지 여부를 나타내는 부울 값을 반환합니다.  
  
## 요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|----------------------------------|  
|네임스페이스|root\\ServiceModel에 정의되어 있습니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>