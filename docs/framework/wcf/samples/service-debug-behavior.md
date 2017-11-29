---
title: "서비스 디버그 동작"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d8fd3fb-dc39-427a-8235-336a7e7162ba
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 04520eda9fe7ce2cd461e094fe2cec76d52ccc7d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="service-debug-behavior"></a>서비스 디버그 동작
이 샘플에서는 서비스 디버그 동작 설정을 구성하는 방법을 보여 줍니다. 샘플 기반는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)를 구현 하는 `ICalculator` 서비스 계약입니다. 이 샘플에서는 구성 파일에 서비스 디버그 동작을 명시적으로 정의합니다. 또한 코드에서 명령적으로 정의할 수 있습니다.  
  
 이 샘플에서 클라이언트는 콘솔 응용 프로그램(.exe)이고 서비스는 IIS(인터넷 정보 서비스)를 통해 호스트됩니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 서버에 대한 Web.config 파일에서는 다음 샘플과 같이 서비스 디버그 동작을 정의하여 도움말 페이지 및 예외 처리를 사용하도록 설정합니다.  
  
```xml  
<behaviors>  
     <serviceBehaviors>  
         <behavior name="CalculatorServiceBehavior">  
         <!-- WARNING: Setting includeExceptionDetailInFaults = "True" could result in leaking secured server information to the client.-->  
         <!-- Please set this to false when deploying -->  
             <serviceDebug includeExceptionDetailInFaults="True" httpHelpPageEnabled="True"/>  
         </behavior>  
     </serviceBehaviors>  
</behaviors>  
```  
  
 [\<serviceDebug >](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) 서비스 디버그 동작 속성을 변경 하는 허용 하는 구성 요소입니다. 사용자는 이 동작을 수정하여 다음을 수행할 수 있습니다.  
  
-   <xref:System.ServiceModel.FaultContractAttribute>를 사용하여 예외가 선언되지 않은 경우에도 서비스에서 응용 프로그램 코드에 의해 throw된 예외를 반환할 수 있습니다. 이 작업은 `includeExceptionDetailInFaults`를 `true`로 설정하여 수행합니다. 이 설정은 서버가 예기치 않은 예외를 throw하는 경우를 디버깅할 때 유용합니다.  
  
    > [!IMPORTANT]
    >  프로덕션 환경에서는 이 설정을 켜면 안전하지 않습니다. 예기치 않은 서버 예외에 클라이언트에 사용할 수 없는 정보가 포함될 수 있으므로 `includeExceptionDetailsInFaults`를 `true`로 설정하면 정보 누수가 발생할 수 있습니다.  
  
-   [ \<serviceDebug >](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) 도움말 페이지를 사용 하지 않도록 설정 하거나 설정 하려면 사용자도 있습니다. 각 서비스는 서비스의 WSDL을 가져오기 위한 끝점을 비롯하여 서비스에 대한 정보를 포함하는 도움말 페이지를 선택적으로 노출할 수 있습니다. 이는 `httpHelpPageEnabled`를 `true`로 설정하여 활성화할 수 있습니다. 이렇게 하면 서비스의 기본 주소에 대한 GET 요청으로 도움말 페이지가 반환될 수 있습니다. 이 주소는 다른 특성 `httpHelpPageUrl`을 설정하여 변경할 수 있습니다. HTTP 대신 HTTPS를 사용하여 보안을 유지할 수 있습니다. 이 작업은 `httpsHelpPageEnabled` 및 `httpsHelpPageUrl`을 설정하여 수행할 수 있습니다.  
  
 샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다. 처음 세 가지 연산(더하기, 빼기 및 곱하기)은 성공해야 합니다. 마지막 연산("나누기 ")은 0으로 나누기 예외가 발생하여 실패합니다.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3.  지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\ServiceDebug`  
  
## <a name="see-also"></a>참고 항목
