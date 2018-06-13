---
title: 메시지 보안 인증서
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: 909333b3-35ec-48f0-baff-9a50161896f6
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 769827d10139a659971890a452227b650e89ba20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33508451"
---
# <a name="message-security-certificate"></a><span data-ttu-id="c0075-102">메시지 보안 인증서</span><span class="sxs-lookup"><span data-stu-id="c0075-102">Message Security Certificate</span></span>
<span data-ttu-id="c0075-103">이 샘플에서는 클라이언트에 대해 X.509 v3 인증서를 통한 WS-Security 인증을 사용하며 서버의 X.509 v3 인증서를 사용한 서버 인증을 수행해야 하는 응용 프로그램의 구현 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-103">This sample demonstrates how to implement an application that uses WS-Security with X.509 v3 certificate authentication for the client and requires server authentication using the server's X.509 v3 certificate.</span></span> <span data-ttu-id="c0075-104">이 샘플에서는 클라이언트와 서버 간의 모든 응용 프로그램 메시지가 서명 및 암호화되도록 기본 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-104">This sample uses default settings such that all application messages between the client and server are signed and encrypted.</span></span> <span data-ttu-id="c0075-105">이 샘플에 따라는 [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md) 인터넷 정보 서비스 (IIS)에서 호스팅하는 서비스 라이브러리 및 클라이언트 콘솔 프로그램으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-105">This sample is based on the [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md) and consists of a client console program and a service library hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="c0075-106">이 서비스는 요청-회신 통신 패턴을 정의하는 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-106">The service implements a contract that defines a request-reply communication pattern.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0075-107">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="c0075-108">이 샘플에서는 다음 샘플 코드에 표시된 것과 같이 구성을 이용하여 인증을 제어하는 방법과 보안 컨텍스트에서 호출자의 ID를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-108">The sample demonstrates controlling authentication by using configuration and how to obtain the caller’s identity from the security context, as shown in the following sample code.</span></span>  

```csharp
public class CalculatorService : ICalculator  
{  
    public string GetCallerIdentity()  
    {  
        // The client certificate is not mapped to a Windows identity by default.  
        // ServiceSecurityContext.PrimaryIdentity is populated based on the information  
        // in the certificate that the client used to authenticate itself to the service.  
        return ServiceSecurityContext.Current.PrimaryIdentity.Name;  
    }  
    ...  
}  
```  
  
 <span data-ttu-id="c0075-109">서비스에서는 서비스와 통신하기 위한 하나의 끝점과 WS-MetadataExchange 프로토콜을 사용하여 서비스의 WSDL 문서를 노출하기 위한 하나의 끝점을 노출하며 이러한 끝점은 구성 파일(Web.config)을 사용하여 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-109">The service exposes one endpoint for communicating with the service and one endpoint for exposing the service's WSDL document using the WS-MetadataExchange protocol, defined by using the configuration file (Web.config).</span></span> <span data-ttu-id="c0075-110">끝점은 하나의 주소, 바인딩 및 계약으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-110">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="c0075-111">표준 바인딩이 구성 된 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 기본적으로 메시지 보안을 사용 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-111">The binding is configured with a standard [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element, which defaults to using message security.</span></span> <span data-ttu-id="c0075-112">이 샘플에서는 클라이언트 인증을 요구하도록 `clientCredentialType` 특성을 Certificate로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-112">This sample sets the `clientCredentialType` attribute to Certificate to require client authentication.</span></span>  
  
```xml  
<system.serviceModel>  
    <protocolMapping>  
      <add scheme="http" binding="wsHttpBinding"/>  
    </protocolMapping>  
    <bindings>  
      <wsHttpBinding>  
        <!--   
        This configuration defines the security mode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding>  
          <security mode ="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--   
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by the service to authenticate itself to its clients and to provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </clientCertificate>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
```  
  
 <span data-ttu-id="c0075-113">동작에서는 클라이언트가 서비스를 인증할 때 사용되는 서비스의 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-113">The behavior specifies the service's credentials that are used when the client authenticates the service.</span></span> <span data-ttu-id="c0075-114">서버 인증서 주체 이름에 지정 되는 `findValue` 특성에 [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-114">The server certificate subject name is specified in the `findValue` attribute in the [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) element.</span></span>  
  
