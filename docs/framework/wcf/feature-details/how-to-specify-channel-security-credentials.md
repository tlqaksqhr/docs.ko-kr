---
title: '방법: 채널 보안 자격 증명 지정'
ms.date: 03/30/2017
ms.assetid: f8e03f47-9c4f-4dd5-8f85-429e6d876119
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: f25089f7f5ffa16bb46e0833b15b4cbc4a7735ac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33496853"
---
# <a name="how-to-specify-channel-security-credentials"></a><span data-ttu-id="72965-102">방법: 채널 보안 자격 증명 지정</span><span class="sxs-lookup"><span data-stu-id="72965-102">How to: Specify Channel Security Credentials</span></span>
<span data-ttu-id="72965-103">Windows Communication Foundation (WCF) 서비스 모니커 COM 응용 프로그램을을 WCF 서비스를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72965-103">The Windows Communication Foundation (WCF) Service Moniker allows COM applications to call WCF services.</span></span> <span data-ttu-id="72965-104">대부분의 WCF 서비스에 클라이언트 인증 및 권한 부여에 대 한 자격 증명을 지정할 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="72965-104">Most WCF services require the client to specify credentials for authentication and authorization.</span></span> <span data-ttu-id="72965-105">WCF 클라이언트에서 WCF 서비스를 호출할 때 응용 프로그램 구성 파일에서 또는 관리 코드에서 이러한 자격 증명을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72965-105">When calling a WCF service from a WCF client, you can specify these credentials in managed code or in an application configuration file.</span></span> <span data-ttu-id="72965-106">COM 응용 프로그램에서 WCF 서비스를 호출할 때 사용할 수 있습니다는 <xref:System.ServiceModel.ComIntegration.IChannelCredentials> 인터페이스 자격 증명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="72965-106">When calling a WCF service from a COM application, you can use the <xref:System.ServiceModel.ComIntegration.IChannelCredentials> interface to specify credentials.</span></span> <span data-ttu-id="72965-107">이 항목에서는 <xref:System.ServiceModel.ComIntegration.IChannelCredentials> 인터페이스를 사용하여 자격 증명을 지정하는 다양한 방식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72965-107">This topic will illustrate various ways to specify credentials using the <xref:System.ServiceModel.ComIntegration.IChannelCredentials> interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="72965-108"><xref:System.ServiceModel.ComIntegration.IChannelCredentials>는 IDispatch 기반 인터페이스이며 Visual Studio 환경에서는 IntelliSense 기능을 가져오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="72965-108"><xref:System.ServiceModel.ComIntegration.IChannelCredentials> is an IDispatch-based interface and you will not get IntelliSense functionality in the Visual Studio environment.</span></span>  
  
 <span data-ttu-id="72965-109">이 문서에 정의 된 WCF 서비스를 사용 합니다는 [Message Security 샘플](../../../../docs/framework/wcf/samples/message-security-sample.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="72965-109">This article will use the WCF service defined in the [Message Security Sample](../../../../docs/framework/wcf/samples/message-security-sample.md).</span></span>  
  
### <a name="to-specify-a-client-certificate"></a><span data-ttu-id="72965-110">클라이언트 인증서 지정</span><span class="sxs-lookup"><span data-stu-id="72965-110">To specify a client certificate</span></span>  
  
1.  <span data-ttu-id="72965-111">Message Security 디렉터리에서 Setup.bat 파일을 실행하여 필요한 테스트 인증서를 만든 후 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="72965-111">Run the Setup.bat file in the Message Security directory to create and install the required test certificates.</span></span>  
  
2.  <span data-ttu-id="72965-112">메시지 보안 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="72965-112">Open the Message Security project.</span></span>  
  
3.  <span data-ttu-id="72965-113">추가 `[ServiceBehavior(Namespace=``http://Microsoft.ServiceModel.Samples``)]` 에 `ICalculator` 인터페이스 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="72965-113">Add `[ServiceBehavior(Namespace=``http://Microsoft.ServiceModel.Samples``)]` to the `ICalculator` interface definition.</span></span>  
  
4.  <span data-ttu-id="72965-114">추가 `bindingNamespace=``http://Microsoft.ServiceModel.Samples` 서비스에 대 한 App.config에 있는 끝점 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="72965-114">Add `bindingNamespace=``http://Microsoft.ServiceModel.Samples` to the endpoint tag in the App.config for the service.</span></span>  
  
5.  <span data-ttu-id="72965-115">메시지 보안 샘플을 빌드하고 Service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="72965-115">Build the Message Security Sample and run Service.exe.</span></span> <span data-ttu-id="72965-116">Internet Explorer를 사용 하 고 서비스의 URI로 이동 (http://localhost:8000/ServiceModelSamples/Service) 서비스가 작동 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="72965-116">Use Internet Explorer and browse to the service's URI (http://localhost:8000/ServiceModelSamples/Service) to ensure that the service is working.</span></span>  
  
6.  <span data-ttu-id="72965-117">Visual Basic 6.0을 열고 새 표준 .exe 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="72965-117">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="72965-118">폼에 단추를 추가하고 단추를 두 번 클릭하여 다음 코드를 클릭 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="72965-118">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
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
  
7.  <span data-ttu-id="72965-119">Visual Basic 응용 프로그램을 실행하고 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="72965-119">Run the Visual Basic application and verify the results.</span></span>  
  
     <span data-ttu-id="72965-120">Visual Basic 응용 프로그램에 메시지 상자가 나타나며 Add(3, 4)를 호출한 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="72965-120">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span> <span data-ttu-id="72965-121"><xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromFile%28System.String%2CSystem.String%2CSystem.String%29> 또는 <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStoreByName%28System.String%2CSystem.String%2CSystem.String%29>을 <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStore%28System.String%2CSystem.String%2CSystem.String%2CSystem.Object%29> 대신 사용하여 클라이언트 인증서를 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72965-121"><xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromFile%28System.String%2CSystem.String%2CSystem.String%29> or <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStoreByName%28System.String%2CSystem.String%2CSystem.String%29> can also be used in place of <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStore%28System.String%2CSystem.String%2CSystem.String%2CSystem.Object%29> to set the Client Certificate:</span></span>  
  
    ```  
    monikerProxy.ChannelCredentials.SetClientCertificateFromFile "C:\MyClientCert.pfx", "password", "DefaultKeySet"  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="72965-122">이 호출이 작동하려면 클라이언트가 실행 중인 컴퓨터에서 클라이언트 인증서가 신뢰되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72965-122">For this call to work, the client certificate needs to be trusted on the machine the client is running on.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="72965-123">모니커의 형식이 잘못되었거나 서비스를 사용할 수 없는 경우 `GetObject`를 호출하면 "구문이 잘못되었습니다."라는 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="72965-123">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span> <span data-ttu-id="72965-124">이 오류가 발생하면 사용하고 있는 모니커가 올바르고 서비스를 사용할 수 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="72965-124">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
### <a name="to-specify-user-name-and-password"></a><span data-ttu-id="72965-125">사용자 이름 및 암호 지정</span><span class="sxs-lookup"><span data-stu-id="72965-125">To specify user name and password</span></span>  
  
1.  <span data-ttu-id="72965-126">`wsHttpBinding`을 사용하도록 Service App.config 파일을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="72965-126">Modify the Service App.config file to use the `wsHttpBinding`.</span></span> <span data-ttu-id="72965-127">이 때 사용자 이름과 암호를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72965-127">This is required for user name and password validation:</span></span>  
  
  
  
2.  <span data-ttu-id="72965-128">`clientCredentialType`을 UserName으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="72965-128">Set the `clientCredentialType` to UserName:</span></span>  
  
  
  
3.  <span data-ttu-id="72965-129">Visual Basic 6.0을 열고 새 표준 .exe 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="72965-129">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="72965-130">폼에 단추를 추가하고 단추를 두 번 클릭하여 다음 코드를 클릭 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="72965-130">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
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
  
4.  <span data-ttu-id="72965-131">Visual Basic 응용 프로그램을 실행하고 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="72965-131">Run the Visual Basic application and verify the results.</span></span> <span data-ttu-id="72965-132">Visual Basic 응용 프로그램에 메시지 상자가 나타나며 Add(3, 4)를 호출한 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="72965-132">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="72965-133">이 샘플의 서비스 모니커에 지정된 바인딩이 WSHttpBinding_ICalculator로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="72965-133">The binding specified in the service moniker in this sample has been changed to WSHttpBinding_ICalculator.</span></span> <span data-ttu-id="72965-134">또한 <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetUserNameCredential%28System.String%2CSystem.String%29>을 호출할 때 유효한 사용자 이름과 암호를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72965-134">Also note that you must supply a valid user name and password in the call to <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetUserNameCredential%28System.String%2CSystem.String%29>.</span></span>  
  
### <a name="to-specify-windows-credentials"></a><span data-ttu-id="72965-135">Windows 자격 증명 지정</span><span class="sxs-lookup"><span data-stu-id="72965-135">To specify Windows Credentials</span></span>  
  
1.  <span data-ttu-id="72965-136">Service App.config 파일에서 `clientCredentialType`을 Windows로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="72965-136">Set `clientCredentialType` to Windows in the Service App.config file:</span></span>  
  
  
  
2.  <span data-ttu-id="72965-137">Visual Basic 6.0을 열고 새 표준 .exe 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="72965-137">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="72965-138">폼에 단추를 추가하고 단추를 두 번 클릭하여 다음 코드를 클릭 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="72965-138">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
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
  
3.  <span data-ttu-id="72965-139">Visual Basic 응용 프로그램을 실행하고 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="72965-139">Run the Visual Basic application and verify the results.</span></span> <span data-ttu-id="72965-140">Visual Basic 응용 프로그램에 메시지 상자가 나타나며 Add(3, 4)를 호출한 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="72965-140">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="72965-141">"domain", "userID" 및 "password"를 유효한 값으로 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72965-141">You must replace "domain", "userID", and "password" with valid values.</span></span>  
  
### <a name="to-specify-an-issue-token"></a><span data-ttu-id="72965-142">발급 토큰 지정</span><span class="sxs-lookup"><span data-stu-id="72965-142">To specify an issue token</span></span>  
  
1.  <span data-ttu-id="72965-143">발급 토큰은 페더레이션 보안을 사용하는 응용 프로그램에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="72965-143">Issue tokens are used only for applications using federated security.</span></span> <span data-ttu-id="72965-144">페더레이션된 보안에 대 한 자세한 내용은 참조 [페더레이션 및 발급 된 토큰](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md) 및 [Federation 샘플](../../../../docs/framework/wcf/samples/federation-sample.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="72965-144">For more information about federated security, see [Federation and Issued Tokens](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md) and [Federation Sample](../../../../docs/framework/wcf/samples/federation-sample.md).</span></span>  
  
     <span data-ttu-id="72965-145">다음 Visual Basic 코드 예제에서는 <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29> 메서드를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="72965-145">The following Visual Basic code example illustrates how to call the <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29> method:</span></span>  
  
    ```  
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/SomeService/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://SomeService.Samples"  
        monString = monString + ", binding=WSHttpBinding_ISomeContract, bindingNamespace=http://SomeService.Samples"  
  
        Set monikerProxy = GetObject(monString)  
    monikerProxy.SetIssuedToken("http://somemachine/sts", "bindingType", "binding")  
    ```  
  
     <span data-ttu-id="72965-146">이 메서드의 매개 변수에 대한 자세한 내용은 <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="72965-146">For more information about the parameters for this method, see <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72965-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="72965-147">See Also</span></span>  
 [<span data-ttu-id="72965-148">페더레이션</span><span class="sxs-lookup"><span data-stu-id="72965-148">Federation</span></span>](../../../../docs/framework/wcf/feature-details/federation.md)  
 [<span data-ttu-id="72965-149">방법: 페더레이션 서비스에서 자격 증명 구성</span><span class="sxs-lookup"><span data-stu-id="72965-149">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [<span data-ttu-id="72965-150">방법: 페더레이션 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="72965-150">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="72965-151">메시지 보안</span><span class="sxs-lookup"><span data-stu-id="72965-151">Message Security</span></span>](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 [<span data-ttu-id="72965-152">바인딩 및 보안</span><span class="sxs-lookup"><span data-stu-id="72965-152">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)
