---
title: Custom Binding Security
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6383dff-4308-46d2-bc6d-acd4e18b4b8d
caps.latest.revision: "30"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 94c43586606f42cca120ded59637a998d113d229
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="custom-binding-security"></a><span data-ttu-id="d7dbd-102">Custom Binding Security</span><span class="sxs-lookup"><span data-stu-id="d7dbd-102">Custom Binding Security</span></span>
<span data-ttu-id="d7dbd-103">이 샘플에서는 사용자 지정 바인딩을 사용하여 보안을 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-103">This sample demonstrates how to configure security by using a custom binding.</span></span> <span data-ttu-id="d7dbd-104">여기서는 사용자 지정 바인딩을 사용하여 메시지를 안전하게 전송하고 메시지 수준 보안을 가능하게 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-104">It shows how to use a custom binding to enable message-level security together with a secure transport.</span></span> <span data-ttu-id="d7dbd-105">이러한 방법은 클라이언트와 서비스 간에 메시지를 전송하는 데 보안 전송이 요구되면서 동시에 메시지가 메시지 수준에서 보호되어야 하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-105">This is useful when a secure transport is required to transmit the messages between client and service and simultaneously the messages must be secure on the message level.</span></span> <span data-ttu-id="d7dbd-106">이 구성은 시스템 제공 바인딩에서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-106">This configuration is not supported by system-provided bindings.</span></span>  
  
 <span data-ttu-id="d7dbd-107">이 샘플은 클라이언트 콘솔 프로그램(EXE) 및 서비스 콘솔 프로그램(EXE)으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-107">This sample consists of a client console program (EXE) and a service console program (EXE).</span></span> <span data-ttu-id="d7dbd-108">서비스는 이중 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-108">The service implements a duplex contract.</span></span> <span data-ttu-id="d7dbd-109">계약은 수학 연산(Add, Subtract, Multiply 및 Divide)을 노출시키는 `ICalculatorDuplex` 인터페이스에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-109">The contract is defined by the `ICalculatorDuplex` interface, which exposes math operations (Add, Subtract, Multiply, and Divide).</span></span> <span data-ttu-id="d7dbd-110">`ICalculatorDuplex` 인터페이스를 사용하여 클라이언트는 수학 연산을 수행하고 세션 도중 실행 결과를 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-110">The `ICalculatorDuplex` interface allows the client to perform math operations, calculating a running result over a session.</span></span> <span data-ttu-id="d7dbd-111">서비스는 독립적으로 `ICalculatorDuplexCallback` 인터페이스에서 결과를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-111">Independently, the service may return results on the `ICalculatorDuplexCallback` interface.</span></span> <span data-ttu-id="d7dbd-112">클라이언트와 서비스 간에 전송되는 메시지 집합을 서로 연결하기 위해 컨텍스트를 설정해야 하므로 이중 계약에는 세션이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-112">A duplex contract requires a session, because a context must be established to correlate the set of messages being sent between the client and the service.</span></span> <span data-ttu-id="d7dbd-113">이중 통신을 지원하는 보안된 사용자 지정 바인딩이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-113">A custom binding is defined that supports duplex communication and is secure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7dbd-114">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-114">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="d7dbd-115">서비스 구성에서는 다음을 지원하는 사용자 지정 바인딩을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-115">The service configuration defines a custom binding that supports the following:</span></span>  
  
-   <span data-ttu-id="d7dbd-116">TLS/SSL 프로토콜을 사용하여 보호되는 TCP 통신</span><span class="sxs-lookup"><span data-stu-id="d7dbd-116">TCP communication protected by using the TLS/SSL protocol.</span></span>  
  
-   <span data-ttu-id="d7dbd-117">Windows 메시지 보안</span><span class="sxs-lookup"><span data-stu-id="d7dbd-117">Windows message security.</span></span>  
  
 <span data-ttu-id="d7dbd-118">사용자 지정 바인딩 구성은 메시지 수준 보안을 동시에 사용하도록 하여 보안 전송을 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-118">The custom binding configuration enables secure transport by simultaneously enabling the message-level security.</span></span> <span data-ttu-id="d7dbd-119">바인딩 요소의 순서는 각 채널 스택의 계층을 나타내기 때문에 사용자 지정 바인딩을 정의에서 중요 (참조 [사용자 지정 바인딩을](../../../../docs/framework/wcf/extending/custom-bindings.md)).</span><span class="sxs-lookup"><span data-stu-id="d7dbd-119">The ordering of binding elements is important in defining a custom binding, because each represents a layer in the channel stack (see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md)).</span></span> <span data-ttu-id="d7dbd-120">다음 샘플 구성과 같이 사용자 지정 바인딩은 서비스 및 클라이언트 구성 파일에 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-120">The custom binding is defined in the service and client configuration files, as shown in the following sample configuration.</span></span>  
  
