---
title: "Service Identity 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 79fa8c1c-85bb-4b67-bc67-bfaf721303f8
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cde8966e89a22b19109688d5da0ff5b45eee55ef
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="service-identity-sample"></a><span data-ttu-id="d45f6-102">Service Identity 샘플</span><span class="sxs-lookup"><span data-stu-id="d45f6-102">Service Identity Sample</span></span>
<span data-ttu-id="d45f6-103">이 Service Identity 샘플에서는 서비스의 ID를 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-103">This service identity sample demonstrates how to set the identity for a service.</span></span> <span data-ttu-id="d45f6-104">클라이언트는 디자인 타임에 서비스의 메타데이터를 사용하여 ID를 검색한 다음 런타임에 서비스의 ID를 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-104">At design time, a client can retrieve the identity using the service's metadata and then at runtime the client can authenticate the service's identity.</span></span> <span data-ttu-id="d45f6-105">서비스 ID의 개념을 사용하면 클라이언트가 작업을 호출하기 전에 서비스를 인증함으로써 인증되지 않은 호출로부터 클라이언트를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-105">The concept of service identity is to allow a client to authenticate a service before calling any of its operations, thereby protecting the client from unauthenticated calls.</span></span> <span data-ttu-id="d45f6-106">보안 연결에서는 또한 서비스가 클라이언트의 액세스를 허용하기 전에 클라이언트의 자격 증명을 인증하는데, 이 부분은 샘플에서 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-106">On a secure connection the service also authenticates a client's credentials before allowing it access, but this is not the focus of this sample.</span></span> <span data-ttu-id="d45f6-107">예제를 참조 [클라이언트](../../../../docs/framework/wcf/samples/client.md) 서버 인증을 보여 주는 합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-107">See the samples in [Client](../../../../docs/framework/wcf/samples/client.md) that show server authentication.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d45f6-108">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="d45f6-109">이 샘플에서는 다음 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-109">This sample illustrates the following features:</span></span>  
  
-   <span data-ttu-id="d45f6-110">서비스의 여러 끝점에서 서로 다른 형식의 ID를 설정하는 방법.</span><span class="sxs-lookup"><span data-stu-id="d45f6-110">How to set the different types of identity on different endpoints for a service.</span></span> <span data-ttu-id="d45f6-111">각 ID 형식은 서로 다른 기능을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-111">Each type of identity has different capabilities.</span></span> <span data-ttu-id="d45f6-112">사용할 ID 형식은 끝점의 바인딩에 사용되는 보안 자격 증명의 형식에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-112">The type of identity to use is dependent on the type of security credentials used on the endpoint's binding.</span></span>  
  
-   <span data-ttu-id="d45f6-113">ID는 구성에서 선언을 통해 또는 코드에서 명령을 통해 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-113">Identity can either be set declaratively in configuration or imperatively in code.</span></span> <span data-ttu-id="d45f6-114">클라이언트와 서버 모두 구성을 사용하여 ID를 설정하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-114">Typically for both the client and the service you should use configuration to set the identity.</span></span>  
  
-   <span data-ttu-id="d45f6-115">클라이언트에서 사용자 지정 ID를 설정하는 방법.</span><span class="sxs-lookup"><span data-stu-id="d45f6-115">How to set a custom identity on the client.</span></span> <span data-ttu-id="d45f6-116">사용자 지정 ID는 일반적으로 기존 ID 형식을 사용자 지정한 것으로서, 이를 통해 클라이언트가 서비스의 자격 증명에 제공된 다른 클레임 정보를 검사하여 서비스 호출에 앞서 권한 부여 결정을 내릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-116">A custom identity is typically a customization of an existing type of identity that enables the client to examine other claim information provided in the service's credentials to make authorization decisions before calling the service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d45f6-117">이 샘플에서는 identity.com이라는 특정 인증서의 ID와 이 인증서 내부에 포함된 RSA 키를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-117">This sample checks the identity of a specific certificate called identity.com and the RSA key contained within this certificate.</span></span> <span data-ttu-id="d45f6-118">클라이언트의 구성에서 인증서 및 RSA ID 형식을 사용할 경우 이 값이 serialize되는 서비스에서 WSDL을 검사하면 이 값을 손쉽게 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-118">When using the Certificate and RSA identity types in configuration on the client, an easy way to get these values is to inspect the WSDL for the service where these values are serialized.</span></span>  
  
 <span data-ttu-id="d45f6-119">다음 샘플 코드에서는 WSHttpBinding을 사용하여 인증서의 DNS(도메인 이름 서버)로 서비스 끝점의 ID를 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-119">The following sample code shows how to configure the identity of a service endpoint with the Domain Name Server (DNS) of a certificate using a WSHttpBinding.</span></span>  
  
