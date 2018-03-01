---
title: "끝점 만들기 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- endpoints [WCF], overview
ms.assetid: f4dce0fb-6f54-47e6-8054-86d7f574b91c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fa20edd8fa43fb1e6a28f7b1ec18f83fedd96bca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="endpoint-creation-overview"></a>끝점 만들기 개요
와 모든 통신은 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 서비스를 통해 발생 된 *끝점* 서비스의 합니다. 끝점은 클라이언트에게 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스에서 제공하는 기능에 대한 액세스를 제공합니다. 이 단원에서는 끝점의 구조에 대해 설명하고 구성 및 코드에서 끝점을 정의하는 방법을 간략하게 설명합니다.  
  
## <a name="the-structure-of-an-endpoint"></a>끝점의 구조  
 각 끝점에는 끝점을 찾을 위치를 나타내는 주소, 클라이언트가 끝점과 통신할 수 있는 방법을 지정하는 바인딩, 그리고 사용 가능한 메서드를 식별하는 계약이 포함되어 있습니다.  
  
-   **주소**합니다. 주소는 끝점을 고유하게 식별하고 잠재 고객에게 서비스가 있는 위치를 알려 줍니다. 주소는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 개체 모델에서 <xref:System.ServiceModel.EndpointAddress> 주소로 표시되며 URI(Uniform Resource Identifier) 및 ID를 포함하는 주소 속성, 일부 WSDL(웹 서비스 기술 언어) 요소 및 선택적 헤더의 컬렉션을 포함합니다. 선택적 헤더는 끝점을 확인하거나 상호 작용하는 데 필요한 자세한 주소 지정 정보를 추가로 제공합니다. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][끝점 주소 지정](../../../docs/framework/wcf/specifying-an-endpoint-address.md)합니다.  
  
-   **바인딩**합니다. 바인딩은 끝점과 통신하는 방법을 지정합니다. 바인딩은 사용할 전송 프로토콜(예: TCP 또는 HTTP), 메시지에 사용할 인코딩(예: 텍스트 또는 이진), 필요한 보안 요구 사항(예: SSL[Secure Sockets Layer] 또는 SOAP 메시지 보안) 등을 포함하여 끝점이 대상과 통신하는 방법을 지정합니다. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][바인딩을 사용 하 여 서비스 및 클라이언트 구성](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)합니다.  
  
-   **서비스 계약**합니다. 서비스 계약에서는 끝점이 클라이언트에 노출하는 기능을 간략하게 설명합니다. 계약은 클라이언트가 호출할 수 있는 작업, 작업을 호출하는 데 필요한 입력 매개 변수 또는 데이터의 형식 및 메시지 형식, 클라이언트가 기대할 수 있는 처리 또는 응답 메시지의 종류 등을 지정합니다. 계약의 세 가지 기본 유형은 기본 MEP(메시지 교환 패턴)인 데이터 그램(단방향), 요청/응답 및 이중(양방향)과 일치합니다. 또한 서비스 계약은 액세스할 때 데이터 및 메시지 계약을 사용하여 특정 데이터 형식과 메시지 형식을 요구할 수 있습니다. [!INCLUDE[crabout](../../../includes/crabout-md.md)]서비스 계약 정의 참조 하는 방법 [서비스 계약 디자인](../../../docs/framework/wcf/designing-service-contracts.md)합니다. 클라이언트가 이중 MEP의 서비스로부터 메시지를 받으려면 콜백 계약이라는 서비스 정의 계약을 구현해야 합니다. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][이중 서비스](../../../docs/framework/wcf/feature-details/duplex-services.md)합니다.  
  
 서비스의 끝점을 코드를 사용하여 명령적으로 지정하거나 구성을 통해 선언적으로 지정할 수 있습니다. 끝점을 지정하지 않으면 런타임이 서비스에서 구현되는 각 서비스 계약의 각 기본 주소에 대해 기본 끝점을 하나씩 추가하여 기본 끝점을 제공합니다. 일반적으로 배포된 서비스의 바인딩과 주소가 서비스를 배포할 때 사용된 바인딩 및 주소와 다르기 때문에 코드로 끝점을 정의하는 것은 효과적이지 않습니다. 일반적으로 코드 대신 구성을 사용하여 서비스 끝점을 정의하는 것이 좋습니다. 바인딩 및 주소 지정 정보를 코드와 구분하면 응용 프로그램을 다시 컴파일하여 재배포할 필요 없이 해당 정보를 변경할 수 있습니다.  
  