```xml  
<!--For debugging purposes, set the includeExceptionDetailInFaults attribute to true.-->  
<behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--   
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by the service to authenticate itself to its clients and to provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </clientCertificate>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 <span data-ttu-id="c0075-115">클라이언트 끝점 구성은 서비스 끝점의 절대 주소, 바인딩 및 계약으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-115">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="c0075-116">클라이언트 바인딩은 적절한 보안 모드 및 인증 모드를 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-116">The client binding is configured with the appropriate security mode and authentication mode.</span></span> <span data-ttu-id="c0075-117">다중 컴퓨터 구성에서 실행할 경우 서비스 끝점 주소를 적절하게 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-117">When running in a cross-computer scenario, ensure that the service endpoint address is changed accordingly.</span></span>  
  
```xml  
<system.serviceModel>  
    <client>  
      <!-- Use a behavior to configure the client certificate to present to the service. -->  
      <endpoint address="http://localhost/servicemodelsamples/service.svc" binding="wsHttpBinding" bindingConfiguration="Binding1" behaviorConfiguration="ClientCertificateBehavior" contract="Microsoft.Samples.Certificate.ICalculator"/>  
    </client>  
  
    <bindings>  
      <wsHttpBinding>  
        <!--   
        This configuration defines the security mode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding name="Binding1">  
          <security mode="Message">  
            <message clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="c0075-118">클라이언트 구현에서는 구성 파일이나 코드를 통해 사용할 인증서를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-118">The client implementation can set the certificate to use, either through the configuration file or through code.</span></span> <span data-ttu-id="c0075-119">다음 샘플에서는 구성 파일에서 사용할 인증서를 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-119">The following sample shows how to set the certificate to use in the configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
  ...  
  
<behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientCertificateBehavior">  
          <!--   
        The clientCredentials behavior allows one to define a certificate to present to a service.  
        A certificate is used by a client to authenticate itself to the service and provide message integrity.  
        This configuration references the "client.com" certificate installed during the setup instructions.  
        -->  
          <clientCredentials>  
            <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName"/>  
            <serviceCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certificate authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust"/>  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  
</system.serviceModel>  
```  
  
 <span data-ttu-id="c0075-120">다음 샘플에서는 프로그램에서 서비스를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-120">The following sample shows how to call the service in your program.</span></span>  

```csharp
// Create a client.  
CalculatorClient client = new CalculatorClient();  
  
