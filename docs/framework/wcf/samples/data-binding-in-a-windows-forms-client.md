---
title: Windows 폼 클라이언트 내 데이터 바인딩
ms.date: 03/30/2017
ms.assetid: a2a30b37-d6e2-4552-820e-e60b2bbe8829
ms.openlocfilehash: 38991390f2d0dd272b8d07041b61e6cf16db0cae
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33804380"
---
# <a name="data-binding-in-a-windows-forms-client"></a><span data-ttu-id="9bfe9-102">Windows 폼 클라이언트 내 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="9bfe9-102">Data Binding in a Windows Forms Client</span></span>
<span data-ttu-id="9bfe9-103">이 샘플에는 Windows Communication Foundation (WCF)에서 서비스는 Windows Forms 응용 프로그램에 의해 반환 된 데이터에 바인딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-103">This sample demonstrates how to bind to data returned by a Windows Communication Foundation (WCF) service in a Windows Forms application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9bfe9-104">이 샘플의 설치 절차 및 빌드 지침은 이 문서의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-104">The setup procedure and build instructions for this sample are located at the end of this article.</span></span>  
  
 <span data-ttu-id="9bfe9-105">이 샘플에서는 요청-회신 통신 패턴을 정의하는 계약을 구현하는 서비스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-105">This sample demonstrates a service that implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="9bfe9-106">이 샘플 클라이언트 Windows Forms 응용 프로그램 (.exe) 및 인터넷 정보 서비스 (IIS)에서 호스트 되는 WCF 서비스 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-106">The sample consists of a client Windows Forms application (.exe) and a WCF service hosted by Internet Information Services (IIS).</span></span>  
  
 <span data-ttu-id="9bfe9-107">계약은 `IWeatherService`라는 작업을 노출시키는 `GetWeatherData` 인터페이스에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-107">The contract is defined by the `IWeatherService` interface, which exposes an operation named `GetWeatherData`.</span></span> <span data-ttu-id="9bfe9-108">이 작업은 도시 배열을 사용하여 도시의 최고 및 최저 예상 기온을 나타내는 `WeatherData` 개체의 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-108">This operation accepts an array of cities and returns an array of `WeatherData` objects that represent the high and low forecasted temperature for a city.</span></span>  
  
 <span data-ttu-id="9bfe9-109">데이터 바인딩은 Windows Forms 응용 프로그램의 클라이언트에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-109">The data binding occurs on the client in the Windows Forms application.</span></span> <span data-ttu-id="9bfe9-110">데이터의 그래픽 표시인 `DataGridView`는 Windows Forms 디자이너에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-110">A `DataGridView` is defined in the Windows Forms designer, which is a graphical representation of the data.</span></span> <span data-ttu-id="9bfe9-111">또한 `BindingSource`라는 매개자가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-111">An intermediary named `BindingSource` is also created.</span></span> <span data-ttu-id="9bfe9-112">`BindingSource`의 데이터 소스는 서비스에서 반환하는 데이터 배열로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-112">The data source of `BindingSource` is set to the data array returned by the service.</span></span> <span data-ttu-id="9bfe9-113">`BindingSource`의 용도는 데이터와 데이터 뷰 간의 간접 참조 계층을 제공하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-113">The purpose of the `BindingSource` is to provide a layer of indirection between the data and the data view.</span></span> <span data-ttu-id="9bfe9-114">탐색, 정렬, 필터링 및 업데이트와 같은 데이터와의 모든 상호 작용은 `BindingSource` 구성 요소를 호출하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-114">All interaction with the data, such as navigating, sorting, filtering, and updating, is accomplished with calls to the `BindingSource` component.</span></span> <span data-ttu-id="9bfe9-115">`DataGridView`에 대해 데이터 바인딩을 수행하려면 `datasource`의 `DataGridView`를 `BindingSource` 개체로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-115">To accomplish data binding to the `DataGridView`, the `datasource` of the `DataGridView` is then set to the `BindingSource` object.</span></span> <span data-ttu-id="9bfe9-116">WCF 서비스에서 반환 된 데이터를 모두는 다음 그래픽으로 사용자에 게 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-116">All of the data returned from the WCF service is then displayed graphically to the user.</span></span>  <span data-ttu-id="9bfe9-117">사용자가 단추를 클릭할 때마다 반환된 데이터가 데이터 바인딩된 `DataGridView`에 자동으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-117">Every time the user clicks the button, the returned data is automatically updated in the data-bound `DataGridView`.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9bfe9-118">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="9bfe9-118">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="9bfe9-119">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-119">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="9bfe9-120">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-120">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="9bfe9-121">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-121">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9bfe9-122">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9bfe9-123">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9bfe9-124">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9bfe9-125">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bfe9-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WindowsForms`  
  
## <a name="see-also"></a><span data-ttu-id="9bfe9-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9bfe9-126">See Also</span></span>
