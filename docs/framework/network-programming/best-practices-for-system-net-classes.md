---
title: "System.Net 클래스에 대한 모범 사례 | Microsoft Docs"
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
  - "데이터 보내기, 모범 사례"
  - "인터넷에서 데이터 요청, 모범 사례"
  - "WebRequest 클래스, 모범 사례"
  - "데이터 요청, 모범 사례"
  - "WebResponse 클래스, 모범 사례"
  - "모범 사례, 데이터 요청"
  - "데이터 받기, 모범 사례"
ms.assetid: 716decc6-5952-47b7-9c5a-ba6fc5698684
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# System.Net 클래스에 대한 모범 사례
다음 권장 사항에 포함 된 클래스를 사용 하는 데 도움이 됩니다 <xref:System.Net> 최상의 이용 합니다.  
  
-   사용 <xref:System.Net.WebRequest> 및 <xref:System.Net.WebResponse> 하위 클래스 형식 캐스팅 하지 않고 가능 합니다.  사용 하는 응용 프로그램  **WebRequest** 및  **WebResponse** 새 인터넷 프로토콜의 광범위 한 코드 변경 없이 이용할 수 있습니다.  
  
-   사용 하는 서버에서 실행 되는 ASP.NET 응용 프로그램을 작성할 때의  **System.Net** 클래스,이 비동기 메서드를 사용 하는 성능 측면에서 향상, <xref:System.Net.WebRequest.GetResponse%2A> 및 <xref:System.Net.WebResponse.GetResponseStream%2A>.  
  
-   열 인터넷 리소스에 연결 된 네트워크 성능 및 처리량에 상당한 영향을 가질 수 있습니다.  **System.Net** 기본적으로 응용 프로그램 마다 호스트 마다 두 개의 연결을 사용 합니다.  설정 하는 <xref:System.Net.ServicePoint.ConnectionLimit%2A> 속성에는 <xref:System.Net.ServicePoint> 응용 프로그램은 특정 호스트에 대 한이 수를 늘릴 수 있습니다에 대 한.  설정 하는 <xref:System.Net.ServicePointManager.DefaultPersistentConnectionLimit?displayProperty=fullName> 속성이 모든 호스트에 대 한이 기본이 늘어날 수 있습니다.  
  
-   소켓 수준의 프로토콜을 작성할 때 사용 하려고  [TCPClient](frlrfsystemnetsocketstcpclientclasstopic) 또는  [UDPClient](frlrfsystemnetsocketsudpclientclasstopic) 가능 하면 직접 쓰는 대신에 <xref:System.Net.Sockets.Socket>.  이 두 클라이언트 클래스 연결 세부 사항을 처리할 필요 없이 TCP 및 UDP 소켓의 생성을 캡슐화 합니다.  
  
-   자격 증명을 요구 하는 사이트에 액세스할 때 사용 하는 <xref:System.Net.CredentialCache> 클래스를 제공 하 여 모든 요청에 대해 대신 자격 증명의 캐시를 만듭니다.  **CredentialCache** 클래스 검색 찾기 요청을 만들고 URL을 기반으로 하는 자격을 증명 하는 책임의 선도에 제공할 적절 한 자격 증명을 캐시 합니다.  
  
## 참고 항목  
 [.NET Framework의 네트워크 프로그래밍](../../../docs/framework/network-programming/index.md)