// Call the GetCallerIdentity service operation.  
Console.WriteLine(client.GetCallerIdentity());  
...  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
```
  
 <span data-ttu-id="c0075-121">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-121">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="c0075-122">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-122">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
CN=client.com  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="c0075-123">Message Security 샘플에 포함된 Setup.bat 배치 파일을 사용하면 인증서 기반 보안이 필요한 자체 호스팅 응용 프로그램을 실행하도록 관련 인증서가 있는 클라이언트와 서버를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-123">The Setup.bat batch file included with the Message Security samples enables you to configure the client and server with relevant certificates to run a hosted application that requires certificate-based security.</span></span> <span data-ttu-id="c0075-124">이 배치 파일을 세 가지 모드로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-124">The batch file can be run in three modes.</span></span> <span data-ttu-id="c0075-125">형식이 단일 컴퓨터 모드에서 실행 하려면 **setup.bat** Visual Studio 명령 프롬프트에서, 서비스 모드 유형에 대 한 **setup.bat service**; 및 클라이언트 모드 형식에 대 한 **setup.bat client** .</span><span class="sxs-lookup"><span data-stu-id="c0075-125">To run in single-computer mode type **setup.bat** in a Visual Studio Command Prompt ; for service mode type **setup.bat service**; and for client mode type **setup.bat client**.</span></span> <span data-ttu-id="c0075-126">다중 컴퓨터 구성에서 샘플을 실행할 경우 클라이언트 및 서버 모드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-126">Use the client and server mode when running the sample across computers.</span></span> <span data-ttu-id="c0075-127">자세한 내용은 이 항목의 끝에 있는 설치 절차를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0075-127">See the setup procedure at the end of this topic for details.</span></span> <span data-ttu-id="c0075-128">다음 부분에는 적절한 구성으로 실행되게 수정할 수 있도록 배치 파일의 다양한 섹션에 대한 간략한 개요가 소개되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-128">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in appropriate configuration:</span></span>  
  
-   <span data-ttu-id="c0075-129">클라이언트 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="c0075-129">Creating the client certificate.</span></span>  
  
     <span data-ttu-id="c0075-130">배치 파일의 다음 줄에서는 클라이언트 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-130">The following line in the batch file creates the client certificate.</span></span> <span data-ttu-id="c0075-131">지정된 클라이언트 이름은 만든 인증서의 제목 이름에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-131">The client name specified is used in the subject name of the certificate created.</span></span> <span data-ttu-id="c0075-132">인증서는 `My` 저장소 위치에 있는 `CurrentUser` 저장소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-132">The certificate is stored in `My` store at the `CurrentUser` store location.</span></span>  
  
    ```bat
    echo ************  
    echo making client cert  
    echo ************  
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe  
    ```  
  
-   <span data-ttu-id="c0075-133">서버의 신뢰할 수 있는 인증서 저장소에 클라이언트 인증서 설치</span><span class="sxs-lookup"><span data-stu-id="c0075-133">Installing the client certificate into the server’s trusted certificate store.</span></span>  
  
     <span data-ttu-id="c0075-134">배치 파일의 다음 줄에서는 서버에서 관련된 신뢰 여부를 결정할 수 있도록 서버의 TrustedPeople 저장소에 클라이언트 인증서를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-134">The following line in the batch file copies the client certificate into the server's TrustedPeople store so that the server can make the relevant trust or no-trust decisions.</span></span> <span data-ttu-id="c0075-135">TrustedPeople 저장소에 설치 된 인증서에 대 한 Windows Communication Foundation (WCF) 서비스에서 신뢰 하려면 순서에 클라이언트 인증서 유효성 검사 모드 설정 해야 `PeerOrChainTrust` 또는 `PeerTrust`합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-135">In order for a certificate installed in the TrustedPeople store to be trusted by a Windows Communication Foundation (WCF) service, the client certificate validation mode must be set to `PeerOrChainTrust` or `PeerTrust`.</span></span> <span data-ttu-id="c0075-136">구성 파일을 사용하여 이 작업을 수행하는 방법을 보려면 앞서 소개된 서비스 구성 샘플을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c0075-136">See the previous service configuration sample to learn how this can be done by using a configuration file.</span></span>  
  
    ```bat
    echo ************  
    echo copying client cert to server's LocalMachine store  
    echo ************  
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople   
    ```  
  
-   <span data-ttu-id="c0075-137">서버 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="c0075-137">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="c0075-138">Setup.bat 배치 파일에서 다음 행은 사용할 서버 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-138">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span>  
  
    ```bat
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     <span data-ttu-id="c0075-139">%SERVER_NAME% 변수는 서버 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-139">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="c0075-140">인증서는 LocalMachine 저장소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-140">The certificate is stored in the LocalMachine store.</span></span> <span data-ttu-id="c0075-141">서비스의 인수와 함께 Setup.bat 배치 파일을 실행할 경우 (예: **setup.bat service**) % SERVER_NAME %는 컴퓨터의 정규화 된 도메인 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-141">If the Setup.bat batch file is run with an argument of service (such as, **setup.bat service**) the %SERVER_NAME% contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="c0075-142">그렇지 않은 경우 기본적으로 localhost입니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-142">Otherwise it defaults to localhost.</span></span>  
  
