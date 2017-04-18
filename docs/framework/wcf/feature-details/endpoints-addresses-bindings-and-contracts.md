---
title: "끝점: 주소, 바인딩 및 계약 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "끝점 [WCF]"
  - "WCF [WCF], 끝점"
  - "Windows Communication Foundation [WCF], 끝점"
ms.assetid: 9ddc46ee-1883-4291-9926-28848c57e858
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# 끝점: 주소, 바인딩 및 계약
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스와의 모든 통신은 서비스의 *끝점*을 통해 발생합니다.끝점은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서 제공하는 기능에 대한 클라이언트 액세스를 제공합니다.  
  
 각 끝점은 다음 네 가지 속성으로 구성됩니다.  
  
-   끝점을 찾을 위치를 나타내는 주소  
  
-   클라이언트가 끝점과 통신할 수 있는 방법을 지정하는 바인딩  
  
-   사용 가능한 작업을 식별하는 계약  
  
-   끝점의 로컬 구현 세부 정보를 지정하는 동작 집합  
  
 이 항목에서는 이 끝점 구조 및 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개체 모델에서 끝점 구조가 표현되는 방법에 대해 설명합니다.  
  
## 끝점의 구조  
 각 끝점은 다음으로 구성됩니다.  
  
-   주소: 주소는 끝점을 고유하게 식별하고 잠재 고객에게 서비스가 있는 위치를 알려 줍니다.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개체 모델에서 <xref:System.ServiceModel.EndpointAddress> 클래스로 표현됩니다.<xref:System.ServiceModel.EndpointAddress> 클래스에는 다음이 포함됩니다.  
  
    -   서비스의 주소를 나타내는 <xref:System.ServiceModel.EndpointAddress.Uri%2A> 속성.  
  
    -   서비스의 보안 ID 및 선택적 메시지 헤더의 컬렉션을 나타내는 <xref:System.ServiceModel.EndpointAddress.Identity%2A> 속성.선택적 메시지 헤더는 끝점 확인 또는 끝점과의 상호 작용을 위해 자세한 추가 주소 지정 정보를 제공하는 데 사용합니다.  
  
     [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [끝점 주소 지정](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).  
  
-   바인딩: 바인딩은 끝점과 통신하는 방법을 지정합니다.여기에는 다음이 포함됩니다.  
  
    -   사용할 전송 프로토콜\(예: TCP 또는 HTTP\)  
  
    -   메시지에 사용할 인코딩\(예: 텍스트 또는 이진\)  
  
    -   필요한 보안 요구 사항\(예: SSL 또는 SOAP 메시지 보안\)  
  
     [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [WCF 바인딩 개요](../../../../docs/framework/wcf/bindings-overview.md).[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 개체 모델에서 바인딩은 추상 기본 클래스 <xref:System.ServiceModel.Channels.Binding>으로 표현됩니다.대부분의 시나리오의 경우 사용자는 시스템 제공 바인딩 중 하나를 사용할 수 있습니다.자세한 내용은 [시스템 제공 바인딩](../../../../docs/framework/wcf/system-provided-bindings.md)을 참조하십시오.  
  
-   계약: 계약에서는 끝점이 클라이언트에 노출하는 기능을 간략하게 설명합니다.계약에서는 다음을 지정합니다.  
  
    -   클라이언트가 호출할 수 있는 작업  
  
    -   메시지 형식  
  
    -   작업을 호출하는 데 필요한 입력 매개 변수 또는 데이터 형식  
  
    -   클라이언트가 예상할 수 있는 처리 또는 응답 메시지 형식  
  
     계약 정의에 대한 자세한 내용은 [서비스 계약 디자인](../../../../docs/framework/wcf/designing-service-contracts.md)을 참조하십시오.  
  
-   동작: 끝점 동작을 사용하여 서비스 끝점의 로컬 동작을 사용자 지정할 수 있습니다.끝점 동작은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 런타임 빌드 프로세스에 참여하여 이를 수행합니다.끝점 동작의 예는 <xref:System.ServiceModel.Description.ServiceEndpoint.ListenUri%2A> 속성이며, 이 속성을 사용하여 SOAP 또는 WSDL\(웹 서비스 기술 언어\) 주소 이외의 다른 수신 대기 주소를 지정할 수 있습니다.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][ClientViaBehavior](../../../../docs/framework/wcf/diagnostics/wmi/clientviabehavior.md).  
  
## 끝점 정의  
 구성을 통해 코드를 명령적으로 또는 선언적으로 사용하여 서비스의 끝점을 지정할 수 있습니다.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][방법: 구성에서 서비스 끝점 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md) 및 [방법: 코드에서 서비스 끝점 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).  
  
## 단원 내용  
 이 단원에서는 바인딩, 끝점 및 주소의 용도에 대해 설명하고 바인딩 및 끝점을 구성하는 방법과 `ClientVia` 동작 및 `ListenUri` 속성을 사용하는 방법을 보여 줍니다.  
  
 [주소](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 끝점의 주소를 지정하는 방법에 대해 설명합니다.  
  
 [바인딩](../../../../docs/framework/wcf/feature-details/bindings.md)  
 바인딩을 사용하여 클라이언트와 서비스 간에 통신하는 데 필요한 전송, 인코딩 및 프로토콜 세부 정보를 지정하는 방법에 대해 설명합니다.  
  
 [계약](../../../../docs/framework/wcf/feature-details/contracts.md)  
 계약이 서비스 메서드를 정의하는 방법에 대해 설명합니다.  
  
 [방법: 구성에서 서비스 끝점 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 구성에서 서비스 끝점을 만드는 방법에 대해 설명합니다.  
  
 [방법: 코드에서 서비스 끝점 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 코드에서 서비스 끝점을 만드는 방법에 대해 설명합니다.  
  
 [방법: Svcutil.exe를 사용하여 컴파일된 서비스 코드 유효성 검사](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-validate-compiled-service-code.md)  
 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)를 사용하여 서비스를 호스팅하지 않고 서비스 구현과 구성에서 오류를 검색하는 방법에 대해 설명합니다.  
  
## 참고 항목  
 [서비스 구성](../../../../docs/framework/wcf/configuring-services.md)   
 [바인딩 확장](../../../../docs/framework/wcf/extending/extending-bindings.md)