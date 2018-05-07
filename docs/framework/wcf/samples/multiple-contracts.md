---
title: 다중 계약
ms.date: 03/30/2017
ms.assetid: 2bef319b-fe9c-4d49-ac6c-dfb23eb35099
ms.openlocfilehash: 8e96d1ac27eb69d8e7e4da76aa8679aa35bf8ad4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="multiple-contracts"></a>다중 계약
Multiple Contracts 샘플에서는 서비스에서 두 개 이상의 계약을 구현하는 방법과 구현된 각 계약과의 통신을 위해 끝점을 구성하는 방법을 보여 줍니다. 이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)합니다. 서비스는 `ICalculator` 계약과 `ICalculatorSession` 계약의 두 가지 계약을 정의하도록 수정되었습니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 서비스 클래스에서는 `ICalculator` 및 `ICalculatorSession` 계약을 모두 구현합니다. 계약 중 하나에 세션이 필요하기 때문에, 서비스에서는 <xref:System.ServiceModel.InstanceContextMode.PerSession> 인스턴스 모드를 사용하여 세션 수명이 지속되는 동안 상태를 유지 관리합니다.  
  
 각 계약을 노출하는 두 개의 끝점을 정의하도록 서비스 구성이 수정되었습니다. `ICalculator` 끝점은 `basicHttpBinding`을 사용하여 기본 주소에서 노출됩니다. `ICalculatorSession` 끝점은 다음 샘플 구성에 표시된 것과 같이 `wsHttpBinding` 특성이 `bindingConfiguration`으로 설정된 `BindingWithSession`을 사용하여 baseaddress/세션에 노출됩니다.  
  
```xml  
<service   
    name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">  
  <!-- ICalculator endpoint is exposed using BasicBinding at the base  
       address provided by host:   
       http://localhost/servicemodelsamples/service.svc  -->  
  <endpoint address=""  
            binding="basicHttpBinding"  
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  <!-- ICalculatorSession endpoint is exposed using BindingWithSession  
       at {baseaddress}/session:  
       http://localhost/servicemodelsamples/service.svc/session -->  
  <endpoint address="session"  
            binding="wsHttpBinding"  
            bindingConfiguration="BindingWithSession"   
           contract="Microsoft.ServiceModel.Samples.ICalculatorSession" />  
  ...  
</service>  
```  
  
 생성된 클라이언트 코드에는 이제 원래 `ICalculator` 계약과 새 `ICalculatorSession` 계약 모두의 클라이언트 클래스가 포함됩니다. 클라이언트 구성 및 코드는 적절한 서비스 끝점에서 각 계약과 통신하도록 수정되었습니다.  
  
 클라이언트는 콘솔 창 응용 프로그램(.exe)입니다. 서비스는 인터넷 정보 서비스(IIS)에 의해 호스팅됩니다.  
  
 클라이언트 콘솔 창은 각 끝점에 전송되는 작업을 표시하며, 먼저 기본 끝점을 표시하고 그 뒤에 보안 끝점을 표시합니다.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3.  지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\MultipleContracts`  
  
## <a name="see-also"></a>참고 항목
