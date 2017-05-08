---
title: "TCP/UDP | Microsoft Docs"
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
  - "프로토콜, TCP/UDP"
  - "네트워크 리소스, TCP/UDP"
  - "데이터 보내기, TCP/UDP"
  - "TCP/UDP"
  - "TcpClient 클래스, TcpClient 클래스 정보"
  - "응용 프로그램 프로토콜, TCP/UDP"
  - "데이터 받기, TCP/UDP"
  - "TcpListener 클래스, TcpListener 클래스 정보"
  - "Socket 클래스, Socket 클래스 정보"
  - "UDP"
  - "데이터 요청, TCP/UDP"
  - "인터넷에서 데이터 요청, TCP/UDP"
  - "인터넷, TCP/UDP"
ms.assetid: df29b4b0-49e8-4923-82b9-13150dfc40f5
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# TCP/UDP
응용 프로그램이 전송 제어 프로토콜 \(TCP\) 및 사용자 데이터 그램 프로토콜 \(UDP\) 서비스를 사용할 수 있는 <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener>, 및 <xref:System.Net.Sockets.UdpClient> 클래스.  이러한 프로토콜 클래스의 맨 위에 빌드된는 <xref:System.Net.Sockets.Socket?displayProperty=fullName> 클래스 및 데이터 전송의 세부 사항을 주의 해야 합니다.  
  
 프로토콜 클래스의 동기 메서드를 사용 하는  **소켓** 네트워크 서비스 상태 정보를 유지 관리 또는 위로 프로토콜 관련 소켓 설정의 세부 정보를 파악 하는 오버 헤드 없이 간단 하 고 편리한 액세스를 제공 하는 클래스입니다.  비동기 사용  **소켓** 메서드를 제공 하는 비동기 메서드를 사용할 수 있는 <xref:System.Net.Sockets.NetworkStream> 클래스.  액세스 기능을 하는  **소켓** 프로토콜 클래스가 노출 하지 클래스 사용 해야는  **소켓** 클래스.  
  
 **TcpClient** 및  **TcpListener** 사용 하 여 네트워크를 나타내는  **NetworkStream** 클래스입니다.  사용 하는 <xref:System.Net.Sockets.TcpClient.GetStream%2A> 네트워크 스트림을 반환 하 고 스트림의 호출 하는 메서드 <xref:System.Net.Sockets.NetworkStream.Read%2A> 및 <xref:System.Net.Sockets.NetworkStream.Write%2A> 메서드.  **NetworkStream** 닫으면 소켓에 영향을 주지 않도록 내부 소켓 프로토콜 클래스를 소유 하지 않습니다.  
  
 **UdpClient** 클래스 바이트 배열을 사용 하 여 UDP 데이터 그램을 저장할 수 있습니다.  사용은 <xref:System.Net.Sockets.UdpClient.Send%2A> 네트워크에 데이터를 보낼 수 있는 메서드 및 <xref:System.Net.Sockets.UdpClient.Receive%2A> 메서드는 들어오는 데이터 그램을 받을 수.  
  
## 참고 항목  
 [TCP 서비스 사용](../../../docs/framework/network-programming/using-tcp-services.md)   
 [UDP 서비스 사용](../../../docs/framework/network-programming/using-udp-services.md)   
 [네트워크에서 스트림 사용](../../../docs/framework/network-programming/using-streams-on-the-network.md)   
 [비동기 서버 소켓 사용](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)   
 [비동기 클라이언트 소켓 사용](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)   
 [응용 프로그램 프로토콜 사용](../../../docs/framework/network-programming/using-application-protocols.md)