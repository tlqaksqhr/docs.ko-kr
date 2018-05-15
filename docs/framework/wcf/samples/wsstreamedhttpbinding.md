---
title: WSStreamedHttpBinding
ms.date: 03/30/2017
ms.assetid: 97ce4d3d-ca6f-45fa-b33b-2429bb84e65b
ms.openlocfilehash: b0a4c316957a002f7541d230f96299e3f43ef778
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="wsstreamedhttpbinding"></a><span data-ttu-id="32835-102">WSStreamedHttpBinding</span><span class="sxs-lookup"><span data-stu-id="32835-102">WSStreamedHttpBinding</span></span>
<span data-ttu-id="32835-103">이 샘플에서는 HTTP 전송이 사용될 때 스트리밍 시나리오를 지원하도록 디자인된 바인딩을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="32835-103">The sample demonstrates how to create a binding that is designed to support streaming scenarios when the HTTP transport is used.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32835-104">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32835-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="32835-105">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32835-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="32835-106">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="32835-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="32835-107">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="32835-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="32835-108">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32835-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Binding\WSStreamedHttpBinding`  
  
 <span data-ttu-id="32835-109">새 표준 바인딩을 만들고 구성하기 위한 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="32835-109">The steps to create and configure a new standard binding are as follows.</span></span>  
  
1.  <span data-ttu-id="32835-110">새 표준 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="32835-110">Create a new standard binding</span></span>  
  
     <span data-ttu-id="32835-111">BasicHttpBinding 및 netTcpBinding 등 표준 바인딩이 Windows Communication Foundation (WCF)의 기본 전송 및 특정 요구 사항에 대 한 채널 스택을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="32835-111">The standard bindings in Windows Communication Foundation (WCF) such as basicHttpBinding, and netTcpBinding configure the underlying transports and channel stack for specific requirements.</span></span> <span data-ttu-id="32835-112">이 샘플에서 `WSStreamedHttpBinding`은 스트리밍을 지원하도록 채널 스택을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="32835-112">In this sample, `WSStreamedHttpBinding` configures the channel stack to support streaming.</span></span> <span data-ttu-id="32835-113">기본적으로 WS-Security 및 신뢰할 수 있는 메시징은 스트리밍에서 지원되지 않으므로 이러한 기능은 둘 다 채널 스택에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32835-113">By default, WS-Security and reliable messaging are not added to the channel stack because both features are not supported by streaming.</span></span> <span data-ttu-id="32835-114">새 바인딩은 `WSStreamedHttpBinding`에서 파생되는 <xref:System.ServiceModel.Channels.Binding> 클래스에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="32835-114">The new binding is implemented in the class `WSStreamedHttpBinding` that derives from <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="32835-115">`WSStreamedHttpBinding`은 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>, <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> 및 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> 바인딩 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="32835-115">The `WSStreamedHttpBinding` contains the following binding elements: <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>, <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>, and <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>.</span></span> <span data-ttu-id="32835-116">다음 샘플 코드와 같이 결과 바인딩 스택을 구성하기 위해 클래스에서 `CreateBindingElements()` 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="32835-116">The class provides a `CreateBindingElements()` method to configure the resulting binding stack, as shown in the following sample code.</span></span>  
  
    ```  
    public override BindingElementCollection CreateBindingElements()  
    {  
         // return collection of BindingElements  
         BindingElementCollection bindingElements = new BindingElementCollection();  
  
        // the order of binding elements within the collection is important: layered channels are applied in the order included, followed by  
        // the message encoder, and finally the transport at the end  
        if (flowTransactions)  
        {  
            bindingElements.Add(transactionFlow);  
        }  
        bindingElements.Add(textEncoding);  
  
        // add transport (http or https)  
        bindingElements.Add(transport);  
        return bindingElements.Clone();  
    }  
    ```  
  
