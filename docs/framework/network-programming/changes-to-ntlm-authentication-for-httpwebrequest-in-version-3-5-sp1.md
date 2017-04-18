---
title: "버전 3.5 SP1에서 HttpWebRequest에 대한 NTLM 인증 변경 내용 | Microsoft Docs"
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
ms.assetid: 8bf0b428-5a21-4299-8d6e-bf8251fd978a
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# 버전 3.5 SP1에서 HttpWebRequest에 대한 NTLM 인증 변경 내용
보안 변경 사항을.NET Framework 버전 3.5 s p 1 적용 하 고 영향을 나중에 줄 어떻게 통합된 Windows 인증을 처리 하는 <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpListener>, <xref:System.Net.Security.NegotiateStream>, 및 System.Net 네임 스페이스의에서 클래스와 관련 된.  이러한 변경 내용에서 NTLM 기반 Windows 통합된 인증이 사용 되는 위치 웹 요청 및 응답을 수신 하려면 이러한 클래스를 사용 하는 응용 프로그램에 영향을 줍니다.  이 변경 웹 서버와 클라이언트 응용 프로그램 통합된 Windows 인증을 사용 하도록 구성 된 영향을 줄 수 있습니다.  
  
## 개요  
 Windows 통합된 인증에서는 일부 자격 증명 응답 범용 다시 사용 하거나 전달 될 수 있는 의미 수 있습니다.  다음이 특정 디자인 기능이 필요 없는 경우 특정 채널 정보 뿐만 아니라 특정 대상 정보 인증 프로토콜 수행 해야 합니다.  다음 서비스 자격 증명 응답 서비스 정보 등의 SPN \(서비스 사용자 이름\)를 포함할 수 있도록 확장된 보호를 제공할 수 있습니다.  자격 증명 교환에이 정보를 서비스 잘못 가져온 있습니다 자격 증명 응답의 악의적인 사용에 대해 더 잘 보호할 수 있습니다.  
  
 여러 구성 요소에는 <xref:System.Net> 및 <xref:System.Net.Security> 네임 스페이스는 호출 응용 프로그램 대신 Windows 통합된 인증을 수행 합니다.  System.Net 구성 요소를 사용 하는 Windows 통합된 인증에 확장 보호를 변경 내용을 설명 합니다.  
  
