---
title: Message Security 샘플
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82444166-6288-493a-85d4-85f43f134d19
caps.latest.revision: 33
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 0ead08c454ed8b9e484d23d426e918c9f11fe3ed
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="message-security-sample"></a><span data-ttu-id="52d1b-102">Message Security 샘플</span><span class="sxs-lookup"><span data-stu-id="52d1b-102">Message Security Sample</span></span>
<span data-ttu-id="52d1b-103">이 샘플에서는 `basicHttpBinding` 및 메시지 보안을 사용하는 응용 프로그램을 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-103">This sample demonstrates how to implement an application that uses the `basicHttpBinding` and message security.</span></span> <span data-ttu-id="52d1b-104">이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md) 계산기 서비스를 구현 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52d1b-105">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="52d1b-106">`basicHttpBinding`의 보안 모드는 `Message`, `Transport`, `TransportWithMessageCredential`, `TransportCredentialOnly` 및 `None` 등의 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-106">The security mode of `basicHttpBinding` can be set to the following values: `Message`, `Transport`, `TransportWithMessageCredential`, `TransportCredentialOnly` and `None`.</span></span> <span data-ttu-id="52d1b-107">다음 샘플 서비스 App.config 파일에서 끝점 정의는 `basicHttpBinding`을 지정하며, 다음 샘플 구성에서 보여 주는 것처럼 `Binding1`이라는 바인딩 구성을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-107">In the following sample service App.config file, the endpoint definition specifies the `basicHttpBinding` and references a binding configuration named `Binding1`, as shown in the following sample configuration:</span></span>  
  
```xml  
<system.serviceModel>  
  <services>  
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
     <!-- This endpoint is exposed at the base address provided by -->  
     <!-- host: http://localhost:8000/ServiceModelSamples/service.-->  
     <endpoint address=""  
               binding="basicHttpBinding"  
               bindingConfiguration="Binding1"   
               contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>   …  
</system.serviceModel>  
```  
  
 <span data-ttu-id="52d1b-108">바인딩 구성 집합은 `mode` 특성의는 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) 를 `Message` 설정는 `clientCredentialType` 특성의는 [ \<메시지 >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-basichttpbinding.md)를 `Certificate` 다음 샘플 구성 에서처럼:</span><span class="sxs-lookup"><span data-stu-id="52d1b-108">The binding configuration sets the `mode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) to `Message` and sets the `clientCredentialType` attribute of the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-basichttpbinding.md) to `Certificate` as shown in the following sample configuration:</span></span>  
  
```xml  
<bindings>  
  <basicHttpBinding>  
    <!--   
        This configuration defines the SecurityMode as Message and   
        the clientCredentialType as Certificate.  
        -->  
    <binding name="Binding1" >  
      <security mode = "Message">  
        <message clientCredentialType="Certificate"/>  
      </security>  
    </binding>  
  </basicHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="52d1b-109">서비스가 클라이언트에게 자신을 인증하는 데 사용하는 인증서는 구성 파일의 behaviors 섹션에 있는 `serviceCredentials` 요소 아래에 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-109">The certificate that the service uses to authenticate itself to the client is set in the behaviors section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="52d1b-110">클라이언트가 서비스에 자신을 인증하는 데 사용하는 인증서에 적용되는 유효성 검사 모드 또한 behaviors 섹션에서 `clientCertificate` 요소 아래에 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-110">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the behaviors section under the `clientCertificate` element.</span></span>  
  
