---
title: "TransportBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# TransportBindingElement
TransportBindingElement  
  
## 구문  
  
```  
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## 메서드  
 TransportBindingElement 클래스는 메서드를 정의하지 않습니다.  
  
## 속성  
 TransportBindingElement 클래스에는 다음과 같은 속성이 있습니다.  
  
### ManualAddressing  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 사용자가 메시지 주소 지정을 제어하는지 여부를 지정하는 부울 값입니다.  
  
### MaxBufferPoolSize  
 데이터 형식: sint64  
  
 액세스 형식: 읽기 전용  
  
 바인딩에 대한 최대 버퍼 풀 크기입니다.  
  
### MaxReceivedMessageSize  
 데이터 형식: sint64  
  
 액세스 형식: 읽기 전용  
  
 이 바인딩에서 처리하는 메시지의 최대 크기입니다.  
  
### Scheme  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 전송을 위한 URI 스키마입니다.  
  
## 요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|----------------------------------|  
|네임스페이스|root\\ServiceModel에 정의되어 있습니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Channels.TransportBindingElement>