---
title: "WebContentTypeMapper 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4fe59e7-44d8-43c6-a1f8-40c45223adca
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 34adf191d3edbff33fe989cf036c32104a6754ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="webcontenttypemapper-sample"></a><span data-ttu-id="16865-102">WebContentTypeMapper 샘플</span><span class="sxs-lookup"><span data-stu-id="16865-102">WebContentTypeMapper Sample</span></span>
<span data-ttu-id="16865-103">이 샘플에서는 새 콘텐츠 형식을 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 메시지 본문 형식에 매핑하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="16865-103">This sample demonstrates how to map new content types to [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] message body formats.</span></span>  
  
 <span data-ttu-id="16865-104"><xref:System.ServiceModel.Description.WebHttpEndpoint> 요소가 웹 메시지 인코더에 플러그 인되므로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 동일한 끝점에서 JSON, XML 또는 원시 이진 메시지를 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16865-104">The <xref:System.ServiceModel.Description.WebHttpEndpoint> element plugs in the Web message encoder, which allows [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to receive JSON, XML, or raw binary messages at the same endpoint.</span></span> <span data-ttu-id="16865-105">인코더는 요청의 HTTP 콘텐츠 형식을 확인하여 메시지의 본문 형식을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="16865-105">The encoder determines the body format of the message by looking at the HTTP content-type of the request.</span></span> <span data-ttu-id="16865-106">이 샘플에서는 콘텐츠 형식과 본문 형식 간의 매핑을 사용자가 제어할 수 있게 하는 <xref:System.ServiceModel.Channels.WebContentTypeMapper> 클래스를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="16865-106">This sample introduces the <xref:System.ServiceModel.Channels.WebContentTypeMapper> class, which allows the user to control the mapping between content type and body format.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="16865-107">는 콘텐츠 형식에 대한 기본 매핑 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="16865-107"> provides a set of default mappings for content types.</span></span> <span data-ttu-id="16865-108">예를 들어, `application/json`은  JSON에 매핑되고 `text/xml`은 XML에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="16865-108">For example, `application/json` maps to JSON and `text/xml` maps to XML.</span></span> <span data-ttu-id="16865-109">JSON 또는 XML에 매핑되지 않는 모든 콘텐츠 형식은 원시 이진 형식에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="16865-109">Any content type that is not mapped to JSON or XML is mapped to raw binary format.</span></span>  
  
 <span data-ttu-id="16865-110">푸시 스타일 API와 같은 일부 시나리오에서 서비스 개발자는 클라이언트가 반환하는 콘텐츠 형식을 제어하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="16865-110">In some scenarios (for example, push-style APIs), the service developer does not control the content type returned by the client.</span></span> <span data-ttu-id="16865-111">예를 들어, 클라이언트가 JSON을 `text/javascript` 대신에 `application/json`로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16865-111">For example, clients might return JSON as `text/javascript` instead of `application/json`.</span></span> <span data-ttu-id="16865-112">이 경우 서비스 개발자는 다음 샘플 코드와 같이 지정된 콘텐츠 형식을 올바르게 처리하기 위해 <xref:System.ServiceModel.Channels.WebContentTypeMapper>에서 파생되는 형식을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16865-112">In this case, the service developer must provide a type that derives from <xref:System.ServiceModel.Channels.WebContentTypeMapper> to handle the given content type correctly, as shown in the following sample code.</span></span>  
  
```  
public class JsonContentTypeMapper : WebContentTypeMapper  
{  
    public override WebContentFormat  
               GetMessageFormatForContentType(string contentType)  
    {  
        if (contentType == "text/javascript")  
        {  
            return WebContentFormat.Json;  
        }  
        else  
        {  
            return WebContentFormat.Default;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="16865-113">이 형식은 <xref:System.ServiceModel.Channels.WebContentTypeMapper.GetMessageFormatForContentType%28System.String%29> 메서드를 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16865-113">The type must override the <xref:System.ServiceModel.Channels.WebContentTypeMapper.GetMessageFormatForContentType%28System.String%29> method.</span></span> <span data-ttu-id="16865-114">이 메서드는 `contentType` 인수를 평가하고 <xref:System.ServiceModel.Channels.WebContentFormat.Json>, <xref:System.ServiceModel.Channels.WebContentFormat.Xml>, <xref:System.ServiceModel.Channels.WebContentFormat.Raw> 또는 <xref:System.ServiceModel.Channels.WebContentFormat.Default> 값 중 하나를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16865-114">The method must evaluate the `contentType` argument and return one of the following values: <xref:System.ServiceModel.Channels.WebContentFormat.Json>, <xref:System.ServiceModel.Channels.WebContentFormat.Xml>, <xref:System.ServiceModel.Channels.WebContentFormat.Raw>, or <xref:System.ServiceModel.Channels.WebContentFormat.Default>.</span></span> <span data-ttu-id="16865-115"><xref:System.ServiceModel.Channels.WebContentFormat.Default> 반환은 기본 웹 메시지 인코더 매핑을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="16865-115">Returning <xref:System.ServiceModel.Channels.WebContentFormat.Default> defers to the default Web message encoder mappings.</span></span> <span data-ttu-id="16865-116">위의 샘플 코드에서 `text/javascript` 콘텐츠 형식은 JSON에 매핑되고 다른 모든 매핑은 변경되지 않은 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="16865-116">In the previous sample code, the `text/javascript` content type is mapped to JSON, and all other mappings remain unchanged.</span></span>  
  
 <span data-ttu-id="16865-117">`JsonContentTypeMapper` 클래스를 사용하여 Web.config에서 다음을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="16865-117">To use the `JsonContentTypeMapper` class, use the following in your Web.config:</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>  
    <webHttpEndpoint>  
      <standardEndpoint name="" contentTypeMapper="Microsoft.Samples.WebContentTypeMapper.JsonContentTypeMapper, JsonContentTypeMapper, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
    </webHttpEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="16865-118">JsonContentTypeMapper 사용을 위한 요구 사항을 확인하려면 위의 구성 파일에서 contentTypeMapper 특성을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="16865-118">To verify the requirement for using the JsonContentTypeMapper, remove the contentTypeMapper attribute from the above configuration file.</span></span> <span data-ttu-id="16865-119">그러면 `text/javascript`를 사용하여 JSON 콘텐츠를 보내려고 할 때 클라이언트 페이지를 로드하는 데 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="16865-119">The client page fails to load when attempting to use `text/javascript` to send JSON content.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="16865-120">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="16865-120">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="16865-121">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="16865-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="16865-122">에 설명 된 대로 WebContentTypeMapperSample.sln 솔루션을 구축 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="16865-122">Build the solution WebContentTypeMapperSample.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="16865-123">http://localhost/ServiceModelSamples/JCTMClientPage.htm으로 이동합니다. 프로젝트 디렉터리 내에서 브라우저를 사용하여 JCTMClientPage.htm을 열지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="16865-123">Navigate to http://localhost/ServiceModelSamples/JCTMClientPage.htm (do not open JCTMClientPage.htm in the browser from within the project directory).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="16865-124">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16865-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="16865-125">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="16865-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="16865-126">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="16865-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="16865-127">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16865-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Ajax\WebContentTypeMapper`  
  
## <a name="see-also"></a><span data-ttu-id="16865-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16865-128">See Also</span></span>
