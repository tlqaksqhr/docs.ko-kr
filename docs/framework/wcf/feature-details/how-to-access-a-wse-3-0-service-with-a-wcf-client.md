---
title: '방법: WCF 클라이언트를 사용하여 WSE 3.0 서비스에 액세스'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1f9bcd9b-8f8f-47fa-8f1e-0d47236eb800
ms.openlocfilehash: 54d795858b85bd72a01f619b3603c9927df655d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33492527"
---
# <a name="how-to-access-a-wse-30-service-with-a-wcf-client"></a><span data-ttu-id="0a3a3-102">방법: WCF 클라이언트를 사용하여 WSE 3.0 서비스에 액세스</span><span class="sxs-lookup"><span data-stu-id="0a3a3-102">How to: Access a WSE 3.0 Service with a WCF Client</span></span>
<span data-ttu-id="0a3a3-103">Windows Communication Foundation (WCF) 클라이언트는 Microsoft.NET 서비스에 대 한 유선 수준으로 호환와 향상 된 기능 WSE (Web Services) 3.0는 2004 년 8 월 버전의 Ws-addressing 사양 사용 하도록 WCF 클라이언트를 구성 하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-103">Windows Communication Foundation (WCF) clients are wire-level compatible with Web Services Enhancements (WSE) 3.0 for Microsoft .NET services when WCF clients are configured to use the August 2004 version of the WS-Addressing specification.</span></span> <span data-ttu-id="0a3a3-104">그러나 WSE 3.0 서비스 지원 하지 않습니다 메타 데이터 교환 (MEX) 프로토콜은 지금 사용 하는 경우는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) WCF 클라이언트 클래스를 만들려면 보안 설정이 적용 되지 않습니다을 생성 된 WCF 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-104">However, WSE 3.0 services do not support the metadata exchange (MEX) protocol, so when you use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to create a WCF client class, the security settings are not applied to the generated WCF client.</span></span> <span data-ttu-id="0a3a3-105">보안 설정을 지정 해야 하는 따라서 WCF 클라이언트 생성 된 후 WSE 3.0이 서비스에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-105">Therefore, you must specify the security settings that the WSE 3.0 service requires after the WCF client is generated.</span></span>  
  
 <span data-ttu-id="0a3a3-106">WSE 3.0 서비스와 WCF 클라이언트 간의 상호 운용 가능한 요구 사항 및 WSE 3.0 서비스의 요구 사항을 고려해 야 할 사용자 지정 바인딩을 사용 하 여 이러한 보안 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-106">You can apply these security settings by using a custom binding to take into account the WSE 3.0 service's requirements and the interoperable requirements between a WSE 3.0 service and a WCF client.</span></span> <span data-ttu-id="0a3a3-107">이러한 상호 운용성 요구 사항에는 앞에서 말한 August 2004 WS-Addressing 사양 및 WSE 3.0의 <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt> 기본 메시지 보호를 사용하는 것이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-107">These interoperability requirements include the aforementioned use of the August 2004 WS-Addressing specification and the  WSE 3.0default message protection of <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>.</span></span> <span data-ttu-id="0a3a3-108">WCF에 대 한 기본 메시지 보호는 <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-108">The default message protection for WCF is <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>.</span></span> <span data-ttu-id="0a3a3-109">이 항목에서는 WSE 3.0 서비스와 상호 작용 하는 WCF 바인딩을 만드는 방법을 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-109">This topic details how to create a WCF binding that interoperates with a WSE 3.0 service.</span></span> <span data-ttu-id="0a3a3-110">WCF에서는이 바인딩을 통합 하는 샘플도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-110">WCF also provides a sample that incorporates this binding.</span></span> <span data-ttu-id="0a3a3-111">이 샘플에 대 한 자세한 내용은 참조 [ASMX 웹 서비스와의 상호 운용](../../../../docs/framework/wcf/samples/interoperating-with-asmx-web-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-111">For more information about this sample, see [Interoperating with ASMX Web Services](../../../../docs/framework/wcf/samples/interoperating-with-asmx-web-services.md).</span></span>  
  
### <a name="to-access-a-wse-30-web-service-with-a-wcf-client"></a><span data-ttu-id="0a3a3-112">WCF 클라이언트를 사용하여 WSE 3.0 웹 서비스에 액세스하려면</span><span class="sxs-lookup"><span data-stu-id="0a3a3-112">To access a WSE 3.0 Web service with a WCF client</span></span>  
  
