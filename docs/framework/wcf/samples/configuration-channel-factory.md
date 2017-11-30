---
title: "구성 채널 팩터리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a79a5c4997403f018ba34aea65e4c9fadab29443
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="configuration-channel-factory"></a><span data-ttu-id="e96a8-102">구성 채널 팩터리</span><span class="sxs-lookup"><span data-stu-id="e96a8-102">Configuration Channel Factory</span></span>
<span data-ttu-id="e96a8-103">이 샘플에서는 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>의 사용법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e96a8-103">This sample covers the usage of the <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>.</span></span> <span data-ttu-id="e96a8-104"><xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 구성을 중앙에서 관리할 수 있도록 해 주며,</span><span class="sxs-lookup"><span data-stu-id="e96a8-104">The <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> allows central management of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client configuration.</span></span> <span data-ttu-id="e96a8-105">응용 프로그램 도메인의 로드 이후 구성이 선택되었거나 변경된 경우에도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="e96a8-105">This can also be useful in scenarios in which configuration is selected or changed after the application domain load time.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="e96a8-106">세부 항목</span><span class="sxs-lookup"><span data-stu-id="e96a8-106">Demonstrates</span></span>  
 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>  
  
## <a name="discussion"></a><span data-ttu-id="e96a8-107">토론</span><span class="sxs-lookup"><span data-stu-id="e96a8-107">Discussion</span></span>  
 <span data-ttu-id="e96a8-108">이 샘플에서는 기본 응용 프로그램 구성 파일을 사용할 필요 없이 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>를 사용하여 클라이언트 응용 프로그램에 특정 구성 파일을 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e96a8-108">This sample shows how to use <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> to add a particular configuration file to a client application, without having to use the default application configuration file.</span></span>  
  
 <span data-ttu-id="e96a8-109">이 샘플은 두 프로젝트로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e96a8-109">The sample consists of two projects.</span></span> <span data-ttu-id="e96a8-110">첫 번째 프로젝트는 클라이언트가 보내는 메시지에 회신하기 위해 실행되는 간단한 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="e96a8-110">The first project is a simple service that runs to reply to messages coming from the clients.</span></span> <span data-ttu-id="e96a8-111">두 번째 프로젝트는 Test.config 구성 파일에 대해 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>을 사용하여 두 개의 <xref:System.Configuration.ExeConfigurationFileMap> 개체를 빌드하고 이 개체를 사용하여 서비스와 통신하는 클라이언트 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="e96a8-111">The second project is a client application that builds two <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> objects using a <xref:System.Configuration.ExeConfigurationFileMap> for the Test.config configuration file and uses them to communicate with the service.</span></span> <span data-ttu-id="e96a8-112">두 클라이언트 모두 Test.config에 지정된 구성을 사용하여 서비스와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="e96a8-112">Both clients communicate with the service using the configuration specified in Test.config.</span></span>  
  
 <span data-ttu-id="e96a8-113">다음 코드에서는 클라이언트 응용 프로그램에 사용자 지정 구성 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e96a8-113">The following code adds a custom configuration file to a client application.</span></span>  
  
```  
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();  
fileMap.ExeConfigFilename = "Test.config";  
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);  
  
ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));  
ICalculatorChannel client1 = factory1.CreateChannel();  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e96a8-114">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="e96a8-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="e96a8-115">관리자 권한으로 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e96a8-115">Open [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] with administrator privileges.</span></span>  
  
2.  <span data-ttu-id="e96a8-116">ConfigurationChannelFactory 솔루션 (프로젝트 2)를 마우스 오른쪽 단추로 클릭 한 다음 선택 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="e96a8-116">Right-click the ConfigurationChannelFactory solution (2 projects) and then select **Properties**.</span></span>  
  
3.  <span data-ttu-id="e96a8-117">**공용 속성**선택, **시작 프로젝트**, 클릭 하 고 **여러 개의 시작 프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="e96a8-117">In **Common Properties**, select **Startup Project**, and then click **Multiple startup projects**.</span></span>  
  
4.  <span data-ttu-id="e96a8-118">이동의 **서비스** 으로 프로젝트를 목록의 시작 부분에는 **'시작' 동작**로 이동한 다음는 **클라이언트** 후 프로젝트는 **서비스**프로젝트와도 **'시작' 동작**이므로 **클라이언트** 프로젝트 후 실행 되는 **서비스** 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="e96a8-118">Move the **Service** project to the beginning of the list, with the **Action ‘Start’**, and then move the **Client** project after the **Service** project, also with the **Action ‘Start’**, so the **Client** project is executed after the **Service** project.</span></span>  
  
5.  <span data-ttu-id="e96a8-119">클릭 **확인**, 한 다음 샘플을 실행 하려면 f5 키 (또는 CTRL + F5).</span><span class="sxs-lookup"><span data-stu-id="e96a8-119">Click **OK**, and then press F5 (or CTRL+F5) to run the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e96a8-120">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e96a8-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e96a8-121">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="e96a8-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e96a8-122">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="e96a8-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e96a8-123">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e96a8-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
