---
title: "비동기 찾기 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a713a25-c1f4-42e1-8c4a-93d64ca45a3b
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 229e2ff6e630527e3735e3c48f698f582b0b60f8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="asynchronous-find-sample"></a>비동기 찾기 샘플
이 샘플에서는 클라이언트 응용 프로그램에서 비동기 찾기 작업을 사용하는 방법을 보여 줍니다.  
  
## <a name="sample-details"></a>샘플 세부 정보  
 이 디자인 패턴을 따르면 클라이언트가 찾기 요청의 결과로 찾은 끝점에 대한 알림을 비동기적으로 받을 수 있다는 이점이 있습니다. 이 샘플이 작동하는 방식을 보려면 Client.cs 파일을 엽니다. <xref:System.ServiceModel.Discovery.DiscoveryClient> 개체의 이벤트 처리기에는 두 개의 대리자가 연결되어 있습니다. 하나는 <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> 이벤트가 발생할 때 호출되고 다른 하나는 <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> 이벤트가 발생할 때마다 호출됩니다. 이 샘플에서는 응용 프로그램에 이 패턴을 사용하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  이 샘플에서는 HTTP 끝점을 사용하며 이 샘플을 실행하려면 적절한 URL ACL을 추가해야 합니다. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][HTTP 및 HTTPS 구성](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)합니다. 높은 권한으로 다음 명령을 실행하면 적절한 ACL이 추가됩니다. 명령이 지정한 대로 작동하지 않는 경우 다음 인수의 도메인과 사용자 이름을 대체할 수 있습니다. `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 AsyncFind.sln을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트를 열고 \WCF\Basic\Discovery\AsyncFind\CS\service\bin\Debug 또는 \WCF\Basic\Discovery\AsyncFind\VB\service\bin\Debug 디렉터리로 이동한 다음 Service.exe를 실행합니다.  
  
4.  서비스가 시작된 후 \WCF\Basic\Discovery\AsyncFind\CS\client\bin\Debug 또는 WCF\Basic\Discovery\AsyncFind\VB\client\bin\Debug 디렉터리로 이동하여 Client.exe를 실행합니다.  
  
5.  클라이언트에서 서비스를 찾아 호출할 수 있는지 확인합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\AsyncFind`  
  
## <a name="see-also"></a>참고 항목
