---
title: "Getting Started 샘플 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
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
  - "기본 샘플 [WCF], 시작"
ms.assetid: 967a3d94-0261-49ff-b85a-20bb07f1af20
caps.latest.revision: 60
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 60
---
# Getting Started 샘플
Getting Started 샘플에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]를 사용하여 일반적인 서비스와 일반적인 클라이언트를 구현하는 방법을 보여 줍니다.이 샘플은 다른 모든 기본 기술 샘플의 기준이 됩니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\GettingStarted\GettingStarted`  
  
 서비스는 메타데이터로 공개적으로 노출하는 서비스 계약에서 수행하는 작업을 설명합니다.또한 서비스에는 작업을 구현하기 위한 코드가 포함되어 있습니다.  
  
 클라이언트에는 서비스에 액세스하기 위한 프록시 클래스와 서비스 계약에 대한 정의가 포함되어 있습니다.프록시 코드는 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)를 사용하여 서비스 메타데이터에서 생성됩니다.  
  
 [!INCLUDE[wv](../../../../includes/wv-md.md)]에서 서비스는 WAS\(Windows Activation Service\)에서 호스팅됩니다.[!INCLUDE[wxp](../../../../includes/wxp-md.md)] 및[!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]에서 서비스는 IIS\(인터넷 정보 서비스\) 및 ASP.NET을 통해 호스팅됩니다.IIS 또는 WAS에서 서비스를 호스팅하면 서비스에 처음 액세스할 때 서비스를 자동으로 활성화할 수 있습니다.  
  
> [!NOTE]
>  IIS 대신에 콘솔 응용 프로그램에서 서비스를 호스팅하는 샘플로 시작하려면 [자체 호스팅](../../../../docs/framework/wcf/samples/self-host.md) 샘플을 참조하십시오.  
  
 서비스와 클라이언트는 구성 파일 설정에서 액세스 세부 정보를 지정하므로 배포 시에 유연성을 갖게 됩니다.주소, 바인딩 및 계약을 지정하는 끝점 정의가 여기에 포함됩니다.바인딩은 서비스를 액세스하는 방법에 대한 전송 및 보안 세부 정보를 지정합니다.  
  
 서비스는 해당 메타데이터를 게시하기 위한 런타임 동작을 구성합니다.  
  
 서비스는 요청\-회신 통신 패턴을 정의하는 계약을 구현합니다.계약은 수학 연산\(Add, Subtract, Multiply 및 Divide\)을 노출시키는 `ICalculator` 인터페이스에 의해 정의됩니다.클라이언트에서 지정된 수학 연산을 요청하면 서비스에서 결과로 회신합니다.서비스는 다음 코드에 정의된 `ICalculator` 계약을 구현합니다.  
  
```vb  
' Define a service contract.  
    <ServiceContract(Namespace:="http://Microsoft.Samples.GettingStarted")>  
     Public Interface ICalculator  
        <OperationContract()>  
        Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double  
        <OperationContract()>  
        Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double  
        <OperationContract()>  
        Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double  
        <OperationContract()>  
        Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double  
    End Interface  
  
```  
  
```csharp  
// Define a service contract.  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    [OperationContract]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);  
}  
  
```  
  
 다음 예제 코드와 같이 서비스 구현은 적절한 결과를 계산하여 반환합니다.  
  
```vb  
' Service class which implements the service contract.  
Public Class CalculatorService  
Implements ICalculator  
Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add  
Return n1 + n2  
End Function  
  
Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract  
Return n1 - n2  
End Function  
  
Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply  
Return n1 * n2  
End Function  
  
Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide  
Return n1 / n2  
End Function  
End Class  
  
```  
  
```csharp  
// Service class that implements the service contract.  
public class CalculatorService : ICalculator  
{  
    public double Add(double n1, double n2)  
    {  
        return n1 + n2;  
    }  
    public double Subtract(double n1, double n2)  
    {  
        return n1 - n2;  
    }  
    public double Multiply(double n1, double n2)  
    {  
        return n1 * n2;  
    }  
    public double Divide(double n1, double n2)  
    {  
        return n1 / n2;  
    }  
}  
  
```  
  
 다음 샘플 구성과 같이 서비스에서는 구성 파일\(Web.config\)을 사용하여 정의하는 서비스와의 통신을 위한 끝점을 노출합니다.  
  
```xaml  
<services>  
    <service   
        name="Microsoft.ServiceModel.Samples.CalculatorService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
        <!-- ICalculator is exposed at the base address provided by  
         host: http://localhost/servicemodelsamples/service.svc.  -->  
       <endpoint address=""  
              binding="wsHttpBinding"  
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
       ...  
    </service>  
</services>  
  
