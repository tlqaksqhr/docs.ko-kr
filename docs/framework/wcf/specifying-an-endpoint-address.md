---
title: "끝점 주소 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "주소를 지정 하는 끝점 [WCF]"
ms.assetid: ac24f5ad-9558-4298-b168-c473c68e819b
caps.latest.revision: 41
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 41
---
# 끝점 주소 지정
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 서비스와의 모든 통신은 해당 통신의 끝점을 통해 수행됩니다. 각 <xref:System.ServiceModel.Description.ServiceEndpoint> 포함 한 <xref:System.ServiceModel.Description.ServiceEndpoint.Address%2A>, <xref:System.ServiceModel.Description.ServiceEndpoint.Binding%2A>, 및 <xref:System.ServiceModel.Description.ServiceEndpoint.Contract%2A>합니다. 계약은 사용할 수 있는 작업을 지정합니다. 바인딩은 서비스와 통신하는 방법을 지정하고 주소는 서비스를 찾을 위치를 지정합니다. 모든 끝점에는 고유한 주소가 있어야 합니다. 끝점 주소로 <xref:System.ServiceModel.EndpointAddress> 는 식별자 URI (Uniform Resource)을 나타내는 서비스의 주소를 포함 하는 클래스는 <xref:System.ServiceModel.EndpointAddress.Identity%2A>를 표시 하는 서비스의 보안 id의 선택적 컬렉션 <xref:System.ServiceModel.EndpointAddress.Headers%2A>합니다. 선택적 헤더는 끝점을 확인하거나 상호 작용하는 데 필요한 자세한 주소 지정 정보를 제공합니다. 예를 들어 헤더는 들어오는 메시지를 처리하는 방법, 끝점이 회신 메시지를 보내야 하는 위치 또는 여러 인스턴스를 사용할 수 있는 경우 특정 사용자의 들어오는 메시지를 처리하는 데 사용할 서비스 인스턴스를 나타낼 수 있습니다.  
  
## <a name="definition-of-an-endpoint-address"></a>끝점 주소 정의  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], <xref:System.ServiceModel.EndpointAddress> 는 Ws-addressing 표준에 정의 된 대로 끝점 참조 (EPR)를 모델링 합니다.  
  
 대부분 전송 주소 URI에는 네 가지 부분이 있습니다. 예를 들어 URI, "http://www.fabrikam.com:322/mathservice.svc/secureEndpoint"에는 다음과 같이 네 개 부분이 포함됩니다.  
  
-   스키마: http:  
  
-   시스템: www.fabrikam.com  
  
-   (선택적) 포트: 322  
  
-   경로: /mathservice.svc/secureEndpoint  
  
 EPR 모델 일부에서는 각 끝점 참조에 추가 식별 정보를 추가하는 일부 참조 매개 변수를 포함할 수 있습니다. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], 이러한 참조 매개 변수는의 인스턴스로 모델링 되는 <xref:System.ServiceModel.Channels.AddressHeader> 클래스입니다.  
  
 서비스의 끝점 주소는 코드를 사용하여 명령적으로 지정하거나 구성을 통해 선언적으로 지정할 수 있습니다. 일반적으로 배포된 서비스의 바인딩과 주소가 서비스를 배포할 때 사용된 바인딩 및 주소와 다르기 때문에 코드로 끝점을 정의하는 것은 효과적이지 않습니다. 일반적으로 코드 대신 구성을 사용하여 서비스 끝점을 정의하는 것이 좋습니다. 바인딩 및 주소 지정 정보를 코드와 구분하면 응용 프로그램을 다시 컴파일하여 재배포할 필요 없이 해당 정보를 변경할 수 있습니다. 코드 또는 구성에서 끝점을 지정하지 않으면 런타임이 서비스에서 구현되는 각 계약의 각 기본 주소에 대해 기본 끝점을 하나씩 추가합니다.  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]에서 서비스의 대한 끝점 주소를 지정하기 위한 두 가지 방법이 있습니다. 서비스에 연결 된 각 끝점에 대 한 절대 주소를 지정할 수 또는 대 한 기본 주소를 제공할 수는 <xref:System.ServiceModel.ServiceHost> 서비스의이 기본 주소를 기준으로 정의 하는이 서비스와 연결 된 각 끝점에 대 한 주소를 지정 합니다. 이러한 각 절차를 사용하여 구성 또는 코드에서 서비스에 대한 끝점 주소를 지정할 수 있습니다. 상대 주소를 지정하지 않을 경우 서비스는 기본 주소를 사용합니다. 또한 하나의 서비스에 대해 여러 기본 주소를 사용할 수 있지만 각 서비스는 각 전송에 대해 하나의 기본 주소만 허용됩니다. 여러 끝점을 가진 경우 각 끝점은 서로 다른 바인딩으로 구성되며 해당 주소가 고유해야 합니다. 동일한 바인딩을 사용하지만 서로 다른 계약을 사용하는 끝점은 동일한 주소를 사용할 수 있습니다.  
  
 관리 되지 않는 IIS를 호스팅하는 경우는 <xref:System.ServiceModel.ServiceHost> 인스턴스를 직접. IIS에서 호스팅하는 경우 기본 주소는 항상 서비스의 .svc 파일에 지정된 주소입니다. 따라서 IIS에서 호스팅되는 서비스 끝점에는 상대 끝점 주소를 사용해야 합니다. 정규화된 끝점 주소를 제공할 경우 서비스 배포 시 오류가 발생할 수 있습니다. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][인터넷 정보 서비스에서 호스팅되는 WCF 서비스 배포](../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md)합니다.  
  
