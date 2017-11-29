---
title: "방법: 메타데이터 교환 계약을 통해 서비스 모니커 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ed6ce9b87a5e2d8945a57110c02cce8024439f14
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a><span data-ttu-id="4f05f-102">방법: 메타데이터 교환 계약을 통해 서비스 모니커 사용</span><span class="sxs-lookup"><span data-stu-id="4f05f-102">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>
<span data-ttu-id="4f05f-103">새 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 개발한 후 처음부터 이러한 서비스를 호출하거나 Visual Basic 6.0 응용 프로그램을 호출하도록 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f05f-103">After developing some new [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services, you may decide that you want to be able to call these services from a script or a Visual Basic 6.0 application.</span></span> <span data-ttu-id="4f05f-104">한 메서드는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 어셈블리를 생성하고, 어셈블리를 COM에 등록하고, GAC에 어셈블리를 설치한 다음 Visual Basic 코드에서 COM 형식을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="4f05f-104">One method would be to generate a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client assembly, register the assembly with COM, install the assembly in the GAC, and then reference the COM types from your Visual Basic code.</span></span> <span data-ttu-id="4f05f-105">응용 프로그램을 배포하는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 어셈블리도 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f05f-105">When you distribute the application, you will have to distribute the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Client assembly as well.</span></span> <span data-ttu-id="4f05f-106">사용자는 WCF 클라이언트 어셈블리를 COM에 등록하고 GAC에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f05f-106">The user will then have to register the WCF client assembly with COM and place it in the GAC.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="4f05f-107"> COM Interop를 사용하면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 어셈블리에 의존하지 않고 동일한 서비스 호출을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f05f-107"> COM Interop also allows you to make the same service calls without relying on a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client assembly.</span></span> <span data-ttu-id="4f05f-108">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 모니커를 사용하면 서비스 모니커가 서비스에 대한 형식 정보를 추출하는 데 사용하는 Mex(메타데이터 교환) 끝점 URI를 지정하여 Visual Basic, VBScript, VBA(Visual Basic for Applications) 등의 COM 호환 언어에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f05f-108">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] moniker allows you to call any [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service from any COM-compatible language (Visual Basic, VBScript, Visual Basic for Applications (VBA), and so on) by specifying a metadata exchange (Mex) endpoint URI that the service moniker uses to extract type information about the service.</span></span> <span data-ttu-id="4f05f-109">이 항목에서는 Mex 끝점을 지정하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 모니커를 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 시작 샘플을 호출하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4f05f-109">This topic describes how to call the Getting Started [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sample using a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] moniker that specifies a Mex endpoint.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f05f-110">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 어셈블리에서 정의된 형식은 실제로 인스턴스화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f05f-110">The types defined by the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client assembly are never actually instantiated.</span></span> <span data-ttu-id="4f05f-111">어셈블리는 메타데이터에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f05f-111">The assembly is used only for metadata.</span></span>  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a><span data-ttu-id="4f05f-112">서비스 모니커에 Mex 주소 사용</span><span class="sxs-lookup"><span data-stu-id="4f05f-112">Using the service moniker with a Mex address</span></span>  
  
1.  <span data-ttu-id="4f05f-113">시작 샘플을 작성하고 Internet Explorer에서 해당 URL(http://localhost/ServiceModelSamples/Service.svc)로 이동하여 서비스가 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4f05f-113">Build the Getting Started sample and use Internet Explorer to browse to its URL (http://localhost/ServiceModelSamples/Service.svc) to ensure that the service is working.</span></span>  
  
2.  <span data-ttu-id="4f05f-114">다음 코드가 포함된 Visual Basic 스크립트 또는 Visual Basic 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4f05f-114">Create a Visual Basic script or Visual Basic application that contains the following code:</span></span>  
  
    ```  
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3.  <span data-ttu-id="4f05f-115">Visual Basic 응용 프로그램 또는 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4f05f-115">Run the Visual Basic application or script.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4f05f-116">모니커가 서비스에서 메타데이터를 읽을 수 있도록 하려면 호출 중인 서비스가 Mex 끝점을 노출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f05f-116">The service you are calling must expose a Mex endpoint for the moniker to be able to read the metadata from the service.</span></span> <span data-ttu-id="4f05f-117">자세한 내용은 참조 [하는 방법: 구성 파일을 사용 하 여 서비스에 대 한 메타 데이터 게시](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4f05f-117">For more information, see [How to: Publish Metadata for a Service Using a Configuration File](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4f05f-118">모니커의 형식이 잘못되었거나 서비스를 사용할 수 없는 경우 `GetObject`를 호출하면 "구문이 잘못되었습니다."라는 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f05f-118">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span>  <span data-ttu-id="4f05f-119">이 오류가 발생하면 사용하고 있는 모니커가 올바르고 서비스를 사용할 수 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="4f05f-119">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f05f-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f05f-120">See Also</span></span>  
 [<span data-ttu-id="4f05f-121">방법: 등록 없이 Windows Communication Foundation 서비스 모니커를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="4f05f-121">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 [<span data-ttu-id="4f05f-122">방법: WSDL 계약을 통해 서비스 모니커 사용</span><span class="sxs-lookup"><span data-stu-id="4f05f-122">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