```  
  
 서비스는 IIS 또는 WAS 호스트에서 제공되는 기본 주소에서 끝점을 노출합니다.바인딩은 표준 <xref:System.ServiceModel.WSHttpBinding>을 사용하여 구성되어 주소 지정 및 보안을 위한 HTTP 통신 및 표준 웹 서비스 프로토콜을 제공합니다.계약은 서비스에 의해 구현되는 `ICalculator`입니다.  
  
 구성된 대로 동일한 컴퓨터의 클라이언트는 http:\/\/localhost\/servicemodelsamples\/service.svc에서 서비스에 액세스할 수 있습니다.원격 컴퓨터의 클라이언트가 서비스에 액세스하려면 localhost 대신 정규화된 도메인 이름을 지정해야 합니다.  
  
 기본적으로 프레임워크에서는 메타데이터를 노출하지 않습니다.따라서 서비스는 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>를 설정하고 http:\/\/localhost\/servicemodelsamples\/service.svc\/mex에서 MEX\(메타데이터 교환\) 끝점을 노출합니다.다음 구성에서는 이를 보여 줍니다.  
  
```xaml  
<system.serviceModel>  
  <services>  
    <service   
        name="Microsoft.ServiceModel.Samples.CalculatorService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
      ...  
      <!-- the mex endpoint is explosed at  
       http://localhost/servicemodelsamples/service.svc/mex -->  
      <endpoint address="mex"  
                binding="mexHttpBinding"  
                contract="IMetadataExchange" />  
    </service>  
  </services>  
  
  <!--For debugging purposes set the includeExceptionDetailInFaults  
   attribute to true-->  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
        <serviceMetadata httpGetEnabled="True"/>  
        <serviceDebug includeExceptionDetailInFaults="False" />  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
 클라이언트는 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)에 의해 생성된 클라이언트 클래스를 사용하여 지정된 계약 형식으로 통신합니다.생성된 이 클라이언트는 generatedClient.cs 또는 generatedClient.vb 파일에 포함됩니다.이 유틸리티는 지정된 서비스에 대한 메타데이터를 검색하고 지정된 계약 형식으로 통신하기 위해 클라이언트 응용 프로그램에 사용되는 클라이언트를 생성합니다.업데이트된 메타데이터를 검색하는 데 호스팅된 서비스가 사용되므로 클라이언트 코드를 생성하기 위해 해당 서비스를 사용할 수 있어야 합니다.  
  
 클라이언트 디렉터리의 SDK 명령 프롬프트에서 다음 명령을 실행하여 형식화된 프록시를 생성합니다.  
  
```  
svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs  
```  
  
 Visual Basic에서 클라이언트를 생성하려면 SDK 명령 프롬프트에서 다음을 입력합니다.  
  
 `Svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /l:vb /out:generatedClient.vb`  
  
 생성된 클라이언트를 사용하면 클라이언트에서 적절한 주소와 바인딩을 구성하여 지정된 서비스 끝점에 액세스할 수 있습니다.서비스와 마찬가지로 클라이언트는 구성 파일\(App.config\)을 사용하여 통신할 끝점을 지정합니다.다음 예제와 같이 클라이언트 끝점 구성은 서비스 끝점의 절대 주소, 바인딩 및 계약으로 구성됩니다.  
  
```xaml  
<client>  
     <endpoint  
         address="http://localhost/servicemodelsamples/service.svc"   
         binding="wsHttpBinding"   
         contract=" Microsoft.ServiceModel.Samples.ICalculator" />  
</client>  
  
```  
  
 다음 예제 코드와 같이 클라이언트 구현은 클라이언트를 인스턴스화하고 형식화된 인터페이스를 사용하여 서비스와 통신을 시작합니다.  
  
```vb  
' Create a client  
Dim client As New CalculatorClient()  
  
' Call the Add service operation.  
            Dim value1 = 100.0R  
            Dim value2 = 15.99R  
            Dim result = client.Add(value1, value2)  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)  
  
' Call the Subtract service operation.  
value1 = 145.00R  
value2 = 76.54R  
result = client.Subtract(value1, value2)  
Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)  
  
' Call the Multiply service operation.  
value1 = 9.00R  
value2 = 81.25R  
result = client.Multiply(value1, value2)  
Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)  
  
' Call the Divide service operation.  
value1 = 22.00R  
value2 = 7.00R  
result = client.Divide(value1, value2)  
Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)  
  
'Closing the client gracefully closes the connection and cleans up resources  
  
```  
  
```csharp  
// Create a client.  
CalculatorClient client = new CalculatorClient();  
  
// Call the Add service operation.  
double value1 = 100.00D;  
double value2 = 15.99D;  
double result = client.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
// Call the Subtract service operation.  
value1 = 145.00D;  
value2 = 76.54D;  
result = client.Subtract(value1, value2);  
Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
// Call the Multiply service operation.  
value1 = 9.00D;  
value2 = 81.25D;  
result = client.Multiply(value1, value2);  
Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
// Call the Divide service operation.  
value1 = 22.00D;  
value2 = 7.00D;  
result = client.Divide(value1, value2);  
Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
  
//Closing the client releases all communication resources.  
client.Close();  
  
```  
  
 샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
  
```  
  
 Getting Started 샘플은 서비스와 클라이언트를 만드는 표준 방법을 보여 줍니다.다른 [Basic](../../../../docs/framework/wcf/samples/basic-sample.md)은 이 샘플을 기반으로 하여 특정 제품 기능을 보여 줍니다.  
  
### 샘플을 설치, 빌드 및 실행하려면  
  
1.  [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)를 수행했는지 확인합니다.  
  
2.  C\# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3.  단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)의 지침을 따릅니다.  
  
## 참고 항목  
 [방법: 관리되는 응용 프로그램에서 WCF 서비스 호스팅](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)   
 [방법: IIS에서의 WCF 서비스 호스팅](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)