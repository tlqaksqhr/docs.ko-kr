---
title: 비동기 찾기 샘플
ms.date: 03/30/2017
ms.assetid: 7a713a25-c1f4-42e1-8c4a-93d64ca45a3b
ms.openlocfilehash: ed900ba3cd1b55f4e35ec0d2b92ef6b7283b498e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="asynchronous-find-sample"></a>비동기 찾기 샘플
이 샘플에서는 클라이언트 응용 프로그램에서 비동기 찾기 작업을 사용하는 방법을 보여 줍니다.  
  
## <a name="sample-details"></a>샘플 세부 정보  
 이 디자인 패턴을 따르면 클라이언트가 찾기 요청의 결과로 찾은 끝점에 대한 알림을 비동기적으로 받을 수 있다는 이점이 있습니다. 이 샘플이 작동하는 방식을 보려면 Client.cs 파일을 엽니다. <xref:System.ServiceModel.Discovery.DiscoveryClient> 개체의 이벤트 처리기에는 두 개의 대리자가 연결되어 있습니다. 하나는 <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> 이벤트가 발생할 때 호출되고 다른 하나는 <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> 이벤트가 발생할 때마다 호출됩니다. 이 샘플에서는 응용 프로그램에 이 패턴을 사용하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  이 샘플에서는 HTTP 끝점을 사용하며 이 샘플을 실행하려면 적절한 URL ACL을 추가해야 합니다. 자세한 내용은 참조 [HTTP 및 HTTPS 구성](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)합니다. 높은 권한으로 다음 명령을 실행하면 적절한 ACL이 추가됩니다. 명령이 지정한 대로 작동하지 않는 경우 다음 인수의 도메인과 사용자 이름을 대체할 수 있습니다. `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
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
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\AsyncFind`  
  
## <a name="see-also"></a>참고 항목