```xml  
<bindings>  
  <!-- Configure a custom binding. -->  
  <customBinding>  
    <binding name="Binding1">  
      <security authenticationMode="SecureConversation"  
                 requireSecurityContextCancellation="true">  
      </security>  
      <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8"/>  
      <sslStreamSecurity requireClientCertificate="false"/>  
      <tcpTransport/>  
    </binding>  
  </customBinding>  
</bindings>  
```  
  
 <span data-ttu-id="d7dbd-121">사용자 지정 바인딩은 서비스 인증서를 사용하여 전송 수준에서 서비스를 인증하고 클라이언트와 서비스 간 전송 시 메시지를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-121">The custom binding uses a service certificate to authenticate the service on the transport level and to protect the messages during the transmission between client and service.</span></span> <span data-ttu-id="d7dbd-122">이러한 작업은 `sslStreamSecurity` 바인딩 요소에 의해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-122">This is accomplished by the `sslStreamSecurity` binding element.</span></span> <span data-ttu-id="d7dbd-123">다음 샘플 구성과 같이 서비스의 인증서는 서비스 동작을 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-123">The service's certificate is configured using a service behavior as shown in the following sample configuration.</span></span>  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata />  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName"/>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 <span data-ttu-id="d7dbd-124">또한 사용자 지정 바인딩은 기본 자격 증명 형식인 Windows 자격 증명 형식의 메시지 보안을 사용합니다. </span><span class="sxs-lookup"><span data-stu-id="d7dbd-124">Additionally, the custom binding uses message security with Windows credential type - this is the default credential type.</span></span> <span data-ttu-id="d7dbd-125">이러한 작업은 `security` 바인딩 요소에 의해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-125">This is accomplished by the `security` binding element.</span></span> <span data-ttu-id="d7dbd-126">Kerberos 인증 메커니즘이 사용 가능한 경우 클라이언트 및 서비스는 모두 메시지 수준 보안을 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-126">Both client and service are authenticated using message-level security if the Kerberos authentication mechanism is available.</span></span> <span data-ttu-id="d7dbd-127">Active Directory 환경에서 샘플이 실행될 경우 이 방법이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-127">This happens if the sample is run in the Active Directory environment.</span></span> <span data-ttu-id="d7dbd-128">Kerberos 인증 메커니즘을 사용할 수 없는 경우에는 NTLM 인증이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-128">If the Kerberos authentication mechanism is not available, NTLM authentication is used.</span></span> <span data-ttu-id="d7dbd-129">NTLM은 서비스에 대해 클라이언트를 인증하지만 클라이언트에 대해 서비스를 인증하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-129">NTLM authenticates the client to the service but does not authenticate the service to the client.</span></span> <span data-ttu-id="d7dbd-130">`security` 바인딩 요소는 사용 하도록 구성 된 `SecureConversation``authenticationType`, 결과 클라이언트와 서비스 모두에 보안 세션이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-130">The `security` binding element is configured to use `SecureConversation``authenticationType`, which results in the creation of a security session on both the client and the service.</span></span> <span data-ttu-id="d7dbd-131">이러한 구성은 서비스의 이중 계약을 사용할 때 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-131">This is required to enable the service's duplex contract to work.</span></span>  
  
 <span data-ttu-id="d7dbd-132">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-132">When you run the sample, the operation requests and responses are displayed in the client's console window.</span></span> <span data-ttu-id="d7dbd-133">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-133">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Press <ENTER> to terminate client.  
