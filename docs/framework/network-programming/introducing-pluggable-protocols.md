---
title: "플러그형 프로토콜 소개 | Microsoft Docs"
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
  - "데이터 요청, 플러그형 프로토콜"
  - "WebRequest 클래스, 플러그형 프로토콜 "
  - "인터넷 요청에 응답, 플러그형 프로토콜"
  - "URI"
  - "Windows 소켓"
  - "요청/응답 모델"
  - "데이터 보내기, 플러그형 프로토콜"
  - "플러그형 프로토콜"
  - "WebClient 클래스, WebClient 클래스 정보"
  - "플러그형 프로토콜, 플러그형 프로토콜 정보"
  - "인터넷, 플러그형 프로토콜"
  - "경로 식별자"
  - "URI(Uniform Resource Identifier)"
  - "응용 프로그램 개발[.NET Framework], 플러그형 프로토콜"
  - "인터넷에서 데이터 요청, 플러그형 프로토콜"
  - "데이터 받기, 플러그형 프로토콜"
  - "프로토콜, 플러그형"
  - "서버 식별자"
  - "구성표 식별자"
ms.assetid: 4b48e22d-e4e5-48f0-be80-d549bda97415
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# 플러그형 프로토콜 소개
Microsoft.NET Framework 응용 프로그램에 빠르고 쉽게 통합할 수 있는 인터넷 서비스를 계층화 된 확장성과 관리 되는 구현을 제공 합니다.  인터넷 액세스 클래스에 <xref:System.Net> 및 <xref:System.Net.Sockets> 네임 스페이스를 사용 모두 웹 기반 및 인터넷 기반 응용 프로그램을 구현 합니다.  
  
## 인터넷 응용 프로그램  
 인터넷 응용 프로그램은 있습니다 수 분류 크게 두 가지로: 클라이언트의 정보 요청에 응답 하는 정보 및 서버 응용 프로그램을 요청 하는 클라이언트 응용 프로그램입니다.  기본 인터넷 클라이언트\-서버 응용 프로그램은 사용자 액세스 문서 및 전세계 웹 서버에 저장 된 다른 데이터 브라우저를 사용 하 여 World Wide Web입니다.  
  
 응용 프로그램은 이러한 역할 중 하나에 제한 되지 않습니다. 예를 들어, 친숙 한 중간 계층 응용 프로그램 서버는 요청을 클라이언트의 요청 데이터를 다른 서버에서 응답 경우이 서버와 클라이언트는 작동 합니다.  
  
 클라이언트 응용 프로그램은 요청 된 인터넷 리소스 및 요청과 응답에 사용할 통신 프로토콜을 식별 하 여 요청 합니다.  필요한 경우 클라이언트는 프록시 위치나 인증 정보 \(사용자 이름, 암호 및 등\)와 같이 요청을 완료 하는 데 필요한 추가 데이터도 제공 합니다.  요청은 구성 된 후 서버에 요청을 보낼 수 있습니다.  
  
## 리소스 식별  
 .NET Framework 일관 된 리소스 식별자 \(URI\)를 사용 하 여 요청 된 인터넷 리소스 및 통신 프로토콜을 식별 합니다.  URI의 적어도 3 및 4 조각 구성: 통신 프로토콜에 대 한 요청 및 응답; 식별 하는 체계 식별자 서버 식별자, 인터넷 서버를 고유 하 게 식별 하는 TCP 주소 또는 도메인 이름 시스템 \(DNS\) 호스트 이름으로 구성 됩니다. 경로 식별자는 서버에 요청한 정보를 찾습니다. 한 클라이언트에서 서버로 정보를 전달 하는 선택적 쿼리 문자열을 추가 합니다.  체계 식별자 "http", 경로 서버 식별자 "www.contoso.com"의 "http:\/\/www.contoso.com\/whatsnew.aspx?date\=today" URI 구성 예를 들어, "\/ whatsnew.aspx", 및 쿼리 문자열 "? 날짜 오늘 \=".  
  
 서버에서 요청 받고 응답을 처리 한 후 클라이언트 응용 프로그램에 대 한 응답을 반환 합니다.  응답 종류의 콘텐츠 \(예: 원시 텍스트 또는 XML 데이터\) 같은 추가 정보가 포함 됩니다.  
  