```xml  
<!--For debugging purposes, set the includeExceptionDetailInFaults attribute to true.-->  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
      <!--The serviceCredentials behavior allows one to define a -->  
      <!--service certificate. A service certificate is used by a -->  
      <!--client to authenticate the service and provide message -->  
      <!-- protection. This configuration references the "localhost"-->  
      <!--certificate installed during the setup instructions. -->  
      <serviceCredentials>  
        <serviceCertificate findValue="localhost"  
               storeLocation="LocalMachine"   
               storeName="My" x509FindType="FindBySubjectName" />  
        <clientCertificate>  
          <!-- Setting the certificateValidationMode to -->  
          <!-- PeerOrChainTrust means that if the certificate -->  
          <!--is in the user's Trusted People store, then it is -->  
          <!-- trusted without performing a validation of the -->  
          <!-- certificate's issuer chain. This setting is used -->  
          <!-- here for convenience so that the sample can be run -->  
          <!-- without having to have certificates issued by a -->  
          <!-- certification authority (CA). -->  
          <!-- This setting is less secure than the default, -->  
          <!-- ChainTrust. The security implications of this -->  
          <!-- setting should be carefully considered before using -->  
          <!-- PeerOrChainTrust in production code. -->  
          <authentication   
                       certificateValidationMode="PeerOrChainTrust" />  
        </clientCertificate>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="52d1b-111">동일한 바인딩 및 보안 세부 정보가 클라이언트 구성 파일에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-111">The same binding and security details are specified in the client configuration file.</span></span>  
  
 <span data-ttu-id="52d1b-112">호출자의 ID는 다음 코드를 사용하여 서비스 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-112">The identity of the caller is displayed in the service console window by using the following code:</span></span>  

```csharp
Console.WriteLine("Called by {0}", ServiceSecurityContext.Current.PrimaryIdentity.Name);  
```

 <span data-ttu-id="52d1b-113">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-113">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="52d1b-114">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-114">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="52d1b-115">샘플을 설치하고 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="52d1b-115">To set up and build the sample</span></span>  
  
1.  <span data-ttu-id="52d1b-116">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-116">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="52d1b-117">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-117">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="52d1b-118">단일 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="52d1b-118">To run the sample on the same machine</span></span>  
  
1.  <span data-ttu-id="52d1b-119">샘플 설치 폴더에서 Setup.bat를 실행하여</span><span class="sxs-lookup"><span data-stu-id="52d1b-119">Run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="52d1b-120">이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-120">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="52d1b-121">Setup.bat 배치 파일은 Windows SDK 명령 프롬프트에서 실행되도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-121">The Setup.bat batch file is designed to be run from a Windows SDK Command Prompt.</span></span> <span data-ttu-id="52d1b-122">MSSDK 환경 변수는 SDK가 설치되는 디렉터리를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-122">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="52d1b-123">이 환경 변수는 Windows SDK 명령 프롬프트 내에서 자동으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-123">This environment variable is automatically set within a Windows SDK Command Prompt.</span></span>  
  
2.  <span data-ttu-id="52d1b-124">\service\bin에서 서비스 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-124">Run the service application from \service\bin.</span></span>  
  
3.  <span data-ttu-id="52d1b-125">\client\bin에서 클라이언트 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-125">Run the client application from \client\bin.</span></span> <span data-ttu-id="52d1b-126">클라이언트 콘솔 응용 프로그램에 클라이언트 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-126">Client activity is displayed on the client console application.</span></span>  
  
4.  <span data-ttu-id="52d1b-127">클라이언트와 서비스가 통신할 수 없는 경우 참조 [문제 해결 팁](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)합니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-127">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
5.  <span data-ttu-id="52d1b-128">샘플 사용을 마치면 Cleanup.bat를 실행하여 인증서를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-128">Remove the certificates by running Cleanup.bat when you have finished with the sample.</span></span> <span data-ttu-id="52d1b-129">다른 보안 샘플에도 동일한 인증서가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-129">Other security samples use the same certificates.</span></span>  
  
### <a name="to-run-the-sample-across-machines"></a><span data-ttu-id="52d1b-130">다중 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="52d1b-130">To run the sample across machines</span></span>  
  
1.  <span data-ttu-id="52d1b-131">서비스 컴퓨터에 서비스 이진 파일용 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-131">Create a directory on the service machine for the service binaries.</span></span>  
  
2.  <span data-ttu-id="52d1b-132">서비스 프로그램 파일을 서버의 서비스 디렉터리에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-132">Copy the service program files to the service directory on the server.</span></span> <span data-ttu-id="52d1b-133">Setup.bat, Cleanup.bat 및 ImportClientCert.bat 파일도 서버에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-133">Also copy the Setup.bat, Cleanup.bat, and ImportClientCert.bat files to the server.</span></span>  
  
3.  <span data-ttu-id="52d1b-134">클라이언트 컴퓨터에 클라이언트 이진 파일용 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-134">Create a directory on the client machine for the client binaries.</span></span>  
  
4.  <span data-ttu-id="52d1b-135">클라이언트 프로그램 파일을 클라이언트 컴퓨터의 클라이언트 디렉터리로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-135">Copy the client program files to the client directory on the client machine.</span></span> <span data-ttu-id="52d1b-136">Setup.bat, Cleanup.bat 및 ImportServiceCert.bat 파일도 클라이언트로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-136">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5.  <span data-ttu-id="52d1b-137">서버에서 `setup.bat service`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-137">On the server, run `setup.bat service`.</span></span> <span data-ttu-id="52d1b-138">실행 `setup.bat` 와 `service` 인수가 컴퓨터의 정규화 된 도메인 이름을 사용 하 여 서비스 인증서를 만들고 되어 Service.cer 이라는 파일로 서비스 인증서를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-138">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the machine and exports the service certificate to a file named Service.cer.</span></span>  
  
6.  <span data-ttu-id="52d1b-139">새 인증서 이름을 반영 하도록 Service.exe.config 편집 (에 `findValue` 특성에 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) 요소) 컴퓨터의 정규화 된 도메인 이름과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-139">Edit Service.exe.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) element) which is the same as the fully-qualified domain name of the machine.</span></span> <span data-ttu-id="52d1b-140">또한 기본 주소 값을 변경하여 localhost 대신 정규화된 컴퓨터 이름을 지정합니다.`.`</span><span class="sxs-lookup"><span data-stu-id="52d1b-140">Also change the value of the base address to specify a fully-qualified machine name instead of localhost`.`</span></span>  
  
7.  <span data-ttu-id="52d1b-141">서비스 디렉터리에서 클라이언트 컴퓨터의 클라이언트 디렉터리로 Service.cer 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-141">Copy the Service.cer file from the service directory to the client directory on the client machine.</span></span>  
  
8.  <span data-ttu-id="52d1b-142">클라이언트에서 `setup.bat client`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-142">On the client, run `setup.bat client`.</span></span> <span data-ttu-id="52d1b-143">`setup.bat` 인수를 사용하여 `client`를 실행하면 client.com이라는 클라이언트 인증서가 생성되어 Client.cer이라는 파일로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-143">Running `setup.bat` with the `client` argument creates a client certificate named client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
9. <span data-ttu-id="52d1b-144">클라이언트 컴퓨터의 Client.exe.config 파일에서 끝점의 주소 값을 서비스의 새 주소와 일치하도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-144">In the Client.exe.config file on the client machine, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="52d1b-145">이 작업을 수행하려면 localhost를 서버의 정규화된 도메인 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-145">You do this by replacing localhost with the fully-qualified domain name of the server.</span></span> <span data-ttu-id="52d1b-146">변경할 수도 `findValue` 특성에는 [ \<defaultCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md) 이 서버의 정규화 된 도메인 이름을 새 서비스 인증서 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-146">Also change the `findValue` attribute of the [\<defaultCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md) to the new service certificate name which is the fully-qualified domain name of the server.</span></span>  
  
10. <span data-ttu-id="52d1b-147">클라이언트 디렉터리에서 서버의 서비스 디렉터리로 Client.cer 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-147">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
11. <span data-ttu-id="52d1b-148">클라이언트에서 ImportServiceCert.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-148">On the client, run ImportServiceCert.bat.</span></span> <span data-ttu-id="52d1b-149">이 작업은 Service.cer 파일의 서비스 인증서를 CurrentUser - TrustedPeople 저장소로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-149">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
12. <span data-ttu-id="52d1b-150">서버에서 ImportClientCert.bat를 실행하여 Client.cer 파일에서 LocalMachine - TrustedPeople 저장소로 클라이언트 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-150">On the server, run ImportClientCert.bat, This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
13. <span data-ttu-id="52d1b-151">서비스 컴퓨터의 명령 프롬프트에서 Service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-151">On the service machine, run Service.exe from a command prompt.</span></span>  
  
14. <span data-ttu-id="52d1b-152">클라이언트 컴퓨터의 명령 프롬프트 창에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-152">On the client machine, launch Client.exe from a command prompt window.</span></span>  
  
    1.  <span data-ttu-id="52d1b-153">클라이언트와 서비스가 통신할 수 없는 경우 참조 [문제 해결 팁](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)합니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-153">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="52d1b-154">샘플 실행 후 정리를 수행하려면</span><span class="sxs-lookup"><span data-stu-id="52d1b-154">To clean up after the sample</span></span>  
  
-   <span data-ttu-id="52d1b-155">샘플 실행을 완료했으면 샘플 폴더에서 Cleanup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-155">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="52d1b-156">다중 컴퓨터 구성에서 이 샘플을 실행할 경우에는 이 스크립트로 서비스 인증서를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-156">This script does not remove service certificates on a client when running this sample across machines.</span></span> <span data-ttu-id="52d1b-157">여러 시스템에서 인증서를 사용하는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 샘플을 실행한 경우에는 CurrentUser - TrustedPeople 저장소에 설치된 서비스 인증서를 지워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-157">If you have run [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] samples that use certificates across machines, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="52d1b-158">이를 수행하려면 `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` 명령을 사용합니다(예: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`).</span><span class="sxs-lookup"><span data-stu-id="52d1b-158">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="52d1b-159">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-159">The samples may already be installed on your machine.</span></span> <span data-ttu-id="52d1b-160">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="52d1b-160">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="52d1b-161">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="52d1b-161">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="52d1b-162">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52d1b-162">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Basic\MessageSecurity`  
  
## <a name="see-also"></a><span data-ttu-id="52d1b-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="52d1b-163">See Also</span></span>