> [!NOTE]
>  가장을 수행하는 서비스 끝점을 추가할 때는 <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> 메서드 또는 <xref:System.ServiceModel.Description.ContractDescription.GetContract%28System.Type%2CSystem.Type%29> 메서드 중 하나를 사용하여 계약을 새 <xref:System.ServiceModel.Description.ServiceDescription> 개체로 적절하게 로드해야 합니다.  
  
## <a name="defining-endpoints-in-code"></a>코드로 끝점 정의  
 다음 예제에서는 코드로 끝점을 지정하는 방법을 보여 줍니다.  
  
-   에 대 한 계약 정의 `IEcho` 다른 사용자의 이름 및 에코 응답을 허용 하는 서비스의 유형 "Hello \<이름 >!".  
  
-   `Echo` 계약에 정의된 유형의 `IEcho` 서비스를 구현합니다.  
  
-   서비스에 대한 http://localhost:8000/Echo 끝점 주소를 지정합니다.  
  
-   `Echo` 바인딩을 사용하여 <xref:System.ServiceModel.WSHttpBinding> 서비스를 구성합니다.  
  
```csharp  
Namespace Echo  
{  
   // Define the contract for the IEcho service   
   [ServiceContract]  
   public interface IEcho  
   {  
       [OperationContract]  
       String Hello(string name)  
   }  
  
   // Create an Echo service that implements IEcho contract  
   class Echo : IEcho  
   {  
      public string Hello(string name)  
      {  
         return "Hello" + name + "!";  
      }  
      public static void Main ()  
      {  
          //Specify the base address for Echo service.  
          Uri echoUri = new Uri("http://localhost:8000/");  
  
          //Create a ServiceHost for the Echo service.  
          ServiceHost serviceHost = new ServiceHost(typeof(Echo),echoUri);  
  
          // Use a predefined WSHttpBinding to configure the service.  
          WSHttpBinding binding = new WSHttpBinding();  
  
          // Add the endpoint for this service to the service host.  
          serviceHost.AddServiceEndpoint(  
             typeof(IEcho),   
             binding,   
             echoUri  
           );  
  
          // Open the service host to run it.  
          serviceHost.Open();  
     }  
  }  
}  
```  
  
```vb  
' Define the contract for the IEcho service  
    <ServiceContract()> _  
    Public Interface IEcho  
        <OperationContract()> _  
        Function Hello(ByVal name As String) As String  
    End Interface  
  
' Create an Echo service that implements IEcho contract  
    Public Class Echo   
        Implements IEcho  
        Public Function Hello(ByVal name As String) As String _  
 Implements ICalculator.Hello  
            Dim result As String = "Hello" + name + "!"  
            Return result  
        End Function  
  
' Specify the base address for Echo service.  
Dim echoUri As Uri = New Uri("http://localhost:8000/")  
  
' Create a ServiceHost for the Echo service.  
Dim svcHost As ServiceHost = New ServiceHost(GetType(HelloWorld), echoUri)  
  
' Use a predefined WSHttpBinding to configure the service.  
Dim binding As New WSHttpBinding()  
  
' Add the endpoint for this service to the service host.  
serviceHost.AddServiceEndpoint(GetType(IEcho), binding, echoUri)  
  
' Open the service host to run it.  
serviceHost.Open()  
```  
  
> [!NOTE]
>  서비스 호스트가 기본 주소로 만들어집니다. 나머지 주소는 기본 주소를 기준으로 끝점의 일부로 지정됩니다. 이 주소 분할을 통해 호스트에서 서비스에 대해 여러 끝점을 쉽게 정의할 수 있습니다.  
  
