---
title: "AJAX Service Using Complex Types 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2c340d947082fa3141b417c1a7dfbce3b7ddf86f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ajax-service-using-complex-types-sample"></a><span data-ttu-id="96efb-102">AJAX Service Using Complex Types 샘플</span><span class="sxs-lookup"><span data-stu-id="96efb-102">AJAX Service Using Complex Types Sample</span></span>
<span data-ttu-id="96efb-103">이 샘플에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]를 사용하여 복합 형식의 인스턴스를 만들고 서비스 및 클라이언트 사이에서 이러한 인스턴스를 JSON(JavaScript Object Notation)으로 전송하는 ASP.NET AJAX(Asynchronous JavaScript and XML) 서비스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96efb-103">This sample demonstrates how to use [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to create an ASP.NET Asynchronous JavaScript and XML (AJAX) service that creates instances of complex types and sends them between service and client as JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="96efb-104">웹 브라우저 클라이언트에서 JavaScript 코드를 사용하여 AJAX 서비스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96efb-104">You can access an AJAX service by using JavaScript code from a Web browser client.</span></span> <span data-ttu-id="96efb-105">기반으로 하는이 샘플은 [기본 AJAX 서비스](../../../../docs/framework/wcf/samples/basic-ajax-service.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="96efb-105">This sample builds on the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample.</span></span>  
  
 <span data-ttu-id="96efb-106">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 AJAX 지원은 <xref:System.Web.UI.ScriptManager> 컨트롤을 통해 ASP.NET AJAX와 함께 사용되도록 최적화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="96efb-106">AJAX support in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is optimized for use with ASP.NET AJAX through the <xref:System.Web.UI.ScriptManager> control.</span></span> <span data-ttu-id="96efb-107">사용 하는 예제에 대 한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET AJAX와 함께 참조는 [AJAX 샘플과](http://msdn.microsoft.com/en-us/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e)합니다.</span><span class="sxs-lookup"><span data-stu-id="96efb-107">For an example of using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with ASP.NET AJAX, see the [AJAX Samples](http://msdn.microsoft.com/en-us/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96efb-108">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96efb-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="96efb-109">다음 샘플의 서비스는 AJAX 특정 코드가 없는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="96efb-109">The service in the following sample is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service with no AJAX-specific code.</span></span> <span data-ttu-id="96efb-110"><xref:System.ServiceModel.Web.WebGetAttribute> 특성이 적용되지 않으므로 기본 HTTP 동사("POST")가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="96efb-110">Because the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is not applied, the default HTTP verb ("POST") is used.</span></span> <span data-ttu-id="96efb-111">서비스에는 `DoMath`라는 복합 형식을 반환하는 단일 작업인 `MathResult`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96efb-111">The service has one operation, `DoMath`, which returns a complex type named `MathResult`.</span></span> <span data-ttu-id="96efb-112">복합 형식은 마찬가지로 AJAX 특정 코드가 없는 표준 데이터 계약 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="96efb-112">The complex type is a standard data contract type, which also contains no AJAX-specific code.</span></span>  
  
```  
[DataContract]  
    public class MathResult  
    {  
        [DataMember]  
        public double sum;  
        [DataMember]  
        public double difference;  
        [DataMember]  
        public double product;  
        [DataMember]  
        public double quotient;  
    }  
```  
  
 <span data-ttu-id="96efb-113">기본 AJAX 서비스 샘플에서와 마찬가지로, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>를 사용하여 서비스에 AJAX 끝점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96efb-113">Create an AJAX endpoint on the service by using the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, just as in the Basic AJAX Service sample.</span></span>  
  
 <span data-ttu-id="96efb-114">클라이언트 웹 페이지 ComplexTypeClientPage.aspx를 클릭할 때 서비스를 호출 하는 ASP.NET 및 JavaScript 코드를 포함 합니다.는 **계산을 수행할** 페이지에서 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="96efb-114">The client Web page ComplexTypeClientPage.aspx contains ASP.NET and JavaScript code to invoke the service when the user clicks the **Perform calculation** button on the page.</span></span> <span data-ttu-id="96efb-115">서비스를 호출 하는 코드의 JSON 본문을 생성 하 고 유사한 HTTP POST를 사용 하 여 전송 된 [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="96efb-115">The code to invoke the service constructs a JSON body and sends it using HTTP POST, similar to the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) sample.</span></span>  
  
 <span data-ttu-id="96efb-116">서비스 호출에 성공한 후 결과 JavaScript 개체에서 개별 데이터 멤버(`sum`, `difference`, `product` 및 `quotient`)에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96efb-116">After the service call succeeds, you can access the individual data members (`sum`, `difference`, `product` and `quotient`) on the resulting JavaScript object.</span></span>  
  
```  
function onSuccess(mathResult){  
     document.getElementById("sum").value = mathResult.sum;  
     document.getElementById("difference").value = mathResult.difference;  
     document.getElementById("product").value = mathResult.product;  
     document.getElementById("quotient").value = mathResult.quotient;  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="96efb-117">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="96efb-117">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="96efb-118">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="96efb-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="96efb-119">에 설명 된 대로 ComplexTypeAjaxService.sln 솔루션을 구축 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="96efb-119">Build the solution ComplexTypeAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="96efb-120">http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx로 이동합니다. 브라우저에서 프로젝트 디렉터리의 ComplexTypeClientPage.aspx를 열지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="96efb-120">Navigate to http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx (do not open ComplexTypeClientPage.aspx in the browser from the project directory).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="96efb-121">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96efb-121">The samples may already be installed on your computer.</span></span> <span data-ttu-id="96efb-122">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="96efb-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="96efb-123">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="96efb-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="96efb-124">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96efb-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`  
  
## <a name="see-also"></a><span data-ttu-id="96efb-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96efb-125">See Also</span></span>  
 [<span data-ttu-id="96efb-126">기본 AJAX 서비스</span><span class="sxs-lookup"><span data-stu-id="96efb-126">Basic AJAX Service</span></span>](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
