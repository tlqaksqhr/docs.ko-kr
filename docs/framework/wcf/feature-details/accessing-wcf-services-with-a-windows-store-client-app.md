---
title: "Windows 스토어 클라이언트 응용 프로그램을 사용하여 WCF 서비스에 액세스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2002ef4-5dee-4a54-9d87-03b33d35fc52
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1a1d30258063063cd4b91e328fc39e961ecb4425
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="accessing-wcf-services-with-a-windows-store-client-app"></a><span data-ttu-id="6a79e-102">Windows 스토어 클라이언트 응용 프로그램을 사용하여 WCF 서비스에 액세스</span><span class="sxs-lookup"><span data-stu-id="6a79e-102">Accessing WCF Services with a Windows Store Client App</span></span>
<span data-ttu-id="6a79e-103">Windows 8에서는 Windows 스토어 응용 프로그램이라는 새로운 형식의 응용 프로그램을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-103">Windows 8 introduces a new type of application called Windows Store applications.</span></span> <span data-ttu-id="6a79e-104">이러한 응용 프로그램은 터치 스크린 인터페이스를 바탕으로 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-104">These applications are designed around a touch screen interface.</span></span> <span data-ttu-id="6a79e-105">.NET Framework 4.5에서는 Windows 스토어 응용 프로그램을 사용하여 WCF 서비스를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-105">.NET Framework 4.5 enables Windows Store applications to call WCF services.</span></span>  
  