## <a name="defining-endpoint-addresses-in-configuration"></a>구성에서 끝점 주소 정의  
 사용 하 여 구성 파일에서 끝점을 정의 하는 [ <> \> ](http://msdn.microsoft.com/ko-kr/13aa23b7-2f08-4add-8dbf-a99f8127c017) 요소입니다.  
  
 <!-- TODO: review snippet reference [!code[S_UEHelloWorld#5](../../../samples/snippets/common/VS_Snippets_CFX/s_uehelloworld/common/serviceapp2.config#5)]  -->  
  
 때는 <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> 메서드는 (즉, 호스팅 응용 프로그램 서비스를 시작 하려고), 시스템은 한 [ <> \> ](../../../docs/framework/configure-apps/file-schema/wcf/service.md) "UE 지정 하는 이름 특성을 가진 요소. Samples.HelloService "로 설정 합니다. 하는 경우는 [ <> \> ](../../../docs/framework/configure-apps/file-schema/wcf/service.md) 요소를 찾을 때, 시스템 지정된 된 클래스를 로드 하 고 구성 파일에 제공 된 끝점 정의 사용 하 여 끝점을 만듭니다. 이 메커니즘을 통해 두 개의 코드 줄에서 서비스를 로드하고 시작하는 동시에 해당 코드의 바인딩 및 주소 지정 정보를 유지할 수 있습니다. 이 접근 방식의 이점은 응용 프로그램을 다시 컴파일하거나 다시 배포할 필요 없이 이러한 변경 작업을 수행할 수 있다는 점입니다.  
  
 선택적 헤더에 선언 된 [ <> \</> \> ](../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)합니다. 다음은 두 가지 헤더(예: http://tempuri1.org/의 "Gold" 클라이언트 및 http://tempuri2.org/의 "Standard" 클라이언트) 간에 구분되는 구성 파일의 서비스에 대한 끝점을 지정하는 데 사용되는 요소의 예제입니다. 이 서비스를 호출 하는 클라이언트에서 적절 한 있어야 [ <> \> ](../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md) 의 구성 파일에 있습니다.  
  
 <!-- TODO: review snippet reference [!code[S_UEHelloWorld#1](../../../samples/snippets/common/VS_Snippets_CFX/s_uehelloworld/common/serviceapp.config#1)]  -->  
  
 또한 헤더는 이전에 설명한 것처럼 끝점의 모든 메시지 대신 개별 메시지에서 설정될 수 있습니다. 사용 하 여 이렇게 <xref:System.ServiceModel.OperationContextScope> 다음 예제 에서처럼 보내는 메시지에 사용자 지정 헤더를 추가 하는 클라이언트 응용 프로그램에서 새 컨텍스트를 만드는를 합니다.  
  
 [!code-csharp[OperationContextScope#4](../../../samples/snippets/csharp/VS_Snippets_CFX/operationcontextscope/cs/client.cs#4)]
 [!code-vb[OperationContextScope#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/operationcontextscope/vb/client.vb#4)]  
  
## <a name="endpoint-address-in-metadata"></a>메타데이터의 끝점 주소  
 끝점 주소는 해당 끝점의 `EndpointReference` 요소 내에서 WS-Addressing `wsdl:port`(EPR) 요소로서 WSDL(웹 서비스 기술 언어)로 표시됩니다. EPR에는 끝점 주소와 주소 속성이 포함되어 있습니다. `wsdl:port` 내의 EPR은 다음 예제에 표시된 것처럼 `soap:Address`로 바뀝니다.  
  
  
  
## <a name="defining-endpoint-addresses-in-code"></a>코드에서 끝점 주소 정의  
 끝점 주소를 사용 하 여 코드에서 만들 수는 <xref:System.ServiceModel.EndpointAddress> 클래스입니다. 끝점 주소에 대해 지정된 URI는 정규화된 경로 또는 서비스 기본 주소에 상대적인 경로일 수 있습니다. 인스턴스를 만드는 다음 코드에서는 <xref:System.ServiceModel.EndpointAddress> 클래스에 추가 하는 <xref:System.ServiceModel.ServiceHost> 서비스를 호스팅하는 인스턴스에 있습니다.  
  
 다음 예제에서는 전체 끝점 주소를 코드에서 지정하는 방법을 보여 줍니다.  
  
 [!code-csharp[S_UEHelloWorld#2](../../../samples/snippets/csharp/VS_Snippets_CFX/s_uehelloworld/cs/snippet.cs#2)]  
  
 다음 예제에서는 상대 주소("MyService")를 서비스 호스트의 기본 주소에 추가하는 방법을 보여 줍니다.  
  
 [!code-csharp[S_UEHelloWorld#3](../../../samples/snippets/csharp/VS_Snippets_CFX/s_uehelloworld/cs/snippet.cs#3)]  
  
> [!NOTE]
>  속성은 <xref:System.ServiceModel.Description.ServiceDescription> 서비스에서 응용 프로그램을 수정 해서는 안 다음에 나오는 <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> 메서드를 <xref:System.ServiceModel.ServiceHostBase>합니다. 일부 멤버와 같은 <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> 속성 및 `AddServiceEndpoint` 메서드 <xref:System.ServiceModel.ServiceHostBase> 및 <xref:System.ServiceModel.ServiceHost>, 해당 지점을 지나서 수정할 경우 예외를 throw 합니다. 다른 멤버에서는 이를 수정할 수 있지만 그 결과는 예측할 수 없습니다.  
>   
>  마찬가지로, 클라이언트에는 <xref:System.ServiceModel.Description.ServiceEndpoint> 를 호출한 후 값을 수정 해서는 안 <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> 에 <xref:System.ServiceModel.ChannelFactory>합니다. <xref:System.ServiceModel.ChannelFactory.Credentials%2A> 속성 해당 지점을 지나서 수정할 경우 예외를 throw 합니다. 다른 클라이언트 설명 값은 수정해도 오류가 발생하지 않지만 결과가 정의되어 있지 않습니다.  
>   
>  여부를 서비스 또는 클라이언트에 대 한 것이 좋습니다 호출 하기 이전에 설명을 수정 하는 <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>합니다.  
  
## <a name="using-default-endpoints"></a>기본 끝점 사용  
 코드 또는 구성에서 끝점을 지정하지 않으면 런타임이 서비스에서 구현되는 각 서비스 계약의 각 기본 주소에 대해 기본 끝점을 하나씩 추가하여 기본 끝점을 제공합니다. 코드 또는 구성에서 기본 주소를 지정할 수 있으며 하면 기본 끝점이 추가 됩니다 <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> 라고 하는 <xref:System.ServiceModel.ServiceHost>합니다.  
  
 호출 하 여 여전히 기본 끝점을 추가할 수 끝점을 명시적으로 제공 하는 경우 <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints%2A> 에 <xref:System.ServiceModel.ServiceHost> 호출 하기 전에 <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>합니다. [!INCLUDE[crabout](../../../includes/crabout-md.md)]기본 끝점, 바인딩 및 동작, 참조 [단순화 된 구성](../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스를 위한 단순화 된 구성](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.EndpointAddress>   
 [서비스 Id 및 인증](../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [끝점 만들기 개요](../../../docs/framework/wcf/endpoint-creation-overview.md)   
 [호스팅](../../../docs/framework/wcf/feature-details/hosting.md)