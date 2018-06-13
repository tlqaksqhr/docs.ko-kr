---
title: '&lt;netMsmqBinding&gt;의 &lt;message&gt;'
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: 0e947667c414079f24398b401456efd56bf9922c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358559"
---
# <a name="ltmessagegt-of-ltnetmsmqbindinggt"></a><span data-ttu-id="3f8e6-102">&lt;netMsmqBinding&gt;의 &lt;message&gt;</span><span class="sxs-lookup"><span data-stu-id="3f8e6-102">&lt;message&gt; of &lt;netMsmqBinding&gt;</span></span>
<span data-ttu-id="3f8e6-103">이 `netMsmqBinding` 바인딩에 대한 SOAP 메시지 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8e6-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>  
  
 <span data-ttu-id="3f8e6-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3f8e6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3f8e6-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="3f8e6-105">\<bindings></span></span>  
<span data-ttu-id="3f8e6-106">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="3f8e6-106">\<netMsmqBinding></span></span>  
<span data-ttu-id="3f8e6-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="3f8e6-107">\<binding></span></span>  
<span data-ttu-id="3f8e6-108">\<security></span><span class="sxs-lookup"><span data-stu-id="3f8e6-108">\<security></span></span>  
<span data-ttu-id="3f8e6-109">\<message></span><span class="sxs-lookup"><span data-stu-id="3f8e6-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f8e6-110">구문</span><span class="sxs-lookup"><span data-stu-id="3f8e6-110">Syntax</span></span>  
  
```xml  
<netMsmqBinding>  
    <binding>  
      <security>  
         <message   
                      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />  
    </security>  
</netMsmqBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f8e6-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3f8e6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3f8e6-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8e6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f8e6-113">특성</span><span class="sxs-lookup"><span data-stu-id="3f8e6-113">Attributes</span></span>  
  
|<span data-ttu-id="3f8e6-114">특성</span><span class="sxs-lookup"><span data-stu-id="3f8e6-114">Attribute</span></span>|<span data-ttu-id="3f8e6-115">설명</span><span class="sxs-lookup"><span data-stu-id="3f8e6-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3f8e6-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="3f8e6-116">algorithmSuite</span></span>|<span data-ttu-id="3f8e6-117">MSMQ 전송을 통해 전송되는 메시지에 메시지 기반 보안을 적용하는 데 사용되는 메시지 암호화 및 키 랩 알고리즘을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8e6-117">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="3f8e6-118">기본값은 `Aes256`입니다.</span><span class="sxs-lookup"><span data-stu-id="3f8e6-118">The default value is `Aes256`.</span></span> <span data-ttu-id="3f8e6-119">이 특성은 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3f8e6-119">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|  
|<span data-ttu-id="3f8e6-120">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="3f8e6-120">clientCredentialType</span></span>|<span data-ttu-id="3f8e6-121">MSMQ 전송을 통해 전송되는 메시지에 대해 클라이언트 인증을 수행할 때 사용되는 자격 증명의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8e6-121">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="3f8e6-122">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8e6-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3f8e6-123">-None: 따라서 서비스와 익명 클라이언트가 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8e6-123">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="3f8e6-124">서비스와 클라이언트 모두 자격 증명이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f8e6-124">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="3f8e6-125">-Windows:이 통해 될 Windows 자격 증명의 인증 된 컨텍스트에서 SOAP 교환이.</span><span class="sxs-lookup"><span data-stu-id="3f8e6-125">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="3f8e6-126">이 설정은 항상 Kerberos 기반 인증을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8e6-126">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="3f8e6-127">-UserName:이 통해 요구 하는 서비스에서 UserName 자격 증명을 사용 하 여 클라이언트를 인증 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8e6-127">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="3f8e6-128">자격 증명이 예에서 사용 하 여 지정 해야 합니다는 `clientCredentials` 동작 **주의:** Windows Communication Foundation (WCF)는 암호 다이제스트 또는 파생 된 키 및 암호를 사용 하 여 이러한 키에 대 한 보내는 지원 하지 않습니다 메시지 보안입니다.</span><span class="sxs-lookup"><span data-stu-id="3f8e6-128">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="3f8e6-129">따라서 WCF UserName 자격 증명을 사용 하는 경우 교환에 보안을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8e6-129">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="3f8e6-130">이 모드에서는 `clientCredential` 동작 및 `serviceCertificate`를 사용하여 클라이언트에 서비스 인증서를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8e6-130">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="3f8e6-131">-인증서:이 통해 서비스 요구할 수 있는 인증서를 사용 하 여 클라이언트 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="3f8e6-131">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="3f8e6-132">이 경우 `clientCredentials` 동작을 사용하여 클라이언트 자격 증명을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8e6-132">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="3f8e6-133">이 경우 `clientCredentials`를 지정하여 `serviceCertificate` 동작을 통해 서비스 자격 증명을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8e6-133">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="3f8e6-134">-CardSpace: 이렇게 하면 요구 하는 서비스에서 CardSpace를 사용 하 여 클라이언트를 인증 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8e6-134">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="3f8e6-135">`serviceCertiifcate` 동작에 `clientCredential`가 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8e6-135">The `serviceCertiifcate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="3f8e6-136">기본값은 `Windows`입니다.</span><span class="sxs-lookup"><span data-stu-id="3f8e6-136">The default value is `Windows`.</span></span> <span data-ttu-id="3f8e6-137">이 특성은 <xref:System.ServiceModel.MessageCredentialType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3f8e6-137">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3f8e6-138">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3f8e6-138">Child Elements</span></span>  
 <span data-ttu-id="3f8e6-139">없음</span><span class="sxs-lookup"><span data-stu-id="3f8e6-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3f8e6-140">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3f8e6-140">Parent Elements</span></span>  
  
|<span data-ttu-id="3f8e6-141">요소</span><span class="sxs-lookup"><span data-stu-id="3f8e6-141">Element</span></span>|<span data-ttu-id="3f8e6-142">설명</span><span class="sxs-lookup"><span data-stu-id="3f8e6-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3f8e6-143">\<security></span><span class="sxs-lookup"><span data-stu-id="3f8e6-143">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="3f8e6-144">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3f8e6-144">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3f8e6-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f8e6-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>  
 <xref:System.ServiceModel.MessageSecurityOverMsmq>  
 [<span data-ttu-id="3f8e6-146">WCF의 큐</span><span class="sxs-lookup"><span data-stu-id="3f8e6-146">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="3f8e6-147">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="3f8e6-147">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="3f8e6-148">바인딩</span><span class="sxs-lookup"><span data-stu-id="3f8e6-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="3f8e6-149">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="3f8e6-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="3f8e6-150">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="3f8e6-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="3f8e6-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="3f8e6-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
