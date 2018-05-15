---
title: '방법: Windows 자격 증명을 사용하여 서비스에 보안 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, security
ms.assetid: d171b5ca-96ef-47ff-800c-c138023cf76e
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 2fa8d753d5fb168c14ee71cbbf6de62e0e4aff9e
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-secure-a-service-with-windows-credentials"></a><span data-ttu-id="9eded-102">방법: Windows 자격 증명을 사용하여 서비스에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="9eded-102">How to: Secure a Service with Windows Credentials</span></span>
<span data-ttu-id="9eded-103">이 항목에서는 Windows 도메인에 있으며 동일한 도메인에 클라이언트에서 호출 하는 Windows Communication Foundation (WCF) 서비스에서 전송 보안을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-103">This topic shows how to enable transport security on a Windows Communication Foundation (WCF) service that resides in a Windows domain and is called by clients in the same domain.</span></span> <span data-ttu-id="9eded-104">이 시나리오에 대 한 자세한 내용은 참조 [Windows 인증과 함께 전송 보안](../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-104">For more information about this scenario, see [Transport Security with Windows Authentication](../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md).</span></span> <span data-ttu-id="9eded-105">샘플 응용 프로그램에 대 한 참조는 [WSHttpBinding](../../../docs/framework/wcf/samples/wshttpbinding.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="9eded-105">For a sample application, see the [WSHttpBinding](../../../docs/framework/wcf/samples/wshttpbinding.md) sample.</span></span>  
  
 <span data-ttu-id="9eded-106">이 항목에서는 사용자의 기존 계약 인터페이스 및 구현이 이미 정의되어 있다고 가정하고 여기에 더 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-106">This topic assumes you have an existing contract interface and implementation already defined, and adds on to that.</span></span> <span data-ttu-id="9eded-107">사용자는 기존 서비스 및 클라이언트를 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-107">You can also modify an existing service and client.</span></span>  
  
 <span data-ttu-id="9eded-108">Windows 자격 증명을 사용하여 코드로 완전하게 서비스의 보안을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-108">You can secure a service with Windows credentials completely in code.</span></span> <span data-ttu-id="9eded-109">또는 구성 파일을 사용하여 일부 코드를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-109">Alternatively, you can omit some of the code by using a configuration file.</span></span> <span data-ttu-id="9eded-110">이 항목에서는 이 두 방법을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-110">This topic shows both ways.</span></span> <span data-ttu-id="9eded-111">그러나 실제로는 이 두 방법 중 하나만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-111">Be sure you only use one of the ways, not both.</span></span>  
  
 <span data-ttu-id="9eded-112">처음 세 개의 프로시저에서는 코드를 사용하여 서비스의 보안을 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-112">The first three procedures show how to secure the service using code.</span></span> <span data-ttu-id="9eded-113">네 번째 및 다섯 번째 프로시저에서는 구성 파일을 사용하여 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-113">The fourth and fifth procedure shows how to do it with a configuration file.</span></span>  
  
## <a name="using-code"></a><span data-ttu-id="9eded-114">코드 사용</span><span class="sxs-lookup"><span data-stu-id="9eded-114">Using Code</span></span>  
 <span data-ttu-id="9eded-115">서비스 및 클라이언트에 대한 전체 코드는 이 항목 끝부분의 예제 단원에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-115">The complete code for the service and the client is in the Example section at the end of this topic.</span></span>  
  
 <span data-ttu-id="9eded-116">첫 번째 프로시저에서는 코드로 <xref:System.ServiceModel.WSHttpBinding> 클래스를 만들고 구성하는 과정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-116">The first procedure walks through creating and configuring a <xref:System.ServiceModel.WSHttpBinding> class in code.</span></span> <span data-ttu-id="9eded-117">바인딩은 HTTP 전송을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-117">The binding uses the HTTP transport.</span></span> <span data-ttu-id="9eded-118">클라이언트에도 동일한 바인딩이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-118">The same binding is used on the client.</span></span>  
  
#### <a name="to-create-a-wshttpbinding-that-uses-windows-credentials-and-message-security"></a><span data-ttu-id="9eded-119">Windows 자격 증명과 메시지 보안을 사용하는 WSHttpBinding을 만들려면</span><span class="sxs-lookup"><span data-stu-id="9eded-119">To create a WSHttpBinding that uses Windows credentials and message security</span></span>  
  
1.  <span data-ttu-id="9eded-120">이 프로시저 코드는 예제 단원의 서비스 코드에 있는 `Run`클래스에 대한 `Test` 메서드의 시작 부분에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-120">This procedure's code is inserted at the beginning of the `Run` method of the `Test` class in the service code in the Example section.</span></span>  
  
2.  <span data-ttu-id="9eded-121"><xref:System.ServiceModel.WSHttpBinding> 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-121">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class.</span></span>  
  
3.  <span data-ttu-id="9eded-122"><xref:System.ServiceModel.WSHttpSecurity.Mode%2A> 클래스의 <xref:System.ServiceModel.WSHttpSecurity> 속성을 <xref:System.ServiceModel.SecurityMode.Message>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-122">Set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property of the <xref:System.ServiceModel.WSHttpSecurity> class to <xref:System.ServiceModel.SecurityMode.Message>.</span></span>  
  
4.  <span data-ttu-id="9eded-123"><xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> 클래스의 <xref:System.ServiceModel.MessageSecurityOverHttp> 속성을 <xref:System.ServiceModel.MessageCredentialType.Windows>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-123">Set the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property of the <xref:System.ServiceModel.MessageSecurityOverHttp> class to <xref:System.ServiceModel.MessageCredentialType.Windows>.</span></span>  
  
5.  <span data-ttu-id="9eded-124">이 프로시저에 대한 코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-124">The code for this procedure is as follows:</span></span>  
  
     [!code-csharp[c_SecureWindowsService#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#1)]
     [!code-vb[c_SecureWindowsService#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsservice/vb/secureservice.vb#1)]  
  
### <a name="using-the-binding-in-a-service"></a><span data-ttu-id="9eded-125">서비스에 바인딩 사용</span><span class="sxs-lookup"><span data-stu-id="9eded-125">Using the Binding in a Service</span></span>  
 <span data-ttu-id="9eded-126">이는 두 번째 프로시저로, 자체 호스트된 서비스에 바인딩을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-126">This is the second procedure, which shows how to use the binding in a self-hosted service.</span></span> <span data-ttu-id="9eded-127">서비스를 호스트 하는 방법에 대 한 자세한 내용은 참조 [호스팅 서비스](../../../docs/framework/wcf/hosting-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-127">For more information about hosting services see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
##### <a name="to-use-a-binding-in-a-service"></a><span data-ttu-id="9eded-128">서비스에 바인딩을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="9eded-128">To use a binding in a service</span></span>  
  
1.  <span data-ttu-id="9eded-129">앞의 프로시저 코드 뒤에 이 프로시저 코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-129">Insert this procedure's code after the code from the preceding procedure.</span></span>  
  
2.  <span data-ttu-id="9eded-130"><xref:System.Type>이라는 `contractType` 변수를 만들어 인터페이스(`ICalculator`)의 형식을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-130">Create a <xref:System.Type> variable named `contractType` and assign it the type of the interface (`ICalculator`).</span></span> <span data-ttu-id="9eded-131">Visual Basic을 사용 하는 경우 사용 된 `GetType` C#을 사용 하 여 사용 하는 경우 현재 연산자는 `typeof` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-131">When using Visual Basic, use the `GetType` operator; when using C#, use the `typeof` keyword.</span></span>  
  
3.  <span data-ttu-id="9eded-132">`Type`이라는 두 번째 `serviceType` 변수를 만들어 구현된 계약(`Calculator`)의 형식을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-132">Create a second `Type` variable named `serviceType` and assign it the type of the implemented contract (`Calculator`).</span></span>  
  
4.  <span data-ttu-id="9eded-133">서비스의 기본 주소를 사용하여 <xref:System.Uri>라는 `baseAddress` 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-133">Create an instance of the <xref:System.Uri> class named `baseAddress` with the base address of the service.</span></span> <span data-ttu-id="9eded-134">기본 주소에는 전송과 일치하는 체계가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-134">The base address must have a scheme that matches the transport.</span></span> <span data-ttu-id="9eded-135">이 경우 전송 체계는 HTTP, 작성과 주소는 특수 식별자 URI (Uniform Resource) "localhost" 및 포트 번호 (8036)와 함께 기본 끝점 주소가 ("serviceModelSamples /): http://localhost:8036/serviceModelSamples/합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-135">In this case, the transport scheme is HTTP, and the address includes the special Uniform Resource Identifier (URI) "localhost" and a port number (8036) as well as a base endpoint address ("serviceModelSamples/): http://localhost:8036/serviceModelSamples/.</span></span>  
  
5.  <span data-ttu-id="9eded-136"><xref:System.ServiceModel.ServiceHost> 및 `serviceType` 변수를 사용하여 `baseAddress` 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-136">Create an instance of the <xref:System.ServiceModel.ServiceHost> class with the `serviceType` and `baseAddress` variables.</span></span>  
  
6.  <span data-ttu-id="9eded-137">`contractType`, 바인딩 및 끝점 이름(secureCalculator)을 사용하여 끝점을 서비스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-137">Add an endpoint to the service using the `contractType`, binding, and an endpoint name (secureCalculator).</span></span> <span data-ttu-id="9eded-138">클라이언트는 서비스에 대한 호출을 시작할 때 기본 주소와 끝점 이름을 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-138">A client must concatenate the base address and the endpoint name when initiating a call to the service.</span></span>  
  
7.  <span data-ttu-id="9eded-139"><xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> 메서드를 호출하여 서비스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-139">Call the <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> method to start the service.</span></span> <span data-ttu-id="9eded-140">이 프로시저에 대한 코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-140">The code for this procedure is shown here:</span></span>  
  
     [!code-csharp[c_SecureWindowsService#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#2)]
     [!code-vb[c_SecureWindowsService#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsservice/vb/secureservice.vb#2)]  
  
### <a name="using-the-binding-in-a-client"></a><span data-ttu-id="9eded-141">클라이언트에 바인딩 사용</span><span class="sxs-lookup"><span data-stu-id="9eded-141">Using the Binding in a Client</span></span>  
 <span data-ttu-id="9eded-142">이 프로시저에서는 서비스와 통신하는 프록시를 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-142">This procedure shows how to generate a proxy that communicates with the service.</span></span> <span data-ttu-id="9eded-143">프록시 사용 하 여 생성 되는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 프록시를 만들려면 서비스 메타 데이터를 사용 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-143">The proxy is generated with the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) which uses the service metadata to create the proxy.</span></span>  
  
 <span data-ttu-id="9eded-144">또한 이 프로시저에서는 서비스와 통신하는 <xref:System.ServiceModel.WSHttpBinding> 클래스의 인스턴스를 만든 다음 서비스를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-144">This procedure also creates an instance of the <xref:System.ServiceModel.WSHttpBinding> class to communicate with the service, and then calls the service.</span></span>  
  
 <span data-ttu-id="9eded-145">이 예제에서는 코드만 사용하여 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-145">This example uses only code to create the client.</span></span> <span data-ttu-id="9eded-146">또는 이 프로시저 다음의 단원에 나오는 구성 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-146">As an alternative, you can use a configuration file, which is shown in the section following this procedure.</span></span>  
  
##### <a name="to-use-a-binding-in-a-client-with-code"></a><span data-ttu-id="9eded-147">코드를 통해 클라이언트에 바인딩을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="9eded-147">To use a binding in a client with code</span></span>  
  
1.  <span data-ttu-id="9eded-148">SvcUtil.exe 도구를 사용하여 서비스의 메타데이터에서 프록시 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-148">Use the SvcUtil.exe tool to generate the proxy code from the service's metadata.</span></span> <span data-ttu-id="9eded-149">자세한 내용은 참조 [하는 방법: 클라이언트 만들기](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-149">For more information, see [How to: Create a Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span> <span data-ttu-id="9eded-150">생성된 된 프록시 코드에서 상속 된 <xref:System.ServiceModel.ClientBase%601> 모든 클라이언트에 필요한 생성자, 메서드 및 WCF 서비스와 통신 하는 속성을 보장 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-150">The generated proxy code inherits from the <xref:System.ServiceModel.ClientBase%601> class, which ensures that every client has the necessary constructors, methods, and properties to communicate with a WCF service.</span></span> <span data-ttu-id="9eded-151">이 예제에서 생성된 코드에는 `CalculatorClient` 인터페이스를 구현하는 `ICalculator` 클래스가 포함되어 서비스 코드와의 호환성을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-151">In this example, the generated code includes the `CalculatorClient` class, which implements the `ICalculator` interface, enabling compatibility with the service code.</span></span>  
  
2.  <span data-ttu-id="9eded-152">이 프로시저의 코드는 클라이언트 프로그램에 대한 `Main` 메서드의 시작 부분에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-152">This procedure's code is inserted at the beginning of the `Main` method of the client program.</span></span>  
  
3.  <span data-ttu-id="9eded-153"><xref:System.ServiceModel.WSHttpBinding> 클래스의 인스턴스를 만들고 보안 모드를 `Message`로, 클라이언트 자격 증명 형식을 `Windows`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-153">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class and set its security mode to `Message` and its client credential type to `Windows`.</span></span> <span data-ttu-id="9eded-154">이 예제에서는 변수 이름을 `clientBinding`으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-154">The example names the variable `clientBinding`.</span></span>  
  
4.  <span data-ttu-id="9eded-155"><xref:System.ServiceModel.EndpointAddress>라는 `serviceAddress` 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-155">Create an instance of the <xref:System.ServiceModel.EndpointAddress> class named `serviceAddress`.</span></span> <span data-ttu-id="9eded-156">기본 주소를 끝점 이름과 연결하여 인스턴스를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-156">Initialize the instance with the base address concatenated with the endpoint name.</span></span>  
  
5.  <span data-ttu-id="9eded-157">`serviceAddress` 및 `clientBinding` 변수를 사용하여 생성된 클라이언트 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-157">Create an instance of the generated client class with the `serviceAddress` and the `clientBinding` variables.</span></span>  
  
6.  <span data-ttu-id="9eded-158">다음 코드와 같이 <xref:System.ServiceModel.ClientBase%601.Open%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-158">Call the <xref:System.ServiceModel.ClientBase%601.Open%2A> method, as shown in the following code.</span></span>  
  
7.  <span data-ttu-id="9eded-159">서비스를 호출하고 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-159">Call the service and display the results.</span></span>  
  
     [!code-csharp[c_secureWindowsClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#1)]
     [!code-vb[c_secureWindowsClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsclient/vb/secureclient.vb#1)]  
  
## <a name="using-the-configuration-file"></a><span data-ttu-id="9eded-160">구성 파일 사용</span><span class="sxs-lookup"><span data-stu-id="9eded-160">Using the Configuration File</span></span>  
 <span data-ttu-id="9eded-161">프로시저 코드를 사용하여 바인딩을 만드는 대신 구성 파일의 바인딩 섹션에 대해 표시된 다음 코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-161">Instead of creating the binding with procedural code, you can use the following code shown for the bindings section of the configuration file.</span></span>  
  
 <span data-ttu-id="9eded-162">정의 된 서비스 아직 없는 경우 참조 [서비스 디자인 및 구현](../../../docs/framework/wcf/designing-and-implementing-services.md), 및 [서비스 구성](../../../docs/framework/wcf/configuring-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-162">If you do not already have a service defined, see [Designing and Implementing Services](../../../docs/framework/wcf/designing-and-implementing-services.md), and [Configuring Services](../../../docs/framework/wcf/configuring-services.md).</span></span>  
  
 <span data-ttu-id="9eded-163">**참고** 서비스와 클라이언트 구성 파일에서이 구성 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-163">**Note** This configuration code is used in both the service and client configuration files.</span></span>  
  
#### <a name="to-enable-transfer-security-on-a-service-in-a-windows-domain-using-configuration"></a><span data-ttu-id="9eded-164">구성을 사용하여 Windows 도메인의 서비스에서 전송 보안을 활성화하려면</span><span class="sxs-lookup"><span data-stu-id="9eded-164">To enable transfer security on a service in a Windows domain using configuration</span></span>  
  
1.  <span data-ttu-id="9eded-165">추가 [ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 요소는 [ \<바인딩 >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 구성 파일의 요소 섹션.</span><span class="sxs-lookup"><span data-stu-id="9eded-165">Add a [\<wsHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element to the [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element section of the configuration file.</span></span>  
  
2.  <span data-ttu-id="9eded-166"><`binding`> 요소를 <`WSHttpBinding`> 요소에 추가하고 `configurationName` 특성을 응용 프로그램에 적합한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-166">Add a <`binding`> element to the <`WSHttpBinding`> element and set the `configurationName` attribute to a value appropriate to your application.</span></span>  
  
3.  <span data-ttu-id="9eded-167"><`security`> 요소를 추가하고 `mode` 특성을 Message로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-167">Add a <`security`> element and set the `mode` attribute to Message.</span></span>  
  
4.  <span data-ttu-id="9eded-168"><`message`> 요소를 추가하고 `clientCredentialType` 특성을 Windows로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-168">Add a <`message`> element and set the `clientCredentialType` attribute to Windows.</span></span>  
  
5.  <span data-ttu-id="9eded-169">서비스의 구성 파일에서 `<bindings>` 섹션을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-169">In the service's configuration file, replace the `<bindings>` section with the following code.</span></span> <span data-ttu-id="9eded-170">서비스 구성 파일을 아직 없는 경우 참조 [구성 서비스 및 클라이언트에 대 한 바인딩을 사용 하 여](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-170">If you do not already have a service configuration file, see [Using Bindings to Configure Services and Clients](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).</span></span>  
  
    ```xml  
    <bindings>  
      <wsHttpBinding>  
       <binding name = "wsHttpBinding_Calculator">  
         <security mode="Message">  
           <message clientCredentialType="Windows"/>  
         </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    ```  
  
### <a name="using-the-binding-in-a-client"></a><span data-ttu-id="9eded-171">클라이언트에 바인딩 사용</span><span class="sxs-lookup"><span data-stu-id="9eded-171">Using the Binding in a Client</span></span>  
 <span data-ttu-id="9eded-172">이 프로시저에서는 두 파일인 서비스와 통신하는 프록시 및 구성 파일을 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-172">This procedure shows how to generate two files: a proxy that communicates with the service and a configuration file.</span></span> <span data-ttu-id="9eded-173">또한 클라이언트에 사용된 세 번째 파일인 클라이언트 프로그램에 대한 변경 내용에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-173">It also describes changes to the client program, which is the third file used on the client.</span></span>  
  
##### <a name="to-use-a-binding-in-a-client-with-configuration"></a><span data-ttu-id="9eded-174">구성을 통해 클라이언트에 바인딩을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="9eded-174">To use a binding in a client with configuration</span></span>  
  
1.  <span data-ttu-id="9eded-175">SvcUtil.exe 도구를 사용하여 서비스의 메타데이터에서 프록시 코드 및 구성 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-175">Use the SvcUtil.exe tool to generate the proxy code and configuration file from the service's metadata.</span></span> <span data-ttu-id="9eded-176">자세한 내용은 참조 [하는 방법: 클라이언트 만들기](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-176">For more information, see [How to: Create a Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
2.  <span data-ttu-id="9eded-177">대체는 [ \<바인딩 >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 구성 코드는 이전 섹션에서 사용 하 여 생성 된 구성 파일의 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-177">Replace the [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) section of the generated configuration file with the configuration code from the preceding section.</span></span>  
  
3.  <span data-ttu-id="9eded-178">프로시저 코드는 클라이언트 프로그램에 대한 `Main` 메서드의 시작 부분에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-178">Procedural code is inserted at the beginning of the `Main` method of the client program.</span></span>  
  
4.  <span data-ttu-id="9eded-179">바인딩 이름을 구성 파일에 입력 매개 변수로 전달하는 생성된 클라이언트 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-179">Create an instance of the generated client class passing the name of the binding in the configuration file as an input parameter.</span></span>  
  
5.  <span data-ttu-id="9eded-180">다음 코드와 같이 <xref:System.ServiceModel.ClientBase%601.Open%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-180">Call the <xref:System.ServiceModel.ClientBase%601.Open%2A> method, as shown in the following code.</span></span>  
  
6.  <span data-ttu-id="9eded-181">서비스를 호출하고 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9eded-181">Call the service and display the results.</span></span>  
  
     [!code-csharp[c_secureWindowsClient#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#2)]  
  
## <a name="example"></a><span data-ttu-id="9eded-182">예제</span><span class="sxs-lookup"><span data-stu-id="9eded-182">Example</span></span>  
 [!code-csharp[c_SecureWindowsService#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#0)]  
  
 [!code-csharp[c_SecureWindowsClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#0)] 
 [!code-vb[c_SecureWindowsClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsclient/vb/secureclient.vb#0)]      
  
## <a name="see-also"></a><span data-ttu-id="9eded-183">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9eded-183">See Also</span></span>  
 <xref:System.ServiceModel.WSHttpBinding>  
 [<span data-ttu-id="9eded-184">ServiceModel Metadata 유틸리티 도구(Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="9eded-184">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [<span data-ttu-id="9eded-185">방법: 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="9eded-185">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [<span data-ttu-id="9eded-186">서비스에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="9eded-186">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)  
 [<span data-ttu-id="9eded-187">보안 개요</span><span class="sxs-lookup"><span data-stu-id="9eded-187">Security Overview</span></span>](../../../docs/framework/wcf/feature-details/security-overview.md)