## 요청 및 응답에.NET Framework  
 .NET Framework 특정 클래스를 사용 하 여 요청\/응답 모델을 통해 인터넷 리소스에 액세스 하는 데 필요한 정보는 세 가지를 제공 합니다:의 <xref:System.Uri> 원하는 됩니다; 인터넷 리소스의 URI를 포함 하는 클래스 <xref:System.Net.WebRequest> ; 리소스에 대 한 요청을 포함 하는 클래스 및 <xref:System.Net.WebResponse> 컨테이너에 대 한 들어오는 응답을 제공 하는 클래스입니다.  
  
 클라이언트 응용 프로그램을 만드는 `WebRequest` 인스턴스는 네트워크 리소스의 URI를 전달 하는 <xref:System.Net.WebRequest.Create%2A> 메서드.  만든이 정적 메서드는 `WebRequest` HTTP와 같은 특정 프로토콜에 대 한.  `WebRequest` 가 반환 요청 서버와 요청이 있을 때 전송 되는 데이터 스트림에 액세스 모두를 제어 하는 속성에 액세스를 제공 합니다.  <xref:System.Net.WebRequest.GetResponse%2A> 메서드는 `WebRequest` 서버에서 URI를 식별 하는 클라이언트 응용 프로그램에서 요청을 보냅니다.  비동기적으로 사용 하 여 요청에 응답 수 있습니다 연기할 경우에 만들 수는 <xref:System.Net.WebRequest.BeginGetResponse%2A> 메서드는  **WebRequest**, 및 응답 시간 이후 using에 반환 될 수 있습니다는 <xref:System.Net.WebRequest.EndGetResponse%2A> 메서드.  
  
 **GetResponse**  및  **EndGetResponse** 메서드 반환에  **WebResponse** 서버에서 반환 된 데이터에 액세스를 제공 합니다.  이 데이터를 요청한 응용 프로그램에 스트림으로 제공 되므로 <xref:System.Net.WebResponse.GetResponseStream%2A> 메서드를 응용 프로그램 데이터 스트림을 사용 하는 모든 위치에서 사용할 수 있습니다.  
  
 **WebRequest** 및  **WebResponse** 클래스는 플러그형 프로토콜의 기본\-각 리소스를 사용 하는 프로토콜의 특정 세부 정보에 대 한 걱정 없이 인터넷 리소스를 사용 하는 응용 프로그램을 개발할 수 있도록 네트워크 서비스의 구현.  하위 클래스의  **WebRequest** 등록 되는  **WebRequest** 리소스를 인터넷에 실제 연결의 세부 정보를 관리 하는 클래스.  
  
 예를 들어,는 <xref:System.Net.HttpWebRequest> 클래스는 HTTP를 사용 하 여 인터넷 리소스에 연결 세부 사항을 관리 합니다.  기본적으로 때의  **WebRequest.Create** 메서드 시작 하는 URI를 발견 "http:" 또는 "https:" \(프로토콜 식별자 보안 HTTP 및 HTTP\)는  **WebRequest** 는 반환, 사용 하거나 하려면 형식 변환 될 수 있습니다  **HttpWebRequest** 프로토콜 관련 속성에 액세스 합니다.  대부분의 경우에  **WebRequest** 요청에 대해 필요한 모든 정보를 제공 합니다.  
  
 요청\/응답 트랜잭션을 사용할 수 있습니다으로 나타낼 수 있는 모든 프로토콜은  **WebRequest**.  프로토콜 관련 클래스를 파생 시키는  **WebRequest** 및  **WebResponse**  다음을 사용할 수 있도록 응용 프로그램에 정적으로 등록 하 고 <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=fullName> 메서드.  
  
 인터넷 요청에 대 한 클라이언트 권한 부여 해야 하는 경우는 <xref:System.Net.WebRequest.Credentials%2A> 속성에는  **WebRequest** 필요한 자격 증명을 제공 합니다.  이러한 자격 증명 기본 HTTP 또는 다이제스트 인증의 간단한 이름\/암호 쌍 이거나 NTLM 또는 Kerberos 인증의 이름\/암호\/도메인을 설정 합니다.  하나의 자격 증명 집합에 저장할 수 있는  [NetworkCredentials](frlrfsystemnetnetworkcredentialclasstopic) 인스턴스 또는 집합을 여러 개 저장할 수에 동시에 <xref:System.Net.CredentialCache> 인스턴스.  **CredentialCache** URI를 요청 하 고 서버에 보낼 수 있는 자격 증명을 확인 하는 서버에서 지 원하는 인증 구성표를 사용 합니다.  
  
## 간단한 WebClient 요청  
 인터넷 리소스의 간단한 요청을 해야 하는 응용 프로그램은 <xref:System.Net.WebClient> 클래스에 데이터를 업로드 하거나 인터넷 서버에서 데이터를 다운로드 하는 방법에 대 한 일반적인 방법을 제공 합니다.  **WebClient** 에 의존 하는  **WebRequest** 인터넷 리소스에 액세스를 제공 하는 클래스 따라서의  **WebClient** 클래스는 등록 된 플러그 가능한 프로토콜을 사용할 수 있습니다.  
  
 요청\/응답 모델을 사용할 수 없는 응용 프로그램 또는 네트워크에서 수신 대기 하 고 요청을 전송 해야 하는 응용 프로그램은  **System.Net.Sockets** 네임 스페이스를 제공의  [TCPClient](frlrfsystemnetsocketstcpclientclasstopic),  [TCPListener](frlrfsystemnetsocketstcplistenerclasstopic), 및  [UDPClient](frlrfsystemnetsocketsudpclientclasstopic) 클래스.  이러한 클래스는 서로 다른 전송 프로토콜을 사용하는 연결 정보를 처리하고 네트워크 연결을 응용 프로그램에 스트림으로 노출합니다.  
  
 Windows 소켓 인터페이스 또는 프로그래밍 소켓 수준에서 제공 되는 컨트롤을 해야 하는 사람들에 익숙한 개발자는 찾을 수 있는  **System.Net.Sockets** 클래스의 요구를 충족 합니다.  **System.Net.Sockets** 클래스에서 전환 점을 내의 네이티브 코드에서 관리 되는  **System.Net** 클래스입니다.  대부분의 경우  **System.Net.Sockets** 은 Windows 32 비트 하드웨어는 물론에 필요한 보안 검사를 처리 데이터 마샬링 클래스.  
  
## 참고 항목  
 [플러그형 프로토콜 프로그래밍](../../../docs/framework/network-programming/programming-pluggable-protocols.md)   
 [.NET Framework의 네트워크 프로그래밍](../../../docs/framework/network-programming/index.md)   
 [네트워크 프로그래밍 샘플](../../../docs/framework/network-programming/network-programming-samples.md)   
 [MSDN 코드 갤러리에서.net 네트워킹 샘플](http://code.msdn.microsoft.com/Wiki/View.aspx?ProjectName=nclsamples)