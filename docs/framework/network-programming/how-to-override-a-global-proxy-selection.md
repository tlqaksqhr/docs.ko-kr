---
title: '방법: 전역 프록시 선택 재정의'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: c10cff979a18d8e07a1e7089f96157e4c38f040e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33393908"
---
# <a name="how-to-override-a-global-proxy-selection"></a>방법: 전역 프록시 선택 재정의
이 예제에서는 전역 프록시 선택을 포트 80의 `alternateproxy`라는 프록시 서버로 재정의하는 **WebRequest**를 www.contoso.com에 보냅니다.  
  
## <a name="example"></a>예  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   **System.Net** 네임스페이스에 대한 참조.  
  
## <a name="see-also"></a>참고 항목  
 [응용 프로그램 프로토콜 사용](../../../docs/framework/network-programming/using-application-protocols.md)  
 [프록시를 통해 인터넷 액세스](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
