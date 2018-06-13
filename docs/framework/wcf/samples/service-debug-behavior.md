---
title: 서비스 디버그 동작
ms.date: 03/30/2017
ms.assetid: 9d8fd3fb-dc39-427a-8235-336a7e7162ba
ms.openlocfilehash: 5edbf640fbda72599b5d14ce482ae186e91681c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33503683"
---
# <a name="service-debug-behavior"></a><span data-ttu-id="45f99-102">서비스 디버그 동작</span><span class="sxs-lookup"><span data-stu-id="45f99-102">Service Debug Behavior</span></span>
<span data-ttu-id="45f99-103">이 샘플에서는 서비스 디버그 동작 설정을 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-103">This sample demonstrates how service debug behavior settings can be configured.</span></span> <span data-ttu-id="45f99-104">샘플 기반는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)를 구현 하는 `ICalculator` 서비스 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="45f99-105">이 샘플에서는 구성 파일에 서비스 디버그 동작을 명시적으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-105">This sample explicitly defines service debug behavior in the configuration file.</span></span> <span data-ttu-id="45f99-106">또한 코드에서 명령적으로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-106">It can also be done imperatively in code.</span></span>  
  
 <span data-ttu-id="45f99-107">이 샘플에서 클라이언트는 콘솔 응용 프로그램(.exe)이고 서비스는 IIS(인터넷 정보 서비스)를 통해 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45f99-108">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="45f99-109">서버에 대한 Web.config 파일에서는 다음 샘플과 같이 서비스 디버그 동작을 정의하여 도움말 페이지 및 예외 처리를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-109">The Web.config file for the server defines the service debug behavior to enable the help page and exception handling as shown in the following sample.</span></span>  
  
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
  
 <span data-ttu-id="45f99-110">[\<serviceDebug >](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) 서비스 디버그 동작 속성을 변경 하는 허용 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-110">[\<serviceDebug>](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) is the configuration element that allows changing the service debug behavior properties.</span></span> <span data-ttu-id="45f99-111">사용자는 이 동작을 수정하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-111">The user can modify this behavior to achieve the following:</span></span>  
  
-   <span data-ttu-id="45f99-112"><xref:System.ServiceModel.FaultContractAttribute>를 사용하여 예외가 선언되지 않은 경우에도 서비스에서 응용 프로그램 코드에 의해 throw된 예외를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-112">This allows the service to return any exception that is thrown by the application code even if the exception is not declared using the <xref:System.ServiceModel.FaultContractAttribute>.</span></span> <span data-ttu-id="45f99-113">이 작업은 `includeExceptionDetailInFaults`를 `true`로 설정하여 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-113">It is done by setting `includeExceptionDetailInFaults` to `true`.</span></span> <span data-ttu-id="45f99-114">이 설정은 서버가 예기치 않은 예외를 throw하는 경우를 디버깅할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-114">This setting is useful when debugging cases where the server is throwing an unexpected exception.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="45f99-115">프로덕션 환경에서는 이 설정을 켜면 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-115">It is not secure to turn this setting on in a production environment.</span></span> <span data-ttu-id="45f99-116">예기치 않은 서버 예외에 클라이언트에 사용할 수 없는 정보가 포함될 수 있으므로 `includeExceptionDetailsInFaults`를 `true`로 설정하면 정보 누수가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-116">An unexpected server exception may have some information that is not intended for the client and so setting `includeExceptionDetailsInFaults` to `true` might result in an information leak.</span></span>  
  
-   <span data-ttu-id="45f99-117">[ \<serviceDebug >](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) 도움말 페이지를 사용 하지 않도록 설정 하거나 설정 하려면 사용자도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-117">The [\<serviceDebug>](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) also allows a user to enable or disable the help page.</span></span> <span data-ttu-id="45f99-118">각 서비스는 서비스의 WSDL을 가져오기 위한 끝점을 비롯하여 서비스에 대한 정보를 포함하는 도움말 페이지를 선택적으로 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-118">Each service can optionally expose a help page that contains information about the service including the endpoint to get WSDL for the service.</span></span> <span data-ttu-id="45f99-119">이는 `httpHelpPageEnabled`를 `true`로 설정하여 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-119">This can be enabled by setting `httpHelpPageEnabled` to `true`.</span></span> <span data-ttu-id="45f99-120">이렇게 하면 서비스의 기본 주소에 대한 GET 요청으로 도움말 페이지가 반환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-120">This enables the help page to be returned to a GET request to the base address of the service.</span></span> <span data-ttu-id="45f99-121">이 주소는 다른 특성 `httpHelpPageUrl`을 설정하여 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-121">You can change this address by setting another attribute `httpHelpPageUrl`.</span></span> <span data-ttu-id="45f99-122">HTTP 대신 HTTPS를 사용하여 보안을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-122">You can make this secure by using HTTPS instead of HTTP.</span></span> <span data-ttu-id="45f99-123">이 작업은 `httpsHelpPageEnabled` 및 `httpsHelpPageUrl`을 설정하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-123">This can be done by setting `httpsHelpPageEnabled` and `httpsHelpPageUrl`.</span></span>  
  
 <span data-ttu-id="45f99-124">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-124">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="45f99-125">처음 세 가지 연산(더하기, 빼기 및 곱하기)은 성공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-125">The first three operations (Add, Subtract and Multiply) must succeed.</span></span> <span data-ttu-id="45f99-126">마지막 연산("나누기 ")은 0으로 나누기 예외가 발생하여 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-126">The last operation ("divide") fails with a division by zero exception.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="45f99-127">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="45f99-127">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="45f99-128">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-128">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="45f99-129">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-129">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="45f99-130">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-130">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="45f99-131">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="45f99-132">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="45f99-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="45f99-133">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="45f99-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="45f99-134">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f99-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\ServiceDebug`  
  
## <a name="see-also"></a><span data-ttu-id="45f99-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45f99-135">See Also</span></span>