1.  <span data-ttu-id="0a3a3-113">실행 된 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) WSE 3.0 웹 서비스에 대 한 WCF 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-113">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to create a WCF client for the WSE 3.0 Web service.</span></span>  
  
     <span data-ttu-id="0a3a3-114">WSE 3.0 웹 서비스에 대 한 WCF 클라이언트 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-114">For a WSE 3.0 Web service, a WCF client is created.</span></span> <span data-ttu-id="0a3a3-115">WSE 3.0이 MEX 프로토콜을 지원하지 않으므로 해당 도구를 사용하여 웹 서비스에 대한 보안 요구 사항을 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-115">Because WSE 3.0 does not support the MEX protocol, you cannot use the tool to retrieve the security requirements for the Web service.</span></span> <span data-ttu-id="0a3a3-116">응용 프로그램 개발자는 해당 클라이언트에 대한 보안 설정을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-116">The application developer must add the security settings for the client.</span></span>  
  
     <span data-ttu-id="0a3a3-117">WCF 클라이언트 만들기에 대 한 자세한 내용은 참조는 [하는 방법: 클라이언트 만들기](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-117">For more information about creating a WCF client, see the [How to: Create a Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
2.  <span data-ttu-id="0a3a3-118">WSE 3.0 웹 서비스와 통신할 수 있는 바인딩을 나타내는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-118">Create a class that represents a binding that can communicate with WSE 3.0 Web services.</span></span>  
  
     <span data-ttu-id="0a3a3-119">다음 클래스의 일부인는 [WSE와의 상호 운용](http://msdn.microsoft.com/library/f6816861-96a0-45f9-8736-8e4e82cd3a41) 샘플:</span><span class="sxs-lookup"><span data-stu-id="0a3a3-119">The following class is part of the [Interoperating with WSE](http://msdn.microsoft.com/library/f6816861-96a0-45f9-8736-8e4e82cd3a41) sample:</span></span>  
  
    1.  <span data-ttu-id="0a3a3-120"><xref:System.ServiceModel.Channels.Binding> 클래스에서 파생되는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-120">Create a class that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         <span data-ttu-id="0a3a3-121">다음 코드 예제에서는 `WseHttpBinding` 클래스로부터 파생되는 <xref:System.ServiceModel.Channels.Binding>이라는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-121">The following code example creates a class named `WseHttpBinding` that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2.  <span data-ttu-id="0a3a3-122">WSE 서비스에서 사용되는 WSE 턴키 어설션, 파생된 키가 필요한지 여부, 보안 세션이 사용되는지 여부, 서명 확인이 필요한지 여부 및 메시지 보호 설정을 지정하는 클래스에 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-122">Add properties to the class that specify the WSE turnkey assertion used by the WSE service, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings.</span></span> <span data-ttu-id="0a3a3-123">WSE 3.0 턴키 어설션이 클라이언트 또는 웹 서비스에 대 한 보안 요구 사항을 지정 하며,-WCF에서 바인딩의 인증 모드와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-123">In WSE 3.0, a turnkey assertion specifies the security requirements for a client or Web service—similar to the authentication mode of a binding in WCF.</span></span>  
  
         <span data-ttu-id="0a3a3-124">다음 코드 예제에서는 WSE 턴키 어설션, 파생된 키가 필요한지 여부, 보안 세션이 사용되는지 여부, 서명 확인이 필요한지 여부 및 메시지 보호 설정을 각각 지정하는 `SecurityAssertion`, `RequireDerivedKeys`, `EstablishSecurityContext` 및 `MessageProtectionOrder` 속성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-124">The following code example defines the `SecurityAssertion`, `RequireDerivedKeys`, `EstablishSecurityContext`, and `MessageProtectionOrder` properties that specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings, respectively.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3.  <span data-ttu-id="0a3a3-125"><xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> 메서드를 재정의하여 바인딩 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-125">Override the <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> method to set the binding properties.</span></span>  
  
         <span data-ttu-id="0a3a3-126">다음 코드 예제에서는 `SecurityAssertion` 및 `MessageProtectionOrder` 속성의 값을 가져옴으로써 전송, 메시지 인코딩, 메시지 보호 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-126">The following code example specifies the transport, message encoding, and message protection settings by getting the values of the `SecurityAssertion` and `MessageProtectionOrder` properties.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3.  <span data-ttu-id="0a3a3-127">클라이언트 응용 프로그램 코드에서 바인딩 속성을 설정하기 위해 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-127">In the client application code, add code to set the binding properties.</span></span>  
  
     <span data-ttu-id="0a3a3-128">다음 코드 예제에서는 WSE 3.0에 정의 된 대로 메시지 보호 및 인증 WCF 클라이언트 사용 해야 하도록 지정 `AnonymousForCertificate` 턴키 보안 어설션 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-128">The following code example specifies that the WCF client must use message protection and authentication as defined by the WSE 3.0 `AnonymousForCertificate` turnkey security assertion.</span></span> <span data-ttu-id="0a3a3-129">또한 보안 세션 및 파생된 키도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-129">Additionally, secure sessions and derived keys are required.</span></span>  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="0a3a3-130">예제</span><span class="sxs-lookup"><span data-stu-id="0a3a3-130">Example</span></span>  
 <span data-ttu-id="0a3a3-131">다음 코드 예제에서는 WSE 3.0 턴키 보안 어설션의 속성에 해당하는 속성을 노출하는 사용자 지정 바인딩을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-131">The following code example defines a custom binding that exposes properties that correspond to the properties of a WSE 3.0 turnkey security assertion.</span></span> <span data-ttu-id="0a3a3-132">이름으로 지정 된 사용자 지정 바인딩을 지 `WseHttpBinding`, 다음 그러면 WSSecurityAnonymous WSE 3.0 QuickStart 샘플과 통신 하는 WCF 클라이언트에 대 한 바인딩 속성을 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a3a3-132">That custom binding, which is named `WseHttpBinding`, is then used to specify the binding properties for a WCF client that communicates with the WSSecurityAnonymous WSE 3.0 QuickStart sample.</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="0a3a3-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a3a3-133">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 [<span data-ttu-id="0a3a3-134">WSE와의 상호 운용</span><span class="sxs-lookup"><span data-stu-id="0a3a3-134">Interoperating with WSE</span></span>](http://msdn.microsoft.com/library/f6816861-96a0-45f9-8736-8e4e82cd3a41)
