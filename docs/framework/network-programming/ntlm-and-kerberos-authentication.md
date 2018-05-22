---
title: NTLM 및 Kerberos 인증
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
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
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d1f621af2b365d229b7b5e62069471af98be267a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ntlm-and-kerberos-authentication"></a><span data-ttu-id="d837f-102">NTLM 및 Kerberos 인증</span><span class="sxs-lookup"><span data-stu-id="d837f-102">NTLM and Kerberos Authentication</span></span>
<span data-ttu-id="d837f-103">기본 NTLM 인증 및 Kerberos 인증에서는 호출 응용 프로그램과 연결된 Microsoft Windows NT 사용자 자격 증명을 사용하여 서버에 인증을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="d837f-103">Default NTLM authentication and Kerberos authentication use the Microsoft Windows NT user credentials associated with the calling application to attempt authentication with the server.</span></span> <span data-ttu-id="d837f-104">기본이 아닌 NTLM 인증을 사용할 때, 다음 예제에 표시된 대로 응용 프로그램에서 인증 형식을 NTLM으로 설정하고 <xref:System.Net.NetworkCredential> 개체를 사용하여 호스트에 사용자 이름, 암호 및 도메인을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="d837f-104">When using non-default NTLM authentication, the application sets the authentication type to NTLM and uses a <xref:System.Net.NetworkCredential> object to pass the user name, password, and domain to the host, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="d837f-105">응용 프로그램 사용자의 자격 증명을 사용하여 인터넷 서비스에 연결해야 하는 응용 프로그램에서는 다음 예제에 표시된 대로 사용자의 기본 자격 증명을 사용하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d837f-105">Applications that need to connect to Internet services using the credentials of the application user can do so with the user's default credentials, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="d837f-106">협상 인증 모듈을 통해 원격 서버에서 NTLM 또는 Kerberos 인증을 사용하는지 판별하고 적절한 응답을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="d837f-106">The negotiate authentication module determines whether the remote server is using NTLM or Kerberos authentication, and sends the appropriate response.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d837f-107">NTLM 인증은 프록시 서버를 통해 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d837f-107">NTLM authentication does not work through a proxy server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d837f-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d837f-108">See Also</span></span>  
 [<span data-ttu-id="d837f-109">기본 인증 및 다이제스트 인증</span><span class="sxs-lookup"><span data-stu-id="d837f-109">Basic and Digest Authentication</span></span>](../../../docs/framework/network-programming/basic-and-digest-authentication.md)  
 [<span data-ttu-id="d837f-110">인터넷 인증</span><span class="sxs-lookup"><span data-stu-id="d837f-110">Internet Authentication</span></span>](../../../docs/framework/network-programming/internet-authentication.md)