Result(100)  
Result(50)  
Result(882.5)  
Result(441.25)  
Equation(0 + 100 - 50 * 17.65 / 2 = 441.25)  
```  
  
 <span data-ttu-id="d7dbd-134">샘플을 실행하면 서비스에서 전송된 콜백 인터페이스에서 클라이언트에 반환된 메시지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-134">When you run the sample, you see the messages returned to the client on the callback interface sent from the service.</span></span> <span data-ttu-id="d7dbd-135">각 중간 결과가 표시된 다음 모든 작업이 완료되면 전체 수식이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-135">Each intermediate result is displayed, followed by the entire equation upon completion of all operations.</span></span> <span data-ttu-id="d7dbd-136">클라이언트를 종료하려면 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-136">Press ENTER to shut down the client.</span></span>  
  
 <span data-ttu-id="d7dbd-137">포함된 Setup.bat 파일을 사용하면 인증서 기반 보안이 필요한 호스팅된 응용 프로그램을 실행하도록 관련 서비스 인증서가 있는 클라이언트와 서버를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-137">The included Setup.bat file enables you to configure the client and server with the relevant service certificate to run a hosted application that requires certificate-based security.</span></span> <span data-ttu-id="d7dbd-138">다중 컴퓨터 구성이나 호스트되지 않는 환경에서 이 배치 파일을 사용하려면 배치 파일을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-138">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>  
  
 <span data-ttu-id="d7dbd-139">다음 부분에는 이 샘플에 적용되는 배치 파일을 적절한 구성에서 실행하도록 수정하는 데 도움이 되는 여러 관련 단원의 간략한 개요가 소개되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-139">The following provides a brief overview of the different sections of the batch files that apply to this sample so that they can be modified to run in the appropriate configuration:</span></span>  
  
-   <span data-ttu-id="d7dbd-140">서버 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="d7dbd-140">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="d7dbd-141">Setup.bat 파일에서 다음 줄은 사용할 서버 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-141">The following lines from the Setup.bat file create the server certificate to be used.</span></span> <span data-ttu-id="d7dbd-142">`%SERVER_NAME%`변수는 서버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-142">The `%SERVER_NAME%` variable specifies the server name.</span></span> <span data-ttu-id="d7dbd-143">이 변수를 변경하여 고유의 서버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-143">Change this variable to specify your own server name.</span></span> <span data-ttu-id="d7dbd-144">이 배치 파일에서 서버 이름의 기본값은 localhost입니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-144">This batch file defaults the server name to localhost.</span></span>  
  
     <span data-ttu-id="d7dbd-145">인증서는 웹 호스팅 서비스에 대한 CurrentUser 저장소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-145">The certificate is stored in the CurrentUser store for the Web-hosted services.</span></span>  
  
    ```  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
-   <span data-ttu-id="d7dbd-146">클라이언트의 신뢰할 수 있는 인증서 저장소에 서버 인증서 설치</span><span class="sxs-lookup"><span data-stu-id="d7dbd-146">Installing the server certificate into the client's trusted certificate store.</span></span>  
  
     <span data-ttu-id="d7dbd-147">Setup.bat 파일에서 다음 줄은 클라이언트의 신뢰할 수 있는 사용자 저장소로 서버 인증서를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-147">The following lines in the Setup.bat file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="d7dbd-148">이 단계는 Makecert.exe에서 생성한 인증서를 클라이언트 컴퓨터에서 절대적으로 신뢰하지는 않기 때문에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-148">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="d7dbd-149">Microsoft에서 발급한 인증서와 같이 클라이언트가 신뢰할 수 있는 루트 인증서를 기반으로 하는 인증서가 이미 있는 경우 클라이언트 인증서 저장소를 서버 인증서로 채우는 이 단계를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-149">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="d7dbd-150">Setup.bat 배치 파일은 Visual Studio 2010 명령 프롬프트에서 실행되도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-150">The Setup.bat batch file is designed to be run from a Visual Studio 2010 Command Prompt.</span></span> <span data-ttu-id="d7dbd-151">MSSDK 환경 변수는 SDK가 설치되는 디렉터리를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-151">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="d7dbd-152">이 환경 변수는 Visual Studio 2010 명령 프롬프트 내에서 자동으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-152">This environment variable is automatically set within a Visual Studio 2010 Command Prompt.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d7dbd-153">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="d7dbd-153">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="d7dbd-154">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-154">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="d7dbd-155">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-155">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="d7dbd-156">지침에 따라 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-156">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="d7dbd-157">단일 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="d7dbd-157">To run the sample on the same computer</span></span>  
  
