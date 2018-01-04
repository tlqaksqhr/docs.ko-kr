---
title: "전송 보안 포함한 기본 바인딩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f49b1de6-0254-4362-8ef2-fccd8ff9688b
caps.latest.revision: "26"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 2a65adbb908aded9f4124f473f0b298d573a521f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="basicbinding-with-transport-security"></a><span data-ttu-id="fca9c-102">전송 보안 포함한 기본 바인딩</span><span class="sxs-lookup"><span data-stu-id="fca9c-102">BasicBinding with Transport Security</span></span>
<span data-ttu-id="fca9c-103">이 샘플에서는 기본 바인딩이 있는 SSL 전송 보안을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fca9c-103">This sample demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="fca9c-104">이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md) 계산기 서비스를 구현 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9c-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fca9c-105">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca9c-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="fca9c-106">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="fca9c-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="fca9c-107">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="fca9c-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fca9c-108">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca9c-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Basic\TransportSecurity`  
  
## <a name="sample-details"></a><span data-ttu-id="fca9c-109">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="fca9c-109">Sample Details</span></span>  
 <span data-ttu-id="fca9c-110">기본적으로 기본 바인딩은 HTTP 통신을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9c-110">By default, the basic binding supports HTTP communication.</span></span> <span data-ttu-id="fca9c-111">이 샘플에서는 기본 바인딩에 대해 전송 보안을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fca9c-111">The sample shows how to enable transport security for the basic binding.</span></span> <span data-ttu-id="fca9c-112">샘플을 실행하려면 먼저 웹 서버 인증서 마법사를 사용하여 인증서를 만들고 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9c-112">Before you run the sample, you must create a certificate and assign it by using the Web Server Certificate Wizard.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fca9c-113">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca9c-113">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="fca9c-114">이 샘플에 있는 프로그램 코드는 동일 합니다는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md) 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="fca9c-114">The program code in the sample is identical to that of the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) service.</span></span> <span data-ttu-id="fca9c-115">다음 샘플 구성과 같이 구성 파일 설정의 끝점 정의 및 바인딩 정의를 수정하여 보안 통신을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9c-115">The endpoint definition and binding definition in the configuration file settings are modified to enable secure communication, as shown in the following sample configuration.</span></span>  
  
```xml  
<system.serviceModel>  
  <services>  
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
      <endpoint address=""  
                binding="basicHttpBinding"  
                bindingConfiguration="Binding1"   
                contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
   </services>  
  <bindings>  
    <basicHttpBinding>  
      <!-- Configure basicHttpBinding with Transport security -- >  
      <!-- mode and clientCredentialType set to None.-->  
      <binding name="Binding1">  
        <security mode="Transport">  
          <transport clientCredentialType="None"/>  
        </security>  
      </binding>  
    </basicHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="fca9c-116">이 샘플에 사용된 인증서는 Makecert.exe를 사용하여 만든 테스트 인증서이므로 브라우저에서 https://localhost/servicemodelsamples/service.svc와 같은 HTTPS: 주소에 액세스하려고 하면 보안 경고가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="fca9c-116">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert appears when you try to access an HTTPS: address in your browser, such as https://localhost/servicemodelsamples/service.svc.</span></span> <span data-ttu-id="fca9c-117">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 클라이언트에서 테스트 인증서를 사용하여 작업을 수행할 수 있도록 하려면 클라이언트에 일부 코드를 추가하여 보안 경고가 나타나지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9c-117">To allow the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client to work with a test certificate, some additional code is added to the client to suppress the security alert.</span></span> <span data-ttu-id="fca9c-118">실제 인증서를 사용할 때는 이 코드 및 함께 사용되는 클래스가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fca9c-118">This code, and the accompanying class, is not necessary when using real certificates.</span></span>  
  
```  
// This code is required only for test certificates such as those   
// created by Makecert.exe.  
PermissiveCertificatePolicy.Enact(  
                           "CN=ServiceModelSamples-HTTPS-Server");  
```  
  
 <span data-ttu-id="fca9c-119">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fca9c-119">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="fca9c-120">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="fca9c-120">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="fca9c-121">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="fca9c-121">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="fca9c-122">다음 명령을 사용하여 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9c-122">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command:</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="fca9c-123">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9c-123">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="fca9c-124">수행 했는지 확인 하십시오.는 [인터넷 정보 서비스 (IIS) 서버 인증서 설치 지침](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9c-124">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>  
  
4.  <span data-ttu-id="fca9c-125">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="fca9c-125">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
5.  <span data-ttu-id="fca9c-126">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fca9c-126">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fca9c-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fca9c-127">See Also</span></span>
