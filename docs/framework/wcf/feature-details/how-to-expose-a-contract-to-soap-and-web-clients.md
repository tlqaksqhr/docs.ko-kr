---
title: "방법: SOAP 및 웹 클라이언트에 계약 공개"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: bb765a48-12f2-430d-a54d-6f0c20f2a23a
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5c04da670c84aaecf3587e6620c70e94c6b7350e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-expose-a-contract-to-soap-and-web-clients"></a><span data-ttu-id="86a79-102">방법: SOAP 및 웹 클라이언트에 계약 공개</span><span class="sxs-lookup"><span data-stu-id="86a79-102">How to: Expose a Contract to SOAP and Web Clients</span></span>
<span data-ttu-id="86a79-103">기본적으로 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서는 SOAP 클라이언트에 대해서만 끝점을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="86a79-103">By default, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] makes endpoints available only to SOAP clients.</span></span> <span data-ttu-id="86a79-104">[하는 방법: 기본 WCF 웹 HTTP 서비스 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md), 비 SOAP 클라이언트를 끝점 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86a79-104">In [How to: Create a Basic WCF Web HTTP Service](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md), an endpoint is made available to non-SOAP clients.</span></span> <span data-ttu-id="86a79-105">동일한 계약을 웹 끝점 및 SOAP 끝점으로 모두 사용해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86a79-105">There may be times when you want to make the same contract available both ways, as a Web endpoint and as a SOAP endpoint.</span></span> <span data-ttu-id="86a79-106">이 항목에서는 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="86a79-106">This topic shows an example of how to do this.</span></span>  
  
### <a name="to-define-the-service-contract"></a><span data-ttu-id="86a79-107">서비스 계약을 정의하려면</span><span class="sxs-lookup"><span data-stu-id="86a79-107">To define the service contract</span></span>  
  
