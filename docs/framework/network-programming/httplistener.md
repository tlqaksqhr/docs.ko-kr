---
title: HttpListener
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: db2c42dab15b4282c5474c50f970ffe47a101215
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33393454"
---
# <a name="httplistener"></a>HttpListener
<xref:System.Net.HttpListener> 클래스는 프로그래밍 방식으로 제어되는 HTTP 프로토콜 수신기를 제공합니다. 수신기는 <xref:System.Net.HttpListener> 개체의 수명 동안 활성화되며 응용 프로그램 내에서 실행됩니다.  
  
## <a name="httpsys"></a>HTTP.SYS  
 <xref:System.Net.HttpListener> 클래스는 Windows에 대한 모든 HTTP 트래픽을 처리하는 커널 모드 수신기인 HTTP.sys를 기반으로 합니다. HTTP.sys는 연결 관리, 대역폭 제한 및 웹 서버 로깅 기능을 제공합니다. `HttpCfg.exe` 도구를 사용하여 SSL 인증서를 추가합니다. 자세한 내용은 [서버](http://go.microsoft.com/fwlink/?LinkID=178285) 설명서의 [HttpCfg.exe](http://go.microsoft.com/fwlink/?LinkID=178284) 도구에 대한 설명서를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Net.HttpListener>  
 <xref:System.Net.HttpWebRequest>  
 <xref:System.Net.HttpWebResponse>  
 [HTTP 서버](http://go.microsoft.com/fwlink/?LinkID=178285)  
 [인터넷 정보의 향상된 보안 기능](http://go.microsoft.com/fwlink/?LinkID=178286)  
 [HttpListener ASPX 호스트 응용 프로그램 샘플](http://go.microsoft.com/fwlink/?LinkID=179560)  
 [HttpListener 기술 샘플](http://go.microsoft.com/fwlink/?LinkID=179558)  
 [네트워크 프로그래밍 샘플](../../../docs/framework/network-programming/network-programming-samples.md)
