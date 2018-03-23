---
title: '방법: 채널 보안 자격 증명 지정'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8e03f47-9c4f-4dd5-8f85-429e6d876119
caps.latest.revision: ''
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: e2aedb06ec694f6c7dfb12b70ab919ae23eed17e
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2018
---
# <a name="how-to-specify-channel-security-credentials"></a><span data-ttu-id="1db04-102">방법: 채널 보안 자격 증명 지정</span><span class="sxs-lookup"><span data-stu-id="1db04-102">How to: Specify Channel Security Credentials</span></span>
<span data-ttu-id="1db04-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스 모니커를 사용하여 COM 응용 프로그램에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-103">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Service Moniker allows COM applications to call [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services.</span></span> <span data-ttu-id="1db04-104">대부분의 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서는 클라이언트가 인증 및 권한 부여를 위한 자격 증명을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-104">Most [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services require the client to specify credentials for authentication and authorization.</span></span> <span data-ttu-id="1db04-105">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 호출할 경우 관리되는 코드 또는 응용 프로그램 구성 파일에서 이러한 자격 증명을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-105">When calling a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service from a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client, you can specify these credentials in managed code or in an application configuration file.</span></span> <span data-ttu-id="1db04-106">COM 응용 프로그램에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 호출할 경우 <xref:System.ServiceModel.ComIntegration.IChannelCredentials> 인터페이스를 사용하여 자격 증명을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-106">When calling a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service from a COM application, you can use the <xref:System.ServiceModel.ComIntegration.IChannelCredentials> interface to specify credentials.</span></span> <span data-ttu-id="1db04-107">이 항목에서는 <xref:System.ServiceModel.ComIntegration.IChannelCredentials> 인터페이스를 사용하여 자격 증명을 지정하는 다양한 방식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-107">This topic will illustrate various ways to specify credentials using the <xref:System.ServiceModel.ComIntegration.IChannelCredentials> interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1db04-108"><xref:System.ServiceModel.ComIntegration.IChannelCredentials>는 IDispatch 기반 인터페이스이며 Visual Studio 환경에서는 IntelliSense 기능을 가져오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-108"><xref:System.ServiceModel.ComIntegration.IChannelCredentials> is an IDispatch-based interface and you will not get IntelliSense functionality in the Visual Studio environment.</span></span>  
  
 <span data-ttu-id="1db04-109">이 문서 ´ ֲ는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 에 정의 된 서비스는 [Message Security 샘플](../../../../docs/framework/wcf/samples/message-security-sample.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-109">This article will use the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service defined in the [Message Security Sample](../../../../docs/framework/wcf/samples/message-security-sample.md).</span></span>  
  
### <a name="to-specify-a-client-certificate"></a><span data-ttu-id="1db04-110">클라이언트 인증서 지정</span><span class="sxs-lookup"><span data-stu-id="1db04-110">To specify a client certificate</span></span>  
  
1.  <span data-ttu-id="1db04-111">Message Security 디렉터리에서 Setup.bat 파일을 실행하여 필요한 테스트 인증서를 만든 후 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-111">Run the Setup.bat file in the Message Security directory to create and install the required test certificates.</span></span>  
  
2.  <span data-ttu-id="1db04-112">메시지 보안 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-112">Open the Message Security project.</span></span>  
  
3.  <span data-ttu-id="1db04-113">추가 `[ServiceBehavior(Namespace=``http://Microsoft.ServiceModel.Samples``)]` 에 `ICalculator` 인터페이스 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-113">Add `[ServiceBehavior(Namespace=``http://Microsoft.ServiceModel.Samples``)]` to the `ICalculator` interface definition.</span></span>  
  
4.  <span data-ttu-id="1db04-114">추가 `bindingNamespace=``http://Microsoft.ServiceModel.Samples` 서비스에 대 한 App.config에 있는 끝점 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-114">Add `bindingNamespace=``http://Microsoft.ServiceModel.Samples` to the endpoint tag in the App.config for the service.</span></span>  
  
5.  <span data-ttu-id="1db04-115">메시지 보안 샘플을 빌드하고 Service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-115">Build the Message Security Sample and run Service.exe.</span></span> <span data-ttu-id="1db04-116">Internet Explorer를 사용하여 서비스의 URI(http://localhost:8000/ServiceModelSamples/Service)를 찾은 다음 서비스가 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-116">Use Internet Explorer and browse to the service's URI (http://localhost:8000/ServiceModelSamples/Service) to ensure that the service is working.</span></span>  
  
6.  <span data-ttu-id="1db04-117">Visual Basic 6.0을 열고 새 표준 .exe 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-117">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="1db04-118">폼에 단추를 추가하고 단추를 두 번 클릭하여 다음 코드를 클릭 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-118">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```  
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
        monString = monString + ", binding=BasicHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
        Set monikerProxy = GetObject(monString)  
  
        'Set the Service Certificate.  
     monikerProxy.ChannelCredentials.SetServiceCertificateAuthentication "CurrentUser", "NoCheck", "PeerOrChainTrust"  
    monikerProxy.ChannelCredentials.SetDefaultServiceCertificateFromStore "CurrentUser", "TrustedPeople", "FindBySubjectName", "localhost"  
  
        'Set the Client Certificate.  
        monikerProxy.ChannelCredentials.SetClientCertificateFromStoreByName "CN=client.com", "CurrentUser", "My"  
        MsgBox monikerProxy.Add(3, 4)  
    ```  
  
7.  <span data-ttu-id="1db04-119">Visual Basic 응용 프로그램을 실행하고 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-119">Run the Visual Basic application and verify the results.</span></span>  
  
     <span data-ttu-id="1db04-120">Visual Basic 응용 프로그램에 메시지 상자가 나타나며 Add(3, 4)를 호출한 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-120">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span> <span data-ttu-id="1db04-121"><xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromFile%28System.String%2CSystem.String%2CSystem.String%29> 또는 <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStoreByName%28System.String%2CSystem.String%2CSystem.String%29>을 <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStore%28System.String%2CSystem.String%2CSystem.String%2CSystem.Object%29> 대신 사용하여 클라이언트 인증서를 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-121"><xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromFile%28System.String%2CSystem.String%2CSystem.String%29> or <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStoreByName%28System.String%2CSystem.String%2CSystem.String%29> can also be used in place of <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStore%28System.String%2CSystem.String%2CSystem.String%2CSystem.Object%29> to set the Client Certificate:</span></span>  
  
    ```  
    monikerProxy.ChannelCredentials.SetClientCertificateFromFile "C:\MyClientCert.pfx", "password", "DefaultKeySet"  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="1db04-122">이 호출이 작동하려면 클라이언트가 실행 중인 컴퓨터에서 클라이언트 인증서가 신뢰되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-122">For this call to work, the client certificate needs to be trusted on the machine the client is running on.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1db04-123">모니커의 형식이 잘못되었거나 서비스를 사용할 수 없는 경우 `GetObject`를 호출하면 "구문이 잘못되었습니다."라는 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-123">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span> <span data-ttu-id="1db04-124">이 오류가 발생하면 사용하고 있는 모니커가 올바르고 서비스를 사용할 수 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="1db04-124">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
### <a name="to-specify-user-name-and-password"></a><span data-ttu-id="1db04-125">사용자 이름 및 암호 지정</span><span class="sxs-lookup"><span data-stu-id="1db04-125">To specify user name and password</span></span>  
  
1.  <span data-ttu-id="1db04-126">`wsHttpBinding`을 사용하도록 Service App.config 파일을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-126">Modify the Service App.config file to use the `wsHttpBinding`.</span></span> <span data-ttu-id="1db04-127">이 때 사용자 이름과 암호를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-127">This is required for user name and password validation:</span></span>  
  
  
  
2.  <span data-ttu-id="1db04-128">`clientCredentialType`을 UserName으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-128">Set the `clientCredentialType` to UserName:</span></span>  
  
  
  
3.  <span data-ttu-id="1db04-129">Visual Basic 6.0을 열고 새 표준 .exe 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-129">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="1db04-130">폼에 단추를 추가하고 단추를 두 번 클릭하여 다음 코드를 클릭 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-130">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```  
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set monikerProxy = GetObject(monString)  
  
    monikerProxy.ChannelCredentials.SetServiceCertificateAuthentication "CurrentUser", "NoCheck", "PeerOrChainTrust"  
    monikerProxy.ChannelCredentials.SetUserNameCredential "username", "password"  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
4.  <span data-ttu-id="1db04-131">Visual Basic 응용 프로그램을 실행하고 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-131">Run the Visual Basic application and verify the results.</span></span> <span data-ttu-id="1db04-132">Visual Basic 응용 프로그램에 메시지 상자가 나타나며 Add(3, 4)를 호출한 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-132">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1db04-133">이 샘플의 서비스 모니커에 지정된 바인딩이 WSHttpBinding_ICalculator로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-133">The binding specified in the service moniker in this sample has been changed to WSHttpBinding_ICalculator.</span></span> <span data-ttu-id="1db04-134">또한 <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetUserNameCredential%28System.String%2CSystem.String%29>을 호출할 때 유효한 사용자 이름과 암호를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-134">Also note that you must supply a valid user name and password in the call to <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetUserNameCredential%28System.String%2CSystem.String%29>.</span></span>  
  
### <a name="to-specify-windows-credentials"></a><span data-ttu-id="1db04-135">Windows 자격 증명 지정</span><span class="sxs-lookup"><span data-stu-id="1db04-135">To specify Windows Credentials</span></span>  
  
1.  <span data-ttu-id="1db04-136">Service App.config 파일에서 `clientCredentialType`을 Windows로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-136">Set `clientCredentialType` to Windows in the Service App.config file:</span></span>  
  
  
  
2.  <span data-ttu-id="1db04-137">Visual Basic 6.0을 열고 새 표준 .exe 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-137">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="1db04-138">폼에 단추를 추가하고 단추를 두 번 클릭하여 다음 코드를 클릭 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-138">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```  
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", upnidentity=domain\userID"  
  
    Set monikerProxy = GetObject(monString)  
     monikerProxy.ChannelCredentials.SetWindowsCredential "domain", "userID", "password", 1, True  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
3.  <span data-ttu-id="1db04-139">Visual Basic 응용 프로그램을 실행하고 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-139">Run the Visual Basic application and verify the results.</span></span> <span data-ttu-id="1db04-140">Visual Basic 응용 프로그램에 메시지 상자가 나타나며 Add(3, 4)를 호출한 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-140">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1db04-141">"domain", "userID" 및 "password"를 유효한 값으로 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-141">You must replace "domain", "userID", and "password" with valid values.</span></span>  
  
### <a name="to-specify-an-issue-token"></a><span data-ttu-id="1db04-142">발급 토큰 지정</span><span class="sxs-lookup"><span data-stu-id="1db04-142">To specify an issue token</span></span>  
  
1.  <span data-ttu-id="1db04-143">발급 토큰은 페더레이션 보안을 사용하는 응용 프로그램에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-143">Issue tokens are used only for applications using federated security.</span></span> <span data-ttu-id="1db04-144">페더레이션된 보안에 대 한 자세한 내용은 참조 [페더레이션 및 발급 된 토큰](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md) 및 [Federation 샘플](../../../../docs/framework/wcf/samples/federation-sample.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-144">For more information about federated security, see [Federation and Issued Tokens](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md) and [Federation Sample](../../../../docs/framework/wcf/samples/federation-sample.md).</span></span>  
  
     <span data-ttu-id="1db04-145">다음 Visual Basic 코드 예제에서는 <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29> 메서드를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1db04-145">The following Visual Basic code example illustrates how to call the <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29> method:</span></span>  
  
    ```  
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/SomeService/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://SomeService.Samples"  
        monString = monString + ", binding=WSHttpBinding_ISomeContract, bindingNamespace=http://SomeService.Samples"  
  
        Set monikerProxy = GetObject(monString)  
    monikerProxy.SetIssuedToken("http://somemachine/sts", "bindingType", "binding")  
    ```  
  
     <span data-ttu-id="1db04-146">이 메서드의 매개 변수에 대한 자세한 내용은 <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1db04-146">For more information about the parameters for this method, see <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1db04-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1db04-147">See Also</span></span>  
 [<span data-ttu-id="1db04-148">페더레이션</span><span class="sxs-lookup"><span data-stu-id="1db04-148">Federation</span></span>](../../../../docs/framework/wcf/feature-details/federation.md)  
 [<span data-ttu-id="1db04-149">방법: 페더레이션 서비스에서 자격 증명 구성</span><span class="sxs-lookup"><span data-stu-id="1db04-149">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [<span data-ttu-id="1db04-150">방법: 페더레이션 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="1db04-150">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="1db04-151">메시지 보안</span><span class="sxs-lookup"><span data-stu-id="1db04-151">Message Security</span></span>](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 [<span data-ttu-id="1db04-152">바인딩 및 보안</span><span class="sxs-lookup"><span data-stu-id="1db04-152">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)
