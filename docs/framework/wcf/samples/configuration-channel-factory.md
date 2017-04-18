---
title: "구성 채널 팩터리 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# 구성 채널 팩터리
이 샘플에서는 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>의 사용법에 대해 설명합니다.<xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 구성을 중앙에서 관리할 수 있도록 해 주며,응용 프로그램 도메인의 로드 이후 구성이 선택되었거나 변경된 경우에도 유용합니다.  
  
## 세부 항목  
 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>  
  
## 추가 설명  
 이 샘플에서는 기본 응용 프로그램 구성 파일을 사용할 필요 없이 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>를 사용하여 클라이언트 응용 프로그램에 특정 구성 파일을 추가하는 방법을 보여 줍니다.  
  
 이 샘플은 두 프로젝트로 구성되어 있습니다.첫 번째 프로젝트는 클라이언트가 보내는 메시지에 회신하기 위해 실행되는 간단한 서비스입니다.두 번째 프로젝트는 Test.config 구성 파일에 대해 <xref:System.Configuration.ExeConfigurationFileMap>을 사용하여 두 개의 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> 개체를 빌드하고 이 개체를 사용하여 서비스와 통신하는 클라이언트 응용 프로그램입니다.두 클라이언트 모두 Test.config에 지정된 구성을 사용하여 서비스와 통신합니다.  
  
 다음 코드에서는 클라이언트 응용 프로그램에 사용자 지정 구성 파일을 추가합니다.  
  
```  
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();  
fileMap.ExeConfigFilename = "Test.config";  
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);  
  
ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));  
ICalculatorChannel client1 = factory1.CreateChannel();  
  
```  
  
#### 샘플을 설치, 빌드 및 실행하려면  
  
1.  관리자 권한으로 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 엽니다.  
  
2.  ConfigurationChannelFactory 솔루션\(두 개의 프로젝트\)을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 선택합니다.  
  
3.  **공용 속성**에서 **시작 프로젝트**를 선택한 다음 **여러 개의 시작 프로젝트**를 클릭합니다.  
  
4.  **Client** 프로젝트가 **Service** 프로젝트 다음에 실행되도록 **'시작' 동작**을 사용하여 **Service** 프로젝트를 목록의 처음으로 이동하고 마찬가지로 **'시작' 동작**을 사용하여 **Client** 프로젝트를 **Service** 프로젝트 다음으로 이동합니다.  
  
5.  **확인**을 클릭한 다음 F5 키\(또는 Ctrl\+F5\)를 눌러 샘플을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`