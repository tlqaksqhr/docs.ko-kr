---
title: "방법: 소켓 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "응용 프로그램 프로토콜, 소켓"
  - "네트워킹"
  - "데이터 보내기, 소켓"
  - "데이터 요청, 소켓"
  - "인터넷에서 데이터 요청, 소켓"
  - "소켓 클래스, 소켓 만들기"
  - "네트워크 리소스"
  - "데이터 받기, 소켓"
  - "프로토콜, 소켓"
  - "인터넷, 소켓"
  - "소켓, 만들기"
ms.assetid: c64a049c-5981-43bc-a2dc-1851473589c7
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# 방법: 소켓 만들기
소켓 프로토콜 및 네트워크 주소 정보를 원격 장치와 통신 하는 소켓을 사용 하기 전에 초기화 해야 합니다.  생성자는 <xref:System.Net.Sockets.Socket> 주소 패밀리, 소켓 종류 및 소켓 연결을 사용 하는 프로토콜 종류를 지정 하는 매개 변수 클래스에 있습니다.  
  
## 예제  
 다음 예제에서는 인터넷과 같은 IP 기반 네트워크에서 통신 하는 데 사용할 수 있는 소켓을 만듭니다.  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,   
   SocketType.Stream, ProtocolType.Tcp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Stream, ProtocolType.Tcp)  
  
```  
  
 TCP 대신 UDP를 사용 하려면 다음 예제와 같이 프로토콜 종류를 변경 합니다.  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,   
   SocketType.Dgram, ProtocolType.Udp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Dgram, ProtocolType.Udp)  
  
```  
  
 <xref:System.Net.Sockets.AddressFamily> 열거형을 사용 하는 표준 주소 패밀리 지정의  **소켓** 클래스 네트워크 주소를 확인 하려면 \(예를 들어,는  **AddressFamily.InterNetwork** 구성원 IP 버전 4 주소 패밀리를 지정\).  
  
 <xref:System.Net.Sockets.SocketType> 열거형 소켓의 종류를 지정 합니다 \(예를 들어,는  **SocketType.Stream** 구성원 흐름 제어를 사용 하 여 데이터를 송수신 하는 표준 소켓 나타냅니다\).  
  
 <xref:System.Net.Sockets.ProtocolType> 열거형에서 통신할 때 사용할 네트워크 프로토콜을 지정 된  **소켓** \(예를 들어,  **ProtocolType.Tcp** 나타냅니다; TCP 소켓을 사용 하도록  **ProtocolType.Udp** UDP 소켓을 사용 하도록 나타냅니다\).  
  
 후에  **소켓** 입니다 만든이 원격 끝점에 연결을 시작 하거나 원격 장치에서 연결을 수신 합니다.  
  
## 참고 항목  
 [클라이언트 소켓 사용](../../../docs/framework/network-programming/using-client-sockets.md)   
 [소켓으로 수신](../../../docs/framework/network-programming/listening-with-sockets.md)