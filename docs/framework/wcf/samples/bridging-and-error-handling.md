---
title: "브리징과 오류 처리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ae87d1a-b615-4014-a494-a53f63ff0137
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cc809b75a965107594f7b2aa8a78d412bf284d8e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="bridging-and-error-handling"></a>브리징과 오류 처리
이 샘플에서는 서로 다른 바인딩을 사용하는 클라이언트와 서비스 간의 브리징 통신에 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 라우팅 서비스를 사용하는 방법을 보여 줍니다. 또한 장애 조치 시나리오에 백업 서비스를 사용하는 방법도 보여 줍니다. 라우팅 서비스는 응용 프로그램에 내용 기반 라우터를 손쉽게 포함할 수 있게 해 주는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 구성 요소입니다. 이 샘플에서는 라우팅 서비스를 사용하여 통신하도록 표준 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Calculator 샘플을 조정합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\ErrorHandlingAndBridging`  
  
## <a name="sample-details"></a>샘플 세부 정보  
 이 샘플에서 계산기 클라이언트는 라우터에 의해 노출된 끝점으로 메시지를 보내도록 구성되어 있습니다. 라우팅 서비스는 전송된 모든 메시지를 승인하고 이를 계산기 서비스에 해당하는 끝점에 전달하도록 구성되어 있습니다. 다음은 기본 계산기 서비스, 백업 계산기 서비스 및 계산기 클라이언트의 구성과 라우팅 서비스를 사용하여 클라이언트와 서비스 간에 통신이 이루어지는 방법에 대한 설명입니다.  
  
-   계산기 클라이언트는 BasicHttpBinding을 사용하도록 구성된 반면 계산기 서비스는 NetTcpBinding을 사용하도록 구성되어 있습니다. 라우팅 서비스에서는 메시지를 계산기 서비스로 보내기 전에 필요에 따라 자동으로 변환하며, 계산기 클라이언트에서 액세스할 수 있도록 응답도 변환합니다.  
  
-   라우팅 서비스에서는 두 개의 계산기 서비스, 즉 기본 계산기 서비스와 백업 계산기 서비스를 인식합니다. 라우팅 서비스는 먼저 기본 Calculator 서비스 끝점과 통신하려고 시도합니다. 끝점이 다운되어 통신에 실패하면 라우팅 서비스는 백업 계산기 서비스 끝점과 통신하려고 시도합니다.  
  
 따라서 클라이언트에서 보내는 메시지는 라우터가 받아 실제 계산기 서비스로 다시 라우트합니다. 계산기 서비스 끝점이 다운된 경우 라우팅 서비스에서는 백업 계산기 서비스 끝점으로 메시지를 라우트합니다. 백업 계산기 서비스에서 보내는 메시지는 다시 서비스 라우터로 전송되고 라우터는 이를 다시 계산기 클라이언트에 전달합니다.  
  
> [!NOTE]
>  백업 목록에는 둘 이상의 끝점이 정의되어 있을 수 있습니다. 이 경우 백업 서비스 끝점이 다운되면 라우팅 서비스에서는 연결에 성공할 때까지 목록의 다음 백업 끝점에 연결하려는 시도를 계속합니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 RouterBridgingAndErrorHandling.sln을 엽니다.  
  
2.  Visual Studio에서 F5 키나 Ctrl+Shift+B를 누릅니다.  
  
    1.  F5 키를 누를 때 필요한 프로젝트가 자동 시작 하려는 경우 솔루션을 마우스 오른쪽 단추로 클릭를 **속성**, 및는 **시작 프로젝트** 노드 아래의 **공용속성**선택, **여러 개의 시작 프로젝트**, 모든 프로젝트 설정 하 고 **시작**합니다.  
  
    2.  Ctrl+Shift+B를 사용하여 프로젝트를 빌드하는 경우에는 다음 응용 프로그램을 시작합니다.  
  
        1.  계산기 클라이언트(./CalculatorClient/bin/client.exe)  
  
        2.  계산기 서비스(./CalculatorService/bin/service.exe)  
  
        3.  라우팅 서비스(./RoutingService/bin/RoutingService.exe)  
  
3.  계산기 클라이언트에서 Enter 키를 눌러 클라이언트를 시작합니다.  
  
     다음과 같은 내용이 출력됩니다.  
  
    ```Output  
    Add(100,15.99) = 115.99  
    Subtract(145,76.54) = 68.46  
    Multiply(9,81.25) = 731.25  
    Divide(22,7) = 3.14285714285714  
    ```  
  
## <a name="configurable-via-code-or-appconfig"></a>코드 또는 App.config를 통해 구성 가능  
 이 샘플은 App.config 파일을 사용하여 라우터 동작을 정의하도록 구성되어 있습니다. App.config 파일이 인식되지 않도록 이 파일의 이름을 다른 이름으로 바꾸고 `ConfigureRouterViaCode()` 메서드 호출의 주석 처리를 제거할 수도 있습니다. 어떤 방법을 사용하든 라우터 동작은 동일합니다.  
  
### <a name="scenario"></a>시나리오  
 이 샘플에서는 프로토콜 브리지 및 오류 처리기 역할을 하는 서비스 라우터를 보여 줍니다. 이 시나리오에서는 내용 기반 라우팅이 발생하지 않으므로 라우팅 서비스는 대상 끝점의 미리 구성된 집합에 직접 메시지를 전달하도록 구성된 투명 프록시 노드 역할을 합니다. 또한 라우팅 서비스에서는 통신하도록 구성된 끝점에 메시지를 보내려고 할 때 발생하는 오류를 투명하게 처리하는 추가 단계를 수행합니다. 프로토콜 브리지 역할을 하는 라우팅 서비스를 사용하면 사용자가 외부 통신용 프로토콜과 내부 통신용 프로토콜을 정의할 수 있습니다.  
  
### <a name="real-world-scenario"></a>실제 시나리오  
 Contoso에서는 상호 운용할 수는 서비스 끝점을 제공하면서 내부적으로 성능을 최적화하려고 합니다. 따라서 Contoso에서는 BasicHttpBinding을 사용하는 끝점을 통해 서비스를 노출하지만, 내부적으로는 라우팅 서비스를 통해 해당 서비스에서 사용하는 NetTcpBinding을 사용하는 끝점에 해당 연결을 브리징합니다. 더욱이 Contoso에서는 프로덕션 서비스 중 어느 하나가 일시적으로 중지되더라도 정상적으로 서비스를 제공할 수 있기를 원하므로, 필요할 때 오류 처리 기능을 사용하여 자동으로 백업 끝점으로 장애 조치하는 라우터 서비스 뒤에 여러 개의 끝점을 가상화하려고 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [AppFabric 호스팅 및 지 속성 샘플](http://go.microsoft.com/fwlink/?LinkId=193961)
