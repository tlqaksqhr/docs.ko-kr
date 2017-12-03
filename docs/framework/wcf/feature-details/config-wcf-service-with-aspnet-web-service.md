---
title: "방법: ASP.NET 웹 서비스 클라이언트와 상호 운용하도록 WCF 서비스 구성"
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
ms.assetid: 48e1cd90-de80-4d6c-846e-631878955762
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7ed4bf8e86e727505d48e85bb55a88452217c76b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-configure-wcf-service-to-interoperate-with-aspnet-web-service-clients"></a><span data-ttu-id="946f9-102">방법: ASP.NET 웹 서비스 클라이언트와 상호 운용하도록 WCF 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="946f9-102">How to: Configure WCF Service to Interoperate with ASP.NET Web Service Clients</span></span>
<span data-ttu-id="946f9-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 웹 서비스 클라이언트와 상호 운용 가능하도록 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 서비스 끝점을 구성하려면 <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> 형식을 서비스 끝점의 바인딩 형식으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="946f9-103">To configure a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service endpoint to be interoperable with [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web service clients, use the <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> type as the binding type for your service endpoint.</span></span>  
  
 <span data-ttu-id="946f9-104">바인딩에서 HTTPS 및 전송 수준 클라이언트 인증에 대한 지원을 선택적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="946f9-104">You can optionally enable support for HTTPS and transport-level client authentication on the binding.</span></span> [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="946f9-105"> 웹 서비스 클라이언트는 MTOM 메시지 인코딩을 지원하지 않기 때문에 <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> 속성을 기본값인 <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType>로 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="946f9-105"> Web service clients do not support MTOM message encoding, so the <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> property should be left as its default value, which is <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType>.</span></span> <span data-ttu-id="946f9-106">ASP.Net 웹 서비스 클라이언트는 WS-Security를 지원하지 않기 때문에 <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType>를 <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="946f9-106">ASP.Net Web Service clients do not support WS-Security, so the <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> should be set to <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>.</span></span>  
  
 <span data-ttu-id="946f9-107">에 대 한 메타 데이터를 확인 하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 를 사용할 수 있는 서비스 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 웹 서비스 프록시 생성 도구 (즉, [웹 서비스 설명 언어 도구 (Wsdl.exe)](http://go.microsoft.com/fwlink/?LinkId=73833), [웹 서비스 검색 도구 ( Disco.exe)](http://go.microsoft.com/fwlink/?LinkId=73834), 및 Visual Studio에서 웹 참조 추가 기능), HTTP/GET 메타 데이터 끝점을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="946f9-107">To make the metadata for a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service available to [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web service proxy generation tools (that is, [Web Services Description Language Tool (Wsdl.exe)](http://go.microsoft.com/fwlink/?LinkId=73833), [Web Services Discovery Tool (Disco.exe)](http://go.microsoft.com/fwlink/?LinkId=73834), and the Add Web Reference feature in Visual Studio), you should expose an HTTP/GET metadata endpoint.</span></span>  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-code"></a><span data-ttu-id="946f9-108">코드에서 ASP.NET 웹 서비스 클라이언트와 호환되는 WCF 끝점을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="946f9-108">To add a WCF endpoint that is compatible with ASP.NET Web service clients in code</span></span>  
  
1.  <span data-ttu-id="946f9-109">새 <xref:System.ServiceModel.BasicHttpBinding> 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="946f9-109">Create a new <xref:System.ServiceModel.BasicHttpBinding> instance</span></span>  
  
2.  <span data-ttu-id="946f9-110">바인딩의 보안 모드를 <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>로 설정하여 이 서비스 끝점 바인딩에 대한 전송 보안을 선택적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="946f9-110">Optionally enable transport security for this service endpoint binding by setting the security mode for the binding to <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>.</span></span> <span data-ttu-id="946f9-111">자세한 내용은 참조 하세요 [전송 보안](../../../../docs/framework/wcf/feature-details/transport-security.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="946f9-111">For details, please see [Transport Security](../../../../docs/framework/wcf/feature-details/transport-security.md).</span></span>  
  
3.  <span data-ttu-id="946f9-112">방금 만든 바인딩 인스턴스를 사용하여 새 응용 프로그램 끝점을 서비스 호스트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="946f9-112">Add a new application endpoint to your service host using the binding instance that you just created.</span></span> <span data-ttu-id="946f9-113">코드에서 서비스 끝점을 추가 하는 방법에 대 한 세부 정보를 참조 하십시오.는 [하는 방법: 코드에서 서비스 끝점을 만드는](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="946f9-113">For details about how to add a service endpoint in code, see the [How to: Create a Service Endpoint in Code](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).</span></span>  
  
4.  <span data-ttu-id="946f9-114">서비스에 대해 HTTP/GET 메타데이터 끝점을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="946f9-114">Enable an HTTP/GET metadata endpoint for your service.</span></span> <span data-ttu-id="946f9-115">자세한 내용은 [하는 방법: 서비스를 사용 하 여 코드에 대 한 메타 데이터 게시](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="946f9-115">For details see [How to: Publish Metadata for a Service Using Code](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).</span></span>  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-a-configuration-file"></a><span data-ttu-id="946f9-116">구성 파일에서 ASP.NET 웹 서비스 클라이언트와 호환되는 WCF 끝점을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="946f9-116">To add a WCF endpoint that is compatible with ASP.NET Web service clients in a configuration file</span></span>  
  
1.  <span data-ttu-id="946f9-117">새 <xref:System.ServiceModel.BasicHttpBinding> 바인딩 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="946f9-117">Create a new <xref:System.ServiceModel.BasicHttpBinding> binding configuration.</span></span> <span data-ttu-id="946f9-118">자세한 내용은 참조는 [하는 방법: 구성에서 서비스 바인딩 지정](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="946f9-118">For details, see the [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
2.  <span data-ttu-id="946f9-119">바인딩의 보안 모드를 <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>로 설정하여 이 서비스 끝점 바인딩 구성에 대한 전송 보안을 선택적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="946f9-119">Optionally enable transport security for this service endpoint binding configuration by setting the security mode for the binding to <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>.</span></span> <span data-ttu-id="946f9-120">자세한 내용은 참조 [전송 보안](../../../../docs/framework/wcf/feature-details/transport-security.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="946f9-120">For details, see [Transport Security](../../../../docs/framework/wcf/feature-details/transport-security.md).</span></span>  
  
3.  <span data-ttu-id="946f9-121">방금 만든 바인딩 구성을 사용하여 서비스에 대한 새 응용 프로그램 끝점을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="946f9-121">Configure a new application endpoint for your service using the binding configuration that you just created.</span></span> <span data-ttu-id="946f9-122">구성 파일에서 서비스 끝점을 추가 하는 방법에 대 한 세부 정보를 참조 하십시오.는 [하는 방법: 구성에서 서비스 끝점을 만드는](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="946f9-122">For details about how to add a service endpoint in a configuration file, see the [How to: Create a Service Endpoint in Configuration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).</span></span>  
  
4.  <span data-ttu-id="946f9-123">서비스에 대해 HTTP/GET 메타데이터 끝점을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="946f9-123">Enable an HTTP/GET metadata endpoint for your service.</span></span> <span data-ttu-id="946f9-124">자세한 내용은 참조는 [하는 방법: 구성 파일을 사용 하 여 서비스에 대 한 메타 데이터 게시](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="946f9-124">For details see the [How to: Publish Metadata for a Service Using a Configuration File](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="946f9-125">예제</span><span class="sxs-lookup"><span data-stu-id="946f9-125">Example</span></span>  
 <span data-ttu-id="946f9-126">다음 예제 코드에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 웹 서비스 클라이언트와 호환되는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 끝점을 코드 또는 구성 파일에 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="946f9-126">The following example code demonstrates how to add a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint that is compatible with [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web service clients in code and alternatively in configuration files.</span></span>  
  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)] 
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)] 
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]     
  
## <a name="see-also"></a><span data-ttu-id="946f9-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="946f9-127">See Also</span></span>  
 [<span data-ttu-id="946f9-128">방법: 코드에서 서비스 끝점 만들기</span><span class="sxs-lookup"><span data-stu-id="946f9-128">How to: Create a Service Endpoint in Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 [<span data-ttu-id="946f9-129">방법: 코드를 사용 하 여 서비스에 대 한 메타 데이터를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="946f9-129">How to: Publish Metadata for a Service Using Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 [<span data-ttu-id="946f9-130">방법: 구성에서 서비스 바인딩 지정</span><span class="sxs-lookup"><span data-stu-id="946f9-130">How to: Specify a Service Binding in Configuration</span></span>](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)  
 [<span data-ttu-id="946f9-131">방법: 구성에서 서비스 끝점 만들기</span><span class="sxs-lookup"><span data-stu-id="946f9-131">How to: Create a Service Endpoint in Configuration</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 [<span data-ttu-id="946f9-132">방법: 구성 파일을 사용 하 여 서비스에 대 한 메타 데이터를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="946f9-132">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="946f9-133">전송 보안</span><span class="sxs-lookup"><span data-stu-id="946f9-133">Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [<span data-ttu-id="946f9-134">메타 데이터 사용</span><span class="sxs-lookup"><span data-stu-id="946f9-134">Using Metadata</span></span>](../../../../docs/framework/wcf/feature-details/using-metadata.md)
