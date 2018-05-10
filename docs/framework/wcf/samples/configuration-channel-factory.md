---
title: 구성 채널 팩터리
ms.date: 03/30/2017
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
ms.openlocfilehash: fc3a564128e520133c2404a82438e692b1381875
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="configuration-channel-factory"></a>구성 채널 팩터리
이 샘플에서는 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>의 사용법에 대해 설명합니다. <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> WCF 클라이언트 구성 중앙에서 관리할 수 있습니다. 응용 프로그램 도메인의 로드 이후 구성이 선택되었거나 변경된 경우에도 유용합니다.  
  
## <a name="demonstrates"></a>세부 항목  
 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>  
  
## <a name="discussion"></a>토론  
 이 샘플에서는 기본 응용 프로그램 구성 파일을 사용할 필요 없이 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>를 사용하여 클라이언트 응용 프로그램에 특정 구성 파일을 추가하는 방법을 보여 줍니다.  
  
 이 샘플은 두 프로젝트로 구성되어 있습니다. 첫 번째 프로젝트는 클라이언트가 보내는 메시지에 회신하기 위해 실행되는 간단한 서비스입니다. 두 번째 프로젝트는 Test.config 구성 파일에 대해 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>을 사용하여 두 개의 <xref:System.Configuration.ExeConfigurationFileMap> 개체를 빌드하고 이 개체를 사용하여 서비스와 통신하는 클라이언트 응용 프로그램입니다. 두 클라이언트 모두 Test.config에 지정된 구성을 사용하여 서비스와 통신합니다.  
  
 다음 코드에서는 클라이언트 응용 프로그램에 사용자 지정 구성 파일을 추가합니다.  
  
```  
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();  
fileMap.ExeConfigFilename = "Test.config";  
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);  
  
ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));  
ICalculatorChannel client1 = factory1.CreateChannel();  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  관리자 권한으로 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 엽니다.  
  
2.  ConfigurationChannelFactory 솔루션 (프로젝트 2)를 마우스 오른쪽 단추로 클릭 한 다음 선택 **속성**합니다.  
  
3.  **공용 속성**선택, **시작 프로젝트**, 클릭 하 고 **여러 개의 시작 프로젝트**합니다.  
  
4.  이동의 **서비스** 으로 프로젝트를 목록의 시작 부분에는 **'시작' 동작**로 이동한 다음는 **클라이언트** 후 프로젝트는 **서비스**프로젝트와도 **'시작' 동작**이므로 **클라이언트** 프로젝트 후 실행 되는 **서비스** 프로젝트.  
  
5.  클릭 **확인**, 한 다음 샘플을 실행 하려면 f5 키 (또는 CTRL + F5).  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
