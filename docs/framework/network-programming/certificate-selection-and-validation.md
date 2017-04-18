---
title: "인증서 선택 및 유효성 검사 | Microsoft Docs"
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
ms.assetid: c933aca2-4cd0-4ff1-9df9-267143f25a6f
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# 인증서 선택 및 유효성 검사
<xref:System.Net> 선택 하 고 유효성을 검사 하는 여러 가지 방법으로 클래스를 지 원하는 <xref:System.Security.Cryptography.X509Certificates> 보안 소켓 계층 \(SSL\) 연결에 대 한.  클라이언트가 서버에 자신을 인증 하는 하나 이상의 인증서를 선택할 수 있습니다.  서버는 클라이언트 인증서 인증에 대 한 하나 이상의 특정 특성이 있는지 필요할 수 있습니다.  
  
## 정의  
 인증서는 공개 키, 특성 \(예: 버전 번호, 일련 번호 및 만료 날짜\) 및 인증 기관의 디지털 서명을 포함 하는 ASCII 바이트 스트림입니다.  인증서는 암호화 된 연결을 설정할 수 또는 클라이언트에서 서버로 인증할 수 사용 됩니다.  
  
## 클라이언트 인증서 선택 및 유효성 검사  
 클라이언트는 특정 SSL 연결에 대 한 하나 이상의 인증서를 선택할 수 있습니다.  클라이언트 인증서는 SSL 연결을 웹 서버 또는 SMTP 메일 서버에 연결 될 수 있습니다.  클라이언트 인증서의 컬렉션에 추가 <xref:System.Security.Cryptography.X509Certificates.X509Certificate> 또는 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> 개체 클래스입니다.  예를 들어 전자 메일을 사용 하 여 인증서 컬렉션의 인스턴스 수는 <xref:System.Security.Cryptography.X509Certificates.X509CertificateCollection>\) 연결의 <xref:System.Net.Mail.SmtpClient.ClientCertificates%2A> 속성의는 <xref:System.Net.Mail.SmtpClient> 클래스.  <xref:System.Net.HttpWebRequest> 클래스에는 유사한 <xref:System.Net.HttpWebRequest.ClientCertificates%2A> 속성.  
  
 사이의 주요 차이점은 <xref:System.Security.Cryptography.X509Certificates.X509Certificate> 및 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> 클래스에는 개인 키에 대 한 인증서 저장소에 있어야는 <xref:System.Security.Cryptography.X509Certificates.X509Certificate> 클래스.  
  
 인증서 컬렉션에 추가 되 고 특정 SSL 연결과 관련 된 경우에 서버에서 요청 하지 않으면 인증서 서버에 보내집니다.  클라이언트 인증서를 여러 연결을 설정 하면 최고의 하나 사용 고려 서버 및 클라이언트 인증서 발급자 이름을 제공한 인증서 발급자 목록에 일치 하는 알고리즘에 기반 합니다.  
  
 <xref:System.Net.Security.SslStream> 클래스 SSL 핸드셰이크를 통해 더 많은 컨트롤을 제공 합니다.  클라이언트가 사용할 클라이언트 인증서를 선택 하는 대리자를 지정할 수 있습니다.  
  
 원격 서버에 클라이언트 인증서가 잘못 되었으므로 해당 인증 기관에서 서명한 지 확인할 수 있습니다.  대리자에 추가할 수는 <xref:System.Net.ServicePointManager.ServerCertificateValidationCallback%2A> 인증서 유효성 검사를 적용 합니다.  
  
## 클라이언트 인증서 선택  
 .NET Framework 서버에 다음과 같은 방식으로 제공 하는 클라이언트 인증서를 선택 합니다.  
  
1.  이전에 서버에 클라이언트 인증서가 제시 된 경우 인증서를 먼저 제시 하 고 후속 클라이언트 인증서 요청에 대해 다시 사용 될 때 캐시 됩니다.  
  
2.  대리자가 있을 경우 항상 대리자에서 결과를 클라이언트 인증서로 선택 하십시오.  가능 하면 캐시 된 인증서를 사용 하려고 하지만 인증서 컬렉션 비어 있지 않은 경우 대리자는 null을 반환 했습니다 익명 자격 증명 캐시를 사용 하지 마십시오.  
  
3.  클라이언트 인증서에 대 한 첫 번째 도전 경우 프레임 워크에서 인증서 열거 <xref:System.Security.Cryptography.X509Certificates.X509Certificate> 또는 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> 클래스 개체를 찾고 일치 하는 서버 및 클라이언트 인증서 발급자 이름을 제공한 인증서 발급자 목록에 대 한 연결을 연결 합니다.  일치 하는 첫 번째 인증서를 서버에 전송 됩니다.  일치 하는 인증서 또는 인증서 컬렉션이 비어 있는 경우는 익명 자격 증명을 서버에 보내집니다.  
  
## 도구에 대 한 인증서 구성  
 여러 가지 도구에 대 한 클라이언트 및 서버 인증서 구성을 사용할 수 있습니다.  
  
 *Winhttpcertcfg.exe* 도구를 사용 하려면 클라이언트 인증서를 구성 합니다.  *Winhttpcertcfg.exe* 도구와 Windows Server 2003 Resource Kit 도구 중 하나로 제공 됩니다.  이 도구는 Windows Server 2003 리소스 키트 도구에 www.microsoft.com의 일부로 다운로드할 사용할 수도 있습니다.  
  
 *Httpcfg.exe는* 도구를 사용에 대 한 서버 인증서를 구성 하는 <xref:System.Net.HttpListener> 클래스입니다.  *HttpCfg.exe* 도구 제공 된 지원 도구 중 하나로 Windows Server 2003 및 Windows XP 서비스 팩 2에 대 한.  *HttpCfg.exe* 및 지원 도구는 Windows Server 2003 또는 Windows XP에서 기본적으로 설치 되지 않습니다.  Windows Server 2003.  지원 도구는 다음 폴더 및 파일에는 Windows Server 2003 CD\-ROM에서 별도로 설치 됩니다.  
  
 \\Support\\Tools\\Suptools.msi  
  
 Windows XP 서비스 팩 2 사용에 대 한 Windows XP 지원 도구는 www.microsoft.com에서 다운로드할 사용할 수 있습니다.  
  
 소스 코드의 버전은  *HttpCfg.exe* 도구도 Windows Server SDK에는 샘플으로 제공 됩니다.  소스 코드는  *HttpCfg.exe* 샘플 설치 네트워킹 샘플에 기본적으로 다음 폴더에서 Windows SDK의 일부로.  
  
 *C:\\Program 상자 SDKs\\Windows\\v1.0\\Samples\\NetDS\\http\\serviceconfig*  
  
 이러한 도구 외에 <xref:System.Security.Cryptography.X509Certificates.X509Certificate> 및 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> 클래스는 파일 시스템에서 인증서를 로드 하는 메서드를 제공 합니다.  
  
## 참고 항목  
 [네트워크 프로그래밍의 보안](../../../docs/framework/network-programming/security-in-network-programming.md)   
 [.NET Framework의 네트워크 프로그래밍](../../../docs/framework/network-programming/index.md)