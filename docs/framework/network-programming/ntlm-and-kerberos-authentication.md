---
title: "NTLM 및 Kerberos 인증 | Microsoft Docs"
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
  - "인증[.NET Framework], NTLM"
  - "인증[.NET Framework], Kerberos"
  - "사용자 인증, Kerberos"
  - "사용자 인증, NTLM"
  - "Kerberos 인증"
  - "데이터 받기, 인증"
  - "NTLM 인증"
  - "인터넷, 인증"
  - "클라이언트 인증, Kerberos"
  - "데이터 보내기, 인증"
  - "네트워크 리소스, 인증"
  - "클래스[.NET Framework], 인증"
  - "클라이언트 인증, NTLM"
ms.assetid: 9ef65560-f596-4469-bcce-f4d5407b55cd
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# NTLM 및 Kerberos 인증
기본 NTLM 인증 및 Kerberos 인증 서버에서 인증을 시도 하도록 호출 응용 프로그램에 연결 하는 Microsoft Windows NT 사용자 자격 증명을 사용 합니다.  기본값이 아닌 NTLM 인증을 사용 하는 경우 응용 프로그램 인증 형식을 NTLM으로 설정 하 고 사용 하는 <xref:System.Net.NetworkCredential> 개체를 다음 예제와 같이 사용자 이름, 암호 및 도메인을 호스트에 전달 합니다.  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = _  
    New NetworkCredential(UserName, SecurelyStoredPassword, Domain)  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create (MyURI);  
WReq.Credentials =   
    new NetworkCredential(UserName, SecurelyStoredPassword, Domain);  
```  
  
 응용 프로그램 사용자의 자격 증명을 사용 하 여 인터넷 서비스에 연결 하는 응용 프로그램에서 다음 예제와 같이 사용자의 기본 자격 증명으로 수행할 수 있습니다.  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = CredentialCache.DefaultCredentials  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create (MyURI);  
WReq.Credentials = CredentialCache.DefaultCredentials;  
```  
  
 협상 인증 모듈 원격 서버가 NTLM 또는 Kerberos 인증을 사용 하 여 적절 한 응답을 보냅니다 여부가 결정 됩니다.  
  
> [!NOTE]
>  NTLM 인증 프록시 서버를 통해 작동 하지 않습니다.  
  
## 참고 항목  
 [기본 인증 및 다이제스트 인증](../../../docs/framework/network-programming/basic-and-digest-authentication.md)   
 [인터넷 인증](../../../docs/framework/network-programming/internet-authentication.md)