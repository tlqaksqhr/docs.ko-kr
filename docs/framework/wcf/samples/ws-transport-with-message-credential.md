---
title: WS Transport With Message Credential
ms.date: 03/30/2017
ms.assetid: 0d092f3a-b309-439b-920b-66d8f46a0e3c
ms.openlocfilehash: 708869f2350f01e75b949f4817fcf8aac35ea018
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="ws-transport-with-message-credential"></a><span data-ttu-id="3a48b-102">WS Transport With Message Credential</span><span class="sxs-lookup"><span data-stu-id="3a48b-102">WS Transport With Message Credential</span></span>
<span data-ttu-id="3a48b-103">이 샘플에서는 메시지로 전달되는 클라이언트 자격 증명과 SSL 전송 보안을 조합하여 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-103">This sample demonstrates the use of SSL transport security in combination with client credential being carried in the message.</span></span> <span data-ttu-id="3a48b-104">이 샘플에서는 `wsHttpBinding` 바인딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-104">This sample uses the `wsHttpBinding` binding.</span></span>  
  
 <span data-ttu-id="3a48b-105">기본적으로 `wsHttpBinding` 바인딩은 HTTP 통신을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-105">By default, the `wsHttpBinding` binding provides HTTP communication.</span></span> <span data-ttu-id="3a48b-106">전송 보안용으로 구성된 경우, 바인딩은 HTTPS 통신을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-106">When configured for transport security, the binding supports HTTPS communication.</span></span> <span data-ttu-id="3a48b-107">HTTPS는 통신을 통해 전송되는 메시지의 기밀성 및 무결성을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-107">HTTPS provides confidentiality and integrity protection for the messages that are transmitted over the wire.</span></span> <span data-ttu-id="3a48b-108">하지만 서비스에 대한 클라이언트의 인증에 사용되는 인증 메커니즘은 HTTPS 전송에서 지원되는 범위로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-108">However the set of authentication mechanisms that can be used to authenticate the client to the service is limited to what the HTTPS transport supports.</span></span> <span data-ttu-id="3a48b-109">Windows Communication Foundation (WCF) 제공 된 `TransportWithMessageCredential` 이 제한을 극복 하도록 디자인 된 보안 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-109">Windows Communication Foundation (WCF) offers a `TransportWithMessageCredential` security mode that is designed to overcome this limitation.</span></span> <span data-ttu-id="3a48b-110">이 보안 모드가 구성되어 있으면 전송 보안을 사용하여 전송되는 메시지에 기밀성과 무결성을 제공하고 서비스 인증을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-110">When this security mode is configured, the transport security is used to provide confidentiality and integrity for the transmitted messages and to perform the service authentication.</span></span> <span data-ttu-id="3a48b-111">그러나 클라이언트 인증이 메시지에서 직접 클라이언트 자격 증명을 배치 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-111">However, the client authentication is performed by putting the client credential directly in the message.</span></span> <span data-ttu-id="3a48b-112">이 옵션을 사용 하면 동시에 전송 보안 모드의 성능 이점은 클라이언트 인증을 위해 메시지 보안 모드에서 지원 되는 모든 자격 증명 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-112">This allows you to use any credential type that is supported by the message security mode for the client authentication while keeping the performance benefit of transport security mode.</span></span>  
  
 <span data-ttu-id="3a48b-113">이 샘플에서는 `UserName` 자격 증명 형식을 사용하여 클라이언트를 서비스에 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-113">In this sample, a `UserName` credential type is used to authenticate the client to the service.</span></span>  
  
 <span data-ttu-id="3a48b-114">이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md) 계산기 서비스를 구현 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-114">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="3a48b-115">`wsHttpBinding` 바인딩은 클라이언트 및 서비스의 응용 프로그램 구성 파일에서 지정 및 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-115">The `wsHttpBinding` binding is specified and configured in the application configuration files for the client and service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a48b-116">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-116">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="3a48b-117">이 샘플에 있는 프로그램 코드는 거의 동일 합니다는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md) 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-117">The program code in the sample is almost identical to that of the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) service.</span></span> <span data-ttu-id="3a48b-118">서비스 계약에서 제공되는 추가 작업으로 `GetCallerIdentity`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-118">There is one additional operation provided by the service contract - `GetCallerIdentity`.</span></span> <span data-ttu-id="3a48b-119">이 작업에서는 호출자의 ID 이름을 호출자에게 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-119">This operation returns the name of the caller's identity to the caller.</span></span>  

