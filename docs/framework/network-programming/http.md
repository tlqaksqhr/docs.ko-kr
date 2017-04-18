---
title: "HTTP | Microsoft Docs"
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
  - "프로토콜, HTTP"
  - "데이터 보내기, HTTP"
  - "HttpWebResponse 클래스, 데이터 보내기 및 받기"
  - "HTTP"
  - "데이터 받기, HTTP"
  - "응용 프로그램 프로토콜, HTTP"
  - "인터넷, HTTP"
  - "네트워크 리소스, HTTP"
  - "HTTP, HTTP 정보"
  - "HttpWebRequest 클래스, 데이터 보내기 및 받기"
ms.assetid: 985fe5d8-eb71-4024-b361-41fbdc1618d8
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# HTTP
대부분의 모든 인터넷 트래픽 사용 하는 HTTP 프로토콜에 대 한 포괄적인 지원을 제공 하는.NET Framework<xref:System.Net.HttpWebRequest> 및 <xref:System.Net.HttpWebResponse> 클래스입니다.  이러한 클래스에서 파생 <xref:System.Net.WebRequest> 및 <xref:System.Net.WebResponse>, 기본적으로 반환 되는 때마다 정적 메서드 <xref:System.Net.WebRequest.Create%2A?displayProperty=fullName> "http" 또는 "https"로 시작 하는 URI를 발견 합니다.  대부분의 경우에  **WebRequest** 및  **WebResponse** 클래스는 요청을 확인 하는 데 필요한 모든 제공 하지만 속성으로 노출 하는 HTTP 관련 기능에 액세스 해야 하는 경우 이러한 클래스를 형식 변환할 수 있습니다  **HttpWebRequest** 또는  **HttpWebResponse**.  
  
 **HttpWebRequest** 및  **HttpWebResponse** 표준 HTTP 요청\-응답 트랜잭션을 캡슐화 하 고 일반적인 HTTP 헤더에 액세스를 제공 합니다.  이러한 클래스는 또한 파이프라인, 송수신 데이터 청크, 인증, 사전 인증, 암호화, 프록시 지원, 서버 인증서 확인 및 연결 관리에 포함 하 여 대부분의 HTTP 1.1 기능을 지원 합니다.  사용자 지정 헤더 및 헤더 속성을 통해 제공 하지 저장 고를 통해 액세스할 수 있는  **헤더** 속성.  
  
 **HttpWebRequest** 가 사용 되는 기본 클래스입니다  **WebRequest** 및 URI에 전달할 수 있습니다 전에 등록 하지 않아도  **WebRequest.Create** 메서드.  
  
 설정 하 여 자동으로 HTTP 리디렉션에 따라 응용 프로그램을 만들 수 있는 <xref:System.Net.HttpWebRequest.AllowAutoRedirect%2A> 속성에  **true**  \(기본값\).  응용 프로그램 요청을 리디렉션합니다 및  [ResponseURI](frlrfsystemnethttpwebresponseclassresponseuritopic) 속성의  **HttpWebResponse** 요청에 응답 하는 실제 웹 리소스 포함 됩니다.  설정한 경우  **AllowAutoRedirect** 에  **거짓**, 응용 프로그램 리디렉션을 처리할 수 있어야 합니다. HTTP 프로토콜 오류로.  
  
 응용 프로그램 수신 HTTP 프로토콜 오류를 catch 하 여는 <xref:System.Net.WebException> 에 <xref:System.Net.WebException.Status%2A> 설정  [WebExceptionStatus.ProtocolError](frlrfsystemnetwebexceptionstatusclasstopic).  <xref:System.Net.WebException.Response%2A> 속성 포함의  **WebResponse** 서버에서 전송 하 고 발생 한 실제 HTTP 오류를 나타냅니다.  
  
## 참고 항목  
 [프록시를 통해 인터넷 액세스](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)   
 [응용 프로그램 프로토콜 사용](../../../docs/framework/network-programming/using-application-protocols.md)   
 [방법: HTTP 관련 속성에 액세스](../../../docs/framework/network-programming/how-to-access-http-specific-properties.md)