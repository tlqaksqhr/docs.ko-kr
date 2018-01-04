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
ms.workload: dotnet
ms.openlocfilehash: 7c36ac73ced510c1ba3b7e16c71f764c46d6c8f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-service-moniker-with-wsdl-contracts"></a>방법: WSDL 계약을 통해 서비스 모니커 사용
완전히 독립된 COM Interop 클라이언트가 필요한 경우가 있습니다. 호출하려는 서비스에서 MEX 끝점을 노출하지 않을 수도 있고 WCF 클라이언트 DLL이 COM interop에 등록되지 않을 수도 있습니다. 이 경우 서비스를 설명하는 WSDL 파일을 만들어 WCF 서비스 모니커에 전달할 수 있습니다. 이 항목에서는 WCF WSDL 모니커를 사용하여 WCF 시작 샘플을 호출하는 방법에 대해 설명합니다.  
  
### <a name="using-the-wsdl-service-moniker"></a>WSDL 서비스 모니커 사용  
  
1.  GettingStarted 샘플 솔루션을 열고 빌드합니다.  
  
2.  Internet Explorer를 열고 http://localhost/ServiceModelSamples/Service.svc로 이동하여 서비스가 작동하는지 확인합니다.  
  
3.  Service.cs 파일에서 CalculatorService 클래스에 다음 특성을 추가합니다.  
  
     [!code-csharp[S_WSDL_Client#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wsdl_client/cs/service.cs#0)]  
  
4.  서비스 App.config에 바인딩 네임스페이스를 추가합니다.  
  
  
  
5.  응용 프로그램에서 읽을 WSDL 파일을 만듭니다. 3단계와 4단계에서 네임스페이스가 추가되었기 때문에 IE에서 http://localhost/ServiceModelSamples/Service.svc?wsdl로 이동하여 서비스의 WSDL 설명 전체를 쿼리할 수 있습니다. 그런 다음 Internet Explorer에서 serviceWSDL.xml로 파일을 저장할 수 있습니다. 3단계와 4단계에서 네임스페이스를 지정하지 않은 경우 위 URL을 쿼리했을 때 반환되는 WSDL 문서는 전체 WSDL이 아닙니다. 반환되는 WSDL 문서에는 다른 WSDL 문서를 가져오는 몇 개의 import 문이 포함됩니다. 각 import 문을 수행하고 전체 WSDL 문서를 빌드하여 서비스에서 반환되는 WSDL과 가져온 WSDL을 결합해야 합니다.  
  
6.  Visual Basic 6.0을 열고 새 표준 .exe 파일을 만듭니다. 폼에 단추를 추가하고 단추를 두 번 클릭하여 다음 코드를 클릭 처리기에 추가합니다.  
  
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
    >  모니커의 형식이 잘못되었거나 서비스를 사용할 수 없는 경우 `GetObject`를 호출하면 "구문이 잘못되었습니다."라는 오류가 반환됩니다.  이 오류가 발생하면 사용하고 있는 모니커가 올바르고 서비스를 사용할 수 있는지 확인하세요.  
  
7.  Visual Basic 응용 프로그램을 실행합니다. Subtract(145, 76.54)를 호출한 결과가 표시된 메시지 상자가 나타납니다.  
  
## <a name="see-also"></a>참고 항목  
 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [COM 응용 프로그램과 통합 개요](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)
