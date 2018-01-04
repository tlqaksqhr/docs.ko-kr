---
title: "방법: WebSocket을 통해 통신하는 WCF 서비스 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bafbbd89-eab8-4e9a-b4c3-b7b0178e12d8
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 99d091e5ef0998a3818609b7d52ecd62a609eeb1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-wcf-service-that-communicates-over-websockets"></a><span data-ttu-id="7391d-102">방법: WebSocket을 통해 통신하는 WCF 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="7391d-102">How to: Create a WCF Service that Communicates over WebSockets</span></span>
<span data-ttu-id="7391d-103">WCF 서비스 및 클라이언트는 <xref:System.ServiceModel.NetHttpBinding> 바인딩을 사용하여 WebSocket에서 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7391d-103">WCF services and clients can use the <xref:System.ServiceModel.NetHttpBinding> binding to communicate over WebSockets.</span></span>  <span data-ttu-id="7391d-104">WebSocket은 <xref:System.ServiceModel.NetHttpBinding>에서 서비스 계약이 콜백 계약을 정의한다고 판단할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7391d-104">WebSockets will be used when the <xref:System.ServiceModel.NetHttpBinding> determines the service contract defines a callback contract.</span></span> <span data-ttu-id="7391d-105">이 항목은 WebSocket에서 통신하기 위해 <xref:System.ServiceModel.NetHttpBinding>을 사용하는 WCF 서비스와 클라이언트를 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7391d-105">This topic describes how to implement a WCF service and client that uses the <xref:System.ServiceModel.NetHttpBinding> to communicate over WebSockets.</span></span>  
  
### <a name="define-the-service"></a><span data-ttu-id="7391d-106">서비스 정의</span><span class="sxs-lookup"><span data-stu-id="7391d-106">Define the Service</span></span>  
  
1.  <span data-ttu-id="7391d-107">콜백 계약 정의</span><span class="sxs-lookup"><span data-stu-id="7391d-107">Define a callback contract</span></span>  
  
    ```csharp  
    [ServiceContract]  
        public interface IStockQuoteCallback  
        {  
            [OperationContract(IsOneWay = true)]  
            Task SendQuote(string code, double value);  
        }  
    ```  
  
     <span data-ttu-id="7391d-108">이 계약은 클라이언트 응용 프로그램에서 서비스가 메시지를 다시 클라이언트로 보낼 수 있도록 허용하기 위해 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="7391d-108">This contract will be implemented by the client application to allow the service to send messages back to the client.</span></span>  
  
2.  <span data-ttu-id="7391d-109">서비스 계약을 정의하고 `IStockQuoteCallback` 인터페이스를 콜백 계약으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7391d-109">Define the service contract and specify the `IStockQuoteCallback` interface as the callback contract.</span></span>  
  
    ```csharp  
    [ServiceContract(CallbackContract = typeof(IStockQuoteCallback))]  
        public interface IStockQuoteService  
        {  
            [OperationContract(IsOneWay = true)]  
            Task StartSendingQuotes();  
        }  
    ```  
  
3.  <span data-ttu-id="7391d-110">서비스 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="7391d-110">Implement the service contract.</span></span>  
  
    ```  
    public class StockQuoteService : IStockQuoteService  
        {  
            public async Task StartSendingQuotes()  
            {  
                var callback = OperationContext.Current.GetCallbackChannel<IStockQuoteCallback>();  
                var random = new Random();  
                double price = 29.00;  
  
                while (((IChannel)callback).State == CommunicationState.Opened)  
                {  
                    await callback.SendQuote("MSFT", price);  
                    price += random.NextDouble();  
                    await Task.Delay(1000);  
                }  
            }  
        }  
    ```  
  
     <span data-ttu-id="7391d-111">서비스 작업 `StartSendingQuotes`는 비동기 호출로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="7391d-111">The service operation `StartSendingQuotes` is implemented as an asynchronous call.</span></span> <span data-ttu-id="7391d-112">`OperationContext`를 사용하여 콜백 채널을 검색하고 채널이 열려 있을 경우 콜백 채널에 대해 비동기 호출을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7391d-112">We retrieve the callback channel using the `OperationContext` and if the channel is open, we make an async call on the callback channel.</span></span>  
  