## 변경 내용  
 통합된 Windows 인증을 사용 하는 NTLM 인증 프로세스는 대상 컴퓨터에서 실행 및 클라이언트 컴퓨터로 보낸 챌린지 포함 됩니다.  컴퓨터 자체 생성 되는 과제를 받으면 연결 \(IPv4 주소인 127.0.0.1로 예\) 루프 백 연결이 없으면 인증이 실패 합니다.  
  
 내부 웹 서버에서 실행 되는 서비스에 액세스할 때 http:\/\/contoso\/service 또는 https:\/\/contoso\/service과 URL을 사용 하 여 서비스에 액세스 하는 것이 일반적입니다.  이름 "contoso"는 서비스를 배포 하는 데 사용 되는 컴퓨터의 컴퓨터 이름이 아닙니다.  <xref:System.Net> 및 관련된 네임 스페이스를 지 원하는 Active Directory, DNS, Netbios를 사용 하 여 로컬 컴퓨터의 호스트 파일 \(일반적으로 WINDOWS\\system32\\drivers\\etc\\hosts, 예를 들어\) 또는 로컬 컴퓨터의 lmhosts \(일반적으로 WINDOWS\\system32\\drivers\\etc\\lmhosts, 예를 들어\) 파일 이름으로 주소 확인 합니다.  적절 한 서버 컴퓨터에 "contoso"에 전송 요청 전송 되도록 "contoso" 라는 이름이 확인 됩니다.  
  
 대규모 배포를 구성할 때 내부 컴퓨터 이름의 최종 사용자, 클라이언트 응용 프로그램에서 사용 되지 않습니다 배포를 제공 하는 단일 가상 서버 이름을 일반적입니다.  예를 들어, 서버 www.contoso.com 부르지 "contoso"는 내부 네트워크에 사용 될 수 있습니다.  이 이름은 호스트 헤더가 클라이언트 웹 요청에 호출 됩니다.  HTTP 프로토콜에 의해 지정 된 대로 호스트 요청 헤더 필드는 요청 된 리소스의 인터넷 호스트와 포트 번호를 지정 합니다.  이 정보는 사용자 또는 참조 리소스 \(일반적으로 HTTP URL\)가 제공한 원래 URI를 가져옵니다.  .NET Framework 버전 4에서이 정보 또한 새로운 클라이언트에서 설정할 수 있습니다 <xref:System.Net.HttpWebRequest.Host%2A> 속성.  
  
 <xref:System.Net.AuthenticationManager> 클래스를 사용 하는 관리 되는 인증 구성 요소 \("모듈"\) 제어 <xref:System.Net.WebRequest> 파생 클래스 및 <xref:System.Net.WebClient> 클래스입니다.  <xref:System.Net.AuthenticationManager> 클래스를 노출 하는 속성을 제공 된 <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A?displayProperty=fullName> 동안 인증 하는 데 사용할 사용자 지정 SPN 문자열을 제공 하는 응용 프로그램에 대 한 URI 문자열 인덱스 개체를.  
  
 이제 버전 3.5 SP1이 <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A> 속성이 설정되어 있지 않으면 NTLM\(NT LAN Manager\) 인증 교환의 SPN에서 요청 URL에 사용되는 호스트 이름을 지정하는 것이 기본값입니다.  요청 URL에 사용되는 호스트 이름은 클라이언트 요청의 <xref:System.Net.HttpRequestHeader?displayProperty=fullName>에ㅐ\\ 지정된 호스트 헤더와 다를 수 있습니다.  요청 URL에 사용되는 호스트 이름은 서버의 실제 호스트 이름, 서버의 시스템 이름, 컴퓨터의 IP 주소 또는 루프백 주소와 다를 수 있습니다.  이러한 경우에는 Windows가 인증 요청을 실패합니다.  문제를 해결 하기 위해 우리가 호스트 이름을 사용 하는 Windows 알림 해야 요청 url의 클라이언트에서 로컬 컴퓨터의 다른 이름을 실제로 요청 \("contoso", 예를 들어\)입니다.  
  
 이 변경 하는 작업에 서버 응용 프로그램에 대 한 몇 가지 가능한 방법입니다.  권장 되는 방법을 요청 URL에 사용 되는 호스트 이름을 매핑하는 것은 `BackConnectionHostNames` 서버의 레지스트리 키.  `BackConnectionHostNames` 레지스트리 키입니다 일반적으로 루프백 주소에 호스트 이름을 매핑하는 데 사용 합니다.  단계는 다음과 같습니다.  
  
 루프백 주소에 매핑되며 웹 사이트를 로컬 컴퓨터에 연결할 수 있는 호스트 이름을 지정 하려면 다음과이 같이 하십시오.  
  
 1.  시작, 실행을 차례로 클릭하고 regedit를 입력한 다음, 확인을 클릭합니다.  
  
 2.  레지스트리 편집기에서 찾아 다음 다음 레지스트리 키를 누릅니다.  
  
 `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Lsa\MSV1_0`  
  
 3.  MSV1\_0 마우스 오른쪽 단추로 클릭 하 고 새로 만들기를 가리킨 다음 다중 문자열 값을 클릭 합니다.  
  
 4.  `BackConnectionHostNames`을 입력한 다음 Enter 키를 누릅니다.  
  
 5.  마우스 오른쪽 단추로 클릭 `BackConnectionHostNames`를 클릭 한 다음 수정을 클릭 합니다.  
  
 6.  값 데이터 상자에 호스트 이름 또는 호스트 이름에 대 한 다음 확인을 클릭 하 고 로컬 컴퓨터에 있는 사이트 \(요청 URL에 사용 되는 호스트 이름\)을 입력 합니다.  
  
 7.  레지스트리 편집기를 종료 다음 IISAdmin 서비스를 다시 시작 하 고 Iisreset을 실행.  
  
 덜 안전한 해결 루프 백 확인 안 함에 설명 된 대로입니다 [http:\/\/support.microsoft.com\/kb\/896861](http://go.microsoft.com/fwlink/?LinkID=179657).  이 반사 공격 으로부터 보호를 사용 하지 않습니다.  따라서 시간만 컴퓨터를 실제로 사용 하려면 원하는 대체 이름 집합을 제한 하는 것이 좋습니다.  
  
## 참고 항목  
 <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A?displayProperty=fullName>   
 <xref:System.Net.HttpRequestHeader?displayProperty=fullName>   
 <xref:System.Net.HttpWebRequest.Host%2A?displayProperty=fullName>