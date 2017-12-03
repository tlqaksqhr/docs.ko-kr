---
title: "래핑되지 않은 메시지"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 019657bd-1f9b-4315-ad74-eaa4e7551ff6
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 476a708acebc7c671e8d7f6ef1812a34e5221db8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="unwrapped-messages"></a><span data-ttu-id="d15a5-102">래핑되지 않은 메시지</span><span class="sxs-lookup"><span data-stu-id="d15a5-102">Unwrapped Messages</span></span>
<span data-ttu-id="d15a5-103">이 샘플에서는 래핑되지 않은 메시지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d15a5-103">This sample demonstrates unwrapped messages.</span></span> <span data-ttu-id="d15a5-104">기본적으로 메시지 본문은 서비스 작업 매개 변수가 래핑되도록 서식이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d15a5-104">By default, the message body is formatted such that the parameters to a service operation are wrapped.</span></span> <span data-ttu-id="d15a5-105">다음 샘플에서는 `Add` 서비스에 `ICalculator` 요청 메시지를 래핑된 모드로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d15a5-105">The following sample shows an `Add` request message to the `ICalculator` service in wrapped mode.</span></span>  
  
```xml  
<s:Envelope   
    xmlns:s=http://www.w3.org/2003/05/soap-envelope  
    xmlns:a="http://schemas.xmlsoap.org/ws/2005/08/addressing">  
    <s:Header>  
        …  
    </s:Header>  
    <s:Body>  
      <Add xmlns="http://Microsoft.ServiceModel.Samples">  
        <n1>100</n1>  
        <n2>15.99</n2>  
      </Add>  
    </s:Body>  
</s:Envelope>  
```  
  
 <span data-ttu-id="d15a5-106">메시지 본문에 있는 `<Add>` 요소가 `n1` 및 `n2` 매개 변수를 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="d15a5-106">The `<Add>` element in the message body wraps the `n1` and `n2` parameters.</span></span> <span data-ttu-id="d15a5-107">대조적으로, 다음 샘플에서는 같은 메시지를 래핑되지 않은 모드로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d15a5-107">In contrast, the following sample shows the equivalent message in the unwrapped mode.</span></span>  
  
```xml  
<s:Envelope   
    xmlns:s="http://www.w3.org/2003/05/soap-envelope"   
    xmlns:a="http://schemas.xmlsoap.org/ws/2005/08/addressing">  
    <s:Header>  
        ….  
    </s:Header>  
    <s:Body>  
      <n1 xmlns="http://Microsoft.ServiceModel.Samples">100</n1>  
      <n2 xmlns="http://Microsoft.ServiceModel.Samples">15.99</n2>  
    </s:Body>  
  </s:Envelope>  
</MessageLogTraceRecord>  
```  
  
 <span data-ttu-id="d15a5-108">래핑되지 않은 메시지는 포함하는 요소에 `n1` 및 `n2` 매개 변수를 래핑하지 않으며 SOAP 본문 요소의 직계 자식입니다.</span><span class="sxs-lookup"><span data-stu-id="d15a5-108">The unwrapped message does not wrap the `n1` and `n2` parameters in a containing element, they are direct children of the soap body element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d15a5-109">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d15a5-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="d15a5-110">이 샘플에서는 서비스 작업 매개 변수 형식에 <xref:System.ServiceModel.MessageContractAttribute>를 적용하고 다음 샘플 코드에 표시된 것과 같이 값 형식을 반환하여 래핑되지 않은 메시지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d15a5-110">In this sample, an unwrapped message is created by applying the <xref:System.ServiceModel.MessageContractAttribute> to the service operation parameter type and return value type as shown in the following sample code.</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    ResponseMessage Add(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Subtract(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Multiply(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Divide(RequestMessage request);  
}  
  
//setting IsWrapped to false means the n1 and n2  
//members will be direct children of the soap body element  
[MessageContract(IsWrapped = false)]  
public class RequestMessage  
{  
    [MessageBodyMember]  
    private double n1;  
    [MessageBodyMember]  
    private double n2;  
    //…  
}  
  
//setting IsWrapped to false means the result  
//member will be a direct child of the soap body element  
[MessageContract(IsWrapped = false)]  
public class ResponseMessage  
{  
    [MessageBodyMember]  
    private double result;  
    //…  
}  
```  
  
 <span data-ttu-id="d15a5-111">메시지를 보내고 받는 상황을 볼 수 있도록 이 샘플에서는 추적을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d15a5-111">To allow you to see the messages being sent and received, this sample uses tracing.</span></span> <span data-ttu-id="d15a5-112">또한 <xref:System.ServiceModel.WSHttpBinding>은 기록하는 메시지의 수를 줄이기 위해 보안 없이 구성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d15a5-112">In addition, the <xref:System.ServiceModel.WSHttpBinding> has been configured without security, to reduce the number of messages it logs.</span></span>  
  
 <span data-ttu-id="d15a5-113">결과 추적 로그 (c:\logs\Message.log)를 사용 하 여 볼 수는 [Service Trace Viewer 도구 (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d15a5-113">The resulting trace log (c:\logs\Message.log) can be viewed by using the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="d15a5-114">메시지 내용을 보려면 선택 **메시지** 왼쪽 및 오른쪽 Service Trace Viewer 도구 창 모두에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="d15a5-114">To view message contents, select **Messages** in both the left and the right panes of the Service Trace Viewer tool.</span></span> <span data-ttu-id="d15a5-115">이 샘플에서 추적 로그는 C:\LOGS 폴더에 생성되도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d15a5-115">Trace logs in this sample are configured to be generated into the C:\LOGS folder.</span></span> <span data-ttu-id="d15a5-116">샘플을 실행하기 전에 이 폴더를 만들고 사용자에게 이 디렉터리에 대한 네트워크 서비스 쓰기 권한을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d15a5-116">Create this folder before running the sample and give the user Network Service write permissions for this directory.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d15a5-117">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="d15a5-117">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="d15a5-118">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d15a5-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="d15a5-119">메시지를 기록할 C:\LOGS 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d15a5-119">Create a C:\LOGS directory for logging messages.</span></span> <span data-ttu-id="d15a5-120">사용자에게 이 디렉터리에 대한 네트워크 서비스 쓰기 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="d15a5-120">Give the user Network Service write permissions for this directory.</span></span>  
  
3.  <span data-ttu-id="d15a5-121">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d15a5-121">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="d15a5-122">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d15a5-122">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d15a5-123">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d15a5-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d15a5-124">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="d15a5-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d15a5-125">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="d15a5-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d15a5-126">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d15a5-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\Unwrapped`  
  
## <a name="see-also"></a><span data-ttu-id="d15a5-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d15a5-127">See Also</span></span>
