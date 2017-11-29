---
title: "방법: HTTP 관련 속성에 액세스"
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
ms.assetid: f8848c7e-f5c5-4d42-b86d-9951ff8f4146
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f277321ab94874970cb392dfe7f84a52a1cc2c40
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-http-specific-properties"></a><span data-ttu-id="162a4-102">방법: HTTP 관련 속성에 액세스</span><span class="sxs-lookup"><span data-stu-id="162a4-102">How to: Access HTTP-Specific Properties</span></span>
<span data-ttu-id="162a4-103">이 샘플은 HTTP **Keep-alive** 동작을 끄고 웹 서버에서 프로토콜 버전 번호를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="162a4-103">This sample shows how to turn off the HTTP **Keep-alive** behavior and get the protocol version number from the Web server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="162a4-104">예제</span><span class="sxs-lookup"><span data-stu-id="162a4-104">Example</span></span>  
  
```vb  
Dim HttpWReq As HttpWebRequest= _  
    CType(WebRequest.Create("http://www.contoso.com"), HttpWebRequest)  
' Turn off connection keep-alives.  
HttpWReq.KeepAlive = False  
  
Dim HttpWResp As HttpWebResponse = _  
    CType(HttpWReq.GetResponse(), HttpWebResponse)  
  
' Get the HTTP protocol version number returned by the server.  
Dim ver As String = HttpWResp.ProtocolVersion.ToString()  
HttpWResp.Close()  
```  
  
```csharp  
HttpWebRequest HttpWReq =   
    (HttpWebRequest)WebRequest.Create("http://www.contoso.com");  
// Turn off connection keep-alives.  
HttpWReq.KeepAlive = false;  
  
HttpWebResponse HttpWResp = (HttpWebResponse)HttpWReq.GetResponse();  
  
// Get the HTTP protocol version number returned by the server.  
String ver = HttpWResp.ProtocolVersion.ToString();  
HttpWResp.Close();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="162a4-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="162a4-105">Compiling the Code</span></span>  
 <span data-ttu-id="162a4-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="162a4-106">This example requires:</span></span>  
  
-   <span data-ttu-id="162a4-107">**System.Net** 네임스페이스에 대한 참조.</span><span class="sxs-lookup"><span data-stu-id="162a4-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="162a4-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="162a4-108">See Also</span></span>  
 [<span data-ttu-id="162a4-109">프록시를 통해 인터넷 액세스</span><span class="sxs-lookup"><span data-stu-id="162a4-109">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [<span data-ttu-id="162a4-110">응용 프로그램 프로토콜 사용</span><span class="sxs-lookup"><span data-stu-id="162a4-110">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 [<span data-ttu-id="162a4-111">HTTP</span><span class="sxs-lookup"><span data-stu-id="162a4-111">HTTP</span></span>](../../../docs/framework/network-programming/http.md)
