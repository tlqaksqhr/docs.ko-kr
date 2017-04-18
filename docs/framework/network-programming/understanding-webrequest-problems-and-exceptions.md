---
title: "WebRequest 문제 및 예외 이해 | Microsoft Docs"
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
ms.assetid: 74a361a5-e912-42d3-8f2e-8e9a96880a2b
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# WebRequest 문제 및 예외 이해
<xref:System.Net.WebRequest>와 해당 파생된 클래스 \(<xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, 및 <xref:System.Net.FileWebRequest>\)은 비정상 상태를 알리는 데 예외를 throw 합니다.  때때로 이러한 문제는 분명 하지 않습니다.  
  
## 솔루션  
 검사는 <xref:System.Net.WebException.Status%2A> 속성의의 <xref:System.Net.WebException> 문제를 확인 합니다.  다음 표에서 몇 가지 상태 값 및 가능한 몇 가지 해결책을 보여 줍니다.  
  
|상태|설명|해결책|  
|--------|--------|---------|  
|<xref:System.Net.WebExceptionStatus><br /><br /> 또는<br /><br /> <xref:System.Net.WebExceptionStatus>|기본 소켓에 문제가 있습니다.  연결이 재설정 되었습니다.|다시 연결 하 고 요청을 다시 받도록 합니다.<br /><br /> 최신 서비스 팩이 설치 되어 있는지 확인 합니다.<br /><br /> 값은 <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A?displayProperty=fullName> 속성.<br /><br /> <xref:System.Net.HttpWebRequest.KeepAlive%2A?displayProperty=fullName>을 `false`로 설정합니다.<br /><br /> 최대 연결 수가 증가 된 <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> 속성.<br /><br /> 프록시 구성을 확인 하십시오.<br /><br /> SSL을 사용 하는 경우 서버 프로세스에 인증서 저장소에 액세스할 수 있는 권한이 있는지 확인 하십시오.<br /><br /> 많은 양의 데이터를 전송 하는 경우 설정 <xref:System.Net.HttpWebRequest.AllowWriteStreamBuffering%2A> 에 `false`.|  
|<xref:System.Net.WebExceptionStatus>|서버 인증서를 확인할 수 없습니다.|Internet Explorer 사용 하 여 URI를 열려고 합니다.  IE에서 표시 되는 보안 경고를 해결 합니다.  보안 경고를 해결할 수 없는 경우 구현 하는 인증서 정책 클래스를 만들 수 있습니다 <xref:System.Net.ICertificatePolicy> 반환 `true`를 전달 하 고 <xref:System.Net.ServicePointManager.CertificatePolicy%2A>.<br /><br /> 참조 [http:\/\/support.microsoft.com\/?id\=823177](http://go.microsoft.com/fwlink/?LinkID=179653).<br /><br /> 인증 기관이 서명한 서버 인증서의 인증서를 신뢰할 수 있는 인증 기관 목록에 Internet Explorer 추가 되는지 확인 합니다.<br /><br /> URL의 호스트 이름이 서버 인증서의 일반 이름이 일치 하는지 확인 합니다.|  
|<xref:System.Net.WebExceptionStatus>|SSL 트랜잭션에 오류가 발생 했거나 인증서 문제.|.NET Framework 버전 1.1만 SSL 버전 3.0 지원합니다.  서버가 TLS 버전 1.0 또는 버전 2.0 SSL만 사용 하는 경우 예외가 throw 됩니다.  .NET Framework 버전 2.0으로 업그레이드 하 고 설정 <xref:System.Net.ServicePointManager.SecurityProtocol%2A> 는 서버와 일치 하도록 합니다.<br /><br /> 클라이언트 인증서는 인증 기관 \(CA\) 서버를 신뢰 하지 않는 서명 된.  CA의 인증서를 서버에 설치 합니다.  참조 [http:\/\/support.microsoft.com\/?id\=332077](http://go.microsoft.com/fwlink/?LinkID=179654).<br /><br /> 최신 서비스 팩이 설치 되어 있는지 확인 합니다.|  
|<xref:System.Net.WebExceptionStatus>|연결하지 못했습니다.|방화벽 또는 프록시 연결을 차단 합니다.  방화벽 또는 프록시 연결을 허용 하도록 수정 합니다.<br /><br /> 명시적으로 지정은 <xref:System.Net.WebProxy> 를 호출 하 여 클라이언트 응용 프로그램에는 <xref:System.Net.WebProxy> 생성자 \(WebServiceProxyClass.Proxy \= 새 WebProxy \([http:\/\/server:80](http://server/), 참\)\).<br /><br /> Filemon 이나 Regmon 작업자 프로세스 id WSPWSP.dll, HKLM\\System\\CurrentControlSet\\Services\\DnsCache 또는 hklm\\system\\currentcontrolset\\services\\winsock2에 액세스할 수 있는 권한이 있는지 확인 하려면 실행 합니다.|  
|<xref:System.Net.WebExceptionStatus>|도메인 이름 서비스가 호스트 이름을 확인할 수 없습니다.|프록시를 올바르게 구성 합니다.  참조 [http:\/\/support.microsoft.com\/?id\=318140](http://go.microsoft.com/fwlink/?LinkID=179655).<br /><br /> 모든 바이러스 백신 소프트웨어를 설치 하거나 방화벽 연결을 차단 하지 않습니다 확인 합니다.|  
|<xref:System.Net.WebExceptionStatus>|<xref:System.Net.WebRequest.Abort%2A>호출, 또는 오류가 발생 했습니다.|클라이언트 또는 서버의 로드가이 문제의 원인이 될 수 있습니다.  부하를 줄이십시오.<br /><br /> 증가 된 <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> 설정 합니다.<br /><br /> 참조 [http:\/\/support.microsoft.com\/?id\=821268](http://go.microsoft.com/fwlink/?LinkID=179656) 웹 서비스 성능 설정을 수정할 수 있습니다.|  
|<xref:System.Net.WebExceptionStatus>|응용 프로그램이 이미 닫힌 소켓에 쓰려고 했습니다.|클라이언트 또는 서버가 오버 로드 됩니다.  부하를 줄이십시오.<br /><br /> 증가 된 <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> 설정 합니다.<br /><br /> 참조 [http:\/\/support.microsoft.com\/?id\=821268](http://go.microsoft.com/fwlink/?LinkID=179656) 웹 서비스 성능 설정을 수정할 수 있습니다.|  
|<xref:System.Net.WebExceptionStatus>|제한 집합 \(<xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>\) 메시지의 길이 초과 했습니다.|값은 <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A> 속성.|  
|<xref:System.Net.WebExceptionStatus>|도메인 이름 서비스가 프록시 호스트 이름을 확인할 수 없습니다.|프록시를 올바르게 구성 합니다.  참조 [http:\/\/support.microsoft.com\/?id\=318140](http://go.microsoft.com/fwlink/?LinkID=179655).<br /><br /> 힘 <xref:System.Net.HttpWebRequest> 없음 프록시 설정 하 여 사용 하는 <xref:System.Net.HttpWebRequest.Proxy%2A> 속성을 `null`.|  
|<xref:System.Net.WebExceptionStatus>|서버 응답이 유효한 HTTP 응답이 아닙니다.  서버 응답이 HTTP 1.1 RFC와 맞지 않는.NET Framework 감지 하면이 문제가 발생 합니다.  응답이 잘못 된 헤더 또는 잘못 된 헤더 구분 기호가 포함 된 경우이 문제가 발생할 수 있습니다.RFC 2616 HTTP 1.1 서버 로부터 응답에 대 한 유효한 형식을 정의합니다.  자세한 내용은 [http:\/\/www.ietf.org](http://go.microsoft.com/fwlink/?LinkID=147388).|트랜잭션의 네트워크 추적을 가져와서 응답에서의 헤더를 검사.<br /><br /> 서버가 응답 하지 않고 응용 프로그램에 필요한 경우 \(이 발생할 수 있는 보안 문제가\) 구문 분석, 세트 `useUnsafeHeaderParsing` 에 `true` 구성 파일에서.  자세한 내용은 [\<httpWebRequest\> 요소\(네트워크 설정\)](../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md)를 참조하십시오.|  
  
## 참고 항목  
 <xref:System.Net.HttpWebRequest>   
 <xref:System.Net.HttpWebResponse>   
 <xref:System.Net.Dns>