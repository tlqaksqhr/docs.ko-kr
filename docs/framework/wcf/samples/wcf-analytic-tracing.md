---
title: "WCF 분석 추적"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6029c7c7-3515-4d36-9d43-13e8f4971790
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5c238d4c923b00a6c3387caa9bdafd69b126753c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-analytic-tracing"></a>WCF 분석 추적
이 샘플에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]의 ETW에 기록하는 분석 추적 스트림에 추적 이벤트를 추가하는 방법을 보여 줍니다. 분석 추적은 성능을 크게 저하시키지 않으면서 서비스를 쉽게 확인할 수 있도록 하기 위한 것입니다. 이 샘플에서는 <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> API를 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스와 통합되는 이벤트를 기록하는 방법을 보여 줍니다.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] API에 대한 <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>는 <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>을 참조하십시오.  
  
 Windows에서 이벤트 추적에 대 한 자세한 참조 [디버깅 개선 및 ETW를 사용한 성능 조정](http://go.microsoft.com/fwlink/?LinkId=166488)합니다.  
  
## <a name="disposing-eventprovider"></a>EventProvider 삭제  
 이 샘플에서는 <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType>을 구현하는 <xref:System.IDisposable?displayProperty=nameWithType> 클래스를 사용합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에 대한 추적을 구현할 경우 서비스의 수명 동안 <xref:System.Diagnostics.Eventing.EventProvider>의 리소스를 사용할 수 있습니다. 이러한 이유로, 또한 읽기 쉽게 하려는 목적으로 이 샘플에서는 래핑된 <xref:System.Diagnostics.Eventing.EventProvider>를 삭제하지 않습니다. 어떤 이유로 서비스에 다른 추적 요구 사항이 있으며 이 리소스를 삭제해야 하는 경우 관리되지 않는 리소스를 삭제하기 위한 최선의 방법에 따라 이 샘플을 수정해야 합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]관리 되지 않는 리소스를 삭제, 참조 [Dispose 메서드를 구현](http://go.microsoft.com/fwlink/?LinkId=166436)합니다.  
  
## <a name="self-hosting-vs-web-hosting"></a>자체 호스팅 및 웹 호스팅  
 웹 호스팅 서비스에 대 한 WCF의 분석 추적에서는 추적을 내보내는 서비스를 식별 하는 데 사용 되는 "hostreference" 필드를 제공 합니다. 확장 가능한 사용자 추적이 이 모델에 관여할 수 있으며 이 샘플에서는 이 작업을 수행하기 위한 최선의 방법을 보여 줍니다. 경우 참조는 웹 호스트 형식은 파이프 ' &#124;' 문자는 결과에 실제로 표시 문자열에는 다음 중 하나가 될 수 있습니다.  
  
-   응용 프로그램이 루트에 없는 경우  
  
     \<사이트 이름 >\<ApplicationVirtualPath > &#124;\< ServiceVirtualPath > &#124; \<ServiceName >  
  
-   응용 프로그램이 루트에 있는 경우  
  
     \<사이트 이름 > &#124; \<ServiceVirtualPath > &#124; \<ServiceName >  
  
 자체 호스팅된 서비스에 대 한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 분석 추석 "에서는 HostReference" 필드를 채우지 않습니다. 이 샘플의 `WCFUserEventProvider` 클래스는 자체 호스팅 서비스에서 사용될 때 일관성 있게 동작합니다.  
  
## <a name="custom-event-details"></a>사용자 지정 이벤트 상세 정보  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 ETW 이벤트 공급자 매니페스트는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 작성자가 서비스 코드 내에서 내보내도록 디자인한 세 개의 이벤트를 정의합니다. 다음 표에서는 세 개의 이벤트를 간략하게 설명합니다.  
  
|이벤트|설명|이벤트 ID|  
|-----------|-----------------|--------------|  
|UserDefinedInformationEventOccurred|문제는 아니지만 중요한 사항이 서비스에 발생하면 이 이벤트를 내보냅니다. 예를 들어 데이터베이스를 성공적으로 호출한 후 이벤트를 내보낼 수 있습니다.|301|  
|UserDefinedWarningOccurred|이후에 오류를 초래할 수 있는 문제가 발생하면 이 이벤트를 내보냅니다. 예를 들어 데이터베이스에 대한 호출에 실패했지만 중복 데이터 저장소를 대신 사용하여 복구할 수 있는 경우 경고 이벤트를 내보낼 수 있습니다.|302|  
|UserDefinedErrorOccurred|서비스가 예상한 대로 동작하지 않으면 이 이벤트를 내보냅니다. 예를 들어 데이터베이스에 대한 호출에 실패하고 다른 위치에서 데이터를 검색할 수 없는 경우 이벤트를 내보낼 수 있습니다.|303|  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 WCFAnalyticTracingExtensibility.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl+F5를 눌러 솔루션을 실행합니다.  
  
     웹 브라우저에서 클릭 **Calculator.svc**합니다. 서비스의 WSDL 문서에 대한 URI가 브라우저에 나타납니다. 이 URI를 복사합니다.  
  
4.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 테스트 클라이언트(WcfTestClient.exe)를 실행합니다.  
  
     [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 에 있는 테스트 클라이언트 (WcfTestClient.exe)는 \< [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Install > \Common7\IDE\ WcfTestClient.exe (기본 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 설치 디렉터리는 C:\Program Files\Microsoft Visual Studio 10.0).  
  
5.  내에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 테스트를 선택 하 여 서비스를 추가 **파일**, 차례로 **서비스 추가**합니다.  
  
     입력 상자에 끝점 주소를 추가합니다.  
  
6.  클릭 **확인** 는 대화 상자를 닫습니다.  
  
     ICalculator 서비스가 아래 왼쪽된 창에서 추가 된 **내 서비스 프로젝트**합니다.  
  
7.  이벤트 뷰어 응용 프로그램을 엽니다.  
  
     서비스를 호출하기 전에 이벤트 뷰어를 시작하고 이벤트 로그가 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서 내보낸 추적 이벤트를 수신 대기하고 있는지 확인합니다.  
  
8.  **시작** 메뉴 선택 **관리 도구**, 차례로 **이벤트 뷰어**합니다. 사용 하도록 설정 된 **분석** 및 **디버그** 로그 합니다.  
  
9. 이벤트 뷰어의 트리 뷰에서 이동 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**, 한 다음 **응용 프로그램 서버-응용 프로그램**합니다. 마우스 오른쪽 단추로 클릭 **응용 프로그램 서버-응용 프로그램**선택, **보기**, 차례로 **분석 및 디버그 로그 표시**합니다.  
  
     확인 된 **분석 및 디버그 로그 표시** 옵션을 선택 합니다. 사용 하도록 설정 된 **분석** 로그 합니다.  
  
     이벤트 뷰어의 트리 뷰에서 이동 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**,  **응용 프로그램 서버-응용 프로그램**, 차례로 **분석**합니다. 마우스 오른쪽 단추로 클릭 **분석** 선택 **로그 사용**합니다.  
  
10. WCF 테스트 클라이언트를 사용하여 서비스를 테스트합니다.  
  
    1.  WCF 테스트 클라이언트에서 두 번 클릭 **add ()** ICalculator 서비스 노드에서 합니다.  
  
         **add ()** 메서드가 두 개의 매개 변수가 있는 오른쪽 창에 나타납니다.  
  
    2.  첫 번째 매개 변수에 2를 입력하고 두 번째 매개 변수에 3을 입력합니다.  
  
    3.  클릭 **Invoke** 메서드를 호출 합니다.  
  
11. 이동 하는 **이벤트 뷰어** 이미 열려 있는 창입니다. 로 이동 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용 프로그램**합니다.  
  
12. 마우스 오른쪽 단추로 클릭는 **분석** 노드 선택한 **새로 고침**합니다.  
  
     오른쪽 창에 이벤트가 나타납니다.  
  
13. ID가 303인 이벤트를 찾아서 두 번 클릭하여 열고 해당 내용을 검사합니다.  
  
     이 이벤트를 내보낸는 `Add()` ICalculator 서비스의 메서드, 페이로드 같음 "2 + 3 = 5"입니다.  
  
#### <a name="to-clean-up-optional"></a>정리하려면(옵션)  
  
1.  열기 **이벤트 뷰어**합니다.  
  
2.  로 이동 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**, 차례로  **응용 프로그램 서버-응용 프로그램**합니다. 마우스 오른쪽 단추로 클릭 **분석** 선택 **로그 사용 안 함**합니다.  
  
3.  로 이동 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**,  **응용 프로그램 서버-응용 프로그램**, 차례로 **분석**합니다. 마우스 오른쪽 단추로 클릭 **분석** 선택 **로그 지우기**합니다.  
  
4.  클릭 **지우기** 이벤트의 선택을 취소 합니다.  
  
## <a name="known-issue"></a>알려진 문제  
 알려진 문제가 **이벤트 뷰어** ETW 이벤트가 디코딩되지 실패할 수 있습니다. 없다는 오류 메시지가 표시 될 수 있습니다: "이벤트 ID에 대 한 설명 \<id > 소스에서 Microsoft-Windows-응용 프로그램 서버-응용 프로그램을 찾을 수 없습니다. 이 이벤트를 발생시킨 구성 요소가 로컬 컴퓨터에 설치되어 있지 않거나 설치가 손상되었습니다. 설치 또는 로컬 컴퓨터에 구성 요소를 복구 합니다. " 이 오류를 발생 하는 경우 선택 **새로 고침** 에서 **동작** 메뉴. 그러면 이벤트가 올바르게 디코딩됩니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTrace`  
  
## <a name="see-also"></a>참고 항목  
 [AppFabric 모니터링 샘플](http://go.microsoft.com/fwlink/?LinkId=193959)