1.  <span data-ttu-id="d7dbd-158">관리자 권한으로 Visual Studio 명령 프롬프트 창을 열고 샘플 설치 폴더의 Setup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-158">Open a Visual Studio Command Prompt window with administrator privileges and run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="d7dbd-159">이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-159">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d7dbd-160">Setup.bat 배치 파일은 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트에서 실행되도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-160">The Setup.bat batch file is designed to be run from a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Command Prompt.</span></span> <span data-ttu-id="d7dbd-161">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트에서 설정된 PATH 환경 변수는 Setup.bat 스크립트에 필요한 실행 파일이 포함된 디렉터리를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-161">The PATH environment variable set within the [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>  
  
2.  <span data-ttu-id="d7dbd-162">\service\bin에서 Service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-162">Launch Service.exe from \service\bin.</span></span>  
  
3.  <span data-ttu-id="d7dbd-163">\client\bin에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-163">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="d7dbd-164">클라이언트 콘솔 응용 프로그램에 클라이언트 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-164">Client activity is displayed on the client console application.</span></span>  
  
4.  <span data-ttu-id="d7dbd-165">클라이언트와 서비스가 통신할 수 없는 경우 참조 [문제 해결 팁](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-165">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="d7dbd-166">다중 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="d7dbd-166">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="d7dbd-167">서비스 컴퓨터에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-167">On the service computer:</span></span>  
  
    1.  <span data-ttu-id="d7dbd-168">서비스 컴퓨터에서 servicemodelsamples라는 가상 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-168">Create a virtual directory named servicemodelsamples on the service computer.</span></span>  
  
    2.  <span data-ttu-id="d7dbd-169">\inetpub\wwwroot\servicemodelsamples에서 서비스 컴퓨터의 가상 디렉터리로 서비스 프로그램 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-169">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="d7dbd-170">\bin 하위 디렉터리에 파일을 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-170">Ensure that you copy the files in the \bin subdirectory.</span></span>  
  
    3.  <span data-ttu-id="d7dbd-171">Setup.bat 및 Cleanup.bat 파일을 서비스 컴퓨터로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-171">Copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
    4.  <span data-ttu-id="d7dbd-172">관리자 권한으로 연 Visual Studio 명령 프롬프트에 다음 명령을 실행: `Setup.bat service`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-172">Run the following command in a Visual Studio command prompt opened with administrator privileges: `Setup.bat service`.</span></span> <span data-ttu-id="d7dbd-173">이렇게 하면 배치 파일이 실행된 컴퓨터의 이름과 일치하는 주체 이름을 가진 서비스 인증서가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-173">This creates the service certificate with the subject name matching the name of the computer the batch file was run on.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="d7dbd-174">Setup.bat 배치 파일은 Visual Studio 2010 명령 프롬프트에서 실행되도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-174">The Setup.bat batch file is designed to be run from a Visual Studio 2010 Command Prompt.</span></span> <span data-ttu-id="d7dbd-175">PATH 환경 변수는 SDK가 설치되는 디렉터리를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-175">It requires that the path environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="d7dbd-176">이 환경 변수는 Visual Studio 2010 명령 프롬프트 내에서 자동으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-176">This environment variable is automatically set within a Visual Studio 2010 Command Prompt.</span></span>  
  
    5.  <span data-ttu-id="d7dbd-177">변경 된 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) 이전 단계에서 생성 된 인증서의 주체 이름을 반영 하도록 Service.exe.config 파일 내부.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-177">Change the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) inside the Service.exe.config file to reflect the subject name of the certificate generated in the previous step.</span></span>  
  
    6.  <span data-ttu-id="d7dbd-178">명령 프롬프트에서 Service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-178">Run Service.exe from a command prompt.</span></span>  
  
