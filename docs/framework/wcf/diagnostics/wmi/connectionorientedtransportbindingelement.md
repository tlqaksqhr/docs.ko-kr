---
title: "ConnectionOrientedTransportBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c1308313-f0e2-49e6-977d-6b4ce9ad35d1
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# ConnectionOrientedTransportBindingElement
ConnectionOrientedTransportBindingElement  
  
## 구문  
  
```  
class ConnectionOrientedTransportBindingElement : TransportBindingElement  
{  
  datetime ChannelInitializationTimeout;  
  sint32 ConnectionBufferSize;  
  string HostNameComparisonMode;  
  sint32 MaxBufferSize;  
  datetime MaxOutputDelay;  
  sint32 MaxPendingAccepts;  
  sint32 MaxPendingConnections;  
  string TransferMode;  
};  
```  
  
## 메서드  
 ConnectionOrientedTransportBindingElement 클래스는 메서드를 정의하지 않습니다.  
  
## 속성  
 ConnectionOrientedTransportBindingElement 클래스에는 다음 속성이 있습니다.  
  
### ChannelInitializationTimeout  
 데이터 형식: datetime  
  
 액세스 형식: 읽기 전용  
  
 제한 시간이 초과되기 전에 채널 초기화가 완료되어야 하는 기간을 지정하는 timespan입니다.  
  
### ConnectionBufferSize  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 통신 중에 클라이언트나 서비스로부터 serialize된 메시지 청크를 전송할 때 사용되는 버퍼의 크기입니다.  
  
### HostNameComparisonMode  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 URI를 일치시킬 때 서비스에 연결하기 위해 호스트 이름이 사용되는지 여부를 나타내는 값입니다.  
  
### MaxBufferSize  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 사용할 버퍼의 최대 크기입니다.  
  
### MaxOutputDelay  
 데이터 형식: datetime  
  
 액세스 형식: 읽기 전용  
  
 메시지 청크 또는 전체 메시지를 보내기 전에 메모리에 버퍼링된 상태로 유지할 수 있는 최대 시간 간격입니다.  
  
### MaxPendingAccepts  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 서비스에서 들어오는 연결을 처리하는 데 사용할 수 있는 보류 중인 최대 비동기 수락 스레드 수입니다.  
  
### MaxPendingConnections  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 보류 중 연결의 최대 수입니다.  
  
### TransferMode  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 메시지가 연결 지향 전송을 사용하여 버퍼링되는지 아니면 스트리밍되는지를 지정하는 값입니다.  
  
## 요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|----------------------------------|  
|네임스페이스|root\\ServiceModel에 정의되어 있습니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>