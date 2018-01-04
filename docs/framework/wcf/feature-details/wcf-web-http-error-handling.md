---
title: "WCF 웹 HTTP 오류 처리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02891563-0fce-4c32-84dc-d794b1a5c040
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3c5f397d50a5a97801241afd8e64abf2e56b05dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-web-http-error-handling"></a><span data-ttu-id="ac14f-102">WCF 웹 HTTP 오류 처리</span><span class="sxs-lookup"><span data-stu-id="ac14f-102">WCF Web HTTP Error Handling</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="ac14f-103"> 웹 HTTP 오류 처리를 사용하면 HTTP 상태 코드를 지정하고 작업과 동일한 형식(예: XML 또는 JSON)을 사용하여 오류 정보를 반환하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 웹 HTTP 서비스에서 오류를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac14f-103"> Web HTTP error handling enables you to return errors from [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web HTTP services that specify an HTTP status code and return error details using the same format as the operation (for example, XML or JSON).</span></span>  
  
## <a name="wcf-web-http-error-handling"></a><span data-ttu-id="ac14f-104">WCF 웹 HTTP 오류 처리</span><span class="sxs-lookup"><span data-stu-id="ac14f-104">WCF Web HTTP Error Handling</span></span>  
 <span data-ttu-id="ac14f-105"><xref:System.ServiceModel.Web.WebFaultException> 클래스는 HTTP 상태 코드를 지정할 수 있도록 하는 생성자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ac14f-105">The <xref:System.ServiceModel.Web.WebFaultException> class defines a constructor that allows you to specify an HTTP status code.</span></span> <span data-ttu-id="ac14f-106">이 상태 코드는 나중에 클라이언트에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac14f-106">This status code is then returned to the client.</span></span> <span data-ttu-id="ac14f-107"><xref:System.ServiceModel.Web.WebFaultException> 클래스의 제네릭 버전인 <xref:System.ServiceModel.Web.WebFaultException%601>을 사용하면 발생한 오류에 대한 정보가 들어 있는 사용자 정의 형식을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac14f-107">A generic version of the <xref:System.ServiceModel.Web.WebFaultException> class, <xref:System.ServiceModel.Web.WebFaultException%601> enables you to return a user-defined type that contains information about the error that occurred.</span></span> <span data-ttu-id="ac14f-108">이 사용자 지정 개체는 작업에 지정된 형식을 사용하여 serialize되고 클라이언트에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac14f-108">This custom object is serialized using the format specified by the operation and returned to the client.</span></span> <span data-ttu-id="ac14f-109">다음 예제에서는 HTTP 상태 코드를 반환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac14f-109">The following example shows how to return an HTTP status code.</span></span>  
  
```  
Public string Operation1()  
{   // Operation logic  
   // ...  
   Throw new WebFaultException(HttpStatusCode.Forbidden);  
}  
```  
  
 <span data-ttu-id="ac14f-110">다음 예제에서는 HTTP 상태 코드와 추가 정보를 사용자 정의 형식에 반환하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ac14f-110">The following example shows how to return an HTTP status code and extra information in a user-defined type.</span></span> <span data-ttu-id="ac14f-111">`MyErrorDetail`은 발생한 오류에 대한 추가 정보를 포함하는 사용자 정의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ac14f-111">`MyErrorDetail` is a user-defined type that contains extra information about the error that occurred.</span></span>  
  
```  
Public string Operation2()  
   // Operation logic  
   // ...   MyErrorDetail detail = new MyErrorDetail  
   {  
      Message = "Error Message",  
      ErrorCode = 123,  
   }  
   throw new WebFaultException<MyErrorDetail>(detail, HttpStatusCode.Forbidden);  
}  
```  
  
 <span data-ttu-id="ac14f-112">위의 코드에서는 사용할 수 없음 상태 코드 및 `MyErrorDetails` 개체의 인스턴스가 포함된 본문과 함께 HTTP 응답을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ac14f-112">The preceding code returns an HTTP response with the forbidden status code and a body that contains an instance of the `MyErrorDetails` object.</span></span> <span data-ttu-id="ac14f-113">`MyErrorDetails` 개체의 형식은 다음에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac14f-113">The format of the `MyErrorDetails` object is determined by:</span></span>  
  
-   <span data-ttu-id="ac14f-114">서비스 작업에 지정된 `ResponseFormat` 또는 <xref:System.ServiceModel.Web.WebGetAttribute> 특성의 <xref:System.ServiceModel.Web.WebInvokeAttribute> 매개 변수 값</span><span class="sxs-lookup"><span data-stu-id="ac14f-114">The value of the `ResponseFormat` parameter of the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute specified on the service operation.</span></span>  
  
-   <span data-ttu-id="ac14f-115"><xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>의 값</span><span class="sxs-lookup"><span data-stu-id="ac14f-115">The value of <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>.</span></span>  
  
-   <span data-ttu-id="ac14f-116"><xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A>에 액세스하는 <xref:System.ServiceModel.Web.OutgoingWebResponseContext> 속성의 값</span><span class="sxs-lookup"><span data-stu-id="ac14f-116">The value of the <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> property by accessing the <xref:System.ServiceModel.Web.OutgoingWebResponseContext>.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="ac14f-117">이러한 값을에 따른 작업의 형식 참조 [WCF 웹 HTTP 형식 지정](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ac14f-117"> how these values affect the formatting of the operation, see [WCF Web HTTP Formatting](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>  
  
 <span data-ttu-id="ac14f-118"><xref:System.ServiceModel.Web.WebFaultException>은 <xref:System.ServiceModel.FaultException>이므로 SOAP 끝점과 웹 HTTP 끝점을 둘 다 노출하는 서비스의 오류 예외 프로그래밍 모델로 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac14f-118"><xref:System.ServiceModel.Web.WebFaultException> is a <xref:System.ServiceModel.FaultException> and therefore can be used as the fault exception programming model for services that expose SOAP endpoints as well as web HTTP endpoints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac14f-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ac14f-119">See Also</span></span>  
 [<span data-ttu-id="ac14f-120">WCF 웹 HTTP 프로그래밍 모델</span><span class="sxs-lookup"><span data-stu-id="ac14f-120">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="ac14f-121">WCF 웹 HTTP 형식 지정</span><span class="sxs-lookup"><span data-stu-id="ac14f-121">WCF Web HTTP Formatting</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)  
 [<span data-ttu-id="ac14f-122">오류 정의 및 지정</span><span class="sxs-lookup"><span data-stu-id="ac14f-122">Defining and Specifying Faults</span></span>](../../../../docs/framework/wcf/defining-and-specifying-faults.md)  
 [<span data-ttu-id="ac14f-123">예외 및 오류 처리</span><span class="sxs-lookup"><span data-stu-id="ac14f-123">Handling Exceptions and Faults</span></span>](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md)  
 [<span data-ttu-id="ac14f-124">오류 보내기 및 받기</span><span class="sxs-lookup"><span data-stu-id="ac14f-124">Sending and Receiving Faults</span></span>](../../../../docs/framework/wcf/sending-and-receiving-faults.md)