-   <span data-ttu-id="c0075-143">클라이언트의 신뢰할 수 있는 인증서 저장소에 서버 인증서 설치</span><span class="sxs-lookup"><span data-stu-id="c0075-143">Installing the server certificate into the client’s trusted certificate store.</span></span>  
  
     <span data-ttu-id="c0075-144">다음 줄은 클라이언트의 신뢰할 수 있는 사용자 저장소에 서버 인증서를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-144">The following line copies the server certificate into the client trusted people store.</span></span> <span data-ttu-id="c0075-145">이 단계는 Makecert.exe에서 생성한 인증서를 클라이언트 컴퓨터에서 절대적으로 신뢰하지는 않기 때문에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-145">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="c0075-146">Microsoft에서 발급한 인증서와 같이 클라이언트가 신뢰할 수 있는 루트 인증서를 기반으로 하는 인증서가 이미 있는 경우 클라이언트 인증서 저장소를 서버 인증서로 채우는 이 단계를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-146">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
-   <span data-ttu-id="c0075-147">인증서의 개인 키에 대한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="c0075-147">Granting permissions on the certificate's private key.</span></span>  
  
     <span data-ttu-id="c0075-148">Setup.bat 파일의 다음 줄은 LocalMachine 저장소에 저장된 서버 인증서를 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 작업자 프로세스 계정에서 액세스할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-148">The following lines in the Setup.bat file make the server certificate stored in the LocalMachine store accessible to the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] worker process account.</span></span>  
  
    ```bat
    echo ************  
    echo setting privileges on server certificates  
    echo ************  
    for /F "delims=" %%i in ('"%ProgramFiles%\ServiceModelSampleTools\FindPrivateKey.exe" My LocalMachine -n CN^=%SERVER_NAME% -a') do set PRIVATE_KEY_FILE=%%i  
    set WP_ACCOUNT=NT AUTHORITY\NETWORK SERVICE  
    (ver | findstr /C:"5.1") && set WP_ACCOUNT=%COMPUTERNAME%\ASPNET  
    echo Y|cacls.exe "%PRIVATE_KEY_FILE%" /E /G "%WP_ACCOUNT%":R  
    iisreset  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="c0075-149">미국 영어 버전이 아닌 Windows 버전을 사용하는 경우 Setup.bat 파일을 편집하여 "NT AUTHORITY\NETWORK SERVICE" 계정 이름을 해당 국가별 계정 이름으로 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-149">If you are using a non-U.S. English edition of Windows, you must edit the Setup.bat file and replace the "NT AUTHORITY\NETWORK SERVICE" account name with your regional equivalent.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0075-150">이 배치 파일에서 사용되는 도구는 C:\Program Files\Microsoft Visual Studio 8\Common7\tools 또는 C:\Program Files\Microsoft SDKs\Windows\v6.0\bin에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-150">The tools used in this batch file are located in either C:\Program Files\Microsoft Visual Studio 8\Common7\tools or C:\Program Files\Microsoft SDKs\Windows\v6.0\bin.</span></span> <span data-ttu-id="c0075-151">이러한 디렉터리 중 하나가 시스템 경로에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-151">One of these directories must be in your system path.</span></span> <span data-ttu-id="c0075-152">Visual Studio가 설치된 경우 경로에 이 디렉터리를 포함하는 가장 쉬운 방법은 Visual Studio 명령 프롬프트를 여는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-152">If you have Visual Studio installed, the easiest way to get this directory in your path is to open the Visual Studio Command Prompt.</span></span> <span data-ttu-id="c0075-153">클릭 **시작**를 선택한 후 **모든 프로그램**, **Visual Studio 2012**, **도구**합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-153">Click **Start**, and then select **All Programs**, **Visual Studio 2012**, **Tools**.</span></span> <span data-ttu-id="c0075-154">이 명령 프롬프트에는 이미 구성된 적절한 경로가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-154">This command prompt has the appropriate paths already configured.</span></span> <span data-ttu-id="c0075-155">그렇지 않을 경우 해당 디렉터리를 경로에 수동으로 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-155">Otherwise you must add the appropriate directory to your path manually.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c0075-156">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-156">The samples may already be installed on your computer.</span></span> <span data-ttu-id="c0075-157">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c0075-157">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c0075-158">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="c0075-158">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c0075-159">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-159">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\MessageSecurity`  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c0075-160">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="c0075-160">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="c0075-161">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-161">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="c0075-162">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-162">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="c0075-163">단일 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="c0075-163">To run the sample on the same computer</span></span>  
  