4.  <span data-ttu-id="7391d-113">서비스 구성</span><span class="sxs-lookup"><span data-stu-id="7391d-113">Configure the service</span></span>  
  
    ```xml  
    <configuration>  
        <appSettings>  
          <add key="aspnet:UseTaskFriendlySynchronizationContext" value="true" />        
        </appSettings>  
        <system.web>  
          <compilation debug="true" targetFramework="4.5" />        
        </system.web>  
        <system.serviceModel>  
            <protocolMapping>  
              <add scheme="http" binding="netHttpBinding"/>  
              <add scheme="https" binding="netHttpsBinding"/>  
            </protocolMapping>  
            <behaviors>  
                <serviceBehaviors>  
                    <behavior name="">  
                        <serviceMetadata httpGetEnabled="true" httpsGetEnabled="true" />  
                        <serviceDebug includeExceptionDetailInFaults="false" />  
                    </behavior>  
                </serviceBehaviors>  
            </behaviors>  
            <serviceHostingEnvironment aspNetCompatibilityEnabled="true"  
                multipleSiteBindingsEnabled="true" />  
        </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="7391d-114">서비스 구성 파일은 WCF의 기본 끝점에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="7391d-114">The service’s configuration file relies on WCF’s default endpoints.</span></span> <span data-ttu-id="7391d-115">`<protocolMapping>` 섹션은 생성된 기본 끝점에 `NetHttpBinding`을 사용해야 함을 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7391d-115">The `<protocolMapping>` section is used to specify that the `NetHttpBinding` should be used for the default endpoints created.</span></span>  
  
### <a name="define-the-client"></a><span data-ttu-id="7391d-116">클라이언트 정의</span><span class="sxs-lookup"><span data-stu-id="7391d-116">Define the Client</span></span>  
  
1.  <span data-ttu-id="7391d-117">콜백 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="7391d-117">Implement the callback contract.</span></span>  
  
    ```csharp  
    private class CallbackHandler : StockQuoteServiceReference.IStockQuoteServiceCallback  
            {  
                public async Task SendQuoteAsync(string code, double value)  
                {  
                    Console.WriteLine("{0}: {1:f2}", code, value);  
                }  
            }  
    ```  
  
     <span data-ttu-id="7391d-118">콜백 계약 작업은 비동기 메서드로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="7391d-118">The callback contract operation is implemented as an asynchronous method.</span></span>  
  
    1.  <span data-ttu-id="7391d-119">클라이언트 코드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="7391d-119">Implement the client code.</span></span>  
  
        ```csharp  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                var context = new InstanceContext(new CallbackHandler());  
                var client = new StockQuoteServiceReference.StockQuoteServiceClient(context);  
                client.StartSendingQuotes();              
                Console.ReadLine();  
            }  
  
            private class CallbackHandler : StockQuoteServiceReference.IStockQuoteServiceCallback  
            {  
                public async Task SendQuoteAsync(string code, double value)  
                {  
                    Console.WriteLine("{0}: {1:f2}", code, value);  
                }  
            }  
        }  
        ```  
  
         <span data-ttu-id="7391d-120">여기서 쉽게 구분할 수 있도록 CallbackHandler가 반복되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7391d-120">The CallbackHandler is repeated here for clarity.</span></span> <span data-ttu-id="7391d-121">클라이언트 응용 프로그램은 새 InstanceContext를 만들고 콜백 인스턴스의 구현을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7391d-121">The client application creates a new InstanceContext and specifies the implementation of the callback interface.</span></span> <span data-ttu-id="7391d-122">그런 다음 새로 만들어진 InstanceContext에 참조를 보내는 프록시 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7391d-122">Next it creates an instance of the proxy class sending a reference to the newly created InstanceContext.</span></span> <span data-ttu-id="7391d-123">클라이언트가 서비스를 호출하면 서비스는 지정된 콜백 계약을 사용하여 클라이언트를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7391d-123">When the client calls the service, the service will call the client using the callback contract specified.</span></span>  
  
    2.  <span data-ttu-id="7391d-124">클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="7391d-124">Configure the client</span></span>  
  
        ```xml  
        <?xml version="1.0" encoding="utf-8" ?>  
        <configuration>  
            <startup>   
                <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />  
            </startup>  
            <system.serviceModel>  
                <bindings>  
                    <netHttpBinding>  
                        <binding name="NetHttpBinding_IStockQuoteService">  
                            <webSocketSettings transportUsage="Always" />  
                        </binding>  
                    </netHttpBinding>  
                </bindings>  
                <client>  
                    <endpoint address="ws://localhost/NetHttpSampleServer/StockQuoteService.svc"  
                        binding="netHttpBinding" bindingConfiguration="NetHttpBinding_IStockQuoteService"  
                        contract="StockQuoteServiceReference.IStockQuoteService" name="NetHttpBinding_IStockQuoteService" />  
                </client>  
            </system.serviceModel>  
        </configuration>  
        ```  
  
         <span data-ttu-id="7391d-125">클라이언트 구성에서 특별한 작업이 필요하지 않습니다. `NetHttpBinding`을 사용하여 클라이언트 측 끝점을 지정하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7391d-125">There is nothing special you need to do in the client configuration, just specify the client side endpoint using the `NetHttpBinding`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7391d-126">예</span><span class="sxs-lookup"><span data-stu-id="7391d-126">Example</span></span>  
 <span data-ttu-id="7391d-127">다음은 이 항목에서 사용되는 전체 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="7391d-127">The following is the complete code used in this topic.</span></span>  
  
```csharp  
// IStockQuoteService.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.Text;  
using System.Threading.Tasks;  
  
