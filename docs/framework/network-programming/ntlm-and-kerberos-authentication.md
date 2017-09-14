---
title: "NTLM 및 Kerberos 인증"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- authentication [.NET Framework], NTLM
- authentication [.NET Framework], Kerberos
- user authentication, Kerberos
- user authentication, NTLM
- Kerberos authentication
- receiving data, authentication
- NTLM authentication
- Internet, authentication
- client authentication, Kerberos
- sending data, authentication
- network resources, authentication
- classes [.NET Framework], authentication
- client authentication, NTLM
ms.assetid: 9ef65560-f596-4469-bcce-f4d5407b55cd
caps.latest.revision: 9
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8cb52a70aa34e1011f12a77ea32ec5077f92c127
ms.contentlocale: ko-kr
ms.lasthandoff: 08/21/2017

---
# <a name="ntlm-and-kerberos-authentication"></a>NTLM 및 Kerberos 인증
기본 NTLM 인증 및 Kerberos 인증에서는 호출 응용 프로그램과 연결된 Microsoft Windows NT 사용자 자격 증명을 사용하여 서버에 인증을 시도합니다. 기본이 아닌 NTLM 인증을 사용할 때, 다음 예제에 표시된 대로 응용 프로그램에서 인증 형식을 NTLM으로 설정하고 <xref:System.Net.NetworkCredential> 개체를 사용하여 호스트에 사용자 이름, 암호 및 도메인을 전달합니다.  
  
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
  
 응용 프로그램 사용자의 자격 증명을 사용하여 인터넷 서비스에 연결해야 하는 응용 프로그램에서는 다음 예제에 표시된 대로 사용자의 기본 자격 증명을 사용하여 수행할 수 있습니다.  
  
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
  
 협상 인증 모듈을 통해 원격 서버에서 NTLM 또는 Kerberos 인증을 사용하는지 판별하고 적절한 응답을 전송합니다.  
  
> [!NOTE]
>  NTLM 인증은 프록시 서버를 통해 작동하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [기본 인증 및 다이제스트 인증](../../../docs/framework/network-programming/basic-and-digest-authentication.md)   
 [인터넷 인증](../../../docs/framework/network-programming/internet-authentication.md)

