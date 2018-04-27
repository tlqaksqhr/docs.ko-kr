---
title: 동적 재구성
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b20786ae-cce6-4f91-b6cb-9cae116faf8b
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 36b548ee47ed9165743bbfb1eaab5cf3bbe82bd2
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="dynamic-reconfiguration"></a>동적 재구성
이 샘플에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 라우팅 서비스를 보여 줍니다. 라우팅 서비스는 응용 프로그램에 내용 기반 라우터를 손쉽게 포함할 수 있게 해 주는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 구성 요소입니다. 이 샘플에서는 라우팅 서비스를 사용하여 통신하도록 표준 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Calculator 샘플을 조정합니다. 이 샘플에서는 런타임 동안 라우팅 서비스를 동적으로 다시 구성하는 방법을 보여 줍니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\DynamicReconfiguration`  
  
## <a name="sample-details"></a>샘플 세부 정보  
 런타임 도중 라우팅 서비스를 동적으로 다시 구성하기 위해 이 샘플에서는 새 <xref:System.ServiceModel.Routing.RoutingConfiguration> 개체를 만들고 이를 적용하는 타이머를 5초마다 발생시킵니다. 이 구성에서는 일반 계산기 끝점이나 반올림 계산기 끝점 중 하나를 참조합니다. 계산기 클라이언트 응용 프로그램의 메시지가 반환되는 서비스는 라우팅 서비스가 해당 시점에 라우트하도록 구성된 대상에 따라 달라집니다.  
  
 사용자 지정 동작을 통해 동적으로 다시 구성하는 라우팅 서비스의 기능이 사용됩니다. 이 사용자 지정 동작은 5초마다 발생하는 간단한 스레드 타이머가 들어 있고 `UpdateRules` 메서드에 대한 콜백을 생성하는 서비스 확장을 연결합니다. 이 콜백은 새 라우팅 구성을 만들고 적용합니다. 실제 배포에서 이 콜백은 SQL-Event 알림 또는 WS-Discovery 알림과 같은 일부 다른 형식의 이벤트 결과로 수행될 수 있습니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 DynamicReconfiguration.sln을 엽니다.  
  
2.  열려는 **솔루션 탐색기**선택, **솔루션 탐색기** 에서 **보기** 메뉴.  
  
3.  키를 눌러 **F5** 또는 **CTRL + SHIFT + B** Visual Studio에서.  
  
    1.  키를 누를 때 필요한 프로젝트가 자동 시작을 원하는 경우 **F5**솔루션을 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다. 선택 된 **시작 프로젝트** 노드 아래의 **공용 속성** 왼쪽된 창에서. 선택은 **여러 개의 시작 프로젝트** 라디오 단추 및 모든 프로젝트에 설정 된 **시작** 작업 합니다.  
  
    2.  사용 하 여 프로젝트를 빌드하면 **CTRL + SHIFT + B**, 다음 응용 프로그램을 시작 해야 합니다.  
  
        1.  계산기 클라이언트(./CalculatorClient/bin/client.exe)  
  
        2.  계산기 서비스(./CalculatorService/bin/service.exe)  
  
        3.  반올림 계산기 서비스(./RoundingCalcService/bin/service.exe)  
  
        4.  라우팅 서비스(./RoutingService/bin/RoutingService.exe)  
  
4.  계산기 클라이언트의 콘솔 창에서 Enter 키를 눌러 클라이언트를 시작하고 계산기 서비스 작업을 호출합니다.  
  
     라우팅 서비스에서는 5초마다 라우팅 구성이 동적으로 변경될 때 반올림 계산기와 일반 계산기에 메시지를 교대로 라우트합니다. 라우팅 서비스에서 메시지를 보내도록 구성된 대상 끝점에 따라 클라이언트 콘솔 창에 출력되는 내용이 달라집니다.  
  
5.  Enter 키를 반복해서 5초 이상씩 계속 누르고 서비스 결과의 변화를 살펴봅니다.  
  
    1.  다음은 라우터 서비스가 메시지를 반올림 계산기 서비스로 라우트하도록 구성된 경우에 반환되는 출력입니다.  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.5  
        Multiply(9,81.25) = 731.2  
        Divide(22,7) = 3.1  
        ```  
  
    2.  다음은 라우팅 서비스가 메시지를 일반 계산기 서비스로 라우트하도록 구성된 경우에 반환되는 출력입니다.  
  
        ```Output  
        Add(100,15.99) = 115.99  
        Subtract(145,76.54) = 68.46  
        Multiply(9,81.25) = 731.25  
        Divide(22,7) = 3.14285714285714  
        ```  
  
6.  계산기 서비스 및 반올림 계산기 서비스에서도 호출된 작업의 로그를 각 해당 콘솔 창에 출력합니다.  
  
7.  클라이언트 콘솔 창에서 "quit"를 입력 하 고 enter 키를 눌러 종료 합니다.  
  
8.  서비스 콘솔 창에서 Enter 키를 눌러 서비스를 종료합니다.  
  
## <a name="scenario"></a>시나리오  
 이 샘플에서는 한 끝점을 통해 노출되는 서비스의 여러 형식 또는 구현을 허용하는 내용 기반 라우터의 역할을 하는 라우터를 보여 줍니다.  
  
### <a name="real-world-scenario"></a>실제 시나리오  
 Contoso에서는 모든 서비스를 가상화하여 서로 다른 여러 형식의 서비스에 액세스할 수 있게 해 주는 하나의 끝점만 공개하려고 합니다. 이 경우 라우팅 서비스의 내용 기반 라우팅 기능을 사용하여 들어오는 요청을 보낼 위치를 확인합니다.  
  
## <a name="see-also"></a>참고 항목  
 [AppFabric 호스팅 및 지 속성 샘플](http://go.microsoft.com/fwlink/?LinkId=193961)
