---
title: "WCF 클라이언트를 사용하여 서비스 액세스 | Microsoft Docs"
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
  - "클라이언트 [WCF], 서비스 사용"
ms.assetid: d780af9f-73c5-42db-9e52-077a5e4de7fe
caps.latest.revision: 36
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 36
---
# WCF 클라이언트를 사용하여 서비스 액세스
서비스를 만들고 나면 다음 단계로 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 프록시를 만듭니다.  클라이언트 응용 프로그램은 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 프록시를 사용하여 서비스와 통신합니다.  클라이언트 응용 프로그램은 일반적으로 서비스의 메타데이터를 가져와서 서비스 호출에 사용할 수 있는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 코드를 생성합니다.  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트를 만드는 기본 단계에는 다음이 포함됩니다.  
  
1.  서비스 코드를 컴파일합니다.  
  
2.  [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 프록시를 생성합니다.  
  
3.  WCF 클라이언트 프록시를 인스턴스화합니다.  
  
 WCF 클라이언트 프록시는 서비스 모델 메타데이터 유틸리티 도구\(SvcUtil.exe\)를 사용하여 수동으로 생성할 수 있습니다. 자세한 내용은 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)를 참조하세요.  WCF 클라이언트 프록시는 Visual Studio에서 서비스 참조 추가 기능을 사용하여 생성할 수도 있습니다.  어떤 방법으로 WCF 클라이언트 프록시를 생성하더라도 서비스가 실행되고 있어야 합니다.  자체 호스팅 서비스의 경우 호스트를 실행해야 합니다.  서비스가 IIS\/WAS에서 호스트되는 경우에는 별도의 작업이 필요하지 않습니다.  
  
## ServiceModel Metadata 유틸리티 도구  
 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)는 메타데이터에서 코드를 생성하기 위한 명령줄 도구입니다.  다음 사용은 기본 Svcutil.exe 명령 예제입니다.  
  
```  
Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
```  
  
 또는 Svcutil.exe에 파일 시스템의 WSDL\(웹 서비스 기술 언어\) 및 XSD\(XML 스키마 정의 언어\) 파일을 사용할 수도 있습니다.  
  
```  
Svcutil.exe <list of WSDL and XSD files on file system>  
```  
  
 결과는 클라이언트 응용 프로그램이 서비스 호출에 사용할 수 있는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 코드를 포함하는 코드 파일입니다.  
  
 이 도구를 사용하여 구성 파일을 생성할 수도 있습니다.  
  
```  
Svcutil.exe <file1 [,file2]>  
```  
  
 파일 이름을 제공하면 해당 이름이 출력 파일의 이름이 됩니다.  두 개의 파일 이름을 제공하면 첫 번째 파일은 입력 구성 파일로, 해당 내용이 생성된 구성과 병합되어 두 번째 파일에 기록됩니다.  구성에 대한 [!INCLUDE[crabout](../../../includes/crabout-md.md)]는 [서비스에 대한 바인딩 구성](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)을 참조하세요.  
  
> [!IMPORTANT]
>  보안되지 않은 메타데이터 요청은 보안되지 않은 네트워크 요청과 동일한 방식으로 특정 위험을 노출합니다. 통신하는 끝점이 실제로 주장되는 끝점인지 확실하지 않을 경우 검색한 정보가 악성 서비스의 메타데이터일 수 있습니다.  
  
## Visual Studio의 서비스 참조 추가  
 서비스를 실행하는 상태에서 WCF 클라이언트 프록시를 포함할 프로젝트를 마우스 오른쪽 단추로 클릭하고 **서비스 참조 추가**를 선택합니다.  **서비스 참조 추가 대화 상자**에서 호출하려는 서비스의 URL을 입력한 다음 **이동** 단추를 클릭합니다.  대화 상자에 지정한 주소에서 사용할 수 있는 서비스 목록이 표시됩니다.  서비스를 두 번 클릭해서 사용 가능한 계약과 작업을 확인합니다. 생성된 코드에 대한 네임스페이스를 지정하고 **확인** 단추를 클릭합니다.  
  
## 예제  
 다음 코드 예제에서는 서비스에 대해 만들어진 서비스 계약을 보여 줍니다.  
  
```csharp  
// Define a service contract.  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    // Other methods are not shown here.  
}  
```  
  
```vb  
' Define a service contract.  
<ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")> _  
Public Interface ICalculator  
    <OperationContract()>  _  
    Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double   
    ' Other methods are not shown here.  
End Interface   
```  
  
 ServiceModel Metadata 유틸리티 도구 및 Visual Studio의 서비스 참조 추가는 다음 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 클래스를 생성합니다.  클래스는 제네릭 <xref:System.ServiceModel.ClientBase%601> 클래스에서 상속되며 `ICalculator` 인터페이스를 구현합니다.  또한 이 도구는 여기에 표시되지 않은 `ICalculator` 인터페이스를 생성합니다.  
  
