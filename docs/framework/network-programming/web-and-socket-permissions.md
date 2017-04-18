---
title: "웹 및 소켓 사용 권한 | Microsoft Docs"
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
  - "네트워킹"
  - "위치[.NET Framework], 수락"
  - "소켓, 사용 권한"
  - "네트워크, 사용 권한"
  - "인터넷, 사용 권한"
  - "네트워크 리소스"
  - "SocketPermission 클래스, SocketPermission 클래스 정보"
  - "위치[.NET Framework], 연결"
  - "WebPermission 클래스, WebPermission 클래스 정보"
  - "권한[.NET Framework], 소켓"
  - "보안[.NET Framework], 인터넷"
  - "위치[.NET Framework], 부여"
ms.assetid: d51ad8cb-03ae-4a51-bfcd-cfcf6b98afa9
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# 웹 및 소켓 사용 권한
인터넷 보안 응용 프로그램을 사용 하는 <xref:System.Net> 네임 스페이스에서 제공 되는 <xref:System.Net.WebPermission> 및 <xref:System.Net.SocketPermission> 클래스.  **WebPermission** 클래스는 응용 프로그램의 오른쪽에서 데이터를 요청 URI 나 URI를 인터넷에 사용할 수를 제어 합니다.  **SocketPermission** 응용 프로그램의 오른쪽에 사용 되는 컨트롤 클래스는 <xref:System.Net.Sockets.Socket> 로컬 포트에서 데이터를 수락 하거나 기반 호스트에서 다른 주소에서 전송 프로토콜을 사용 하 여 원격 장치에 연결할 포트 번호, 및 소켓 프로토콜 전송 합니다.  
  
 사용 하는 사용 권한 클래스를 응용 프로그램 형식에 따라 달라 집니다.  사용 하는 응용 프로그램 <xref:System.Net.WebRequest> 및 해당 하위 항목을 사용 해야는  **WebPermission** 사용 권한을 관리 하는 클래스입니다.  소켓 수준 액세스를 사용 하는 응용 프로그램을 사용 해야 하는  **SocketPermission** 클래스 사용 권한을 관리할 수 있습니다.  
  
 **WebPermission** 및  **SocketPermission** 두 권한의 정의: 수락 하 고 연결 합니다.  허용 응용 프로그램 응답 상대방에서 들어오는 연결에 권한을 부여 합니다.  연결할 응용 프로그램이 상대방에 대 한 연결을 시작할 수 있는 권한을 부여 합니다.  
  
 에 대 한  **SocketPermission** 인스턴스를 응용 프로그램 로컬 전송 주소;에서 들어오는 연결을 받아들일 수는 수단 적용 응용 프로그램은 일부 원격 \(또는 로컬\) 전송 주소에 연결할 수 있는 수단을 연결 합니다.  
  
 에 대 한  **WebPermission** 인스턴스를 응용 프로그램에 의해 제어 되는 URI을 내보낼 수 있습니다 수단 적용은  **WebPermission** 세계. 응용 프로그램 URI \(원격 또는 로컬 인지 여부\)에 액세스할 수 있도록 하는 수단을 연결 합니다.  
  
## 참고 항목  
 [보안](../../../docs/standard/security/index.md)   
 [네트워크 프로그래밍의 보안](../../../docs/framework/network-programming/security-in-network-programming.md)