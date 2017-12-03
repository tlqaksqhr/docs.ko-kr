---
title: "방법: WSDL 계약을 통해 서비스 모니커 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a88d9650-bb50-4f48-8c85-12f5ce98a83a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c44b09f512a7625360ca5036316d03a4602c5186
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-use-a-service-moniker-with-wsdl-contracts"></a><span data-ttu-id="787d7-102">방법: WSDL 계약을 통해 서비스 모니커 사용</span><span class="sxs-lookup"><span data-stu-id="787d7-102">How to: Use a Service Moniker with WSDL Contracts</span></span>
<span data-ttu-id="787d7-103">완전히 독립된 COM Interop 클라이언트가 필요한 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="787d7-103">There are situations when you may want to have a completely self-contained COM Interop client.</span></span> <span data-ttu-id="787d7-104">호출하려는 서비스에서 MEX 끝점을 노출하지 않을 수도 있고 WCF 클라이언트 DLL이 COM interop에 등록되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="787d7-104">The service you want to call may not expose a MEX endpoint, and the WCF client DLL may not be registered for COM interop.</span></span> <span data-ttu-id="787d7-105">이 경우 서비스를 설명하는 WSDL 파일을 만들어 WCF 서비스 모니커에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="787d7-105">In these cases, you can create a WSDL file that describes the service and pass it into the WCF service moniker.</span></span> <span data-ttu-id="787d7-106">이 항목에서는 WCF WSDL 모니커를 사용하여 WCF 시작 샘플을 호출하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="787d7-106">This topic describes how to call the Getting Started WCF sample using a WCF WSDL moniker.</span></span>  
  
### <a name="using-the-wsdl-service-moniker"></a><span data-ttu-id="787d7-107">WSDL 서비스 모니커 사용</span><span class="sxs-lookup"><span data-stu-id="787d7-107">Using the WSDL service moniker</span></span>  
  
1.  <span data-ttu-id="787d7-108">GettingStarted 샘플 솔루션을 열고 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="787d7-108">Open and build the GettingStarted sample solution.</span></span>  
  
2.  <span data-ttu-id="787d7-109">Internet Explorer를 열고 http://localhost/ServiceModelSamples/Service.svc로 이동하여 서비스가 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="787d7-109">Open Internet Explorer and browse to http://localhost/ServiceModelSamples/Service.svc to make sure that the service is working.</span></span>  
  
3.  <span data-ttu-id="787d7-110">Service.cs 파일에서 CalculatorService 클래스에 다음 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="787d7-110">In the Service.cs file, add the following attribute on the CalculatorService class:</span></span>  
  
     [!code-csharp[S_WSDL_Client#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wsdl_client/cs/service.cs#0)]  
  
4.  <span data-ttu-id="787d7-111">서비스 App.config에 바인딩 네임스페이스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="787d7-111">Add a binding namespace to the service App.config:</span></span>  
  
  
  
5.  <span data-ttu-id="787d7-112">응용 프로그램에서 읽을 WSDL 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="787d7-112">Create a WSDL file for the application to read.</span></span> <span data-ttu-id="787d7-113">3단계와 4단계에서 네임스페이스가 추가되었기 때문에 IE에서 http://localhost/ServiceModelSamples/Service.svc?wsdl로 이동하여 서비스의 WSDL 설명 전체를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="787d7-113">Because the namespaces were added in steps 3 and 4, you can use IE to query for the entire WSDL description of the service by browsing to http://localhost/ServiceModelSamples/Service.svc?wsdl.</span></span> <span data-ttu-id="787d7-114">그런 다음 Internet Explorer에서 serviceWSDL.xml로 파일을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="787d7-114">You can then save the file from Internet Explorer as serviceWSDL.xml.</span></span> <span data-ttu-id="787d7-115">3단계와 4단계에서 네임스페이스를 지정하지 않은 경우 위 URL을 쿼리했을 때 반환되는 WSDL 문서는 전체 WSDL이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="787d7-115">If you do not specify the namespaces in steps 3 and 4, the WSDL document returned from querying the above URL will not be the complete WSDL.</span></span> <span data-ttu-id="787d7-116">반환되는 WSDL 문서에는 다른 WSDL 문서를 가져오는 몇 개의 import 문이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="787d7-116">The WSDL document returned will include several import statements that import other WSDL documents.</span></span> <span data-ttu-id="787d7-117">각 import 문을 수행하고 전체 WSDL 문서를 빌드하여 서비스에서 반환되는 WSDL과 가져온 WSDL을 결합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="787d7-117">You will have to go through each import statement and build the complete WSDL document, combining the WSDL returned from the service with the WSDL imported.</span></span>  
  
6.  <span data-ttu-id="787d7-118">Visual Basic 6.0을 열고 새 표준 .exe 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="787d7-118">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="787d7-119">폼에 단추를 추가하고 단추를 두 번 클릭하여 다음 코드를 클릭 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="787d7-119">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```  
    ' Open the WSDL contract file and read it all into the wsdlContract string.  
    Const ForReading = 1  
    Set objFSO = CreateObject("Scripting.FileSystemObject")  
    Set objFile = objFSO.OpenTextFile("c:\serviceWsdl.xml", ForReading)  
    wsdlContract = objFile.ReadAll  
    objFile.Close  
  
    ' Create a string for the service moniker including the content of the WSDL contract file.  
    wsdlMonikerString = "service4:address='http://localhost/ServiceModelSamples/service.svc'"  
    wsdlMonikerString = wsdlMonikerString + ", wsdl='" & wsdlContract & "'"  
    wsdlMonikerString = wsdlMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
    wsdlMonikerString = wsdlMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
    ' Create the service moniker object.  
    Set wsdlServiceMoniker = GetObject(wsdlMonikerString)  
  
    ' Call the service operations using the moniker object.  
    MsgBox "WSDL service moniker: 145 - 76.54 = " & wsdlServiceMoniker.Subtract(145, 76.54)  
    ```  
  
    > [!NOTE]
    >  모니커의 형식이 잘못되었거나 서비스를 사용할 수 없는 경우 `GetObject`를 호출하면 "구문이 잘못되었습니다."라는 오류가 반환됩니다.  <span data-ttu-id="787d7-121">이 오류가 발생하면 사용하고 있는 모니커가 올바르고 서비스를 사용할 수 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="787d7-121">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
7.  <span data-ttu-id="787d7-122">Visual Basic 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="787d7-122">Run the Visual Basic application.</span></span> <span data-ttu-id="787d7-123">Subtract(145, 76.54)를 호출한 결과가 표시된 메시지 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="787d7-123">A message box will be displayed with the results of calling Subtract(145, 76.54).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="787d7-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="787d7-124">See Also</span></span>  
 [<span data-ttu-id="787d7-125">시작</span><span class="sxs-lookup"><span data-stu-id="787d7-125">Getting Started</span></span>](../../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="787d7-126">COM 응용 프로그램 개요와 통합</span><span class="sxs-lookup"><span data-stu-id="787d7-126">Integrating with COM Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)
