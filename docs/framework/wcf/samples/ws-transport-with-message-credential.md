---
title: WS Transport With Message Credential
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d092f3a-b309-439b-920b-66d8f46a0e3c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f782ac12c92755eb26eddd30c5d8c15168c35858
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ws-transport-with-message-credential"></a><span data-ttu-id="39b67-102">WS Transport With Message Credential</span><span class="sxs-lookup"><span data-stu-id="39b67-102">WS Transport With Message Credential</span></span>
<span data-ttu-id="39b67-103">이 샘플에서는 메시지로 전달되는 클라이언트 자격 증명과 SSL 전송 보안을 조합하여 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-103">This sample demonstrates the use of SSL transport security in combination with client credential being carried in the message.</span></span> <span data-ttu-id="39b67-104">이 샘플에서는 `wsHttpBinding` 바인딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-104">This sample uses the `wsHttpBinding` binding.</span></span>  
  
 <span data-ttu-id="39b67-105">기본적으로 `wsHttpBinding` 바인딩은 HTTP 통신을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-105">By default, the `wsHttpBinding` binding provides HTTP communication.</span></span> <span data-ttu-id="39b67-106">전송 보안용으로 구성된 경우, 바인딩은 HTTPS 통신을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-106">When configured for transport security, the binding supports HTTPS communication.</span></span> <span data-ttu-id="39b67-107">HTTPS는 통신을 통해 전송되는 메시지의 기밀성 및 무결성을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-107">HTTPS provides confidentiality and integrity protection for the messages that are transmitted over the wire.</span></span> <span data-ttu-id="39b67-108">하지만 서비스에 대한 클라이언트의 인증에 사용되는 인증 메커니즘은 HTTPS 전송에서 지원되는 범위로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-108">However the set of authentication mechanisms that can be used to authenticate the client to the service is limited to what the HTTPS transport supports.</span></span> [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="39b67-109">는 이 제한을 극복하도록 디자인된 `TransportWithMessageCredential` 보안 모드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-109"> offers a `TransportWithMessageCredential` security mode that is designed to overcome this limitation.</span></span> <span data-ttu-id="39b67-110">이 보안 모드가 구성되어 있으면 전송 보안을 사용하여 전송되는 메시지에 기밀성과 무결성을 제공하고 서비스 인증을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-110">When this security mode is configured, the transport security is used to provide confidentiality and integrity for the transmitted messages and to perform the service authentication.</span></span> <span data-ttu-id="39b67-111">그러나 클라이언트 인증이 메시지에서 직접 클라이언트 자격 증명을 배치 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-111">However, the client authentication is performed by putting the client credential directly in the message.</span></span> <span data-ttu-id="39b67-112">이 옵션을 사용 하면 동시에 전송 보안 모드의 성능 이점은 클라이언트 인증을 위해 메시지 보안 모드에서 지원 되는 모든 자격 증명 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-112">This allows you to use any credential type that is supported by the message security mode for the client authentication while keeping the performance benefit of transport security mode.</span></span>  
  
 <span data-ttu-id="39b67-113">이 샘플에서는 `UserName` 자격 증명 형식을 사용하여 클라이언트를 서비스에 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-113">In this sample, a `UserName` credential type is used to authenticate the client to the service.</span></span>  
  
 <span data-ttu-id="39b67-114">이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md) 계산기 서비스를 구현 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-114">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="39b67-115">`wsHttpBinding` 바인딩은 클라이언트 및 서비스의 응용 프로그램 구성 파일에서 지정 및 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-115">The `wsHttpBinding` binding is specified and configured in the application configuration files for the client and service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="39b67-116">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-116">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="39b67-117">이 샘플에 있는 프로그램 코드는 거의 동일 합니다는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md) 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-117">The program code in the sample is almost identical to that of the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) service.</span></span> <span data-ttu-id="39b67-118">서비스 계약에서 제공되는 추가 작업으로 `GetCallerIdentity`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-118">There is one additional operation provided by the service contract - `GetCallerIdentity`.</span></span> <span data-ttu-id="39b67-119">이 작업에서는 호출자의 ID 이름을 호출자에게 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-119">This operation returns the name of the caller's identity to the caller.</span></span>  
  
```  
public string GetCallerIdentity()  
{  
    // Use ServiceSecurityContext.WindowsIdentity to get the name of the caller.  
    return ServiceSecurityContext.Current.WindowsIdentity.Name;  
}  
```  
  
 <span data-ttu-id="39b67-120">샘플을 빌드하고 실행하기 전에 Web Server Certificate Wizard를 사용하여 인증서를 만들고 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-120">You must create a certificate and assign it by using the Web Server Certificate Wizard before building and running the sample.</span></span> <span data-ttu-id="39b67-121">구성 파일 설정의 끝점 정의와 바인딩 정의를 사용하면 클라이언트의 다음 샘플 구성에 표시된 것과 같이 `TransportWithMessageCredential` 보안 모드를 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-121">The endpoint definition and binding definition in the configuration file settings enable `TransportWithMessageCredential` security mode, as shown in the following sample configuration for the client.</span></span>  
  
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
  
 <span data-ttu-id="39b67-122">지정된 주소에서는 https:// 체계를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-122">The address specified uses the https:// scheme.</span></span> <span data-ttu-id="39b67-123">바인딩 구성에서는 보안 모드를 `TransportWithMessageCredential`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-123">The binding configuration sets the security mode to `TransportWithMessageCredential`.</span></span> <span data-ttu-id="39b67-124">서비스의 Web.config 파일에도 같은 보안 모드를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-124">The same security mode must be specified in the service's Web.config file.</span></span>  
  
 <span data-ttu-id="39b67-125">이 샘플에 사용된 인증서는 Makecert.exe를 사용하여 만든 테스트 인증서이므로 브라우저에서 https://localhost/servicemodelsamples/service.svc와 같은 https: 주소에 액세스하려 하면 보안 경고가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-125">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert appears when you try to access an https: address, such as https://localhost/servicemodelsamples/service.svc, from your browser.</span></span> <span data-ttu-id="39b67-126">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트에서 제공되는 테스트 인증서를 사용하여 작업을 수행할 수 있도록 클라이언트에 추가 코드를 추가하여 보안 경고가 나타나지 않게 합니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-126">To allow the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client to work with a test certificate in place, some additional code has been added to the client to suppress the security alert.</span></span> <span data-ttu-id="39b67-127">이 코드 및 함께 사용되는 클래스는 프로덕션 인증서를 사용할 때에는 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-127">This code, and the accompanying class, is not required when using production certificates.</span></span>  
  
```  
// WARNING: This code is only needed for test certificates such as those created by makecert. It is   
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
 <span data-ttu-id="39b67-128">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-128">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="39b67-129">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-129">Press ENTER in the client window to shut down the client.</span></span>  
  
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
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="39b67-130">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="39b67-130">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="39b67-131">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="39b67-132">수행 했는지 확인 하십시오.는 [인터넷 정보 서비스 (IIS) 서버 인증서 설치 지침](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-132">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>  
  
3.  <span data-ttu-id="39b67-133">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="39b67-134">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="39b67-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39b67-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="39b67-135">See Also</span></span>