```  
//Create a service endpoint and set its identity to the certificate's DNS                 
WSHttpBinding wsAnonbinding = new WSHttpBinding (SecurityMode.Message);  
// Client are Anonymous to the service  
wsAnonbinding.Security.Message.ClientCredentialType = MessageCredentialType.None;  
WServiceEndpoint ep = serviceHost.AddServiceEndpoint(typeof(ICalculator),wsAnonbinding, String.Empty);  
EndpointAddress epa = new EndpointAddress(dnsrelativeAddress,EndpointIdentity.CreateDnsIdentity("identity.com"));  
ep.Address = epa;  
```  
  
 <span data-ttu-id="d45f6-120">또한 이 ID는 App.config 파일의 구성에서 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-120">The identity can also be specified in configuration in the App.config file.</span></span> <span data-ttu-id="d45f6-121">다음 예제에서는 서비스 끝점에 대해 UPN(User Principal Name) ID를 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-121">The following example shows how to set the UPN (User Principal Name) identity for a service endpoint.</span></span>  
  
```xml  
<endpoint address="upnidentity"  
        behaviorConfiguration=""  
        binding="wsHttpBinding"  
        bindingConfiguration="WSHttpBinding_Windows"  
        name="WSHttpBinding_ICalculator_Windows"  
        contract="Microsoft.ServiceModel.Samples.ICalculator">  
  <!-- Set the UPN identity for this endpoint -->  
  <identity>  
      <userPrincipalName value="host\myservice.com" />  
  </identity >  
</endpoint>  
```  
  
 <span data-ttu-id="d45f6-122">사용자 지정 ID는 <xref:System.ServiceModel.EndpointIdentity> 및 <xref:System.ServiceModel.Security.IdentityVerifier> 클래스에서 파생하여 클라이언트에 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-122">A custom identity can be set on the client by deriving from the <xref:System.ServiceModel.EndpointIdentity> and the <xref:System.ServiceModel.Security.IdentityVerifier> classes.</span></span> <span data-ttu-id="d45f6-123">개념적으로 <xref:System.ServiceModel.Security.IdentityVerifier> 클래스는 서비스의 `AuthorizationManager` 클래스와 동등한 클라이언트로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-123">Conceptually the <xref:System.ServiceModel.Security.IdentityVerifier> class can be considered to be the client equivalent of the service's `AuthorizationManager` class.</span></span> <span data-ttu-id="d45f6-124">다음 코드 예제에서는 `OrgEndpointIdentity`의 구현을 보여 주는데, 이는 서버 인증서의 주체 이름에 일치시킬 조직 이름을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-124">The following code example shows an implementation of `OrgEndpointIdentity`, which stores an organization name to match in the subject name of the server's certificate.</span></span> <span data-ttu-id="d45f6-125">조직 이름에 대한 권한 부여 검사는 `CheckAccess` 클래스의 `CustomIdentityVerifier` 메서드에서 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-125">The authorization check for the organization name occurs in the `CheckAccess` method on the `CustomIdentityVerifier` class.</span></span>  
  
```  
// This custom EndpointIdentity stores an organization name   
public class OrgEndpointIdentity : EndpointIdentity  
{  
    private string orgClaim;  
    public OrgEndpointIdentity(string orgName)  
    {  
        orgClaim = orgName;  
    }  
    public string OrganizationClaim  
    {  
        get { return orgClaim; }  
        set { orgClaim = value; }  
    }  
}  
  
//This custom IdentityVerifier uses the supplied OrgEndpointIdentity to  
//check that X.509 certificate's distinguished name claim contains  
//the organization name e.g. the string value "O=Contoso"   
class CustomIdentityVerifier : IdentityVerifier  
{  
    public override bool CheckAccess(EndpointIdentity identity, AuthorizationContext authContext)  
    {  
        bool returnvalue = false;  
        foreach (ClaimSet claimset in authContext.ClaimSets)  
        {  
            foreach (Claim claim in claimset)  
            {  
                if (claim.ClaimType == "http://schemas.microsoft.com/ws/2005/05/identity/claims/x500distinguishedname")  
                {  
                    X500DistinguishedName name = (X500DistinguishedName)claim.Resource;  
                    if (name.Name.Contains(((OrgEndpointIdentity)identity).OrganizationClaim))  
                    {  
                        Console.WriteLine("Claim Type: {0}",claim.ClaimType);  
                        Console.WriteLine("Right: {0}", claim.Right);  
                        Console.WriteLine("Resource: {0}",claim.Resource);  
                        Console.WriteLine();  
                        returnvalue = true;  
                    }  
                }  
            }  
        }  
        return returnvalue;  
    }  
}  
```  
  
 <span data-ttu-id="d45f6-126">이 샘플에서는 언어별 ID 솔루션 폴더에 있는 identity.com이라는 인증서를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-126">This sample uses a certificate called identity.com which is in the language-specific Identity solution folder.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d45f6-127">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="d45f6-127">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="d45f6-128">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-128">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="d45f6-129">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-129">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="d45f6-130">지침에 따라 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-130">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="d45f6-131">단일 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="d45f6-131">To run the sample on the same computer</span></span>  
  