2.  <span data-ttu-id="d7dbd-179">클라이언트 컴퓨터에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-179">On the client computer:</span></span>  
  
    1.  <span data-ttu-id="d7dbd-180">\client\bin\ 폴더에서 클라이언트 컴퓨터로 클라이언트 프로그램 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-180">Copy the client program files from the \client\bin\ folder to the client computer.</span></span> <span data-ttu-id="d7dbd-181">Cleanup.bat 파일도 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-181">Also copy the Cleanup.bat file.</span></span>  
  
    2.  <span data-ttu-id="d7dbd-182">Cleanup.bat를 실행하여 이전 샘플에서 이전의 모든 인증서를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-182">Run Cleanup.bat to remove any old certificates from previous samples.</span></span>  
  
    3.  <span data-ttu-id="d7dbd-183">관리자 권한으로 Visual Studio 명령 프롬프트를 열고 서비스 컴퓨터에서 다음 명령을 실행하여 서비스의 인증서를 내보냅니다. `%SERVER_NAME%`은 서비스가 실행되고 있는 컴퓨터의 정규화된 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-183">Export the service's certificate by opening a Visual Studio command prompt with administrative privileges, and running the following command on the service computer (substitute `%SERVER_NAME%` with the fully-qualified name of the computer where the service is running):</span></span>  
  
        ```  
        certmgr -put -r LocalMachine -s My -c -n %SERVER_NAME% %SERVER_NAME%.cer  
        ```  
  
    4.  <span data-ttu-id="d7dbd-184">%SERVER_NAME%.cer을 클라이언트 컴퓨터에 복사합니다. %SERVER_NAME%은 서비스가 실행되고 있는 컴퓨터의 정규화된 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-184">Copy %SERVER_NAME%.cer to the client computer (substitute %SERVER_NAME% with the fully-qualified name of the computer where the service is running).</span></span>  
  
    5.  <span data-ttu-id="d7dbd-185">관리자 권한으로 Visual Studio 명령 프롬프트를 열고 클라이언트 컴퓨터에서 다음 명령을 실행하여 서비스의 인증서를 가져옵니다. %SERVER_NAME%은 서비스가 실행되고 있는 컴퓨터의 정규화된 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-185">Import the service's certificate by opening a Visual Studio command prompt with administrative privileges, and running the following command on the client computer (substitute %SERVER_NAME% with the fully-qualified name of the computer where the service is running):</span></span>  
  
        ```  
        certmgr.exe -add -c %SERVER_NAME%.cer -s -r CurrentUser TrustedPeople  
        ```  
  
         <span data-ttu-id="d7dbd-186">신뢰할 수 있는 발급자에 의해 인증서가 발급된 경우 c, d 및 e 단계는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-186">Steps c, d, and e are not necessary if the certificate is issued by a Trusted Issuer.</span></span>  
  
    6.  <span data-ttu-id="d7dbd-187">클라이언트의 App.config 파일을 다음과 같이 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-187">Modify the client’s App.config file as follows:</span></span>  
  
        ```xml  
        <client>  
            <endpoint name="default"  
                address="net.tcp://ReplaceThisWithServiceMachineName:8000/ServiceModelSamples/Service"   
                binding="customBinding"   
                bindingConfiguration="Binding1"   
                contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex"  
        behaviorConfiguration="CalculatorClientBehavior" />  
        </client>  
        ```  
  
    7.  <span data-ttu-id="d7dbd-188">도메인 환경에서 NetworkService 또는 LocalSystem 계정이 아닌 계정으로 서비스가 실행 중이면 서비스를 실행하는 데 사용되는 해당 계정에 기초하여 적절한 UPN 또는 SPN을 설정하기 위해 클라이언트의 App.config 파일에서 서비스 끝점에 대한 끝점 ID를 수정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-188">If the service is running under an account other than the NetworkService or LocalSystem account in a domain environment, you might need to modify the endpoint identity for the service endpoint inside the client's App.config file to set the appropriate UPN or SPN based on the account that is used to run the service.</span></span> <span data-ttu-id="d7dbd-189">끝점 id에 대 한 자세한 내용은 참조는 [서비스 Id 및 인증](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-189">For more information about endpoint identity, see the [Service Identity and Authentication](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md) topic.</span></span>  
  
    8.  <span data-ttu-id="d7dbd-190">명령 프롬프트에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-190">Run Client.exe from a command prompt.</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="d7dbd-191">샘플 실행 후 정리를 수행하려면</span><span class="sxs-lookup"><span data-stu-id="d7dbd-191">To clean up after the sample</span></span>  
  
-   <span data-ttu-id="d7dbd-192">샘플 실행을 완료한 후 샘플 폴더에서 Cleanup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d7dbd-192">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7dbd-193">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7dbd-193">See Also</span></span>
