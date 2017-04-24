---
title: "WCF 클라이언트 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "클라이언트 [WCF], 아키텍처"
ms.assetid: f60d9bc5-8ade-4471-8ecf-5a07a936c82d
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# WCF 클라이언트 개요
이 단원에서는 클라이언트 응용 프로그램이 수행하는 작업, [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 클라이언트를 구성, 생성 및 사용하는 방법, 그리고 클라이언트 응용 프로그램의 보안을 유지하는 방법에 대해 설명합니다.  
  
## <a name="using-wcf-client-objects"></a>WCF 클라이언트 개체 사용  
 클라이언트 응용 프로그램은 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트를 사용하여 다른 응용 프로그램과 통신하는, 관리되는 응용 프로그램입니다. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스에 대한 클라이언트 응용 프로그램을 만들려면 다음 단계를 수행합니다.  
  
1.  서비스 끝점에 대한 서비스 계약, 바인딩 및 주소 정보를 가져옵니다.  
  
2.  이 정보를 사용하여 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트를 만듭니다.  
  
3.  작업을 호출합니다.  
  
4.  [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 개체를 닫습니다.  
  
 다음 단원에서는 이러한 단계에 대해 설명하고 다음과 같은 문제를 간략하게 소개합니다.  
  
-   오류 처리  
  
-   클라이언트 구성 및 보안  
  
-   이중 서비스에 대한 콜백 개체 만들기  
  
-   비동기적으로 서비스 호출  
  
-   클라이언트 채널을 사용하여 서비스 호출  
  
## <a name="obtain-the-service-contract-bindings-and-addresses"></a>서비스 계약, 바인딩 및 주소 가져오기  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]에서 서비스 및 클라이언트는 관리되는 특성, 인터페이스 및 메서드를 사용하여 계약을 모델링합니다. 클라이언트 응용 프로그램에서 서비스에 연결하려면 서비스 계약에 대한 형식 정보를 가져와야 합니다. 일반적으로 이렇게 하면 사용 하 여는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), 서비스에서 메타 데이터를 다운로드, 변환, 선택한 언어 파일을 클라이언트 응용 프로그램 구성 파일을 만듭니다 관리 되는 소스 코드에 구성 하는 데 사용할 수 여 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 개체입니다. 예를 들어, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 개체를 만들어 `MyCalculatorService`를 호출하려는 경우에 해당 서비스에 대한 메타데이터가 `http://computerName/MyCalculatorService/Service.svc?wsdl`에 게시된다면, 다음 코드 예제에서는 Svcutil.exe를 사용하여 관리되는 코드에 서비스 계약이 들어 있는 `ClientCode.vb` 파일을 가져오는 방법을 보여 줍니다.  
  
```  
svcutil /language:vb /out:ClientCode.vb /config:app.config http://computerName/MyCalculatorService/Service.svc?wsdl  
```  
  
 클라이언트 응용 프로그램에서 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 개체를 만드는 데 사용할 수 있는 다른 어셈블리나 클라이언트 응용 프로그램으로 이 계약 코드를 컴파일할 수 있습니다. 구성 파일을 사용하여 클라이언트 개체가 서비스에 제대로 연결하도록 구성할 수 있습니다.  
  
 이 프로세스의 예를 들어 참조 [하는 방법: 클라이언트 만들기](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)합니다. 계약에 대 한 자세한 정보를 참조 하십시오. [계약](../../../docs/framework/wcf/feature-details/contracts.md)합니다.  
  
## <a name="create-a-wcf-client-object"></a>WCF 클라이언트 개체 만들기  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트는 클라이언트가 원격 서비스와 통신하는 데 사용할 수 있는 형식으로 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 나타내는 로컬 개체입니다. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 형식은 대상 서비스 계약을 구현하기 때문에 대상 서비스 계약을 만들어 구성할 경우 클라이언트 개체를 사용하여 서비스 작업을 직접 호출할 수 있습니다. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 런타임은 변환 메서드 호출을 메시지로, 서비스에 보내, 회신을 수신 대기 및 해당 값을 반환 된 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 반환 값으로 클라이언트 개체 또는 `out` 또는 `ref` 매개 변수입니다.  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 채널 개체를 사용하여 서비스를 연결한 후 사용할 수도 있습니다. 자세한 내용은 다음을 참조 하십시오. [WCF 클라이언트 아키텍처](../../../docs/framework/wcf/feature-details/client-architecture.md)합니다.  
  
#### <a name="creating-a-new-wcf-object"></a>새 WCF 개체 만들기  
 사용을 설명 하기는 <xref:System.ServiceModel.ClientBase%601> 클래스, 서비스 응용 프로그램에서 다음 서비스 계약이 생성 된 것으로 가정 합니다.  
  
> [!NOTE]
>  [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]를 사용하여 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트를 만들 경우 프로젝트에 대한 서비스 참조를 추가하면 개체가 개체 브라우저에 자동으로 로드됩니다.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 사용 하지 않는 경우 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]를 확장 하는 형식을 찾기 위해 생성 된 계약 코드를 검사 <xref:System.ServiceModel.ClientBase%601> 및 서비스 계약 인터페이스 `ISampleService`합니다. 이 경우 형식은 다음 코드와 비슷합니다.  
  
 [!code-csharp[C_GeneratedCodeFiles#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#14)]  
  
 생성자 중 하나를 사용하여 이 클래스를 로컬 개체로 만든 다음 구성하여 `ISampleService` 형식 서비스에 연결하는 데 사용할 수 있습니다.  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 개체를 먼저 만든 다음 단일 try/catch 블록에서 해당 개체를 사용하고 닫는 것이 좋습니다. `using` 문(`Using`의 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)])은 특정 예외 모드에서 예외를 마스킹할 수 있으므로 사용하지 마세요. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]다음 단원 및 같이 [를 사용 하 여 문을 사용 하 여 문제를 방지](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)합니다.  
  
