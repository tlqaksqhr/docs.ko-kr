---
title: 성능 카운터 사용
ms.date: 03/30/2017
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
ms.openlocfilehash: 2e25551494a433c53832127fdb0a32cb4eccac47
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="using-performance-counters"></a>성능 카운터 사용
이 샘플에는 사용자 정의 성능 카운터를 만드는 방법 및 Windows Communication Foundation (WCF) 성능 카운터에 액세스 하는 방법을 보여 줍니다. 이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)합니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 이 샘플에서 클라이언트는 `ICalculator` 서비스의 메서드 4개를 호출합니다. 클라이언트는 사용자가 중단할 때까지 이 작업을 계속 수행합니다. 서비스는 변경되지 않습니다.  
  
 성능 카운터는 다음 샘플 구성에 표시된 것과 같이 서비스에 대한 Web.config 파일의 진단 섹션에서 사용할 수 있습니다.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics performanceCounters="All" />   
  </system.serviceModel>  
</configuration>  
```  
  
 이 작업을 수행할 수도 있습니다를 사용 하 여 [Configuration Editor 도구 (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)합니다.  
  
 성능 카운터가 사용되면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 성능 카운터 모음 전체가 서비스에 대해 사용됩니다. .NET Framework는 `ServiceModelService`, `ServiceModelEndpoint` 및 `ServiceModelOperation`의 세 가지 수준에서 성능 데이터를 자동으로 유지 관리합니다. 이러한 각 수준에는 "Calls", "Calls per Second" 및 "Security Calls Not Authorized"와 같은 성능 카운터가 있습니다.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3.  지침에 따라 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
### <a name="to-view-performance-data"></a>성능 데이터를 보려면  
  
1.  클릭 하 여 성능 모니터 도구를 시작 **시작**, **실행...** , 입력 `perfmon` 클릭 **확인** 하거나 제어판에서 선택 **관리 도구** 두 번 클릭 하 고 **성능**합니다.  
  
    > [!NOTE]
    >  샘플 코드가 실행될 때까지는 카운터를 추가할 수 없습니다.  
  
2.  나열된 성능 카운터를 선택한 다음 Delete 키를 누르면 성능 카운터를 제거할 수 있습니다.  
  
3.  추가 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 그래프 창을 마우스 오른쪽 단추로 클릭 하 고 선택 하 여 카운터 **카운터 추가**합니다. 에 **카운터 추가** 대화 상자에서 **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0 또는 ServiceModelService 3.0.0.0** 성능 개체에 있는 드롭다운 목록 상자입니다. 목록에서 보려는 카운터를 선택합니다.  
  
    > [!NOTE]
    >  컴퓨터에서 실행 중인 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스가 없는 경우에는 서비스의 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 성능 카운터가 없습니다.  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a>Configuration Editor를 사용하여 카운터를 사용하려면  
  
1.  SvcConfigEditor.exe의 인스턴스를 엽니다.  
  
2.  파일 메뉴에서 클릭 **열려** 클릭 한 다음 **구성 파일 중...** .  
  
3.  샘플 응용 프로그램의 서비스 폴더로 이동한 다음 Web.config 파일을 엽니다.  
  
4.  클릭 **진단** 구성 트리에서 합니다.  
  
5.  설정/해제 **성능 카운터** 에 **진단** '모두' 표시 하기 위해 창입니다.  
  
6.  구성 파일을 저장하고 편집기를 끝냅니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a>참고 항목  
 [AppFabric 모니터링 샘플](http://go.microsoft.com/fwlink/?LinkId=193959)
