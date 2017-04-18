---
title: "데이터 요청 | Microsoft Docs"
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
  - "데이터 보내기"
  - "WebRequest 클래스, 데이터 보내기 및 받기"
  - "인터넷에서 데이터 요청, 데이터 요청 정보"
  - "WebClient 클래스, 데이터 보내기 및 받기"
  - "네트워크, 데이터 요청"
  - "데이터 받기"
  - "데이터 보내기, 데이터 보내기 정보"
  - "인터넷 요청에 대한 응답, 인터넷 요청에 대한 응답 정보"
  - "데이터 요청"
  - "데이터 받기, 데이터 받기 정보"
  - "인터넷, 데이터 요청"
ms.assetid: df6f1e1d-6f2a-45dd-8141-4a85c3dafe1d
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# 데이터 요청
오늘날의 인터넷의 분산된 운영 환경에서 실행 되는 응용 프로그램을 개발 하면 효율적이 고 사용 하기 쉬운 메서드는 모든 형식의 리소스에서 데이터를 검색 하는 데 필요 합니다.  플러그형 프로토콜 여러 인터넷 프로토콜에서 데이터를 검색 하는 단일 인터페이스를 사용 하는 응용 프로그램을 개발할 수 있습니다.  
  
## 인터넷 서버에서 데이터를 다운로드 하 고 업로드  
 간단한 요청 및 응답 트랜잭션은 <xref:System.Net.WebClient> 클래스에 데이터를 업로드 하거나 인터넷 서버에서 데이터를 다운로드 하는 방법에 대 한 가장 쉬운 메서드를 제공 합니다.  **WebClient** 업로드와 다운로드 파일, 스트림, 송수신 및 데이터 버퍼를 서버에 전송 및 응답을 수신 메서드를 제공 합니다.  **WebClient** 사용 하는 <xref:System.Net.WebRequest> 및 <xref:System.Net.WebResponse> 플러그형 프로토콜 등록 되므로 실제 연결 된 인터넷 리소스 클래스를 사용할 수 있습니다.  
  
 더 복잡 한 트랜잭션을 요청 데이터를 사용 하 여 서버에서 확인 해야 하는 클라이언트 응용 프로그램은  **WebRequest** 클래스와 그 하위 항목.  **WebRequest** 서버에 연결, 요청을 보내고 응답의 세부 정보를 캡슐화 합니다.  **WebRequest** 플러그형 프로토콜을 사용 하는 모든 응용 프로그램에 사용할 수 있는 메서드와 속성의 집합을 정의 하는 추상 클래스입니다.  하위 항목의  **WebRequest**, 같은 <xref:System.Net.HttpWebRequest>, 속성 및 메서드 정의 구현  **WebRequest** 에 일치 하는 기본 프로토콜을 사용 하는 방법.  
  
 **WebRequest**  프로토콜 특정 인스턴스의 클래스를 만듭니다  **WebRequest** URI 값을 사용 하 여 하위 항목을 전달 하는 <xref:System.Net.WebRequest.Create%2A> 특정 파생 클래스 인스턴스를 만드는 방법은.  응용 프로그램을 지정 하는  **WebRequest** 하위 항목 하위 항목의 생성자에 등록 하 여 요청을 처리 하도록 사용 해야는 <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=fullName> 메서드.  
  
 인터넷 리소스를 호출 하 여 요청을 <xref:System.Net.WebRequest.GetResponse%2A> 메서드는  **WebRequest**.  **GetResponse** 메서드 구문을 속성에서 프로토콜 관련 요청을  **WebRequest**서버에 TCP 또는 UDP 소켓 연결을 설정 하 고 요청을 보냅니다.  같은 HTTP 서버로 데이터를 보내는 요청에 대 한  **Post** 또는 FTP  **배치** 요청은 <xref:System.Net.WebRequest.GetRequestStream%2A?displayProperty=fullName> 메서드에 데이터를 보낼 네트워크 스트림을 제공 합니다.  
  
 **GetResponse** 반환 프로토콜 관련  **WebResponse** 일치 하는  **WebRequest.**  
  
 **WebResponse** 클래스는 플러그형 프로토콜을 사용 하는 모든 응용 프로그램에 사용할 수 있는 메서드와 속성을 정의 하는 추상 클래스 이기도 합니다.  **WebResponse** 하위 이러한 기본 프로토콜에 대 한 메서드와 속성을 구현 합니다.  <xref:System.Net.HttpWebResponse> 예를 들어, 구현 클래스는  **WebResponse** 클래스에 대 한 HTTP.  
  
 서버에서 반환 된 데이터는 응용 프로그램에서 스트림 반환 제공 되는 <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=fullName> 메서드.  이 처럼 다른이 스트림에 다음 예제와 같이 사용할 수 있습니다.  
  
```csharp  
StreamReader sr =  
   new StreamReader(resp.GetResponseStream(), Encoding.ASCII);  
  
```  
  
```vb  
Dim sr As StreamReader  
sr = New StreamReader(resp.GetResponseStream(), Encoding.ASCII)  
```  
  
## 참고 항목  
 [.NET Framework의 네트워크 프로그래밍](../../../docs/framework/network-programming/index.md)   
 [방법: 웹 페이지 요청 및 결과를 스트림으로 검색](../../../docs/framework/network-programming/how-to-request-a-web-page-and-retrieve-the-results-as-a-stream.md)   
 [방법: WebRequest와 일치하는 프로토콜 관련 WebResponse 검색](../../../docs/framework/network-programming/how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest.md)