---
title: "방법: 구성 파일을 사용하여 서비스의 메타데이터 게시"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f061443f-92df-4824-b36a-609c4cd14a17
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 42f70cd34f65d5393d79b8ace4f9eb704f309d0f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-publish-metadata-for-a-service-using-a-configuration-file"></a><span data-ttu-id="8640f-102">방법: 구성 파일을 사용하여 서비스의 메타데이터 게시</span><span class="sxs-lookup"><span data-stu-id="8640f-102">How to: Publish Metadata for a Service Using a Configuration File</span></span>
<span data-ttu-id="8640f-103">이 항목은 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스의 메타데이터 게시를 보여 주는 두 방법 항목 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-103">This is one of two how-to topics that demonstrate publishing metadata for a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service.</span></span> <span data-ttu-id="8640f-104">서비스에서 메타데이터를 게시하는 방법을 지정하는 두 가지 방법은 구성 파일을 사용하는 방법과 코드를 사용하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-104">There are two ways to specify how a service should publish metadata, using a configuration file and using code.</span></span> <span data-ttu-id="8640f-105">이 항목에서는 구성 파일을 사용하여 서비스에 대해 메타데이터를 게시하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-105">This topic shows how to publish metadata for a service using a configuration file.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="8640f-106">이 항목에서는 보호되지 않은 방식으로 메타데이터를 게시하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-106">This topic shows how to publish metadata in an unsecure manner.</span></span> <span data-ttu-id="8640f-107">즉, 모든 클라이언트가 서비스에서 메타데이터를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-107">Any client can retrieve the metadata from the service.</span></span> <span data-ttu-id="8640f-108">안전한 방식으로 메타 데이터를 게시 하려면 해당 서비스에 필요한 경우 참조 [사용자 지정 보안 메타 데이터 끝점](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-108">If you require your service to publish metadata in a secure manner, see [Custom Secure Metadata Endpoint](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="8640f-109">코드에서 메타 데이터 게시 참조 [하는 방법: 서비스를 사용 하 여 코드에 대 한 메타 데이터 게시](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-109"> publishing metadata in code, see [How to: Publish Metadata for a Service Using Code](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).</span></span> <span data-ttu-id="8640f-110">메타데이터를 게시하면 클라이언트에서 WS-Transfer GET 요청을 사용하는 메타데이터 또는 `?wsdl` 쿼리 문자열을 사용하는 HTTP/GET 요청을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-110">Publishing metadata allows clients to retrieve the metadata using a WS-Transfer GET request or an HTTP/GET request using the `?wsdl` query string.</span></span> <span data-ttu-id="8640f-111">코드가 작동 중인지 확인하려면 기본 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-111">To be sure that the code is working, create a basic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="8640f-112">편의상 다음 코드로 된 기본 자체 호스팅 서비스가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-112">For simplicity, a basic self-hosted service is provided in the following code.</span></span>  
  
```csharp  
using System;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
  
namespace Metadata.Samples  
{  
    [ServiceContract]  
    public interface ISimpleService  
    {  
        [OperationContract]  
        string SimpleMethod(string msg);  
    }  
  
    class SimpleService : ISimpleService  
    {  
        public string SimpleMethod(string msg)  
        {  
            Console.WriteLine("The caller passed in " + msg);  
            return "Hello " + msg;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost host = new ServiceHost(typeof(SimpleService),  
                new Uri("http://localhost:8001/MetadataSample"));   
            try  
            {  
                // Open the service host to accept incoming calls  
                host.Open();  
  
                // The service can now be accessed.  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
  
                // Close the ServiceHostBase to shutdown the service.  
                host.Close();  
            }  
            catch (CommunicationException commProblem)  
            {  
                Console.WriteLine("There was a communication problem. " + commProblem.Message);  
                Console.Read();  
            }  
        }  
    }  
}  
```  
  
 <span data-ttu-id="8640f-113">이 서비스는 구성 파일을 사용하여 구성된 자체 호스팅 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-113">This service is a self-hosted service, which is configured using a configuration file.</span></span> <span data-ttu-id="8640f-114">다음 구성 파일을 사용해 작업을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-114">The following configuration file serves as a starting point.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Metadata.Example.SimpleService">  
        <endpoint address=""  
                  binding="basicHttpBinding"  
                  contract="Metadata.Example.ISimpleService" />  
      </service>  
    </services>  
    <behaviors>  
  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="to-publish-metadata-for-a-wcf-service-using-an-application-configuration-file"></a><span data-ttu-id="8640f-115">응용 프로그램 구성 파일을 사용하여 WCF 서비스의 메타데이터를 게시하려면</span><span class="sxs-lookup"><span data-stu-id="8640f-115">To publish metadata for a WCF service using an application configuration file</span></span>  
  
1.  <span data-ttu-id="8640f-116">App.config 파일 내에서 `</services>` 요소를 닫은 후 `<behaviors>` 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-116">Within the App.config file, after the closing `</services>` element, create a `<behaviors>` element.</span></span>  
  
  
  
2.  <span data-ttu-id="8640f-117">`<behaviors>` 요소 내에서 `<serviceBehaviors>` 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-117">Within the `<behaviors>` element, add a `<serviceBehaviors>` element.</span></span>  
  
  
  
3.  <span data-ttu-id="8640f-118">`<behavior>``name` 요소를 `<serviceBehaviors>``<behavior>` 요소에 추가하고  요소의  특성에 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-118">Add a `<behavior>` element to the `<serviceBehaviors>` element and specify a value for the `name` attribute of the `<behavior>` element.</span></span>  
  
  
  
4.  <span data-ttu-id="8640f-119">`<serviceMetadata>` 요소를 `<behavior>` 요소에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-119">Add a `<serviceMetadata>` element to the `<behavior>` element.</span></span> <span data-ttu-id="8640f-120">`httpGetEnabled` 특성을 `true`로 설정하고 `policyVersion` 특성을 Policy15로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-120">Set the `httpGetEnabled` attribute to `true` and the `policyVersion` attribute to Policy15.</span></span> <span data-ttu-id="8640f-121">`httpGetEnabled`를 사용하면 서비스가 HTTP GET 요청으로 수행된 메타데이터 요청에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-121">`httpGetEnabled` allows the service to respond to metadata requests made by an HTTP GET request.</span></span> <span data-ttu-id="8640f-122">`policyVersion`에 따라 서비스는 메타데이터를 생성할 때 WS-Policy 1.5를 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-122">`policyVersion` tells the service to conform to WS-Policy 1.5 when generating metadata.</span></span>  
  
  
  
5.  <span data-ttu-id="8640f-123">다음 코드 예제와 같이 `behaviorConfiguration` 특성을 `<service>` 요소에 추가하고 1단계에 추가된 `name` 요소의 `<behavior>` 특성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-123">Add a `behaviorConfiguration` attribute to the `<service>` element and specify the `name` attribute of the `<behavior>` element added in step 1, as shown in the following code example.</span></span>  
  
    ```xml  
    <services>  
      <service  
          name="Metadata.Example.SimpleService"  
          behaviorConfiguration="SimpleServiceBehavior">  
        ...  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="SimpleServiceBehavior">  
          <serviceMetadata httpGetEnabled="True" policyVersion="Policy15" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
6.  <span data-ttu-id="8640f-124">다음 코드 예제와 같이 계약이 `<endpoint>`로 설정된 하나 이상의 `IMetadataExchange` 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-124">Add one or more `<endpoint>` elements with the contract set to `IMetadataExchange`, as shown in the following code example.</span></span>  
  
    ```xml  
    <services>  
      <service  
          name="Metadata.Example.SimpleService"  
          behaviorConfiguration="SimpleServiceBehavior">  
  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  contract="Metadata.Example.ISimpleService" />  
  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
    ```  
  
7.  <span data-ttu-id="8640f-125">이전 단계에 추가된 메타데이터 끝점에 대해 `binding` 특성을 다음 중 하나로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-125">For the metadata endpoints added in the previous step, set the `binding` attribute to one of the following:</span></span>  
  
    -   <span data-ttu-id="8640f-126">HTTP 게시의 경우 `mexHttpBinding`</span><span class="sxs-lookup"><span data-stu-id="8640f-126">`mexHttpBinding` for HTTP publication.</span></span>  
  
    -   <span data-ttu-id="8640f-127">HTTPS 게시의 경우 `mexHttpsBinding`</span><span class="sxs-lookup"><span data-stu-id="8640f-127">`mexHttpsBinding` for HTTPS publication.</span></span>  
  
    -   <span data-ttu-id="8640f-128">명명된 파이프 게시의 경우 `mexNamedPipeBinding`</span><span class="sxs-lookup"><span data-stu-id="8640f-128">`mexNamedPipeBinding` for named pipe publication.</span></span>  
  
    -   <span data-ttu-id="8640f-129">TCP 게시의 경우 `mexTcpBinding`</span><span class="sxs-lookup"><span data-stu-id="8640f-129">`mexTcpBinding` for TCP publication.</span></span>  
  
8.  <span data-ttu-id="8640f-130">이전 단계에 추가된 메타데이터 끝점에 대해 주소를 다음과 같이 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-130">For the metadata endpoints added in a previous step, set the address equal to:</span></span>  
  
    -   <span data-ttu-id="8640f-131">기본 주소가 메타데이터 바인딩과 동일한 경우 호스트 응용 프로그램의 기본 주소를 게시 지점으로 사용하는 빈 문자열</span><span class="sxs-lookup"><span data-stu-id="8640f-131">An empty string to use the host application's base address as the publication point if the base address is the same as the metadata binding.</span></span>  
  
    -   <span data-ttu-id="8640f-132">호스트 응용 프로그램에 기본 주소가 있는 경우 상대 주소</span><span class="sxs-lookup"><span data-stu-id="8640f-132">A relative address if the host application has a base address.</span></span>  
  
    -   <span data-ttu-id="8640f-133">절대 경로</span><span class="sxs-lookup"><span data-stu-id="8640f-133">An absolute address.</span></span>  
  
9. <span data-ttu-id="8640f-134">콘솔 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-134">Build and run the console application.</span></span>  
  
10. <span data-ttu-id="8640f-135">Internet Explorer를 사용하여 서비스의 기본 주소(이 샘플에서는 http://localhost:8001/MetadataSample)를 찾아 메타데이터 게시가 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-135">Use Internet Explorer to browse to the base address of the service (http://localhost:8001/MetadataSample in this sample) and verify that the metadata publishing is turned on.</span></span> <span data-ttu-id="8640f-136">그렇지 않으면 "이 서비스에 대한 메타데이터 게시는 현재 사용할 수 없습니다."라는 메시지가 결과 페이지의 맨 위에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-136">If not, a message at the top of the resulting page displays: "Metadata publishing for this service is currently disabled."</span></span>  
  
### <a name="to-use-default-endpoints"></a><span data-ttu-id="8640f-137">기본 끝점을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="8640f-137">To use default endpoints</span></span>  
  
1.  <span data-ttu-id="8640f-138">기본 끝점을 사용하는 서비스에서 메타데이터를 구성하려면 이전 예제와 같이 구성 파일에 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>를 구성하되 끝점은 지정하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="8640f-138">To configure metadata on a service that uses default endpoints, specify the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> in the configuration file as in the previous example, but do not specify any endpoints.</span></span> <span data-ttu-id="8640f-139">이렇게 구성하면 구성 파일이 다음과 같아집니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-139">The configuration file would then look like this.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <behaviors>  
          <serviceBehaviors>  
            <behavior name="SimpleServiceBehavior">  
              <serviceMetadata httpGetEnabled="True" policyVersion="Policy12" />  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="8640f-140">서비스에 포함된 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>의 `httpGetEnabled`가 `true`로 설정되어 있으므로 서비스의 메타데이터 게시 기능은 사용하도록 설정되었으며, 끝점을 명시적으로 추가하지 않았으므로 런타임이 기본 끝점을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-140">Because the service has a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> with the `httpGetEnabled` set to `true`, the service has publishing metadata enabled, and because no endpoints were explicitly added, the runtime adds the default endpoints.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="8640f-141">기본 끝점, 바인딩 및 동작, 참조 [단순화 된 구성](../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스에 대 한 구성을 단순화](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-141"> default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8640f-142">예</span><span class="sxs-lookup"><span data-stu-id="8640f-142">Example</span></span>  
 <span data-ttu-id="8640f-143">다음 코드 예제에서는 기본 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스의 구현 및 서비스의 메타데이터를 게시하는 구성 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8640f-143">The following code example shows the implementation of a basic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service and the configuration file that publishes metadata for the service.</span></span>  
  
```csharp  
using System;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
  
namespace Metadata.Samples  
{  
    [ServiceContract]  
    public interface ISimpleService  
    {  
        [OperationContract]  
        string SimpleMethod(string msg);  
    }  
  
    class SimpleService : ISimpleService  
    {  
        public string SimpleMethod(string msg)  
        {  
            Console.WriteLine("The caller passed in " + msg);  
            return "Hello " + msg;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost host = new ServiceHost(typeof(SimpleService),  
                new Uri("http://localhost:8001/MetadataSample"));   
            try  
            {  
                // Open the service host to accept incoming calls  
                host.Open();  
  
                // The service can now be accessed.  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
  
                // Close the ServiceHostBase to shutdown the service.  
                host.Close();  
            }  
            catch (CommunicationException commProblem)  
            {  
                Console.WriteLine("There was a communication problem. " + commProblem.Message);  
                Console.Read();  
            }  
        }  
    }  
}  
```  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="SimpleServiceBehavior">  
          <serviceMetadata httpGetEnabled="True" policyVersion="Policy12" />  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8640f-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8640f-144">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
 [<span data-ttu-id="8640f-145">방법: 관리되는 응용 프로그램에서 WCF 서비스 호스트</span><span class="sxs-lookup"><span data-stu-id="8640f-145">How to: Host a WCF Service in a Managed Application</span></span>](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)  
 [<span data-ttu-id="8640f-146">자체 호스팅</span><span class="sxs-lookup"><span data-stu-id="8640f-146">Self-Host</span></span>](../../../../docs/framework/wcf/samples/self-host.md)  
 [<span data-ttu-id="8640f-147">메타데이터 아키텍처 개요</span><span class="sxs-lookup"><span data-stu-id="8640f-147">Metadata Architecture Overview</span></span>](../../../../docs/framework/wcf/feature-details/metadata-architecture-overview.md)  
 [<span data-ttu-id="8640f-148">메타데이터 사용</span><span class="sxs-lookup"><span data-stu-id="8640f-148">Using Metadata</span></span>](../../../../docs/framework/wcf/feature-details/using-metadata.md)  
 [<span data-ttu-id="8640f-149">방법: 코드를 사용하여 서비스에 대한 메타데이터 게시</span><span class="sxs-lookup"><span data-stu-id="8640f-149">How to: Publish Metadata for a Service Using Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)