1.  <span data-ttu-id="d45f6-132">[!INCLUDE[wxp](../../../../includes/wxp-md.md)] 또는 [!INCLUDE[wv](../../../../includes/wv-md.md)]에서 MMC 스냅인 도구를 사용하여 ID 솔루션 폴더의 Identity.pfx 인증서 파일을 LocalMachine/My(개인) 인증서 저장소로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-132">On [!INCLUDE[wxp](../../../../includes/wxp-md.md)] or [!INCLUDE[wv](../../../../includes/wv-md.md)], import the Identity.pfx certificate file in the Identity solution folder into the LocalMachine/My (Personal) certificate store using the MMC snap-in tool.</span></span> <span data-ttu-id="d45f6-133">이 파일은 암호로 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-133">This file is password protected.</span></span> <span data-ttu-id="d45f6-134">가져오는 동안 암호를 묻는 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-134">During the import you are asked for a password.</span></span> <span data-ttu-id="d45f6-135">형식 `xyz` 암호 상자에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-135">Type `xyz` into the password box.</span></span> <span data-ttu-id="d45f6-136">자세한 내용은 참조는 [하는 방법: MMC 스냅인을 사용 하 여 보기 인증서](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-136">For more information, see the [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md) topic.</span></span> <span data-ttu-id="d45f6-137">이 작업을 마쳤으면 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 Setup.bat를 실행하여 이 인증서를 CurrentUser/Trusted People 저장소로 복사하여 클라이언트에서 사용할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-137">Once this is done, run Setup.bat in a Visual Studio command prompt with administrator privileges, which copies this certificate to the CurrentUser/Trusted People store for use on the client.</span></span>  
  
2.  <span data-ttu-id="d45f6-138">[!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]에서 관리자 권한으로 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트를 열고 샘플 설치 폴더의 Setup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-138">On [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], run Setup.bat from the sample install folder inside a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] command prompt with administrator privileges.</span></span> <span data-ttu-id="d45f6-139">이 작업은 샘플 실행에 필요한 모든 인증서를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-139">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d45f6-140">Setup.bat 배치 파일은 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트에서 실행되도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-140">The Setup.bat batch file is designed to be run from a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Command Prompt.</span></span> <span data-ttu-id="d45f6-141">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트에서 설정된 PATH 환경 변수는 Setup.bat 스크립트에 필요한 실행 파일이 포함된 디렉터리를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-141">The PATH environment variable set within the [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span> <span data-ttu-id="d45f6-142">샘플 사용을 마쳤으면 Cleanup.bat를 실행하여 인증서를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-142">Ensure that you remove the certificates by running Cleanup.bat when you have finished with the sample.</span></span> <span data-ttu-id="d45f6-143">다른 보안 샘플에도 동일한 인증서가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-143">Other security samples use the same certificates.</span></span>  
  
3.  <span data-ttu-id="d45f6-144">\service\bin 디렉터리에서 Service.exe를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-144">Launch Service.exe from the \service\bin directory.</span></span> <span data-ttu-id="d45f6-145">준비를 눌러야 하는 프롬프트를 표시 하는 서비스에 표시 되는지 확인 \<Enter > 서비스를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-145">Ensure that the service indicates that it is ready and displays a prompt to Press \<Enter> to terminate the service.</span></span>  
  
4.  <span data-ttu-id="d45f6-146">빌드하고 실행하려면 \client\bin 디렉터리에서 Client.exe를 시작하거나 Visual Studio에서 F5 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-146">Launch Client.exe from \client\bin directory or by pressing F5 in Visual Studio to build and run.</span></span> <span data-ttu-id="d45f6-147">클라이언트 콘솔 응용 프로그램에 클라이언트 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-147">Client activity is displayed on the client console application.</span></span>  
  
5.  <span data-ttu-id="d45f6-148">클라이언트와 서비스가 통신할 수 없는 경우 [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d45f6-148">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="d45f6-149">다중 컴퓨터 구성에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="d45f6-149">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="d45f6-150">샘플의 클라이언트 부분을 빌드하기 전에 Client.cs 파일의 `CallServiceCustomClientIdentity` 메서드에서 서비스의 끝점 주소 값을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-150">Before building the client part of the sample, be sure to change the value for the service's endpoint address in the Client.cs file in the `CallServiceCustomClientIdentity` method.</span></span> <span data-ttu-id="d45f6-151">그런 다음 샘플을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-151">Then build the sample.</span></span>  
  
2.  <span data-ttu-id="d45f6-152">서비스 컴퓨터에 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-152">Create a directory on the service computer.</span></span>  
  
3.  <span data-ttu-id="d45f6-153">서비스 프로그램 파일을 service\bin에서 서비스 컴퓨터에 있는 디렉터리에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-153">Copy the service program files from service\bin to the directory on the service computer.</span></span> <span data-ttu-id="d45f6-154">Setup.bat 및 Cleanup.bat 파일도 서비스 컴퓨터로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-154">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
4.  <span data-ttu-id="d45f6-155">클라이언트 컴퓨터에 클라이언트 이진 파일용 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-155">Create a directory on the client computer for the client binaries.</span></span>  
  
5.  <span data-ttu-id="d45f6-156">클라이언트 프로그램 파일을 클라이언트 컴퓨터의 클라이언트 디렉터리로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-156">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="d45f6-157">Setup.bat, Cleanup.bat 및 ImportServiceCert.bat 파일도 클라이언트로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-157">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
6.  <span data-ttu-id="d45f6-158">서비스에서 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 `setup.bat service`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-158">On the service, run `setup.bat service` in a Visual Studio command prompt opened with administrator privileges.</span></span> <span data-ttu-id="d45f6-159">실행 `setup.bat` 와 `service` 인수는 컴퓨터의 정규화 된 도메인 이름으로 서비스 인증서를 만들고 되어 Service.cer 이라는 파일로 서비스 인증서를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-159">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
7.  <span data-ttu-id="d45f6-160">서비스 디렉터리에서 클라이언트 컴퓨터의 클라이언트 디렉터리로 Service.cer 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-160">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8.  <span data-ttu-id="d45f6-161">클라이언트 컴퓨터의 Client.exe.config 파일에서 끝점의 주소 값을 서비스의 새 주소와 일치하도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-161">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="d45f6-162">여러 개의 인스턴스를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-162">There are multiple instances that must be changed.</span></span>  
  
9. <span data-ttu-id="d45f6-163">클라이언트에서 관리자 권한으로 Visual Studio 명령 프롬프트를 열고 ImportServiceCert.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-163">On the client, run ImportServiceCert.bat in a Visual Studio command prompt opened with administrator privileges.</span></span> <span data-ttu-id="d45f6-164">이 작업은 Service.cer 파일의 서비스 인증서를 CurrentUser - TrustedPeople 저장소로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-164">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
10. <span data-ttu-id="d45f6-165">서비스 컴퓨터의 명령 프롬프트에서 Service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-165">On the service computer, launch the Service.exe from the command prompt.</span></span>  
  
11. <span data-ttu-id="d45f6-166">클라이언트 컴퓨터의 명령 프롬프트에서 Client.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-166">On the client computer, launch Client.exe from a command prompt.</span></span> <span data-ttu-id="d45f6-167">클라이언트와 서비스가 통신할 수 없는 경우 [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d45f6-167">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="d45f6-168">샘플 실행 후 정리를 수행하려면</span><span class="sxs-lookup"><span data-stu-id="d45f6-168">To clean up after the sample</span></span>  
  
-   <span data-ttu-id="d45f6-169">샘플 실행을 완료했으면 샘플 폴더에서 Cleanup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-169">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d45f6-170">다중 컴퓨터 구성에서 이 샘플을 실행할 경우에는 이 스크립트로 클라이언트의 서비스 인증서를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-170">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="d45f6-171">다중 컴퓨터 구성의 인증서를 사용하는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 샘플을 실행한 경우 CurrentUser - TrustedPeople 저장소에 설치된 서비스 인증서를 지워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d45f6-171">If you have run [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="d45f6-172">이를 수행하려면 `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` 명령을 사용합니다(예: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`).</span><span class="sxs-lookup"><span data-stu-id="d45f6-172">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d45f6-173">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d45f6-173">See Also</span></span>
