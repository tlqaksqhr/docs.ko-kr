---
title: "ASP.NET 클라이언트에서 데이터 바인딩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68b49fa6-94e7-4d4c-a34e-902a2b3770b6
caps.latest.revision: "23"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7ceb63315d94c0deed161bb294e8f61bf523bb63
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="data-binding-in-an-aspnet-client"></a><span data-ttu-id="022d7-102">ASP.NET 클라이언트에서 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="022d7-102">Data Binding in an ASP.NET Client</span></span>
<span data-ttu-id="022d7-103">이 샘플에서는 Web Forms 응용 프로그램에서 일반적인 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스에 의해 반환된 데이터를 바인딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="022d7-103">This sample demonstrates how to bind data returned by a typical [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service in a Web Forms application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="022d7-104">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="022d7-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="022d7-105">이 샘플에서는 요청-회신 통신 패턴을 정의하는 계약을 구현하는 서비스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="022d7-105">This sample demonstrates a service that implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="022d7-106">이 샘플은 브라우저에서 액세스할 수 있는 클라이언트 Web Forms 응용 프로그램과 IIS(인터넷 정보 서비스)에서 호스팅하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="022d7-106">The sample consists of a client Web Forms application accessible from a browser and a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service hosted by Internet Information Services (IIS).</span></span>  
  
 <span data-ttu-id="022d7-107">이 서비스는 요청-회신 통신 패턴을 정의하는 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="022d7-107">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="022d7-108">계약은 `IWeatherService`라는 작업을 노출시키는 `GetWeatherData` 인터페이스에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="022d7-108">The contract is defined by the `IWeatherService` interface, which exposes an operation named `GetWeatherData`.</span></span> <span data-ttu-id="022d7-109">이 작업은 도시 배열을 사용하여 도시의 최고 및 최저 예상 기온을 나타내는 `WeatherData` 개체의 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="022d7-109">This operation accepts an array of cities and returns an array of `WeatherData` objects that represent the high and low forecasted temperature for a city.</span></span>  
  
 <span data-ttu-id="022d7-110">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 클라이언트 .aspx 페이지에는 이 서비스에 의해 반환된 데이터의 그래픽 표현을 포함하는 DataGrid 웹 컨트롤이 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="022d7-110">On the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] client .aspx page, a DataGrid Web control is defined, which contains the graphical representation of the data returned by the service.</span></span> <span data-ttu-id="022d7-111">.aspx 페이지의 코드는 날씨 데이터를 위한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 호출하고 이 데이터를 `WeatherData` 개체의 배열에 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="022d7-111">Code on the .aspx page calls the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service for weather data and returns the data to an array of `WeatherData` objects.</span></span> <span data-ttu-id="022d7-112">DataGrid는 `DataSource` 속성을 이 배열로 설정하여 데이터를 가져올 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="022d7-112">The DataGrid specifies where to get its data from by setting its `DataSource` property to that array.</span></span> <span data-ttu-id="022d7-113">DataGrid의 `DataBind` 메서드를 호출함과 동시에 데이터 바인딩이 발생하며,</span><span class="sxs-lookup"><span data-stu-id="022d7-113">The data binding occurs with a call to the DataGrid's `DataBind` method.</span></span> <span data-ttu-id="022d7-114">에 포함 된 모든이 코드는 합니다.`aspx`</span><span class="sxs-lookup"><span data-stu-id="022d7-114">All of this code is contained inside the .`aspx`</span></span> <span data-ttu-id="022d7-115">페이지의 `Page_Load` 될 때마다 사용자가 브라우저 페이지를 데이터를 새로 고칠 하므로 DataGrid에서 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="022d7-115">page's `Page_Load` method, so every time the user refreshes the browser page, the data is updated in the DataGrid.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="022d7-116">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="022d7-116">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="022d7-117">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="022d7-117">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="022d7-118">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="022d7-118">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="022d7-119">이 샘플의 클라이언트는 개발 웹 서버에서 실행되는 웹 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="022d7-119">This sample's client is a Web site that runs under a development Web server.</span></span> <span data-ttu-id="022d7-120">개발 웹 서버를 시작 하려면 명령 프롬프트에서 다음을 입력: "`%SystemDrive%\Program Files\Common Files\Microsoft Shared\DevServer\9.0\WebDev.WebServer.EXE" /port:8000 /path:<WebFormsSamplePath>\CS\client /vpath:/client`합니다.</span><span class="sxs-lookup"><span data-stu-id="022d7-120">To launch the development Web server, type the following at the command prompt: "`%SystemDrive%\Program Files\Common Files\Microsoft Shared\DevServer\9.0\WebDev.WebServer.EXE" /port:8000 /path:<WebFormsSamplePath>\CS\client /vpath:/client`.</span></span> <span data-ttu-id="022d7-121">그런 다음 http://localhost:8000/client로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="022d7-121">Then browse to http://localhost:8000/client.</span></span> <span data-ttu-id="022d7-122">이 샘플을 여러 컴퓨터에서 실행하려면 클라이언트의 Web.config 파일에서 `localhost`에 대한 모든 참조를 서버의 컴퓨터 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="022d7-122">To run this sample across computers, replace all references to `localhost` in the client's Web.config file with the computer name of the server.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="022d7-123">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="022d7-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="022d7-124">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="022d7-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="022d7-125">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="022d7-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="022d7-126">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="022d7-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WebForms`  
  
## <a name="see-also"></a><span data-ttu-id="022d7-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="022d7-127">See Also</span></span>
