---
title: "소켓 | Microsoft Docs"
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
  - "데이터 보내기, 소켓"
  - "데이터 요청, 소켓"
  - "Windows 소켓"
  - "소켓, 소켓 정보"
  - "Socket 클래스, Socket 클래스 정보"
  - "소켓"
  - "인터넷에서 데이터 요청, 소켓"
  - "네트워크, 소켓"
  - "데이터 받기, 소켓"
  - "프로토콜, 소켓"
  - "인터넷, 소켓"
ms.assetid: 10d22735-bd37-42c1-a2be-c1932f979a7d
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# 소켓
<xref:System.Net.Sockets> 네임 스페이스는 관리 되는 Windows 소켓 인터페이스 구현을 포함 합니다.  모든 다른 네트워크 액세스 클래스에 <xref:System.Net> 네임 스페이스는이 소켓 구현 위에서 만들어집니다.  
  
 .NET Framework <xref:System.Net.Sockets.Socket> 클래스 Winsock32 API에서 제공 하는 소켓 서비스 버전 관리 되는 코드입니다.  대부분의 경우에  **소켓** 메서드는 단순히 클래스 데이터에 해당 하는 네이티브 Win32 이미지를 마샬링하고 필요한 보안 검사를 처리 합니다.  
  
 **소켓** 클래스는 동기 및 비동기 두 가지 기본 모드를 지원 합니다.  동기 모드에서 네트워크 작업을 수행 하는 함수를 호출 \(예: <xref:System.Net.Sockets.Socket.Send%2A> 및 <xref:System.Net.Sockets.Socket.Receive%2A>\) 호출 프로그램에 제어를 반환 하기 전에 작업이 완료 될 때까지 기다립니다.  비동기 모드에서는 이러한 호출은 즉시 반환 됩니다.  
  
## 참고 항목  
 [방법: 소켓 만들기](../../../docs/framework/network-programming/how-to-create-a-socket.md)   
 [TCP\/UDP](../../../docs/framework/network-programming/tcp-udp.md)   
 [응용 프로그램 프로토콜 사용](../../../docs/framework/network-programming/using-application-protocols.md)