```csharp  
public partial class CalculatorClient : System.ServiceModel.ClientBase<ICalculator>, ICalculator  
{  
    public CalculatorClient(){}  
  
    public CalculatorClient(string configurationName) :   
            base(configurationName)  
    {}  
  
    public CalculatorClient(System.ServiceModel.Binding binding) :   
            base(binding)  
    {}  
  
    public CalculatorClient(System.ServiceModel.EndpointAddress address,  
    System.ServiceModel.Binding binding) :   
            base(address, binding)  
    {}  
  
    public double Add(double n1, double n2)  
    {  
        return base.InnerChannel.Add(n1, n2);  
    }  
}  
  
```  
  
```vb  
Partial Public Class CalculatorClient  
    Inherits System.ServiceModel.ClientBase(Of ICalculator)  
    Implements ICalculator  
  
    Public Sub New()  
        MyBase.New  
    End Sub  
  
    Public Sub New(ByVal configurationName As String)  
        MyBase.New(configurationName)  
    End Sub  
  
    Public Sub New(ByVal binding As System.ServiceModel.Binding)  
        MyBase.New(binding)  
    End Sub  
  
    Public Sub New(ByVal address As _  
    System.ServiceModel.EndpointAddress, _  
    ByVal binding As System.ServiceModel.Binding)  
        MyBase.New(address, binding)  
    End Sub  
  
    Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As _  
    Double Implements ICalculator.Add  
        Return MyBase.InnerChannel.Add(n1, n2)  
    End Function   
End Class  
  
```  
  
## WCF 클라이언트 사용  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트를 사용하려면 다음 코드와 같이 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 인스턴스를 만든 다음 해당 메서드를 호출합니다.  
  
```csharp  
// Create a client object with the given client endpoint configuration.  
CalculatorClient calcClient = new CalculatorClient("CalculatorEndpoint"));  
// Call the Add service operation.  
double value1 = 100.00D;  
double value2 = 15.99D;  
double result = calcClient.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
```  
  
```vb  
' Create a client object with the given client endpoint configuration.  
Dim calcClient As CalculatorClient = _  
New CalculatorClient("CalculatorEndpoint")  
  
' Call the Add service operation.  
Dim value1 As Double = 100.00D  
Dim value2 As Double = 15.99D  
Dim result As Double = calcClient.Add(value1, value2)  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)  
  
```  
  
## 클라이언트에서 Throw된 예외 디버깅  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트에서 throw된 많은 예외는 서비스에서의 예외로 인해 발생합니다.  다음은 이를 보여 주는 몇 가지 예입니다.  
  
-   <xref:System.Net.Sockets.SocketException>: 기존 연결이 원격 호스트에 의해 강제로 닫혔습니다.  
  
-   <xref:System.ServiceModel.CommunicationException>: 기본 연결이 예기치 않게 닫혔습니다.  
  
-   <xref:System.ServiceModel.CommunicationObjectAbortedException>: 소켓 연결이 중단되었습니다.  이는 메시지 처리 오류, 원격 호스트에 의해 초과되는 수신 제한 시간 또는 기본 네트워크 리소스 문제로 인해 발생할 수 있습니다.  
  
 이러한 형식의 예외가 발생할 때 가장 좋은 문제 해결 방법은 서비스측에 추적 기능을 설정하고 발생한 예외를 확인하는 것입니다.  추적에 대한 [!INCLUDE[crabout](../../../includes/crabout-md.md)]는 [추적](../../../docs/framework/wcf/diagnostics/tracing/index.md) 및 [추적을 사용하여 응용 프로그램 문제 해결](../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)을 참조하세요.  
  
## 참고 항목  
 [방법: 클라이언트 만들기](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)   
 [방법: 이중 계약을 사용하여 서비스 액세스](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)   
 [방법: 비동기적으로 서비스 작업 호출](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md)   
 [방법: 단방향 및 요청\-회신 계약을 사용하여 서비스 액세스](../../../docs/framework/wcf/feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md)   
 [방법: WSE 3.0 서비스 액세스](../../../docs/framework/wcf/feature-details/how-to-access-a-wse-3-0-service-with-a-wcf-client.md)   
 [생성된 클라이언트 코드 이해](../../../docs/framework/wcf/feature-details/understanding-generated-client-code.md)   
 [방법: XmlSerializer를 사용하여 WCF 클라이언트 응용 프로그램의 시작 시간 개선](../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)   
 [클라이언트 런타임 동작 지정](../../../docs/framework/wcf/specifying-client-run-time-behavior.md)   
 [클라이언트 동작 구성](../../../docs/framework/wcf/configuring-client-behaviors.md)