## <a name="wcf-support-in-windows-store-applications"></a><span data-ttu-id="6a79e-106">Windows 스토어 응용 프로그램의 WCF 지원</span><span class="sxs-lookup"><span data-stu-id="6a79e-106">WCF Support in Windows Store Applications</span></span>  
 <span data-ttu-id="6a79e-107">Windows 스토어 응용 프로그램 내에서 일부 WCF 기능을 사용할 수 있습니다. 자세한 내용은 다음 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6a79e-107">A subset of WCF functionality is available from within a Windows Store application, see the following sections for more details.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6a79e-108">WCF에서 노출하는 API 대신 WinRT 배포 API를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="6a79e-108">Use the WinRT syndication APIs instead of those exposed by WCF.</span></span> <span data-ttu-id="6a79e-109">자세한 내용은 [WinRT 배포 API](http://go.microsoft.com/fwlink/?LinkId=236265)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6a79e-109">For more information see, [WinRT Syndication API](http://go.microsoft.com/fwlink/?LinkId=236265)</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="6a79e-110">서비스 참조 추가 기능을 사용하여 Windows 런타임 구성 요소에 웹 서비스 참조를 추가할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-110">Using Add Service Reference to add a web service reference to a Windows Runtime Component isn’t supported.</span></span>  
  
### <a name="supported-bindings"></a><span data-ttu-id="6a79e-111">지원되는 바인딩</span><span class="sxs-lookup"><span data-stu-id="6a79e-111">Supported Bindings</span></span>  
 <span data-ttu-id="6a79e-112">Windows 스토어 응용 프로그램에서는 다음과 같은 WCF 바인딩이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-112">The following WCF bindings are supported in Windows Store Applications:</span></span>  
  
1.  <xref:System.ServiceModel.BasicHttpBinding>  
  
2.  <xref:System.ServiceModel.NetTcpBinding>  
  
3.  <xref:System.ServiceModel.NetHttpBinding>  
  
4.  <xref:System.ServiceModel.Channels.CustomBinding>
  
 <span data-ttu-id="6a79e-113">Windows 스토어 응용 프로그램에서는 다음과 같은 바인딩 요소가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-113">The following binding elements are supported in Windows Store Applications</span></span>  
  
1.  <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>  
  
2.  <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
  
3.  <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>  
  
4.  <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
  
5.  <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
  
6.  <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
7.  <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
8.  <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
9. <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
 <span data-ttu-id="6a79e-114">텍스트 인코딩과 이진 인코딩 모두가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-114">Both Text and Binary encodings are supported.</span></span> <span data-ttu-id="6a79e-115">모든 WCF 전송 모드가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-115">All WCF transfer modes are supported.</span></span> <span data-ttu-id="6a79e-116">자세한 내용은 [Streaming Message Transfer](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6a79e-116">For more information see, [Streaming Message Transfer](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md).</span></span>  
  
### <a name="add-service-reference"></a><span data-ttu-id="6a79e-117">서비스 참조 추가</span><span class="sxs-lookup"><span data-stu-id="6a79e-117">Add Service Reference</span></span>  
 <span data-ttu-id="6a79e-118">Windows 스토어 응용 프로그램에서 WCF 서비스를 호출하려면 Visual Studio 2012의 서비스 참조 추가 기능을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="6a79e-118">To call a WCF service from a Windows Store application, use the Add Service Reference feature of Visual Studio 2012.</span></span> <span data-ttu-id="6a79e-119">Windows 스토어 응용 프로그램 내에서 서비스 참조 추가 기능이 완료될 때 몇 가지 변경 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-119">You will notice a few changes in the functionality of Add Service Reference when done within a Windows Store application.</span></span> <span data-ttu-id="6a79e-120">먼저, 구성 파일이 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-120">First no configuration file is generated.</span></span> <span data-ttu-id="6a79e-121">Windows 스토어 응용 프로그램은 구성 파일을 사용하지 않으므로 코드로 구성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-121">Windows Store applications do not use configuration files, so they must be configured in code.</span></span> <span data-ttu-id="6a79e-122">이 구성 코드는 서비스 참조 추가를 통해 생성된 References.cs 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-122">This configuration code can be found in the References.cs file generated by Add Service Reference.</span></span> <span data-ttu-id="6a79e-123">이 파일을 보려면 솔루션 탐색기에서 "모든 파일 표시"를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-123">To see this file, make sure to select "Show All Files" in the solution explorer.</span></span> <span data-ttu-id="6a79e-124">해당 파일은 프로젝트 내의 서비스 참조 노드 및 Reference.svcmap 노드 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-124">The file will be located under the Service References and then Reference.svcmap nodes within the project.</span></span> <span data-ttu-id="6a79e-125">Windows 스토어 응용 프로그램 내의 WCF 서비스에 대해 생성된 모든 작업은 태스크 기반 비동기 패턴을 사용하여 비동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-125">All operations generated for WCF services within a Windows Store application will be asynchronous using the Task-based asynchronous pattern.</span></span> <span data-ttu-id="6a79e-126">자세한 내용은 [작업 기반 비동기 패턴](http://msdn.microsoft.com/magazine/ff959203.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6a79e-126">For more information, see [Task-based Asynchronous Pattern](http://msdn.microsoft.com/magazine/ff959203.aspx).</span></span>  
  
 <span data-ttu-id="6a79e-127">이제 구성이 코드로 생성되므로 서비스 참조가 업데이트될 때마다 Reference.cs 파일의 모든 변경 내용을 덮어쓰게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-127">Because configuration is now generated in code, any changes made in the Reference.cs file would be overwritten every time the service reference is updated.</span></span> <span data-ttu-id="6a79e-128">이러한 문제를 해결하기 위해 구성 코드는 부분 메서드(Partial Method) 내에서 생성됩니다. 부분 메서드는 클라이언트 프록시 클래스에서 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-128">To remedy this situation the configuration code is generated within a partial method, which you can implement in your client proxy class.</span></span> <span data-ttu-id="6a79e-129">부분 메서드는 다음과 같이 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-129">The partial method is declared as follows:</span></span>  
  
```csharp  
static partial void Configure(System.ServiceModel.Description.ServiceEndpoint serviceEndpoint,  
            System.ServiceModel.Description.ClientCredentials clientCredentials);  
```  
  
 <span data-ttu-id="6a79e-130">이 부분 메서드를 구현하고 다음과 같이 클라이언트 프록시 클래스에서 바인딩 또는 끝점을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-130">You can then implement this partial method and change the binding or endpoint in your client proxy class as follows:</span></span>  
  
```csharp  
public partial class Service1Client : System.ServiceModel.ClientBase<MetroWcfClient.ServiceRefMultiEndpt.IService1>, MetroWcfClient.ServiceRefMultiEndpt.IService1  
    {   
        static partial void Configure(System.ServiceModel.Description.ServiceEndpoint serviceEndpoint,   
            System.ServiceModel.Description.ClientCredentials clientCredentials)  
        {  
            if (serviceEndpoint.Name ==   
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.BasicHttpBinding_IService1.ToString())  
            {  
                serviceEndpoint.Binding.SendTimeout = new System.TimeSpan(0, 1, 0);  
            }  
            else if (serviceEndpoint.Name ==   
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.BasicHttpBinding_IService11.ToString())  
            {  
                serviceEndpoint.Binding.SendTimeout = new System.TimeSpan(0, 1, 0);  
                clientCredentials.UserName.UserName = "username1";  
                clientCredentials.UserName.Password = "password";  
            }  
            else if (serviceEndpoint.Name ==   
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.NetTcpBinding_IService1.ToString())  
            {  
                serviceEndpoint.Binding.Name = "MyTcpBinding";  
                serviceEndpoint.Address = new System.ServiceModel.EndpointAddress("net.tcp://localhost/tcp");  
            }  
        }  
    }  
```  
  
### <a name="serialization"></a><span data-ttu-id="6a79e-131">Serialization</span><span class="sxs-lookup"><span data-stu-id="6a79e-131">Serialization</span></span>  
 <span data-ttu-id="6a79e-132">Windows 스토어 응용 프로그램에서는 다음과 같은 serializer가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-132">The following serializers are supported in Windows Store applications:</span></span>  
  
1.  <span data-ttu-id="6a79e-133">DataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="6a79e-133">DataContractSerializer</span></span>  
  
2.  <span data-ttu-id="6a79e-134">DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="6a79e-134">DataContractJsonSerializer</span></span>  
  
3.  <span data-ttu-id="6a79e-135">XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="6a79e-135">XmlSerializer</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="6a79e-136">이제 XmlDictionaryWriter.Write(DateTime)는 DateTime 개체를 문자열로 씁니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-136">XmlDictionaryWriter.Write(DateTime) now writes the DateTime object as a string.</span></span>  
  
### <a name="security"></a><span data-ttu-id="6a79e-137">보안</span><span class="sxs-lookup"><span data-stu-id="6a79e-137">Security</span></span>  
 <span data-ttu-id="6a79e-138">Windows 스토어 응용 프로그램에서는 다음과 같은 보안 모드가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-138">The following security modes are supported in Windows Store applications</span></span>  
  
1.  <xref:System.ServiceModel.SecurityMode.None>  
  
2.  <xref:System.ServiceModel.SecurityMode.Transport>  
  
3.  <!--zz <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredentials> --> `System.ServiceModel.SecurityMode.TransportWithMessageCredentials`
  
4.  <!--zz <xref:System.ServiceModel.SecurityMode.TransportCredentialOnly>  --> `System.ServiceModel.SecurityMode.TransportCredentialOnly`
  
 <span data-ttu-id="6a79e-139">Windows 스토어 응용 프로그램에서는 다음과 같은 클라이언트 자격 증명 형식이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-139">The following client credential types are supported in Windows Store applications</span></span>  
  
1.  <span data-ttu-id="6a79e-140">없음</span><span class="sxs-lookup"><span data-stu-id="6a79e-140">None</span></span>  
  
2.  <span data-ttu-id="6a79e-141">Basic</span><span class="sxs-lookup"><span data-stu-id="6a79e-141">Basic</span></span>  
  
3.  <span data-ttu-id="6a79e-142">Digest</span><span class="sxs-lookup"><span data-stu-id="6a79e-142">Digest</span></span>  
  
4.  <span data-ttu-id="6a79e-143">Negotiate</span><span class="sxs-lookup"><span data-stu-id="6a79e-143">Negotiate</span></span>  
  
5.  <span data-ttu-id="6a79e-144">NTLM</span><span class="sxs-lookup"><span data-stu-id="6a79e-144">NTLM</span></span>  
  
6.  <span data-ttu-id="6a79e-145">Windows</span><span class="sxs-lookup"><span data-stu-id="6a79e-145">Windows</span></span>  
  
7.  <span data-ttu-id="6a79e-146">Username(메시지 보안)</span><span class="sxs-lookup"><span data-stu-id="6a79e-146">Username (Message Security)</span></span>  
  
8.  <span data-ttu-id="6a79e-147">Windows(전송 보안)</span><span class="sxs-lookup"><span data-stu-id="6a79e-147">Windows (Transport Security)</span></span>  
  
 <span data-ttu-id="6a79e-148">Windows 스토어 응용 프로그램이 기본 Windows 자격 증명에 액세스하여 이를 보내도록 하려면 Package.appmanifest 파일 내에서 이 기능을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-148">In order for Windows Store applications to access and send default Windows credentials, you must enable this functionality within the Package.appmanifest file.</span></span> <span data-ttu-id="6a79e-149">이 파일을 열고 기능 탭을 선택 "기본 Windows 자격 증명"을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-149">Open this file and select the Capabilities tab and select "Default Windows Credentials".</span></span> <span data-ttu-id="6a79e-150">그러면 도메인 자격 증명이 필요한 인트라넷 리소스에 응용 프로그램을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-150">This allows the application to connect to intranet resources that require domain credentials.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6a79e-151">Windows 스토어 응용 프로그램이 컴퓨터 간 호출을 수행 하려면 "홈/회사 네트워킹" 라는 다른 기능 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-151">In order for Windows Store applications to make cross machine calls you must enable another capability called "Home/Work Networking".</span></span> <span data-ttu-id="6a79e-152">이 설정은 Package.appmanifest 파일의 기능 탭 아래에도 있습니다. 홈/회사 네트워킹 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-152">This setting is also in the Package.appmanifest file under the Capabilities tab. Select the Home/Work Networking checkbox.</span></span> <span data-ttu-id="6a79e-153">그러면 집이나 회사와 같이 사용자가 신뢰할 수 있는 장소의 네트워크에 대한 인바운드 및 아웃바운드 액세스 권한이 응용 프로그램에 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-153">This gives your application inbound and outbound access to the networks of the user’s trusted places like home and work.</span></span> <span data-ttu-id="6a79e-154">중요한 인바운드 포트는 항상 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-154">Inbound critical ports are always blocked.</span></span> <span data-ttu-id="6a79e-155">인터넷의 서비스에 액세스하려면 인터넷(클라이언트) 기능도 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-155">For accessing services on the internet you must also enable Internet (Client) capability.</span></span>  
  
### <a name="misc"></a><span data-ttu-id="6a79e-156">기타</span><span class="sxs-lookup"><span data-stu-id="6a79e-156">Misc</span></span>  
 <span data-ttu-id="6a79e-157">Windows 스토어 응용 프로그램에 는 다음 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-157">The use of the following classes is supported for Windows Store Applications:</span></span>  
  
1.  <xref:System.ServiceModel.ChannelFactory>  
  
2.  <!--zz <xref:System.ServiceModel.DuplexChannelFactory> --> `System.ServiceModel.DuplexChannelFactory`
  
3.  <xref:System.ServiceModel.CallbackBehaviorAttribute>  
  
### <a name="defining-service-contracts"></a><span data-ttu-id="6a79e-158">서비스 계약 정의</span><span class="sxs-lookup"><span data-stu-id="6a79e-158">Defining Service Contracts</span></span>  
 <span data-ttu-id="6a79e-159">태스크 기반 비동기 패턴을 사용하여 비동기 서비스 작업만 정의하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-159">We recommend only defining asynchronous service operations using the task-based async pattern.</span></span> <span data-ttu-id="6a79e-160">그러면 서비스 작업을 호출하는 동안 Windows 스토어 응용 프로그램이 응답을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-160">This ensures Windows Store applications remain responsive while calling a service operation.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="6a79e-161">동기 작업을 정의하더라도 예외가 throw되지는 않지만 비동기 작업만 정의하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-161">While no exception will be thrown if you define a synchronous operation, it is strongly recommended to only define asynchronous operations.</span></span>  
  
### <a name="calling-wcf-services-from-windows-store-applications"></a><span data-ttu-id="6a79e-162">Windows 스토어 응용 프로그램에서 WCF 서비스 호출</span><span class="sxs-lookup"><span data-stu-id="6a79e-162">Calling WCF Services from Windows Store Applications</span></span>  
 <span data-ttu-id="6a79e-163">앞에서 설명한 것처럼 모든 구성은 생성된 프록시 클래스의 GetBindingForEndpoint 메서드에서 코드로 수행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-163">As mentioned before all configuration must be done in code in the GetBindingForEndpoint method in the generated proxy class.</span></span> <span data-ttu-id="6a79e-164">서비스 작업 호출은 다음 코드 조각과 같이 태스크 기반 비동기 메서드를 호출할 때와 동일한 방법으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-164">Calling a service operation is done the same as calling any task-based asynchronous method as shown in the following code snippet.</span></span>  
  
```csharp  
void async SomeMethod()  
{  
    ServiceClient proxy = new ServiceClient();  
    Task<T> results = await proxy.CallAsync(param1, param2);  
    T result = results.Result;  
    if (result.Success)  
    {  
       // Do something with result  
    }  
}  
```  
  
 <span data-ttu-id="6a79e-165">비동기 호출을 수행하는 메서드에서는 async 키워드가 사용되고 비동기 메서드를 호출할 때는 await 키워드가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a79e-165">Notice the use of the async keyword on the method making the asynchronous call and the await keyword when calling the asynchronous method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a79e-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a79e-166">See Also</span></span>  
 [<span data-ttu-id="6a79e-167">Windows 스토어 앱 블로그의 WCF</span><span class="sxs-lookup"><span data-stu-id="6a79e-167">WCF in Windows Store Apps Blog</span></span>](http://blogs.msdn.com/b/piyushjo/archive/2011/09/22/wcf-in-win8-metro-styled-apps-absolutely-supported.aspx)  
 [<span data-ttu-id="6a79e-168">WCF Windows 스토어 클라이언트 및 보안</span><span class="sxs-lookup"><span data-stu-id="6a79e-168">WCF Windows Store Clients and Security</span></span>](http://blogs.msdn.com/b/piyushjo/archive/2011/10/11/calling-a-wcf-service-from-a-metro-application-adding-security.aspx)  
 [<span data-ttu-id="6a79e-169">Windows 스토어 앱 및 컴퓨터 간 호출</span><span class="sxs-lookup"><span data-stu-id="6a79e-169">Windows Store Apps and Cross Machine Calls</span></span>](http://blogs.msdn.com/b/piyushjo/archive/2011/10/22/calling-a-wcf-service-from-a-metro-application-cross-machine-scenario.aspx)  
 [<span data-ttu-id="6a79e-170">Windows 스토어 앱에서 Azure에 배포 된 WCF 서비스 호출</span><span class="sxs-lookup"><span data-stu-id="6a79e-170">Calling a WCF Service Deployed in Azure from a Windows Store App</span></span>](http://blogs.msdn.com/b/piyushjo/archive/2011/10/22/calling-a-wcf-service-from-a-metro-application-cross-machine-scenario.aspx)  
 [<span data-ttu-id="6a79e-171">WCF 보안 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="6a79e-171">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 [<span data-ttu-id="6a79e-172">바인딩</span><span class="sxs-lookup"><span data-stu-id="6a79e-172">Bindings</span></span>](../../../../docs/framework/wcf/bindings.md)