### <a name="contracts-bindings-and-addresses"></a>계약, 바인딩 및 주소  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 개체를 만들려면 클라이언트 개체를 구성해야 합니다. 특히 서비스 있어야 *끝점* 사용 하도록 합니다. 끝점은 서비스 계약, 바인딩 및 주소의 조합입니다. ([!INCLUDE[crabout](../../../includes/crabout-md.md)] 끝점 참조 [끝점: 주소, 바인딩 및 계약](../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md).) 이 정보에는 일반적으로 [ <> \> ](../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md) Svcutil.exe 도구를 생성 하 고 클라이언트 개체를 만들 때 자동으로 로드 되는 것과 같은 클라이언트 응용 프로그램 구성 파일의 요소입니다. 두 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 형식에는 이 정보를 프로그래밍 방식으로 지정할 수 있게 해주는 오버로드가 있습니다.  
  
 예를 들어, 이전 예제에 사용된 `ISampleService`에 대해 생성된 구성 파일에는 다음과 같은 끝점 정보가 포함되어 있습니다.  
  
 <!-- TODO: review snippet reference [!code[C_GeneratedCodeFiles#19](../../../samples/snippets/common/VS_Snippets_CFX/c_generatedcodefiles/common/client.exe.config#19)]  -->  
  
 이 구성 파일은 `<client>` 요소에서 대상 끝점을 지정합니다. [!INCLUDE[crabout](../../../includes/crabout-md.md)]여러 대상 끝점을 사용 하 여 참조는 <xref:System.ServiceModel.ClientBase%601.%23ctor%2A?displayProperty=fullName> 또는 <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A?displayProperty=fullName> 생성자입니다.  
  
## <a name="calling-operations"></a>작업 호출  
 클라이언트 개체를 만들어 구성한 후 try/catch 블록을 만들고 로컬 개체에 대해서와 같은 방법으로 작업을 호출한 다음 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 개체를 닫습니다. 클라이언트 응용 프로그램이 첫 번째 작업을 호출하면 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]에서 기본 채널을 자동으로 엽니다. 개체가 재생되면 기본 채널이 닫힙니다. 또는 다른 작업을 호출하기 이전 또는 이후에 채널을 명시적으로 열었다가 닫을 수 있습니다.  
  
 예를 들어, 다음과 같은 서비스 계약을 가정해 봅니다.  
  
```csharp  
namespace Microsoft.ServiceModel.Samples  
{  
    using System;  
    using System.ServiceModel;  
  
    [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
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
}  
```  
  
```vb  
Namespace Microsoft.ServiceModel.Samples  
  
    Imports System  
    Imports System.ServiceModel  
  
    <ServiceContract(Namespace:= _  
    "http://Microsoft.ServiceModel.Samples")> _   
   Public Interface ICalculator  
        <OperationContract> _   
        Function Add(n1 As Double, n2 As Double) As Double  
        <OperationContract> _   
        Function Subtract(n1 As Double, n2 As Double) As Double  
        <OperationContract> _   
        Function Multiply(n1 As Double, n2 As Double) As Double  
        <OperationContract> _   
     Function Divide(n1 As Double, n2 As Double) As Double  
End Interface  
```  
  
 다음 코드 예제에 설명된 것처럼 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 개체를 만든 다음 해당 메서드를 호출하여 작업을 호출할 수 있습니다. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 개체 열기, 호출 및 닫기는 단일 try/catch 블록 내에서 발생합니다. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][WCF 클라이언트를 사용 하 여 서비스에 액세스](../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md) 및 [문 사용 시 문제 회피](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)합니다.  
  
 [!code-csharp[C_GeneratedCodeFiles#20](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#20)]  
  
## <a name="handling-errors"></a>오류 처리  
 기본 클라이언트 채널을 명시적으로 열거나 작업을 호출하여 자동으로 열 때, 클라이언트 또는 채널 개체를 사용하여 작업을 호출할 경우 또는 기본 클라이언트 채널을 닫을 때 클라이언트 응용 프로그램에서 예외가 발생할 수 있습니다. 것이 좋습니다 최소한 응용 프로그램 가능한 처리 하는 것 <xref:System.TimeoutException?displayProperty=fullName> 및 <xref:System.ServiceModel.CommunicationException?displayProperty=fullName> 예외 사항이 추가 <xref:System.ServiceModel.FaultException?displayProperty=fullName> 작업에서 반환 하는 SOAP 오류로 인해 throw 되는 개체입니다. 클라이언트 응용 프로그램에 발생 하는 작업 계약에 지정 된 SOAP 오류는 <xref:System.ServiceModel.FaultException%601?displayProperty=fullName> 여기서 형식 매개 변수는 SOAP 오류 세부 유형입니다. [!INCLUDE[crabout](../../../includes/crabout-md.md)]참조는 클라이언트 응용 프로그램에서 오류 조건을 처리, [보내기 / 받기 오류](../../../docs/framework/wcf/sending-and-receiving-faults.md)합니다. 전체 샘플은 클라이언트에서 오류를 처리 하는 방법에 대 한 참조 [예상 예외](../../../docs/framework/wcf/samples/expected-exceptions.md)합니다.  
  
## <a name="configuring-and-securing-clients"></a>클라이언트 구성 및 보안  
 클라이언트를 구성하려면 클라이언트 생성자와 속성을 사용하여 클라이언트 또는 채널 개체에 대한 대상 끝점 정보를 프로그래밍 방식으로 로드할 수도 있지만, 일반적으로 구성 파일에서 이 정보를 로드해야 합니다. 그러나 다양한 보안 시나리오에 대해 특정 클라이언트 동작을 활성화하는 추가 구성 단계를 수행해야 합니다.  
  
 예를 들어, 서비스 계약에 대한 보안 요구 사항이 서비스 계약 인터페이스에 선언되어 있고, Svcutil.exe에서 구성 파일을 만든 경우 해당 파일에는 일반적으로 서비스의 보안 요구 사항을 지원할 수 있는 바인딩이 포함되어 있습니다. 그러나, 클라이언트 자격 증명 구성처럼 추가 보안 구성이 필요한 경우도 있습니다. 에 대 한 보안 구성에 대 한 자세한 내용은 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 참조 [클라이언트 보안](../../../docs/framework/wcf/securing-clients.md)합니다.  
  
 또한 클라이언트 응용 프로그램에서 사용자 지정 런타임 동작과 같은 사용자 지정 수정을 사용할 수 있는 경우도 있습니다. [!INCLUDE[crabout](../../../includes/crabout-md.md)]사용자 지정 클라이언트 동작을 구성 하는 방법 [클라이언트 동작 구성](../../../docs/framework/wcf/configuring-client-behaviors.md)합니다.  
  
## <a name="creating-callback-objects-for-duplex-services"></a>이중 서비스에 대한 콜백 개체 만들기  
 이중 서비스는 계약 요구 사항에 따라 서비스를 호출하도록 콜백 개체를 제공하기 위해 클라이언트 응용 프로그램에서 구현해야 하는 콜백 계약을 지정합니다. 콜백 개체는 정식 서비스가 아니지만(예를 들어, 콜백 개체를 사용하여 채널을 시작할 수 없음) 구현 및 구성을 위해 일종의 서비스로 간주될 수 있습니다.  
  
 이중 서비스의 클라이언트는 다음을 수행해야 합니다.  
  
-   콜백 계약 클래스 구현  
  
-   콜백 계약 구현 클래스의 인스턴스를 만들고 사용 하 여 만들는 <xref:System.ServiceModel.InstanceContext?displayProperty=fullName> 전달 하는 개체는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 생성자입니다.  
  
-   작업 호출 및 작업 콜백 처리  
  
 이중 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 개체는 콜백 서비스 구성을 포함하여 콜백을 지원하는 데 필요한 기능을 노출한다는 점만 제외하고 비이중 클라이언트 개체와 같은 역할을 합니다.  
  
 예를 들어, 속성을 사용 하 여 콜백 개체 런타임 동작의 다양 한 측면을 제어할 수 있습니다는 <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=fullName> 콜백 클래스에 있습니다. 사용 하는 또 다른 예로 <xref:System.ServiceModel.Description.CallbackDebugBehavior?displayProperty=fullName> 콜백 개체를 호출 하는 서비스에 예외 정보를 반환 하도록 하는 클래스입니다. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][이중 서비스](../../../docs/framework/wcf/feature-details/duplex-services.md)합니다. 전체 샘플을 참조 하십시오. [이중](../../../docs/framework/wcf/samples/duplex.md)합니다.  
  
 인터넷 정보 서비스 (IIS) 5.1을 실행 하는 Windows XP 컴퓨터에서 이중 클라이언트를 지정 해야 사용 하 여 클라이언트 기본 주소는 <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=fullName> 클래스 또는 예외가 throw 됩니다. 다음 코드 예제에서는 코드에서 이 작업을 수행하는 방법을 보여 줍니다.  
  
 [!code-csharp[S_DualHttp#8](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#8)]
 [!code-vb[S_DualHttp#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_dualhttp/vb/module1.vb#8)]  
  
 다음 코드에서는 구성 파일에서 이 작업을 수행하는 방법을 보여 줍니다.  
  
 [!code-csharp[S_DualHttp#134](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#134)]  
  
## <a name="calling-services-asynchronously"></a>비동기적으로 서비스 호출  
 작업이 호출되는 방법은 클라이언트 개발자에 의해 지정됩니다. 작업을 구성하는 메시지는 관리되는 코드에 표시될 때 동기 메서드나 비동기 메서드에 매핑될 수 있기 때문입니다. 따라서 작업을 비동기적으로 호출하는 클라이언트를 빌드하려면 Svcutil.exe에서 `/async` 옵션을 사용하여 비동기 클라이언트 코드를 생성할 수 있습니다. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][방법: 서비스 작업을 비동기적으로 호출](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md)합니다.  
  
## <a name="calling-services-using-wcf-client-channels"></a>WCF 클라이언트 채널을 사용하여 서비스 호출  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]클라이언트 형식은 확장 <xref:System.ServiceModel.ClientBase%601>에서 파생 되는 <xref:System.ServiceModel.IClientChannel?displayProperty=fullName> 기본 채널 시스템을 노출 하는 인터페이스입니다. 대상 서비스 계약을 사용 하 여 서비스를 호출할 수는 <xref:System.ServiceModel.ChannelFactory%601?displayProperty=fullName> 클래스입니다. 자세한 내용은 다음을 참조 하십시오. [WCF 클라이언트 아키텍처](../../../docs/framework/wcf/feature-details/client-architecture.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.ClientBase%601?displayProperty=fullName>   
 <xref:System.ServiceModel.ChannelFactory%601?displayProperty=fullName>