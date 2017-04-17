---
title: "SSL(Secure Sockets Layer) 사용 | Microsoft Docs"
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
  - "SSL"
  - "SSL(Secure Sockets Layer)"
  - "인터넷에서 데이터 요청, SSL(Secure Sockets Layer)"
  - "데이터 보내기, SSL(Secure Sockets Layer)"
  - "네트워크 리소스"
  - "데이터 요청, SSL(Secure Sockets Layer)"
  - "데이터 받기, SSL(Secure Sockets Layer)"
  - "인터넷, SSL(Secure Sockets Layer)"
ms.assetid: 6e4289e6-d1b7-4e82-ab0d-e83e3b6063ed
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# SSL(Secure Sockets Layer) 사용
<xref:System.Net> 클래스 보안 소켓 계층 \(SSL\) 사용 하 여 여러 네트워크 프로토콜에 대 한 연결을 암호화 합니다.  
  
 Http 연결에 대 한의 <xref:System.Net.WebRequest> 및 <xref:System.Net.WebResponse> 클래스 SSL 사용 하 여 SSL을 지 원하는 웹 호스트와 통신할 수 있습니다.  SSL을 사용 하 여 결정 되는 <xref:System.Net.WebRequest> 클래스에는 지정 된 URI에 따라.  URI로 시작 하는 경우 "https:", SSL을 사용 합니다. URI로 시작 하는 경우 "http:", 암호화 되지 않은 연결에 사용 됩니다.  
  
 FTP \(파일 전송 프로토콜 사용\) SSL을 사용 하도록 설정 된 <xref:System.Net.FtpWebRequest.EnableSsl> 속성을 true로 호출 하기 전에 <xref:System.Net.FtpWebRequest.GetResponse>.  마찬가지로 단순 메일 전송 프로토콜 \(SMTP 사용\) SSL을 사용 하도록 설정 된 <xref:System.Net.Mail.SmtpClient.EnableSsl> 속성을 true로 전자 메일을 보내기 전에.  
  
 <xref:System.Net.Security.SslStream> 클래스 SSL에 대 한 스트림 기반 추상화를 제공 하 고 SSL 핸드셰이크를 구성할 수 있습니다.  
  
## 예제  
  
### 코드  
  
```vb  
Dim MyURI As String = "https://www.contoso.com/"  
Dim Wreq As WebRequest = WebRequest.Create(MyURI)  
  
Dim serverUri As String = "ftp://ftp.contoso.com/file.txt"  
Dim request As FtpWebRequest = CType(WebRequest.Create(serverUri), FtpWebRequest)  
request.Method = WebRequestMethods.Ftp.DeleteFile  
request.EnableSsl = True  
Dim response As FtpWebResponse = CType(request.GetResponse(), FtpWebResponse)  
```  
  
```csharp  
String MyURI = "https://www.contoso.com/";  
WebRequest WReq = WebRequest.Create(MyURI);  
  
String serverUri = "ftp://ftp.contoso.com/file.txt"  
FtpWebRequest request = (FtpWebRequest)WebRequest.Create(serverUri);  
request.EnableSsl = true;  
request.Method = WebRequestMethods.Ftp.DeleteFile;  
FtpWebResponse response = (FtpWebResponse)request.GetResponse();  
```  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   참조 하는  **System.Net** 네임 스페이스입니다.  
  
## 참고 항목  
 [네트워크 프로그래밍의 보안](../../../docs/framework/network-programming/security-in-network-programming.md)   
 [.NET Framework의 네트워크 프로그래밍](../../../docs/framework/network-programming/index.md)   
 [인증서 선택 및 유효성 검사](../../../docs/framework/network-programming/certificate-selection-and-validation.md)