```csharp
public string GetCallerIdentity()  
{  
    // Use ServiceSecurityContext.WindowsIdentity to get the name of the caller.  
    return ServiceSecurityContext.Current.WindowsIdentity.Name;  
}  
```

 <span data-ttu-id="3a48b-120">샘플을 빌드하고 실행하기 전에 Web Server Certificate Wizard를 사용하여 인증서를 만들고 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-120">You must create a certificate and assign it by using the Web Server Certificate Wizard before building and running the sample.</span></span> <span data-ttu-id="3a48b-121">구성 파일 설정의 끝점 정의와 바인딩 정의를 사용하면 클라이언트의 다음 샘플 구성에 표시된 것과 같이 `TransportWithMessageCredential` 보안 모드를 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-121">The endpoint definition and binding definition in the configuration file settings enable `TransportWithMessageCredential` security mode, as shown in the following sample configuration for the client.</span></span>  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint name=""  
              address="https://localhost/servicemodelsamples/service.svc"   
              binding="wsHttpBinding"   
              bindingConfiguration="Binding1"   
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--   
        This configuration defines the security mode as TransportWithMessageCredential.  
        and the clientCredentialType as UserName.  
        -->  
      <binding name="Binding1">  
        <security mode ="TransportWithMessageCredential">  
          <message clientCredentialType="UserName" />  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="3a48b-122">지정된 주소에서는 https:// 체계를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-122">The address specified uses the https:// scheme.</span></span> <span data-ttu-id="3a48b-123">바인딩 구성에서는 보안 모드를 `TransportWithMessageCredential`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-123">The binding configuration sets the security mode to `TransportWithMessageCredential`.</span></span> <span data-ttu-id="3a48b-124">서비스의 Web.config 파일에도 같은 보안 모드를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-124">The same security mode must be specified in the service's Web.config file.</span></span>  
  
 <span data-ttu-id="3a48b-125">Https에 액세스 하려고 할 때 보안 경고가 나타납니다이 샘플에 사용 된 인증서는 Makecert.exe를 사용 하 여 만든 테스트 인증서 이므로: 주소, https://localhost/servicemodelsamples/service.svc, 브라우저에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-125">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert appears when you try to access an https: address, such as https://localhost/servicemodelsamples/service.svc, from your browser.</span></span> <span data-ttu-id="3a48b-126">에서 테스트 인증서를 사용 하도록 WCF 클라이언트를 허용 하려면 일부 추가 코드가 보안 경고가 표시 되지 않도록 클라이언트에 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-126">To allow the WCF client to work with a test certificate in place, some additional code has been added to the client to suppress the security alert.</span></span> <span data-ttu-id="3a48b-127">이 코드 및 함께 사용되는 클래스는 프로덕션 인증서를 사용할 때에는 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-127">This code, and the accompanying class, is not required when using production certificates.</span></span>  

```csharp
// WARNING: This code is only needed for test certificates such as those created by makecert. It is   
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```
  
 <span data-ttu-id="3a48b-128">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-128">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="3a48b-129">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-129">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Username authentication required.  
Provide a valid machine or domain account. [domain\\user]  
   Enter username:   
YourDomainName\YourAccountName  
   Enter password:   
********  
YourDomainName\YourAccountName  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3a48b-130">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="3a48b-130">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="3a48b-131">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="3a48b-132">수행 했는지 확인 하십시오.는 [인터넷 정보 서비스 (IIS) 서버 인증서 설치 지침](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-132">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>  
  
3.  <span data-ttu-id="3a48b-133">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="3a48b-134">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3a48b-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a48b-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a48b-135">See Also</span></span>