1.  <span data-ttu-id="c0075-164">관리자 권한으로 Visual Studio 명령 프롬프트를 열고 샘플 설치 폴더의 Setup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-164">Open a Visual Studio Command Prompt  with administrator privileges and run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="c0075-165">이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-165">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c0075-166">Setup.bat 배치 파일은 Visual Studio 명령 프롬프트에서 실행 되도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-166">The Setup.bat batch file is designed to be run from a Visual Studio Command Prompt .</span></span> <span data-ttu-id="c0075-167">PATH 환경 변수는 SDK가 설치되는 디렉터리를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-167">It requires that the path environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="c0075-168">이 환경 변수는Visual Studio 명령 프롬프트(2010) 내에서 자동으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-168">This environment variable is automatically set within a Visual Studio Command Prompt (2010).</span></span>  
  
2.  <span data-ttu-id="c0075-169">브라우저를 사용 하 여 주소를 입력 하 여 서비스에 대 한 액세스 확인 `http://localhost/servicemodelsamples/service.svc`합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-169">Verify access to the service using a browser by entering the address `http://localhost/servicemodelsamples/service.svc`.</span></span>  
  
3.  <span data-ttu-id="c0075-170">\client\bin에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-170">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="c0075-171">클라이언트 콘솔 응용 프로그램에 클라이언트 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-171">Client activity is displayed on the client console application.</span></span>  
  
