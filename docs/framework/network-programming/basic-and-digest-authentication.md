---
title: "기본 인증 및 다이제스트 인증"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- authentication [.NET Framework], classes
- Basic authentication
- authentication [.NET Framework], basic
- client authentication, basic
- user authentication, basic
- authentication [.NET Framework], digest
- receiving data, authentication
- client authentication, digest
- Internet, authentication
- digest authentication
- sending data, authentication
- network resources, authentication
- user authentication, digest
ms.assetid: 8cce2742-8d52-4643-9dd2-64ddf38aa878
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 7ca66a65c05da3d515358c0fdb26682fa4ec1438
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="basic-and-digest-authentication"></a><span data-ttu-id="ed6b7-102">기본 인증 및 다이제스트 인증</span><span class="sxs-lookup"><span data-stu-id="ed6b7-102">Basic and Digest Authentication</span></span>
<span data-ttu-id="ed6b7-103">기본 및 다이제스트 인증의 <xref:System.Net> 구현은 RFC2617 – HTTP 인증: 기본 및 다이제스트(www.w3.org의 World Wide Web 컨소시엄 웹 사이트에서 사용 가능)를 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6b7-103">The <xref:System.Net> implementation of basic and digest authentication complies with RFC2617 – HTTP Authentication: Basic and Digest Authentication (available on the World Wide Web Consortium's Web site at www.w3.org).</span></span>  
  
 <span data-ttu-id="ed6b7-104">기본 및 다이제스트 인증을 사용하려면 다음 예제와 같이 응용 프로그램이 인터넷에서 데이터를 요청하는 데 사용하는 <xref:System.Net.WebRequest> 개체의 <xref:System.Net.WebRequest.Credentials%2A> 속성에 사용자 이름 및 암호를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6b7-104">To use basic and digest authentication, an application must provide a user name and password in the <xref:System.Net.WebRequest.Credentials%2A> property of the <xref:System.Net.WebRequest> object that it uses to request data from the Internet, as shown in the following example.</span></span>  
  
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
>  <span data-ttu-id="ed6b7-105">기본 및 다이제스트 인증과 함께 전송된 데이터는 암호화되지 않으므로 악의적 사용자가 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed6b7-105">Data sent with Basic and Digest Authentication is not encrypted, so the data can be seen by an adversary.</span></span> <span data-ttu-id="ed6b7-106">또한 기본 인증 자격 증명(사용자 이름 및 암호)은 일반 텍스트로 보내지므로 누군가 이를 가로챌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed6b7-106">Additionally, Basic Authentication credentials (user name and password) are sent in the clear and can be intercepted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed6b7-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed6b7-107">See Also</span></span>  
 [<span data-ttu-id="ed6b7-108">NTLM 및 Kerberos 인증</span><span class="sxs-lookup"><span data-stu-id="ed6b7-108">NTLM and Kerberos Authentication</span></span>](../../../docs/framework/network-programming/ntlm-and-kerberos-authentication.md)  
 [<span data-ttu-id="ed6b7-109">인터넷 인증</span><span class="sxs-lookup"><span data-stu-id="ed6b7-109">Internet Authentication</span></span>](../../../docs/framework/network-programming/internet-authentication.md)