2.  <span data-ttu-id="32835-117">구성 지원 추가</span><span class="sxs-lookup"><span data-stu-id="32835-117">Add configuration support</span></span>  
  
     <span data-ttu-id="32835-118">구성을 통해 전송을 노출하기 위해 샘플에서는 두 개의 추가 클래스인 `WSStreamedHttpBindingConfigurationElement` 및 `WSStreamedHttpBindingSection`을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="32835-118">To expose the transport through configuration the sample implements two more classes—`WSStreamedHttpBindingConfigurationElement` and `WSStreamedHttpBindingSection`.</span></span> <span data-ttu-id="32835-119">클래스 `WSStreamedHttpBindingSection` 는 <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> 노출 하 `WSStreamedHttpBinding` WCF 구성 시스템에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32835-119">The class `WSStreamedHttpBindingSection` is a <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> that exposes `WSStreamedHttpBinding` to the WCF configuration system.</span></span> <span data-ttu-id="32835-120">대량의 구현은 `WSStreamedHttpBindingConfigurationElement`에서 파생되는 <xref:System.ServiceModel.Configuration.StandardBindingElement>에 위임됩니다.</span><span class="sxs-lookup"><span data-stu-id="32835-120">The bulk of the implementation is delegated to `WSStreamedHttpBindingConfigurationElement`, which derives from <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span></span> <span data-ttu-id="32835-121">`WSStreamedHttpBindingConfigurationElement` 클래스에는 `WSStreamedHttpBinding`의 속성에 해당하는 속성과 각 구성 요소를 바인딩에 매핑하기 위한 함수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32835-121">The class `WSStreamedHttpBindingConfigurationElement` has properties that correspond to the properties of `WSStreamedHttpBinding`, and functions to map each configuration element to a binding.</span></span>  
  
     <span data-ttu-id="32835-122">서비스의 구성 파일에 다음 섹션을 추가하여 구성 시스템에 처리기를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="32835-122">Register the handler with the configuration system, by adding the following section to the service's configuration file.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <extensions>  
          <bindingExtensions>  
            <add name="wsStreamedHttpBinding" type="Microsoft.ServiceModel.Samples.WSStreamedHttpBindingCollectionElement, WSStreamedHttpBinding, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null" />  
          </bindingExtensions>  
        </extensions>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="32835-123">그런 다음 serviceModel 구성 섹션에서 처리기를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32835-123">The handler can then be referenced from the serviceModel configuration section.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <endpoint  
                    address="https://localhost/servicemodelsamples/service.svc"  
                    bindingConfiguration="Binding"  
                    binding="wsStreamedHttpBinding"  
                    contract="Microsoft.ServiceModel.Samples.IStreamedEchoService"/>  
        </client>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="32835-124">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="32835-124">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="32835-125">다음 명령을 사용하여 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="32835-125">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="32835-126">에 나열 된 단계를 수행 했는지 확인 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="32835-126">Ensure that you have performed the steps listed in [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="32835-127">수행 했는지 확인 하십시오.는 [인터넷 정보 서비스 (IIS) 서버 인증서 설치 지침](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="32835-127">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>  
  
4.  <span data-ttu-id="32835-128">지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="32835-128">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
5.  <span data-ttu-id="32835-129">다중 컴퓨터 구성에서 샘플을 실행 하려면의 지침에 따라 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="32835-129">To run the sample in a cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
6.  <span data-ttu-id="32835-130">클라이언트 창이 표시되면 "Sample.txt"를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="32835-130">When the client window displays, type "Sample.txt".</span></span> <span data-ttu-id="32835-131">디렉터리에서 "Copy of Sample.txt"를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32835-131">You should find a "Copy of Sample.txt" in your directory.</span></span>  
  
## <a name="the-wsstreamedhttpbinding-sample-service"></a><span data-ttu-id="32835-132">WSStreamedHttpBinding 샘플 서비스</span><span class="sxs-lookup"><span data-stu-id="32835-132">The WSStreamedHttpBinding Sample Service</span></span>  
 <span data-ttu-id="32835-133">`WSStreamedHttpBinding`을 사용하는 샘플 서비스는 서비스 하위 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32835-133">The sample service that uses `WSStreamedHttpBinding` is located in the service subdirectory.</span></span> <span data-ttu-id="32835-134">`OperationContract` 구현에서는 `MemoryStream`을 반환하기 전에 `MemoryStream`을 사용하여 들어오는 스트림에서 모든 데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="32835-134">The implementation of `OperationContract` uses a `MemoryStream` to first retrieve all data from the incoming stream before returning the `MemoryStream`.</span></span> <span data-ttu-id="32835-135">샘플 서비스는 IIS(인터넷 정보 서비스)에 의해 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="32835-135">The sample service is hosted by Internet Information Services (IIS).</span></span>  
  
```  
[ServiceContract]  
public interface IStreamedEchoService  
{  
    [OperationContract]  
    Stream Echo(Stream data);  
}  
  
public class StreamedEchoService : IStreamedEchoService  
{  
    public Stream Echo(Stream data)  
    {  
        MemoryStream dataStorage = new MemoryStream();  
        byte[] byteArray = new byte[8192];  
        int bytesRead = data.Read(byteArray, 0, 8192);  
        while (bytesRead > 0)  
        {  
            dataStorage.Write(byteArray, 0, bytesRead);  
            bytesRead = data.Read(byteArray, 0, 8192);  
        }  
        data.Close();  
        dataStorage.Seek(0, SeekOrigin.Begin);  
  
        return dataStorage;  
    }  
}  
```  
  
## <a name="the-wsstreamedhttpbinding-sample-client"></a><span data-ttu-id="32835-136">WSStreamedHttpBinding 샘플 클라이언트</span><span class="sxs-lookup"><span data-stu-id="32835-136">The WSStreamedHttpBinding Sample Client</span></span>  
 <span data-ttu-id="32835-137">`WSStreamedHttpBinding`을 사용하여 상호 작용하는 데 사용되는 클라이언트는 클라이언트 하위 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32835-137">The client that is used to interact with the service using `WSStreamedHttpBinding` is located in the client subdirectory.</span></span> <span data-ttu-id="32835-138">보안 경고가 표시와 같은 HTTPS 주소 브라우저에 액세스 하려고 할 때이 샘플에 사용 된 인증서는 Makecert.exe를 사용 하 여 만든 테스트 인증서 이므로 https://localhost/servicemodelsamples/service.svc합니다.</span><span class="sxs-lookup"><span data-stu-id="32835-138">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert displays when you attempt to access an HTTPS address in your browser such as https://localhost/servicemodelsamples/service.svc.</span></span> <span data-ttu-id="32835-139">에서 테스트 인증서를 사용 하도록 WCF 클라이언트를 허용 하려면 일부 추가 코드가 보안 경고가 표시 되지 않도록 클라이언트에 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="32835-139">To allow the WCF client to work with a test certificate in place, some additional code has been added to the client to suppress the security alert.</span></span> <span data-ttu-id="32835-140">코드 및 함께 사용되는 클래스는 프로덕션 인증서를 사용할 때에는 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32835-140">The code and the accompanying class are not required when using production certificates.</span></span>  
  
```  
// WARNING: This code is only required for test certificates such as those created by makecert. It is   
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
## <a name="see-also"></a><span data-ttu-id="32835-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="32835-141">See Also</span></span>
