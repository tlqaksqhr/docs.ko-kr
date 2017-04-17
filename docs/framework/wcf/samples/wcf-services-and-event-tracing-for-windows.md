---
title: "Windows용 WCF 서비스 및 이벤트 추척 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Windows용 WCF 서비스 및 이벤트 추척
이 샘플에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]의 분석 추적을 사용하여 ETW\(Windows용 이벤트 추적\)의 이벤트를 내보내는 방법을 보여 줍니다.  분석 추적은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 스택에서 주요 시점에 내보내는 이벤트로서, 프로덕션 환경에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스의 문제를 해결하는 데 사용할 수 있습니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스의 분석 추적은 프로덕션 환경에서 성능에 최소한의 영향만 주면서 설정할 수 있는 추적입니다.  이러한 추적은 ETW 세션에 이벤트로 내보내집니다.  
  
 이 샘플에는 서비스에서 이벤트 뷰어를 사용하여 볼 수 있는 이벤트 로그로 이벤트를 내보내는 기본 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스가 포함되어 있습니다.  또한 이 샘플에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스의 이벤트를 수신 대기하는 전용 ETW 세션을 시작할 수 있습니다.  이 샘플에는 이벤트 뷰어를 사용하여 읽을 수 있는 이진 파일에 이벤트를 저장하는 전용 ETW 세션을 만드는 스크립트가 포함되어 있습니다.  
  
#### 이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 EtwAnalyticTraceSample.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl\+F5를 눌러 솔루션을 실행합니다.  
  
     웹 브라우저에서 **Calculator.svc**를 클릭합니다.  서비스의 WSDL 문서에 대한 URI가 브라우저에 나타납니다.  이 URI를 복사합니다.  
  
     기본적으로 서비스는 포트 1378\(http:\/\/localhost:1378\/Calculator.svc\)에서 요청을 수신 대기하기 시작합니다.  
  
4.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 테스트 클라이언트\(WcfTestClient.exe\)를 실행합니다.  
  
     [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 테스트 클라이언트\(WcfTestClient.exe\)는 \<[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Install Dir\>\\Common7\\IDE\\ WcfTestClient.exe에 있습니다. 기본 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 설치 디렉터리는 C:\\Program Files\\Microsoft Visual Studio 10.0입니다.  
  
5.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 테스트 클라이언트 내에서 **파일**을 선택하고 **서비스 추가**를 선택하여 서비스를 추가합니다.  
  
     입력 상자에 끝점 주소를 추가합니다.  기본값은 http:\/\/localhost:1378\/Calculator.svc입니다.  
  
6.  이벤트 뷰어 응용 프로그램을 엽니다.  
  
     서비스를 호출하기 전에 이벤트 뷰어를 시작하고 이벤트 로그가 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서 내보낸 추적 이벤트를 수신 대기하고 있는지 확인합니다.  
  
7.  **시작** 메뉴에서 **관리 도구**, **이벤트 뷰어**를 차례로 선택합니다.  **분석** 및 **디버그** 로그를 사용하도록 설정합니다.  
  
8.  이벤트 뷰어의 트리 뷰에서 **이벤트 뷰어**, **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램 서버\-응용 프로그램**으로 이동합니다.  **응용 프로그램 서버\-응용 프로그램**을 마우스 오른쪽 단추로 클릭하고 **보기**, **분석 및 디버그 로그 표시**를 차례로 선택합니다.  
  
     **분석 및 디버그 로그 표시** 옵션이 선택되어 있는지 확인합니다.  
  
9. **분석** 로그를 사용하도록 설정합니다.  
  
     이벤트 뷰어의 트리 뷰에서 **이벤트 뷰어**, **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램 서버\-응용 프로그램**으로 이동합니다.  **분석**을 마우스 오른쪽 단추로 클릭하고 **로그 사용**을 선택합니다.  
  
#### 서비스를 테스트하려면  
  
1.  다시 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 테스트 클라이언트로 전환하고 `Divide`를 두 번 클릭한 다음 분모 0을 지정하는 기본값을 유지합니다.  
  
     분모가 0이면 서비스에서는 오류를 throw합니다.  
  
2.  서비스에서 내보낸 이벤트를 확인합니다.  
  
     이벤트 뷰어로 다시 전환한 다음 **이벤트 뷰어**, **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램 서버\-응용 프로그램**으로 이동합니다.  **분석**을 마우스 오른쪽 단추로 클릭하고 **새로 고침**을 선택합니다.  
  
     WCF 분석 추적 이벤트가 이벤트 뷰어에 표시됩니다.  서비스에서 오류가 throw되었으므로 이벤트 뷰어에 오류 추적 이벤트가 표시됩니다.  
  
3.  1\-2단계를 반복하되 이번에는 유효한 입력을 사용합니다.  `N2` 매개 변수 값으로는 0 이외의 모든 숫자를 사용할 수 있습니다.  
  
     분석 채널을 새로 고쳐 WCF 이벤트에 오류 이벤트가 포함되어 있지 않은지 확인합니다.  
  
 이 샘플에서는 WCF 서비스에서 내보낸 분석 추적 이벤트를 보여 줍니다.  
  
#### 정리하려면\(옵션\)  
  
1.  이벤트 뷰어를 엽니다.  
  
2.  **이벤트 뷰어**, **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램 서버\-응용 프로그램**으로 이동합니다.  **분석**을 마우스 오른쪽 단추로 클릭하고 **로그 사용 안 함**을 선택합니다.  
  
3.  **이벤트 뷰어**, **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램 서버\-응용 프로그램**으로 이동합니다.  **분석**을 마우스 오른쪽 단추로 클릭하고 **로그 지우기**를 선택합니다.  
  
4.  **지우기** 옵션을 선택하여 이벤트를 지웁니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.  계속하기 전에 다음\(기본\) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [.NET Framework 4용 WCF\(Windows Communication Foundation\) 및 Windows WF\(Workflow Foundation\) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780)\(영문\)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.  이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## 참고 항목  
 [AppFabric 모니터링 샘플](http://go.microsoft.com/fwlink/?LinkId=193959)