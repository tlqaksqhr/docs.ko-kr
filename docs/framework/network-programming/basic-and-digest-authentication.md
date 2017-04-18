---
title: "기본 인증 및 다이제스트 인증 | Microsoft Docs"
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
  - "기본 인증"
  - "인증[.NET Framework], 기본"
  - "클라이언트 인증, 기본"
  - "사용자 인증, 기본"
  - "인증[.NET Framework], 다이제스트"
  - "데이터 받기, 인증"
  - "클라이언트 인증, 다이제스트"
  - "인터넷, 인증"
  - "다이제스트 인증"
  - "데이터 보내기, 인증"
  - "네트워크 리소스, 인증"
  - "사용자 인증, 다이제스트"
ms.assetid: 8cce2742-8d52-4643-9dd2-64ddf38aa878
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# 기본 인증 및 다이제스트 인증
<xref:System.Net> 구현의 기본 및 다이제스트 인증 준수 RFC2617 – HTTP 인증: 기본 및 다이제스트 인증 \(www.w3.org에서 World Wide Web 컨소시엄 웹 사이트에서 사용 가능\).  
  
 기본 및 다이제스트 인증에 응용 프로그램은 사용자 이름 및 암호를 제공 해야는 <xref:System.Net.WebRequest.Credentials%2A> 속성에는 <xref:System.Net.WebRequest> 인터넷에서 데이터를 요청 하는 다음 예제와 같이 사용 하는 개체.  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = New NetworkCredential(UserName, SecurelyStoredPassword)  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create(MyURI);  
WReq.Credentials = new NetworkCredential(UserName, SecurelyStoredPassword);  
```  
  
> [!CAUTION]
>  기본 및 다이제스트 인증에 보낼 데이터가 암호화 되지 않습니다 적대가 데이터를 볼 수 있습니다.  또한 기본 인증 자격 증명 \(사용자 이름 및 암호\) 일반 텍스트로 전송 되므로 가로챌 수 있습니다.  
  
## 참고 항목  
 [NTLM 및 Kerberos 인증](../../../docs/framework/network-programming/ntlm-and-kerberos-authentication.md)   
 [인터넷 인증](../../../docs/framework/network-programming/internet-authentication.md)