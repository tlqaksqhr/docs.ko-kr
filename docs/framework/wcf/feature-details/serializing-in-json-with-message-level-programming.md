---
title: "메시지 수준의 프로그래밍으로 JSON으로 serialize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bfa8952c54f29d88cb4975c1924b9c3e94c1c226
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="serializing-in-json-with-message-level-programming"></a><span data-ttu-id="dfbb4-102">메시지 수준의 프로그래밍으로 JSON으로 serialize</span><span class="sxs-lookup"><span data-stu-id="dfbb4-102">Serializing in Json with Message Level Programming</span></span>
<span data-ttu-id="dfbb4-103">WCF는 JSON 형식의 데이터 serialize를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="dfbb4-103">WCF supports serializing data in JSON format.</span></span> <span data-ttu-id="dfbb4-104">이 항목에서는 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>를 사용하여 WCF가 형식을 serialize하도록 하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dfbb4-104">This topic describes how to tell WCF to serialize your types using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
## <a name="typed-message-programming"></a><span data-ttu-id="dfbb4-105">형식화된 메시지 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="dfbb4-105">Typed Message Programming</span></span>  
 <span data-ttu-id="dfbb4-106">서비스 작업에 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 또는 <xref:System.ServiceModel.Web.WebGetAttribute>가 적용되면 <xref:System.ServiceModel.Web.WebInvokeAttribute>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dfbb4-106">The <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> is used when the <xref:System.ServiceModel.Web.WebGetAttribute> or the <xref:System.ServiceModel.Web.WebInvokeAttribute> is applied to a service operation.</span></span> <span data-ttu-id="dfbb4-107">두 특성을 사용하여 `RequestFormat` 및 `ResponseFormat`을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfbb4-107">Both of these attributes allow you to specify the `RequestFormat` and `ResponseFormat`.</span></span> <span data-ttu-id="dfbb4-108">요청 및 응답에 JSON을 사용하려면 둘 다 `WebMessageFormat.Json`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dfbb4-108">To use JSON for requests and responses set both of these to `WebMessageFormat.Json`.</span></span>  <span data-ttu-id="dfbb4-109">JSON을 사용하려면 <xref:System.ServiceModel.WebHttpBinding>를 자동으로 구성하는 <xref:System.ServiceModel.Description.WebHttpBehavior>을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfbb4-109">In order to use JSON you must use the <xref:System.ServiceModel.WebHttpBinding> which automatically configures the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span> <span data-ttu-id="dfbb4-110">WCF 직렬화에 대 한 자세한 내용은 참조: [Serialization 및 Deserialization](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md), [Windows Communication Foundation 직렬화](http://msdn.microsoft.com/magazine/cc163569.aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="dfbb4-110">For more information about WCF serialization, see: [Serialization and Deserialization](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md), [Serialization in Windows Communication Foundation](http://msdn.microsoft.com/magazine/cc163569.aspx).</span></span> <span data-ttu-id="dfbb4-111">JSON 및 WCF에 대 한 자세한 내용은 참조 [WCF 사용한 RESTfull 서비스 소개](http://msdn.microsoft.com/magazine/dd315413.aspx), [.NET 3.5에서 만드는 JSON 사용 WCF 서비스](http://www.pluralsight-training.net/community/blogs/fritz/archive/2008/01/31/50121.aspx), 및 [WCF의REST개요](http://msdn.microsoft.com/netframework/dd547388).</span><span class="sxs-lookup"><span data-stu-id="dfbb4-111">For more information about JSON and WCF see [An Introduction to RESTfull Services with WCF](http://msdn.microsoft.com/magazine/dd315413.aspx), [Creating JSON-enabled WCF Services in .NET 3.5](http://www.pluralsight-training.net/community/blogs/fritz/archive/2008/01/31/50121.aspx), and [Overview of REST in WCF](http://msdn.microsoft.com/netframework/dd547388).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dfbb4-112">JSON을 사용하려면 SOAP 통신을 지원하지 않는 <xref:System.ServiceModel.WebHttpBinding> 및 <xref:System.ServiceModel.Description.WebHttpBehavior>를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfbb4-112">Using JSON requires use of <xref:System.ServiceModel.WebHttpBinding> and <xref:System.ServiceModel.Description.WebHttpBehavior> which do not support SOAP communication.</span></span> <span data-ttu-id="dfbb4-113">와 통신 하는 서비스는 <xref:System.ServiceModel.WebHttpBinding> Visual Studio 서비스 참조 추가 기능 또는 svcutil 명령줄 도구를 사용 하 여 클라이언트 측 프록시를 생성할 수 서비스 메타 데이터 노출을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dfbb4-113">Services that communicate with the <xref:System.ServiceModel.WebHttpBinding> do not support exposing service metadata so you will not be able to use Visual Studio’s Add Service Reference functionality or the svcutil command-line tool to generate a client-side proxy.</span></span> <span data-ttu-id="dfbb4-114">자세한 내용은 사용 하는 서비스 프로그래밍 방식으로 호출 하는 방법을 <xref:System.ServiceModel.WebHttpBinding>, 참조 [wcf REST 서비스를 사용 하는 방법을](http://blogs.msdn.com/b/pedram/archive/2008/04/21/how-to-consume-rest-services-with-wcf.aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="dfbb4-114">For more information how you can programmatically call services that use <xref:System.ServiceModel.WebHttpBinding>, see [How to Consume REST Services with WCF](http://blogs.msdn.com/b/pedram/archive/2008/04/21/how-to-consume-rest-services-with-wcf.aspx).</span></span>  
  
## <a name="untyped-message-programming"></a><span data-ttu-id="dfbb4-115">형식화되지 않은 메시지 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="dfbb4-115">Untyped Message Programming</span></span>  
 <span data-ttu-id="dfbb4-116">형식화되지 않은 메시기 개체로 직접 작업할 때는 형식화되지 않은 메시지의 속성을 명시적으로 설정하여 JSON으로 serialize해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfbb4-116">When working directly with untyped Message objects, you must explicitly set the properties on the untyped message to serialize it as JSON.</span></span> <span data-ttu-id="dfbb4-117">다음 코드 조각에서는 이를 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dfbb4-117">The following code snippet shows how to do this.</span></span>  
  
```  
 Message response = Message.CreateMessage(  
                  MessageVersion.None,    // No SOAP message version  
                             "*",                     // SOAP action, ignored since this is JSON  
                             "Response string: JSON format specified", // Message body  
                             new DataContractJsonSerializer(typeof(string))); // Specify DataContractJsonSerializer  
      response.Properties.Add( WebBodyFormatMessageProperty.Name,   
                    new WebBodyFormatMessageProperty(WebContentFormat.Json)); // Use JSON format  
```  
  
## <a name="see-also"></a><span data-ttu-id="dfbb4-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dfbb4-118">See Also</span></span>  
 [<span data-ttu-id="dfbb4-119">AJAX 통합 및 JSON 지원</span><span class="sxs-lookup"><span data-stu-id="dfbb4-119">AJAX Integration and JSON Support</span></span>](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [<span data-ttu-id="dfbb4-120">독립 실행형 JSON Serialization</span><span class="sxs-lookup"><span data-stu-id="dfbb4-120">Stand-Alone JSON Serialization</span></span>](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)  
 [<span data-ttu-id="dfbb4-121">JSON Serialization</span><span class="sxs-lookup"><span data-stu-id="dfbb4-121">JSON Serialization</span></span>](../../../../docs/framework/wcf/samples/json-serialization.md)
