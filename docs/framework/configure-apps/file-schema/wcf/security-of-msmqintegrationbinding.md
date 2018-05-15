---
title: '&lt;msmqIntegrationBinding&gt;의 &lt;security&gt;'
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 861942ac3ce84d75be61d7b4125ab0e17c6d86e1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltsecuritygt-of-ltmsmqintegrationbindinggt"></a><span data-ttu-id="13b0d-102">&lt;msmqIntegrationBinding&gt;의 &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="13b0d-102">&lt;security&gt; of &lt;msmqIntegrationBinding&gt;</span></span>
<span data-ttu-id="13b0d-103">MSMQ(메시지 큐) 통합 채널을 위한 전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="13b0d-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
 <span data-ttu-id="13b0d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="13b0d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="13b0d-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="13b0d-105">\<bindings></span></span>  
<span data-ttu-id="13b0d-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="13b0d-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="13b0d-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="13b0d-107">\<binding></span></span>  
<span data-ttu-id="13b0d-108">\<security></span><span class="sxs-lookup"><span data-stu-id="13b0d-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13b0d-109">구문</span><span class="sxs-lookup"><span data-stu-id="13b0d-109">Syntax</span></span>  
  
```xml  
<msmqIntegrationBinding>  
   <binding>   
       <security mode="None/Transport">  
         <transport msmqAuthenticationMode="None/Windows/Certificate"  
            msmqEncryptionAlgorithm="RC4Stream/AES"  
            msmqProtectionLevel="None/Sign/EncryptAndSign"  
            msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
          <message  algorithmSuite="Aes128/Aes192/Aes256/Rsa15Aes128/ Rsa15Aes256/TripleDes"  
                        clientCredentialType="None/Windows/UserName/Certificate/CardSpace"  
            defaultProtectionLevel="None/Sign/EncryptAndSign" />  
       </security>  
   </binding>  
</msmqIntegrationBinding>   
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13b0d-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="13b0d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="13b0d-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="13b0d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13b0d-112">특성</span><span class="sxs-lookup"><span data-stu-id="13b0d-112">Attributes</span></span>  
  
|<span data-ttu-id="13b0d-113">특성</span><span class="sxs-lookup"><span data-stu-id="13b0d-113">Attribute</span></span>|<span data-ttu-id="13b0d-114">설명</span><span class="sxs-lookup"><span data-stu-id="13b0d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="13b0d-115">모드</span><span class="sxs-lookup"><span data-stu-id="13b0d-115">mode</span></span>|<span data-ttu-id="13b0d-116">메시지 큐 통합 채널로 무결성, 기밀성 및 인증을 제어하는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="13b0d-116">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="13b0d-117">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="13b0d-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="13b0d-118">-None: 보안이 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="13b0d-118">-   None: This disables security.</span></span><br /><span data-ttu-id="13b0d-119">-Transport: 보호 및 인증이 전송에 의해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13b0d-119">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="13b0d-120">이는 두 큐 관리자 간의 메시지 보안에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="13b0d-120">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="13b0d-121">응용 프로그램 및 큐 관리자 간에는 제공되는 보안이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13b0d-121">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="13b0d-122">기존 Msmq 응용 프로그램이 이러한 보안 모드 형식과 동일한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="13b0d-122">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="13b0d-123">기본값은 `Transport`입니다.</span><span class="sxs-lookup"><span data-stu-id="13b0d-123">The default value is `Transport`.</span></span> <span data-ttu-id="13b0d-124">이 특성은 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="13b0d-124">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="13b0d-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="13b0d-125">Child Elements</span></span>  
  
|<span data-ttu-id="13b0d-126">요소</span><span class="sxs-lookup"><span data-stu-id="13b0d-126">Element</span></span>|<span data-ttu-id="13b0d-127">설명</span><span class="sxs-lookup"><span data-stu-id="13b0d-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13b0d-128">\<transport></span><span class="sxs-lookup"><span data-stu-id="13b0d-128">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-msmqintegrationbinding.md)|<span data-ttu-id="13b0d-129">메시지 큐 통합 전송을 위한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="13b0d-129">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="13b0d-130">이 요소는 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="13b0d-130">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="13b0d-131">부모 요소</span><span class="sxs-lookup"><span data-stu-id="13b0d-131">Parent Elements</span></span>  
  
|<span data-ttu-id="13b0d-132">요소</span><span class="sxs-lookup"><span data-stu-id="13b0d-132">Element</span></span>|<span data-ttu-id="13b0d-133">설명</span><span class="sxs-lookup"><span data-stu-id="13b0d-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13b0d-134">\<binding></span><span class="sxs-lookup"><span data-stu-id="13b0d-134">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="13b0d-135">바인딩 요소는 [ \<msmqIntegrationBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="13b0d-135">The binding element of the [\<msmqIntegrationBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="13b0d-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="13b0d-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>  
 [<span data-ttu-id="13b0d-137">WCF의 큐</span><span class="sxs-lookup"><span data-stu-id="13b0d-137">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="13b0d-138">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="13b0d-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="13b0d-139">바인딩</span><span class="sxs-lookup"><span data-stu-id="13b0d-139">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="13b0d-140">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="13b0d-140">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="13b0d-141">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="13b0d-141">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="13b0d-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="13b0d-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="13b0d-143">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="13b0d-143">\<msmqIntegrationBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)