1.  <span data-ttu-id="86a79-108">다음 코드와 같이 <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> 및 <xref:System.ServiceModel.Web.WebGetAttribute> 특성으로 표시된 인터페이스를 사용하여 서비스 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="86a79-108">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> and the <xref:System.ServiceModel.Web.WebGetAttribute> attributes, as shown in the following code.</span></span>  
  
     [!code-csharp[htSoapWeb#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#0)]
     [!code-vb[htSoapWeb#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#0)]  
  
    > [!NOTE]
    >  <span data-ttu-id="86a79-109">기본적으로 <xref:System.ServiceModel.Web.WebInvokeAttribute>는 POST 호출을 작업에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="86a79-109">By default <xref:System.ServiceModel.Web.WebInvokeAttribute> maps POST calls to the operation.</span></span> <span data-ttu-id="86a79-110">그러나 "method=" 매개 변수를 지정하여 작업에 매핑할 메서드를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86a79-110">You can, however, specify the method to map to the operation by specifying a "method=" parameter.</span></span> <span data-ttu-id="86a79-111"><xref:System.ServiceModel.Web.WebGetAttribute>는 "method=" 매개 변수를 사용하지 않고 GET 호출만 서비스 작업에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="86a79-111"><xref:System.ServiceModel.Web.WebGetAttribute> does not have a "method=" parameter and only maps GET calls to the service operation.</span></span>  
  
2.  <span data-ttu-id="86a79-112">다음 코드와 같이 서비스 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="86a79-112">Implement the service contract, as shown in the following code.</span></span>  
  
     [!code-csharp[htSoapWeb#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#1)]
     [!code-vb[htSoapWeb#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#1)]  
  
### <a name="to-host-the-service"></a><span data-ttu-id="86a79-113">서비스를 호스트하려면</span><span class="sxs-lookup"><span data-stu-id="86a79-113">To host the service</span></span>  
  
1.  <span data-ttu-id="86a79-114">다음 코드와 같이 <xref:System.ServiceModel.ServiceHost> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="86a79-114">Create a <xref:System.ServiceModel.ServiceHost> object, as shown in the following code.</span></span>  
  
     [!code-csharp[htSoapWeb#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#2)]
     [!code-vb[htSoapWeb#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#2)]  
  
2.  <span data-ttu-id="86a79-115">다음 코드와 같이 <xref:System.ServiceModel.Description.ServiceEndpoint>을 사용하여 SOAP 끝점에 대해 <xref:System.ServiceModel.BasicHttpBinding>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="86a79-115">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with <xref:System.ServiceModel.BasicHttpBinding> for the SOAP endpoint, as shown in the following code.</span></span>  
  
     [!code-csharp[htSoapWeb#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#3)]
     [!code-vb[htSoapWeb#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#3)]  
  
3.  <span data-ttu-id="86a79-116">그리고 다음 코드와 같이 <xref:System.ServiceModel.Description.ServiceEndpoint>을 사용하여 비 SOAP 끝점에 대해 <xref:System.ServiceModel.WebHttpBinding>를 추가하고 끝점에 <xref:System.ServiceModel.Description.WebHttpBehavior>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="86a79-116">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with <xref:System.ServiceModel.WebHttpBinding> for the non-SOAP endpoint and add the <xref:System.ServiceModel.Description.WebHttpBehavior> to the endpoint, as shown in the following code.</span></span>  
  
     [!code-csharp[htSoapWeb#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#4)]
     [!code-vb[htSoapWeb#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#4)]  
  
4.  <span data-ttu-id="86a79-117">다음 코드와 같이 `Open()` 인스턴스에서 <xref:System.ServiceModel.ServiceHost>을 호출하여 서비스 호스트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="86a79-117">Call `Open()` on a <xref:System.ServiceModel.ServiceHost> instance to open the service host, as shown in the following code.</span></span>  
  
     [!code-csharp[htSoapWeb#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#5)]
     [!code-vb[htSoapWeb#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#5)]  
  
### <a name="to-call-service-operations-mapped-to-get-in-internet-explorer"></a><span data-ttu-id="86a79-118">Internet Explorer에서 GET에 매핑된 서비스 작업을 호출하려면</span><span class="sxs-lookup"><span data-stu-id="86a79-118">To call service operations mapped to GET in Internet Explorer</span></span>  
  
1.  <span data-ttu-id="86a79-119">Internet Explorer를 열고 유형 "`http://localhost:8000/Web/EchoWithGet?s=Hello, world!`" ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="86a79-119">Open Internet Explorer and type "`http://localhost:8000/Web/EchoWithGet?s=Hello, world!`" and press ENTER.</span></span> <span data-ttu-id="86a79-120">URL에는 서비스 기준 주소("http://localhost:8000/"), 끝점 상대 주소(""), 호출할 서비스 작업("EchoWithGet") 및 앰퍼샌드(&)로 구분된 명명된 매개 변수의 목록 앞에 있는 물음표가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="86a79-120">The URL contains the base address of the service ("http://localhost:8000/"), the relative address of the endpoint (""), the service operation to call ("EchoWithGet"), and a question mark followed by a list of named parameters separated by an ampersand (&).</span></span>  
  
### <a name="to-call-service-operations-on-the-web-endpoint-in-code"></a><span data-ttu-id="86a79-121">코드의 웹 끝점에서 서비스 작업을 호출하려면</span><span class="sxs-lookup"><span data-stu-id="86a79-121">To call service operations on the Web endpoint in code</span></span>  
  
1.  <span data-ttu-id="86a79-122">다음 코드와 같이 <xref:System.ServiceModel.Web.WebChannelFactory%601> 블록 내에서 `using` 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="86a79-122">Create an instance of <xref:System.ServiceModel.Web.WebChannelFactory%601> within a `using` block, as shown in the following code.</span></span>  
  
     [!code-csharp[htSoapWeb#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#6)]
     [!code-vb[htSoapWeb#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#6)]  
  
> [!NOTE]
>  <span data-ttu-id="86a79-123">`Close()`는 `using` 블록의 끝에 있는 채널에서 자동으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="86a79-123">`Close()` is automatically called on the channel at the end of the `using` block.</span></span>  
  
1.  <span data-ttu-id="86a79-124">다음 코드와 같이 채널을 만들고 서비스를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="86a79-124">Create the channel and call the service, as shown in the following code.</span></span>  
  
     [!code-csharp[htSoapWeb#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#8)]
     [!code-vb[htSoapWeb#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#8)]  
  
### <a name="to-call-service-operations-on-the-soap-endpoint"></a><span data-ttu-id="86a79-125">SOAP 끝점에서 서비스 작업을 호출하려면</span><span class="sxs-lookup"><span data-stu-id="86a79-125">To call service operations on the SOAP endpoint</span></span>  
  
1.  <span data-ttu-id="86a79-126">다음 코드와 같이 <xref:System.ServiceModel.ChannelFactory> 블록 내에서 `using` 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="86a79-126">Create an instance of <xref:System.ServiceModel.ChannelFactory> within a `using` block, as shown in the following code.</span></span>  
  
     [!code-csharp[htSoapWeb#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#10)]
     [!code-vb[htSoapWeb#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#10)]  
  
2.  <span data-ttu-id="86a79-127">다음 코드와 같이 채널을 만들고 서비스를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="86a79-127">Create the channel and call the service, as shown in the following code.</span></span>  
  
     [!code-csharp[htSoapWeb#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#11)]
     [!code-vb[htSoapWeb#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#11)]  
  
### <a name="to-close-the-service-host"></a><span data-ttu-id="86a79-128">서비스 호스트를 닫으려면</span><span class="sxs-lookup"><span data-stu-id="86a79-128">To close the service host</span></span>  
  
1.  <span data-ttu-id="86a79-129">다음 코드와 같이 서비스 호스트를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="86a79-129">Close the service host, as shown in the following code.</span></span>  
  
     [!code-csharp[htSoapWeb#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#9)]
     [!code-vb[htSoapWeb#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="86a79-130">예제</span><span class="sxs-lookup"><span data-stu-id="86a79-130">Example</span></span>  
 <span data-ttu-id="86a79-131">다음은 이 항목에 해당되는 전체 코드 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="86a79-131">The following is the full code listing for this topic.</span></span>  
  
 [!code-csharp[htSoapWeb#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#13)]
 [!code-vb[htSoapWeb#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#13)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="86a79-132">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="86a79-132">Compiling the Code</span></span>  
 <span data-ttu-id="86a79-133">Service.cs를 컴파일할 때 System.ServiceModel.dll 및 System.ServiceModel.Web.dll을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="86a79-133">When compiling Service.cs, reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86a79-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="86a79-134">See Also</span></span>  
 <xref:System.ServiceModel.WebHttpBinding>  
 <xref:System.ServiceModel.Web.WebGetAttribute>  
 <xref:System.ServiceModel.Web.WebInvokeAttribute>  
 <xref:System.ServiceModel.Web.WebServiceHost>  
 <xref:System.ServiceModel.ChannelFactory>  
 <xref:System.ServiceModel.Description.WebHttpBehavior>  
 [<span data-ttu-id="86a79-135">WCF 웹 HTTP 프로그래밍 모델</span><span class="sxs-lookup"><span data-stu-id="86a79-135">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