> [!NOTE]
>  <xref:System.ServiceModel.Description.ServiceDescription>에서 <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> 메서드 이후에는 서비스 응용 프로그램의 <xref:System.ServiceModel.ServiceHostBase> 속성을 수정해서는 안 됩니다. <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> 및 `AddServiceEndpoint`에서 <xref:System.ServiceModel.ServiceHostBase> 속성 및 <xref:System.ServiceModel.ServiceHost> 메서드와 같은 일부 멤버는 해당 지점을 지나서 수정할 경우 예외를 throw합니다. 다른 멤버에서는 이를 수정할 수 있지만 그 결과는 예측할 수 없습니다.  
>   
>  마찬가지로 클라이언트에서 <xref:System.ServiceModel.Description.ServiceEndpoint>의 <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A>을 호출한 이후에는 <xref:System.ServiceModel.ChannelFactory> 값을 수정해서는 안 됩니다. <xref:System.ServiceModel.ChannelFactory.Credentials%2A> 속성은 해당 지점을 지나서 수정할 경우 예외를 throw합니다. 다른 클라이언트 설명 값은 수정해도 오류가 발생하지 않지만 결과가 정의되어 있지 않습니다.  
>   
>  서비스와 클라이언트 모두에 대해 <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>을 호출하기 이전에 설명을 수정하는 것이 좋습니다.  
  
## <a name="defining-endpoints-in-configuration"></a>구성에서 끝점 정의  
 응용 프로그램을 만들 때 응용 프로그램을 배포하는 관리자에게 결정을 넘겨야 할 경우가 있습니다. 예를 들어, 서비스 주소(URI)가 무엇인지 미리 알 수 없는 경우가 있습니다. 주소를 하드 코딩하는 대신 관리자가 서비스를 작성한 후에 이를 수행하도록 하는 것이 좋습니다. 이러한 유연성은 구성을 통해 수행됩니다. 자세한 내용은 참조 [서비스 구성](../../../docs/framework/wcf/configuring-services.md)합니다.  
  
> [!NOTE]
>  사용 하 여는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 와 `/config:` *filename*`[,`*filename* `]` 로 전환 구성 파일을 빠르게 만듭니다.  
  
## <a name="using-default-endpoints"></a>기본 끝점 사용  
 코드 또는 구성에서 끝점을 지정하지 않으면 런타임이 서비스에서 구현되는 각 서비스 계약의 각 기본 주소에 대해 기본 끝점을 하나씩 추가하여 기본 끝점을 제공합니다. 기본 주소는 코드 또는 구성에서 지정할 수 있으며 기본 끝점은 <xref:System.ServiceModel.ICommunicationObject.Open>에서 <xref:System.ServiceModel.ServiceHost>을 호출하면 추가됩니다. 다음 예제는 이전 단원과 같은 예제이지만 끝점이 지정되지 않았으므로 기본 끝점이 추가됩니다.  
  
```csharp  
Namespace Echo  
{  
   // Define the contract for the IEcho service   
   [ServiceContract]  
   Interface IEcho  
   {  
       [OperationContract]  
       String Hello(string name)  
   }  
  
   // Create an Echo service that implements IEcho contract  
   Class Echo : IEcho  
   {  
      Public string Hello(string name)  
      {  
         return "Hello" + name + "!";  
      }  
      static void Main ()  
      {  
          //Specify the base address for Echo service.  
          Uri echoUri = new Uri("http://localhost:8000/");  
  
          //Create a ServiceHost for the Echo service.  
          ServiceHost serviceHost = new ServiceHost(typeof(Echo),echoUri);  
  
          // Open the service host to run it. Default endpoints  
          // are added when the service is opened.  
          serviceHost.Open();  
     }  
  }  
}  
```  
  
```vb  
' Define the contract for the IEcho service  
    <ServiceContract()> _  
    Public Interface IEcho  
        <OperationContract()> _  
        Function Hello(ByVal name As String) As String  
    End Interface  
  
' Create an Echo service that implements IEcho contract  
    Public Class Echo   
        Implements IEcho  
        Public Function Hello(ByVal name As String) As String _  
 Implements ICalculator.Hello  
            Dim result As String = "Hello" + name + "!"  
            Return result  
        End Function  
  
' Specify the base address for Echo service.  
Dim echoUri As Uri = New Uri("http://localhost:8000/")  
  
' Open the service host to run it. Default endpoints  
' are added when the service is opened.  
serviceHost.Open()  
```  
  
 끝점을 명시적으로 제공하는 경우에도 <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints%2A>을 호출하기 전에 <xref:System.ServiceModel.ServiceHost>에서 <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>를 호출하여 기본 끝점을 추가할 수 있습니다. [!INCLUDE[crabout](../../../includes/crabout-md.md)]기본 끝점, 참조 [단순화 된 구성](../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스에 대 한 구성을 단순화](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [서비스 계약 구현](../../../docs/framework/wcf/implementing-service-contracts.md)