4.  <span data-ttu-id="c0075-172">클라이언트와 서비스가 통신할 수 없는 경우 참조 [문제 해결 팁](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-172">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="c0075-173">다중 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="c0075-173">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="c0075-174">서비스 컴퓨터에 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-174">Create a directory on the service computer.</span></span> <span data-ttu-id="c0075-175">IIS(인터넷 정보 서비스) 관리 도구를 사용하여 이 디렉터리에 servicemodelsamples라는 가상 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-175">Create a virtual application named servicemodelsamples for this directory by using the Internet Information Services (IIS) management tool.</span></span>  
  
2.  <span data-ttu-id="c0075-176">\inetpub\wwwroot\servicemodelsamples에서 서비스 컴퓨터의 가상 디렉터리로 서비스 프로그램 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-176">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="c0075-177">\bin 하위 디렉터리에 파일을 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-177">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="c0075-178">Setup.bat, Cleanup.bat 및 ImportClientCert.bat 파일도 서비스 컴퓨터에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-178">Also copy the Setup.bat, Cleanup.bat, and ImportClientCert.bat files to the service computer.</span></span>  
  
3.  <span data-ttu-id="c0075-179">클라이언트 컴퓨터에 클라이언트 이진 파일용 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-179">Create a directory on the client computer for the client binaries.</span></span>  
  
4.  <span data-ttu-id="c0075-180">클라이언트 프로그램 파일을 클라이언트 컴퓨터의 클라이언트 디렉터리로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-180">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="c0075-181">Setup.bat, Cleanup.bat 및 ImportServiceCert.bat 파일도 클라이언트로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-181">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5.  <span data-ttu-id="c0075-182">서버에서 실행 **setup.bat service** 관리자 권한으로 Visual Studio 명령 프롬프트에서입니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-182">On the server, run **setup.bat service** in a Visual Studio command prompt with administrator privileges.</span></span> <span data-ttu-id="c0075-183">실행 **setup.bat** 와 **서비스** 인수는 컴퓨터의 정규화 된 도메인 이름으로 서비스 인증서를 만들고 되어 Service.cer 이라는 파일로 서비스 인증서를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-183">Running **setup.bat** with the **service** argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
6.  <span data-ttu-id="c0075-184">새로운 인증서 이름을 반영 되도록 Web.config를 편집 (에 `findValue` 특성에 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) 컴퓨터의 정규화 된 도메인 이름과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-184">Edit Web.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) which is the same as the fully-qualified domain name of the computer.</span></span>  
  
7.  <span data-ttu-id="c0075-185">서비스 디렉터리에서 클라이언트 컴퓨터의 클라이언트 디렉터리로 Service.cer 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-185">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8.  <span data-ttu-id="c0075-186">클라이언트에서 실행 **setup.bat client** 관리자 권한으로 Visual Studio 명령 프롬프트에서입니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-186">On the client, run **setup.bat client** in a Visual Studio command prompt with administrator privileges.</span></span> <span data-ttu-id="c0075-187">실행 **setup.bat** 와 **클라이언트** 인수 client.com 이라는 클라이언트 인증서를 만들고 클라이언트 인증서 Client.cer 이라는 파일로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-187">Running **setup.bat** with the **client** argument creates a client certificate named client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
9. <span data-ttu-id="c0075-188">클라이언트 컴퓨터의 Client.exe.config 파일에서 끝점의 주소 값을 서비스의 새 주소와 일치하도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-188">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="c0075-189">이렇게 하려면 localhost를 서버의 정규화된 도메인 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-189">Do this by replacing localhost with the fully-qualified domain name of the server.</span></span>  
  
10. <span data-ttu-id="c0075-190">클라이언트 디렉터리에서 서버의 서비스 디렉터리로 Client.cer 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-190">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
11. <span data-ttu-id="c0075-191">클라이언트에서 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 ImportServiceCert.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-191">On the client, run ImportServiceCert.bat in a Visual Studio command prompt with administrative privileges.</span></span> <span data-ttu-id="c0075-192">이 작업은 Service.cer 파일의 서비스 인증서를 CurrentUser - TrustedPeople 저장소로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-192">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
12. <span data-ttu-id="c0075-193">서버에서 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 ImportClientCert.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-193">On the server, run ImportClientCert.bat in a Visual Studio command prompt with administrative privileges.</span></span> <span data-ttu-id="c0075-194">이 작업은 Client.cer 파일의 클라이언트 인증서를 LocalMachine - TrustedPeople 저장소로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-194">This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
13. <span data-ttu-id="c0075-195">클라이언트 컴퓨터의 명령 프롬프트 창에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-195">On the client computer, launch Client.exe from a command prompt window.</span></span> <span data-ttu-id="c0075-196">클라이언트와 서비스가 통신할 수 없는 경우 참조 [문제 해결 팁](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-196">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="c0075-197">샘플 실행 후 정리를 수행하려면</span><span class="sxs-lookup"><span data-stu-id="c0075-197">To clean up after the sample</span></span>  
  
-   <span data-ttu-id="c0075-198">샘플 실행을 완료한 후 샘플 폴더에서 Cleanup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-198">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c0075-199">다중 컴퓨터 구성에서 이 샘플을 실행할 경우에는 이 스크립트로 클라이언트의 서비스 인증서를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-199">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="c0075-200">컴퓨터 인증서를 사용 하는 Windows Communication Foundation (WCF) 샘플을 실행 한 경우 CurrentUser-TrustedPeople 저장소에에서 설치 된 서비스 인증서의 선택을 취소 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0075-200">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="c0075-201">이를 수행하려면 `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` 명령을 사용합니다(예: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`).</span><span class="sxs-lookup"><span data-stu-id="c0075-201">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0075-202">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0075-202">See Also</span></span>
