---
title: 구성 기반 활성화
ms.date: 03/30/2017
ms.assetid: 21bb762e-c43e-4b0c-887b-5e434d665838
ms.openlocfilehash: 3ac4edd2a51e4ed8a5c0b7e73d7d1afa31334c33
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809916"
---
# <a name="configuration-based-activation"></a>구성 기반 활성화
이 샘플에서는.svc 파일 없이 Windows Communication Foundation (WCF) 서비스를 활성화 하는 방법을 보여 줍니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\ConfigBasedActivation`  
  
## <a name="sample-details"></a>샘플 세부 정보  
 이 샘플에서 클라이언트는 WCF 테스트 클라이언트와 서비스는 IIS에서 호스팅됩니다.  
  
> [!NOTE]
>  이 샘플의 설치 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
### <a name="activation-of-services-without-requiring-a-svc-file"></a>.svc 파일 없이 서비스 활성화  
 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)]에서는 서비스를 활성화는 데 .svc 파일이 필요했습니다. 이 경우 응용 프로그램과 함께 추가 파일을 배포 및 유지 관리해야 하므로 관리 오버헤드가 증가했습니다. [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] 릴리스에서는 응용 프로그램 구성 파일을 사용하여 활성화 구성 요소를 구성할 수 있습니다.  
  
 [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)]에서는 응용 프로그램 구성 파일의 <xref:System.ServiceModel.Configuration.ServiceActivationElement>에 새 구성 요소(<xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>)가 도입되었습니다. <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> 컬렉션은 다음 코드 예제와 같이 서비스 컬렉션을 받아들여 활성화합니다.  
  
```xml  
<serviceActivations>  
   <add relativeAddress="Calculator.svc" service="Microsoft.ServiceModel.Samples.CalculatorService" />  
  
<serviceActivations>  
```  
  
 이 구성은 .svc 파일의 구성과 매우 유사합니다. 도입된 추가 특성은 서비스의 주소를 제공하는 `relativeAddress`입니다. 또한 상대 주소는 서비스의 가상 경로입니다. 호스트에서는 `virtualPath` 위치에서 파일의 Web.config 파일을 검색하고, 이 파일이 없으면 해당 부모 폴더를 재귀적으로 검색합니다.  
  
> [!NOTE]
>  이 샘플은 IIS에서 호스팅해야 작동합니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 Service.csproj 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  WCFTestClient.exe를 실행하여 서비스를 테스트합니다.  
  
4.  [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]를 사용하여 %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE 폴더로 이동합니다.  
  
5.  WcfTestClient.exe를 실행합니다.  
  
6.  서비스의 MEX 주소를 설정합니다.  
  
7.  Ctrl+Shift+A를 눌러 서비스 주소를 설정합니다.  
  
8.  주소를 설정 http://localhost/ServiceModelSamples/Calculator.svc합니다.  
  
9. `Add` 작업을 수행합니다. `n1` 매개 변수의 값을 10으로 설정하고 `n2` 매개 변수의 값을 15로 설정합니다.  
  
10. 키를 눌러 **호출**합니다.  
  
     예상 결과는 25입니다.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행한 반드시는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3.  솔루션을 빌드한 후 Setup.bat를 실행하여 IIS에 ServiceModelSamples 응용 프로그램을 설치합니다. 이제 ServiceModelSamples 디렉터리가 IIS 응용 프로그램으로 나타납니다.  
  
4.  지침에 따라 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [AppFabric 호스팅 및 지 속성 샘플](http://go.microsoft.com/fwlink/?LinkId=193961)
