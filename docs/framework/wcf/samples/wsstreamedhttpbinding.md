---
title: WSStreamedHttpBinding
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97ce4d3d-ca6f-45fa-b33b-2429bb84e65b
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d6259640bae2b4be4fac73883df8945bf1db7ff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="wsstreamedhttpbinding"></a><span data-ttu-id="09fca-102">WSStreamedHttpBinding</span><span class="sxs-lookup"><span data-stu-id="09fca-102">WSStreamedHttpBinding</span></span>
<span data-ttu-id="09fca-103">이 샘플에서는 HTTP 전송이 사용될 때 스트리밍 시나리오를 지원하도록 디자인된 바인딩을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-103">The sample demonstrates how to create a binding that is designed to support streaming scenarios when the HTTP transport is used.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09fca-104">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="09fca-105">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="09fca-106">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="09fca-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="09fca-107">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="09fca-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="09fca-108">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Binding\WSStreamedHttpBinding`  
  
 <span data-ttu-id="09fca-109">새 표준 바인딩을 만들고 구성하기 위한 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-109">The steps to create and configure a new standard binding are as follows.</span></span>  
  
1.  <span data-ttu-id="09fca-110">새 표준 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="09fca-110">Create a new standard binding</span></span>  
  
     <span data-ttu-id="09fca-111">basicHttpBinding 및 netTcpBinding과 같은 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]의 표준 바인딩은 특정 요구 사항에 맞게 기본 전송 및 채널 스택을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-111">The standard bindings in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] such as basicHttpBinding, and netTcpBinding configure the underlying transports and channel stack for specific requirements.</span></span> <span data-ttu-id="09fca-112">이 샘플에서 `WSStreamedHttpBinding`은 스트리밍을 지원하도록 채널 스택을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-112">In this sample, `WSStreamedHttpBinding` configures the channel stack to support streaming.</span></span> <span data-ttu-id="09fca-113">기본적으로 WS-Security 및 신뢰할 수 있는 메시징은 스트리밍에서 지원되지 않으므로 이러한 기능은 둘 다 채널 스택에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-113">By default, WS-Security and reliable messaging are not added to the channel stack because both features are not supported by streaming.</span></span> <span data-ttu-id="09fca-114">새 바인딩은 `WSStreamedHttpBinding`에서 파생되는 <xref:System.ServiceModel.Channels.Binding> 클래스에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-114">The new binding is implemented in the class `WSStreamedHttpBinding` that derives from <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="09fca-115">`WSStreamedHttpBinding`은 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>, <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> 및 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> 바인딩 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-115">The `WSStreamedHttpBinding` contains the following binding elements: <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>, <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>, and <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>.</span></span> <span data-ttu-id="09fca-116">다음 샘플 코드와 같이 결과 바인딩 스택을 구성하기 위해 클래스에서 `CreateBindingElements()` 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-116">The class provides a `CreateBindingElements()` method to configure the resulting binding stack, as shown in the following sample code.</span></span>  
  
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
  
2.  <span data-ttu-id="09fca-117">구성 지원 추가</span><span class="sxs-lookup"><span data-stu-id="09fca-117">Add configuration support</span></span>  
  
     <span data-ttu-id="09fca-118">구성을 통해 전송을 노출하기 위해 샘플에서는 두 개의 추가 클래스인 `WSStreamedHttpBindingConfigurationElement` 및 `WSStreamedHttpBindingSection`을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-118">To expose the transport through configuration the sample implements two more classes—`WSStreamedHttpBindingConfigurationElement` and `WSStreamedHttpBindingSection`.</span></span> <span data-ttu-id="09fca-119">`WSStreamedHttpBindingSection` 클래스는 <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> 구성 시스템에 `WSStreamedHttpBinding`을 노출하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]입니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-119">The class `WSStreamedHttpBindingSection` is a <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> that exposes `WSStreamedHttpBinding` to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configuration system.</span></span> <span data-ttu-id="09fca-120">대량의 구현은 `WSStreamedHttpBindingConfigurationElement`에서 파생되는 <xref:System.ServiceModel.Configuration.StandardBindingElement>에 위임됩니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-120">The bulk of the implementation is delegated to `WSStreamedHttpBindingConfigurationElement`, which derives from <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span></span> <span data-ttu-id="09fca-121">`WSStreamedHttpBindingConfigurationElement` 클래스에는 `WSStreamedHttpBinding`의 속성에 해당하는 속성과 각 구성 요소를 바인딩에 매핑하기 위한 함수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-121">The class `WSStreamedHttpBindingConfigurationElement` has properties that correspond to the properties of `WSStreamedHttpBinding`, and functions to map each configuration element to a binding.</span></span>  
  
     <span data-ttu-id="09fca-122">서비스의 구성 파일에 다음 섹션을 추가하여 구성 시스템에 처리기를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-122">Register the handler with the configuration system, by adding the following section to the service's configuration file.</span></span>  
  
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
  
     <span data-ttu-id="09fca-123">그런 다음 serviceModel 구성 섹션에서 처리기를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-123">The handler can then be referenced from the serviceModel configuration section.</span></span>  
  
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
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="09fca-124">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="09fca-124">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="09fca-125">다음 명령을 사용하여 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-125">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="09fca-126">에 나열 된 단계를 수행 했는지 확인 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-126">Ensure that you have performed the steps listed in [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="09fca-127">수행 했는지 확인 하십시오.는 [인터넷 정보 서비스 (IIS) 서버 인증서 설치 지침](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-127">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>  
  
4.  <span data-ttu-id="09fca-128">지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-128">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
5.  <span data-ttu-id="09fca-129">다중 컴퓨터 구성에서 샘플을 실행 하려면의 지침에 따라 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-129">To run the sample in a cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
6.  <span data-ttu-id="09fca-130">클라이언트 창이 표시되면 "Sample.txt"를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-130">When the client window displays, type "Sample.txt".</span></span> <span data-ttu-id="09fca-131">디렉터리에서 "Copy of Sample.txt"를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-131">You should find a "Copy of Sample.txt" in your directory.</span></span>  
  
## <a name="the-wsstreamedhttpbinding-sample-service"></a><span data-ttu-id="09fca-132">WSStreamedHttpBinding 샘플 서비스</span><span class="sxs-lookup"><span data-stu-id="09fca-132">The WSStreamedHttpBinding Sample Service</span></span>  
 <span data-ttu-id="09fca-133">`WSStreamedHttpBinding`을 사용하는 샘플 서비스는 서비스 하위 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-133">The sample service that uses `WSStreamedHttpBinding` is located in the service subdirectory.</span></span> <span data-ttu-id="09fca-134">`OperationContract` 구현에서는 `MemoryStream`을 반환하기 전에 `MemoryStream`을 사용하여 들어오는 스트림에서 모든 데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-134">The implementation of `OperationContract` uses a `MemoryStream` to first retrieve all data from the incoming stream before returning the `MemoryStream`.</span></span> <span data-ttu-id="09fca-135">샘플 서비스는 IIS(인터넷 정보 서비스)에 의해 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-135">The sample service is hosted by Internet Information Services (IIS).</span></span>  
  
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
  
## <a name="the-wsstreamedhttpbinding-sample-client"></a><span data-ttu-id="09fca-136">WSStreamedHttpBinding 샘플 클라이언트</span><span class="sxs-lookup"><span data-stu-id="09fca-136">The WSStreamedHttpBinding Sample Client</span></span>  
 <span data-ttu-id="09fca-137">`WSStreamedHttpBinding`을 사용하여 상호 작용하는 데 사용되는 클라이언트는 클라이언트 하위 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-137">The client that is used to interact with the service using `WSStreamedHttpBinding` is located in the client subdirectory.</span></span> <span data-ttu-id="09fca-138">이 샘플에 사용된 인증서는 Makecert.exe를 사용하여 만든 테스트 인증서이므로 브라우저에서 https://localhost/servicemodelsamples/service.svc와 같은 HTTPS 주소에 액세스하려 하면 보안 경고가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-138">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert displays when you attempt to access an HTTPS address in your browser such as https://localhost/servicemodelsamples/service.svc.</span></span> <span data-ttu-id="09fca-139">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트에서 제공되는 테스트 인증서를 사용하여 작업을 수행할 수 있도록 클라이언트에 추가 코드를 추가하여 보안 경고가 나타나지 않게 합니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-139">To allow the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client to work with a test certificate in place, some additional code has been added to the client to suppress the security alert.</span></span> <span data-ttu-id="09fca-140">코드 및 함께 사용되는 클래스는 프로덕션 인증서를 사용할 때에는 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09fca-140">The code and the accompanying class are not required when using production certificates.</span></span>  
  
```  
// WARNING: This code is only required for test certificates such as those created by makecert. It is   
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
## <a name="see-also"></a><span data-ttu-id="09fca-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09fca-141">See Also</span></span>
