---
title: '방법: 메타데이터 교환 계약을 통해 서비스 모니커 사용'
ms.date: 03/30/2017
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
ms.openlocfilehash: 6265860c2e1efb2f74a0243157a223a33889629a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491252"
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a><span data-ttu-id="75386-102">방법: 메타데이터 교환 계약을 통해 서비스 모니커 사용</span><span class="sxs-lookup"><span data-stu-id="75386-102">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>
<span data-ttu-id="75386-103">몇 가지 새 WCF 서비스를 개발한 후 스크립트 또는 Visual Basic 6.0 응용 프로그램에서 이러한 서비스를 호출할 수 것인지 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75386-103">After developing some new WCF services, you may decide that you want to be able to call these services from a script or a Visual Basic 6.0 application.</span></span> <span data-ttu-id="75386-104">한 가지 방법은 WCF 클라이언트 어셈블리를 생성, COM 어셈블리에 등록, GAC에 어셈블리를 설치 및 그런 다음 Visual Basic 코드에서 COM 형식을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75386-104">One method would be to generate a WCF client assembly, register the assembly with COM, install the assembly in the GAC, and then reference the COM types from your Visual Basic code.</span></span> <span data-ttu-id="75386-105">응용 프로그램을 배포할 때에 WCF 클라이언트 어셈블리를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75386-105">When you distribute the application, you will have to distribute the WCF Client assembly as well.</span></span> <span data-ttu-id="75386-106">사용자는 WCF 클라이언트 어셈블리를 COM에 등록하고 GAC에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75386-106">The user will then have to register the WCF client assembly with COM and place it in the GAC.</span></span> <span data-ttu-id="75386-107">또한 WCF COM Interop을 사용 하면 WCF 클라이언트 어셈블리에 의존 하지 않고 동일한 서비스 호출을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75386-107">WCF COM Interop also allows you to make the same service calls without relying on a WCF client assembly.</span></span> <span data-ttu-id="75386-108">WCF 모니커를 사용 하면 메타 데이터 교환 (Mex) 끝점 서비스 모니커를 사용 하 여 추출 형식 URI를 지정 하 여 모든 COM 호환 언어 (Visual Basic, VBScript, VBA, 등에 대 한 Visual Basic)에서 WCF 서비스를 호출할 수 있습니다. 서비스에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="75386-108">The WCF moniker allows you to call any WCF service from any COM-compatible language (Visual Basic, VBScript, Visual Basic for Applications (VBA), and so on) by specifying a metadata exchange (Mex) endpoint URI that the service moniker uses to extract type information about the service.</span></span> <span data-ttu-id="75386-109">이 항목에서는 Mex 끝점을 지정 하는 WCF 모니커를 사용 하 여 WCF 시작 샘플을 호출 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="75386-109">This topic describes how to call the Getting Started WCF sample using a WCF moniker that specifies a Mex endpoint.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="75386-110">WCF 클라이언트 어셈블리에 의해 정의 된 형식은 실제로 인스턴스화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75386-110">The types defined by the WCF client assembly are never actually instantiated.</span></span> <span data-ttu-id="75386-111">어셈블리는 메타데이터에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="75386-111">The assembly is used only for metadata.</span></span>  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a><span data-ttu-id="75386-112">서비스 모니커에 Mex 주소 사용</span><span class="sxs-lookup"><span data-stu-id="75386-112">Using the service moniker with a Mex address</span></span>  
  
1.  <span data-ttu-id="75386-113">Getting Started 샘플을 빌드 및 Internet Explorer를 사용 하 여 해당 URL로 이동 (http://localhost/ServiceModelSamples/Service.svc) 서비스가 작동 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="75386-113">Build the Getting Started sample and use Internet Explorer to browse to its URL (http://localhost/ServiceModelSamples/Service.svc) to ensure that the service is working.</span></span>  
  
2.  <span data-ttu-id="75386-114">다음 코드가 포함된 Visual Basic 스크립트 또는 Visual Basic 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="75386-114">Create a Visual Basic script or Visual Basic application that contains the following code:</span></span>  
  
    ```  
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3.  <span data-ttu-id="75386-115">Visual Basic 응용 프로그램 또는 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="75386-115">Run the Visual Basic application or script.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="75386-116">모니커가 서비스에서 메타데이터를 읽을 수 있도록 하려면 호출 중인 서비스가 Mex 끝점을 노출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75386-116">The service you are calling must expose a Mex endpoint for the moniker to be able to read the metadata from the service.</span></span> <span data-ttu-id="75386-117">자세한 내용은 참조 [하는 방법: 구성 파일을 사용 하 여 서비스에 대 한 메타 데이터 게시](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="75386-117">For more information, see [How to: Publish Metadata for a Service Using a Configuration File](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="75386-118">모니커의 형식이 잘못되었거나 서비스를 사용할 수 없는 경우 `GetObject`를 호출하면 "구문이 잘못되었습니다."라는 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="75386-118">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span>  <span data-ttu-id="75386-119">이 오류가 발생하면 사용하고 있는 모니커가 올바르고 서비스를 사용할 수 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="75386-119">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75386-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="75386-120">See Also</span></span>  
 [<span data-ttu-id="75386-121">방법: 등록 없이 Windows Communication Foundation 서비스 모니커 사용</span><span class="sxs-lookup"><span data-stu-id="75386-121">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 [<span data-ttu-id="75386-122">방법: WSDL 계약을 통해 서비스 모니커 사용</span><span class="sxs-lookup"><span data-stu-id="75386-122">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
