---
title: "방법: 메타데이터 교환 계약을 통해 서비스 모니커 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# 방법: 메타데이터 교환 계약을 통해 서비스 모니커 사용
새 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 개발한 후 처음부터 이러한 서비스를 호출하거나 Visual Basic 6.0 응용 프로그램을 호출하도록 결정할 수 있습니다.  한 메서드는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 어셈블리를 생성하고, 어셈블리를 COM에 등록하고, GAC에 어셈블리를 설치한 다음 Visual Basic 코드에서 COM 형식을 참조합니다.  응용 프로그램을 배포하는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 어셈블리도 배포해야 합니다.  사용자는 WCF 클라이언트 어셈블리를 COM에 등록하고 GAC에 배치해야 합니다.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] COM Interop를 사용하면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 어셈블리에 의존하지 않고 동일한 서비스 호출을 수행할 수 있습니다.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 모니커를 사용하면 서비스 모니커가 서비스에 대한 형식 정보를 추출하는 데 사용하는 Mex\(메타데이터 교환\) 끝점 URI를 지정하여 Visual Basic, VBScript, VBA\(Visual Basic for Applications\) 등의 COM 호환 언어에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 호출할 수 있습니다.  이 항목에서는 Mex 끝점을 지정하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 모니커를 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 시작 샘플을 호출하는 방법에 대해 설명합니다.  
  
> [!NOTE]
>  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 어셈블리에서 정의된 형식은 실제로 인스턴스화되지 않습니다.  어셈블리는 메타데이터에만 사용됩니다.  
  
### 서비스 모니커에 Mex 주소 사용  
  
1.  시작 샘플을 작성하고 Internet Explorer에서 해당 URL\(http:\/\/localhost\/ServiceModelSamples\/Service.svc\)로 이동하여 서비스가 작동하는지 확인합니다.  
  
2.  다음 코드가 포함된 Visual Basic 스크립트 또는 Visual Basic 응용 프로그램을 만듭니다.  
  
    ```  
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3.  Visual Basic 응용 프로그램 또는 스크립트를 실행합니다.  
  
    > [!NOTE]
    >  모니커가 서비스에서 메타데이터를 읽을 수 있도록 하려면 호출 중인 서비스가 Mex 끝점을 노출해야 합니다.  자세한 내용은 [방법: 구성 파일을 사용하여 서비스의 메타데이터 게시](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)을 참조하세요.  
  
    > [!NOTE]
    >  모니커의 형식이 잘못되었거나 서비스를 사용할 수 없는 경우 `GetObject`를 호출하면 "구문이 잘못되었습니다."라는 오류가 반환됩니다.  이 오류가 발생하면 사용하고 있는 모니커가 올바르고 서비스를 사용할 수 있는지 확인하세요.  
  
## 참고 항목  
 [방법: 등록 없이 Windows Communication Foundation 서비스 모니커 사용](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)   
 [방법: WSDL 계약을 통해 서비스 모니커 사용](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)