namespace Server  
{  
    [ServiceContract(CallbackContract = typeof(IStockQuoteCallback))]  
    public interface IStockQuoteService  
    {  
        [OperationContract(IsOneWay = true)]  
        Task StartSendingQuotes();  
    }  
  
    [ServiceContract]  
    public interface IStockQuoteCallback  
    {  
        [OperationContract(IsOneWay = true)]  
        Task SendQuote(string code, double value);  
    }  
}  
```  
  
```  
// StockQuoteService.svc.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
using System.Text;  
using System.Threading.Tasks;  
  
namespace Server  
{  
    public class StockQuoteService : IStockQuoteService  
    {  
        public async Task StartSendingQuotes()  
        {  
            var callback = OperationContext.Current.GetCallbackChannel<IStockQuoteCallback>();  
            var random = new Random();  
            double price = 29.00;  
  
            while (((IChannel)callback).State == CommunicationState.Opened)  
            {  
                await callback.SendQuote("MSFT", price);  
                price += random.NextDouble();  
                await Task.Delay(1000);  
            }  
        }  
    }  
}  
```  
  
```xml  
<?xml version="1.0"?>  
  
<!--  
  For more information on how to configure your ASP.NET application, please visit  
  http://go.microsoft.com/fwlink/?LinkId=169433  
  -->  
  
<configuration>  
    <appSettings>  
      <add key="aspnet:UseTaskFriendlySynchronizationContext" value="true" />        
    </appSettings>  
    <system.web>  
      <compilation debug="true" targetFramework="4.5" />        
    </system.web>  
    <system.serviceModel>  
        <protocolMapping>  
          <add scheme="http" binding="netHttpBinding"/>  
          <add scheme="https" binding="netHttpsBinding"/>  
        </protocolMapping>  
        <behaviors>  
            <serviceBehaviors>  
                <behavior name="">  
                    <serviceMetadata httpGetEnabled="true" httpsGetEnabled="true" />  
                    <serviceDebug includeExceptionDetailInFaults="false" />  
                </behavior>  
            </serviceBehaviors>  
        </behaviors>  
        <serviceHostingEnvironment aspNetCompatibilityEnabled="true"  
            multipleSiteBindingsEnabled="true" />  
    </system.serviceModel>  
</configuration>  
```  
  
```  
<!-- StockQuoteService.svc -->  
<%@ ServiceHost Language="C#" Debug="true" Service="Server.StockQuoteService" CodeBehind="StockQuoteService.svc.cs" %>  
```  
  
```csharp  
// Client.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.ServiceModel;  
using System.Text;  
using System.Threading.Tasks;  
  
namespace Client  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            var context = new InstanceContext(new CallbackHandler());  
            var client = new StockQuoteServiceReference.StockQuoteServiceClient(context);  
            client.StartSendingQuotes();              
            Console.ReadLine();  
        }  
  
        private class CallbackHandler : StockQuoteServiceReference.IStockQuoteServiceCallback  
        {  
            public async Task SendQuoteAsync(string code, double value)  
            {  
                Console.WriteLine("{0}: {1:f2}", code, value);  
            }  
        }  
    }  
}  
```  
  
```xml  
<!—App.config -->  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
    <startup>   
        <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />  
    </startup>  
    <system.serviceModel>  
        <bindings>  
            <netHttpBinding>  
                <binding name="NetHttpBinding_IStockQuoteService">  
                    <webSocketSettings transportUsage="Always" />  
                </binding>  
            </netHttpBinding>  
        </bindings>  
        <client>  
            <endpoint address="ws://localhost/NetHttpSampleServer/StockQuoteService.svc"  
                binding="netHttpBinding" bindingConfiguration="NetHttpBinding_IStockQuoteService"  
                contract="StockQuoteServiceReference.IStockQuoteService" name="NetHttpBinding_IStockQuoteService" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7391d-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7391d-128">See Also</span></span>  
 [<span data-ttu-id="7391d-129">동기 및 비동기 작업</span><span class="sxs-lookup"><span data-stu-id="7391d-129">Synchronous and Asynchronous Operations</span></span>](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md)  
 [<span data-ttu-id="7391d-130">NetHttpBinding 사용</span><span class="sxs-lookup"><span data-stu-id="7391d-130">Using the NetHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/using-the-nethttpbinding.md)
