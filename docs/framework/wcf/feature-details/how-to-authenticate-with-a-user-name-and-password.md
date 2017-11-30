---
title: "방법: 사용자 이름 및 암호를 사용하여 인증"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: authentication [WCF], user name and password
ms.assetid: a5415be2-0ef3-464c-9f76-c255cb8165a4
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 73ef3c3f4f4aeb9295cedbbf56635454869b3f4f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-authenticate-with-a-user-name-and-password"></a><span data-ttu-id="c9a2a-102">방법: 사용자 이름 및 암호를 사용하여 인증</span><span class="sxs-lookup"><span data-stu-id="c9a2a-102">How to: Authenticate with a User Name and Password</span></span>
<span data-ttu-id="c9a2a-103">이 항목에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스를 활성화하여 Windows 도메인 사용자 이름 및 암호로 클라이언트를 인증하는 방법을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="c9a2a-103">This topic demonstrates how to enable a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service to authenticate a client with a Windows domain username and password.</span></span> <span data-ttu-id="c9a2a-104">여기에서는 실행 중이면서 자체 호스팅된 서비스가 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="c9a2a-104">It assumes you have a working, self-hosted WCF service.</span></span> <span data-ttu-id="c9a2a-105">기본 자체 호스팅된 WCF 서비스 참조를 만드는 예제를 보려면 [초보자를 위한 자습서](../../../../docs/framework/wcf/getting-started-tutorial.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c9a2a-105">For an example of creating a basic self-hosted WCF service see, [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span> <span data-ttu-id="c9a2a-106">이 항목은 코드에 서비스가 구성된 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="c9a2a-106">This topic assumes the service is configured in code.</span></span> <span data-ttu-id="c9a2a-107">확인 하려는 경우 구성 파일을 사용 하 여 비슷한 서비스 구성의 예 참조 [메시지 보안 사용자 이름](../../../../docs/framework/wcf/samples/message-security-user-name.md)</span><span class="sxs-lookup"><span data-stu-id="c9a2a-107">If you would like to see an example of configuring a similar service using a configuration file see [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md)</span></span>  
  
 <span data-ttu-id="c9a2a-108">Windows 도메인 사용자 이름 및 암호 사용 하 여 클라이언트를 인증 하도록 서비스를 구성 하는 <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> 설정 하 고 해당 `Security.Mode` 속성을 `Message`합니다.</span><span class="sxs-lookup"><span data-stu-id="c9a2a-108">To configure a service to authenticate its clients using Windows Domain username and passwords use the <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> and set its `Security.Mode` property to `Message`.</span></span> <span data-ttu-id="c9a2a-109">또한 사용자 이름과 암호가 클라이언트에서 서비스로 전송되므로 사용자 이름과 암호를 암호화하는 데 사용할 X509 인증서를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9a2a-109">In addition you must specify an X509 certificate that will be used to encrypt the username and password as they are sent from the client to the service.</span></span>  
  
 <span data-ttu-id="c9a2a-110">클라이언트에서 사용자에게 사용자 이름과 암호를 묻고 WCF 클라이언트 프록시에 사용자의 자격 증명을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9a2a-110">On the client, you must prompt the user for the username and password and specify the user’s credentials on the WCF client proxy.</span></span>  
  
### <a name="to-configure-a-wcf-service-to-authenticate-using-windows-domain-username-and-password"></a><span data-ttu-id="c9a2a-111">Windows 도메인 이름 및 암호를 사용하여 인증할 WCF 서비스를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="c9a2a-111">To configure a WCF service to authenticate using Windows domain username and password.</span></span>  
  
1.  <span data-ttu-id="c9a2a-112">인스턴스를 만들고는 <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>, 바인딩의 보안 모드 설정 `SecurityMode.Message`설정는 `ClientCredentialType` 에 대 한 바인딩 `MessageCredentialType.UserName`, 표시 된 것 처럼 서비스 호스트에 구성 된 바인딩을 사용 하 여 서비스 끝점을 추가 하 고 다음 코드:</span><span class="sxs-lookup"><span data-stu-id="c9a2a-112">Create an instance of the <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>, set the security mode of the binding to `SecurityMode.Message`, set the `ClientCredentialType` of the binding to `MessageCredentialType.UserName`, and add a service endpoint using the configured binding to the service host as shown in the following code:</span></span>  
  
    ```  
    // ...  
    WSHttpBinding userNameBinding = new WSHttpBinding();  
    userNameBinding.Security.Mode = SecurityMode.Message;  
    userNameBinding.Security.Message.ClientCredentialType = MessageCredentialType.UserName;  
    svcHost.AddServiceEndpoint(typeof(IService1), userNameBinding, "");  
    // ...  
    ```  
  
2.  <span data-ttu-id="c9a2a-113">유선으로 전송되는 사용자 이름과 암호 정보를 암호화하는 데 사용하는 서버 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c9a2a-113">Specify the server certificate used to encrypt the username and password information sent over the wire.</span></span> <span data-ttu-id="c9a2a-114">이 코드는 위 코드 바로 다음에 나와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9a2a-114">This code should immediately follow the code above.</span></span> <span data-ttu-id="c9a2a-115">다음 예제에서는 만든 인증서를 사용 하 여에서 setup.bat 파일을 여는 [메시지 보안 사용자 이름](../../../../docs/framework/wcf/samples/message-security-user-name.md) 샘플:</span><span class="sxs-lookup"><span data-stu-id="c9a2a-115">The following example uses the certificate that is created by the setup.bat file from the [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md) sample:</span></span>  
  
    ```  
    // ...  
    svcHost.Credentials.ServiceCertificate.SetCertificate(StoreLocation.LocalMachine, StoreName.My, X509FindType.FindBySubjectName, "localhost");  
    // ...  
    ```  
  
     <span data-ttu-id="c9a2a-116">사용자 인증서를 가리키도록 코드를 수정하면 사용자 인증서를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9a2a-116">You can use your own certificate, just modify the code to refer to your certificate.</span></span> <span data-ttu-id="c9a2a-117">만들기 및 인증서를 사용 하는 방법에 대 한 자세한 내용은 참조 [인증서 작업](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c9a2a-117">For more information about creating and using certificates see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span> <span data-ttu-id="c9a2a-118">인증서가 로컬 컴퓨터에 대한 신뢰된 사용자 인증서 저장소에 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="c9a2a-118">Make sure the certificate is in the Trusted People certificate store for the Local Machine.</span></span> <span data-ttu-id="c9a2a-119">Mmc.exe를 실행 하 고 선택 하 여이 작업을 수행할 수는 **파일**, **스냅인 추가/제거...**  메뉴 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="c9a2a-119">You can do this by running mmc.exe and selecting the **File**, **Add/Remove Snap-in...** menu item.</span></span> <span data-ttu-id="c9a2a-120">에 **추가 또는 제거 스냅인** 대화 상자에서는 **인증서 스냅인** 클릭 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="c9a2a-120">In the **Add or Remove Snap-ins** dialog, select the **Certificates snap-in** and click **Add**.</span></span> <span data-ttu-id="c9a2a-121">인증서 스냅인 대화 상자에서 선택 **컴퓨터 계정**합니다.</span><span class="sxs-lookup"><span data-stu-id="c9a2a-121">In the Certificates Snap-in dialog select **Computer account**.</span></span> <span data-ttu-id="c9a2a-122">기본적으로 Message Security User 이름 샘플에서 생성된 인증서는 Personal/Certificates 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9a2a-122">By default the certificate generated from the Message Security User name sample will be located in the Personal/Certificates folder.</span></span>  <span data-ttu-id="c9a2a-123">MMC 창에서 열 발급 대상 "localhost"로 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9a2a-123">It will be listed as "localhost" under the Issued to column in the MMC window.</span></span> <span data-ttu-id="c9a2a-124">인증서를 끌어서는 **신뢰할 수 있는 사용자** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="c9a2a-124">Drag and drop the certificate into the **Trusted People** folder.</span></span> <span data-ttu-id="c9a2a-125">그러면 인증을 수행할 때 WCF가 인증서를 신뢰할 수 있는 인증서로 취급합니다.</span><span class="sxs-lookup"><span data-stu-id="c9a2a-125">This will allow WCF to treat the certificate as a trusted certificate when performing authentication.</span></span>  
  
### <a name="to-call-the-service-passing-username-and-password"></a><span data-ttu-id="c9a2a-126">사용자 이름과 암호를 전달하는 서비스를 호출하려면</span><span class="sxs-lookup"><span data-stu-id="c9a2a-126">To call the service passing username and password</span></span>  
  
1.  <span data-ttu-id="c9a2a-127">클라이언트 응용 프로그램은 사용자에게 사용자 이름과 암호를 물어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9a2a-127">The client application must prompt the user for their username and password.</span></span> <span data-ttu-id="c9a2a-128">다음 코드는 사용자에게 사용자 이름과 암호를 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="c9a2a-128">The following code asks the user for username and password.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="c9a2a-129">암호는 입력하는 동안 표시되므로 이 코드는 프로덕션에서 사용하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9a2a-129">This code should not be used in production as the password is displayed while being entered.</span></span>  
  
    ```  
    public static void GetPassword(out string username, out string password)  
            {  
                Console.WriteLine("Provide a valid machine or domain account. [domain\\user]");  
                Console.WriteLine("   Enter username:");  
                username = Console.ReadLine();  
                Console.WriteLine("   Enter password:");  
                password = Console.ReadLine();             
                return;  
            }  
    ```  
  
2.  <span data-ttu-id="c9a2a-130">다음 코드와 같이 클라이언트의 자격 증명을 지정하는 클라이언트 프록시 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c9a2a-130">Create an instance of the client proxy specifying the client’s credentials as shown in the following code:</span></span>  
  
    ```  
    string username;  
    string password;  
  
    // Instantiate the proxy  
    Service1Client proxy = new Service1Client();  
  
    // Prompt the user for username & password  
    GetPassword(out username, out password);  
  
    // Set the user’s credentials on the proxy  
    proxy.ClientCredentials.UserName.UserName = username;  
    proxy.ClientCredentials.UserName.Password = password;  
  
    // Treat the test certificate as trusted  
    proxy.ClientCredentials.ServiceCertificate.Authentication.CertificateValidationMode = System.ServiceModel.Security.X509CertificateValidationMode.PeerOrChainTrust;  
    // Call the service operation using the proxy  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c9a2a-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9a2a-131">See Also</span></span>  
 <span data-ttu-id="c9a2a-132"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`></span><span class="sxs-lookup"><span data-stu-id="c9a2a-132"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`></span></span>  
 <xref:System.ServiceModel.WSHttpSecurity>  
 <xref:System.ServiceModel.SecurityMode>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.UserName%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.Password%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>  
 <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>  
 <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>  
 [<span data-ttu-id="c9a2a-133">기본 인증과 함께 전송 보안</span><span class="sxs-lookup"><span data-stu-id="c9a2a-133">Transport Security with Basic Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)  
 [<span data-ttu-id="c9a2a-134">분산된 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="c9a2a-134">Distributed Application Security</span></span>](../../../../docs/framework/wcf/feature-details/distributed-application-security.md)  
 [<span data-ttu-id="c9a2a-135">\<wsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="c9a2a-135">\<wsHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)
