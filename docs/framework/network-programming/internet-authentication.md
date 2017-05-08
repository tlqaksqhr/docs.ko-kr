---
title: "인터넷 인증 | Microsoft Docs"
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
  - "인증[.NET Framework], 클래스"
  - "IAuthenticationModule 인터페이스"
  - "ICredentialLookup 인터페이스"
  - "CredentialCache 클래스, CredentialCache 클래스 정보"
  - "데이터 받기, 인증"
  - "AuthenticationManager 클래스, AuthenticationManager 클래스 정보"
  - "인터넷, 인증"
  - "데이터 보내기, 인증"
  - "네트워크 리소스, 인증"
  - "사용자 인증, 인증을 위한 클래스"
  - "NetworkCredential 클래스, NetworkCredential 클래스 정보"
  - "클라이언트 인증, 인증을 위한 클래스"
ms.assetid: d342e87c-f672-4660-a513-41a2f2b80c4a
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# 인터넷 인증
<xref:System.Net> 클래스는 다양 한 클라이언트 인증 메커니즘을 기본 표준 인터넷 인증 메서드를 포함 하 여 지원, 다이제스트, 협상, NTLM 및 Kerberos 인증으로 만들 수 있는 사용자 지정 방법.  
  
 인증 자격 증명에 저장 된의 <xref:System.Net.NetworkCredential> 및 <xref:System.Net.CredentialCache> 는 구현 클래스는 <xref:System.Net.ICredentials> 인터페이스.  이러한 클래스 중 하나의 자격 증명을 쿼리할 때 인스턴스의 반환 된  **NetworkCredential** 클래스입니다.  인증 프로세스에서 관리 되는 <xref:System.Net.AuthenticationManager> 클래스 및 실제 인증 프로세스를 구현 하는 인증 모듈 클래스에서 수행의 <xref:System.Net.IAuthenticationModule> 인터페이스.  사용자 지정 인증 모듈을 등록 해야는  **AuthenticationManager** 를 사용 하기 전에. 모듈에 대 한 기본, 다이제스트, 협상, NTLM 및 Kerberos 인증 방법을 기본적으로 등록 된.  
  
 **NetworkCredential** URI로 식별 되는 단일 인터넷 리소스와 관련 된 자격 증명의 집합을 저장 하 고 모든 호출에 응답에서 하 여 반환 된 <xref:System.Net.NetworkCredential.GetCredential%2A> 메서드.  **NetworkCredential** 클래스는 제한 된 수의 인터넷 리소스에 액세스 하는 응용 프로그램 또는 모든 경우에 동일한 자격 증명 집합을 사용 하는 응용 프로그램에서 일반적으로 사용 합니다.  
  
 **CredentialCache** 클래스는 다양 한 웹 리소스에 대 한 자격 증명의 컬렉션에 저장 합니다.  경우는 <xref:System.Net.CredentialCache.GetCredential%2A> 메서드가 호출  **CredentialCache** 요청한 인증 구성표 및 웹 리소스의 URI가 결정 되는 적절 한 자격 증명 집합을 반환 합니다.  다른 인증 체계와 다양 한 인터넷 리소스를 사용 하는 응용 프로그램 혜택을 사용 하 여는  **CredentialCache** 클래스는 모든 자격 증명을 저장 하 고 요청을 제공 하기 때문입니다.  
  
 인터넷 리소스에 인증을 요청 하는 경우는 <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=fullName> 보냅니다 메서드는 <xref:System.Net.WebRequest> 에  **AuthenticationManager** 자격 증명에 대 한 요청과 함께.  다음 프로세스에 따라 요청이 인증 됩니다.  
  
1.  **AuthenticationManager** 호출 된 <xref:System.Net.IAuthenticationModule.Authenticate%2A> 메서드는 등록 된 순서 대로 등록 된 인증 모듈의 각.  **AuthenticationManager** 반환 되지 않는 첫 번째 모듈을 사용 하 여  **null** 인증 과정을 수행 합니다.  프로세스의 세부 정보에 관련 된 인증 모듈의 형식에 따라 달라 집니다.  
  
2.  인증 프로세스가 완료 되 면 인증 모듈을 반환은 <xref:System.Net.Authorization> 에  **WebRequest** 인터넷 리소스에 액세스 하는 데 필요한 정보가 들어 있습니다.  
  
 일부 인증 구성표 첫 번째 리소스에 대 한 요청 하지 않고 사용자를 인증할 수 있습니다.  응용 프로그램이 있으므로 서버에 하나 이상의 왕복을 하지 않아도 사용자와 리소스를 preauthenticating 하 여 시간을 절약할 수 있습니다.  또는 나중에 사용자에 게 응답성을 수 있도록 인증 프로그램을 시작 하는 동안 수행할 수 있습니다.  사전 인증 설정에 사용할 수 있는 인증 체계는  [CanPreAuthenticate](frlrfsystemnetiauthenticationmoduleclasspreauthenticatetopic) 속성을  **true**.  
  
## 참고 항목  
 [기본 인증 및 다이제스트 인증](../../../docs/framework/network-programming/basic-and-digest-authentication.md)   
 [NTLM 및 Kerberos 인증](../../../docs/framework/network-programming/ntlm-and-kerberos-authentication.md)   
 [네트워크 프로그래밍의 보안](../../../docs/framework/network-programming/security-in-network-programming.md)