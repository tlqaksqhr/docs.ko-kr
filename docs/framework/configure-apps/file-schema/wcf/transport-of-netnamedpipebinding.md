---
title: "&lt;netNamedPipeBinding&gt;의 &lt;transport&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 84811c70f2f3608c10d8886900169f804a8c9b62
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="lttransportgt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="5ec12-102">&lt;netNamedPipeBinding&gt;의 &lt;transport&gt;</span><span class="sxs-lookup"><span data-stu-id="5ec12-102">&lt;transport&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="5ec12-103">명명된 파이프에 대한 전송 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec12-103">Defines the transport security settings for a named pipe.</span></span>  
  
 <span data-ttu-id="5ec12-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5ec12-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5ec12-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="5ec12-105">\<bindings></span></span>  
<span data-ttu-id="5ec12-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="5ec12-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="5ec12-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="5ec12-107">\<binding></span></span>  
<span data-ttu-id="5ec12-108">\<security></span><span class="sxs-lookup"><span data-stu-id="5ec12-108">\<security></span></span>  
<span data-ttu-id="5ec12-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="5ec12-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ec12-110">구문</span><span class="sxs-lookup"><span data-stu-id="5ec12-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>  
   <binding>  
      <security mode="None/Transport">  
            <transport protectionLevel="None/Sign/EncryptAndSign" />  
      </security>  
   </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ec12-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5ec12-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5ec12-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec12-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ec12-113">특성</span><span class="sxs-lookup"><span data-stu-id="5ec12-113">Attributes</span></span>  
  
|<span data-ttu-id="5ec12-114">특성</span><span class="sxs-lookup"><span data-stu-id="5ec12-114">Attribute</span></span>|<span data-ttu-id="5ec12-115">설명</span><span class="sxs-lookup"><span data-stu-id="5ec12-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5ec12-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="5ec12-116">protectionLevel</span></span>|<span data-ttu-id="5ec12-117">명명된 파이프의 보호 수준을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec12-117">Defines protection level of the named pipe.</span></span> <span data-ttu-id="5ec12-118">메시지 서명은 메시지 전송 과정에서 제3자가 메시지를 위조할 수 있는 위험을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="5ec12-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="5ec12-119">암호화는 전송 과정에서 데이터 수준의 개인 정보 보호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec12-119">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="5ec12-120">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5ec12-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5ec12-121">-None: 보호 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ec12-121">-   None: No protection.</span></span><br /><span data-ttu-id="5ec12-122">-Sign: 메시지가 서명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ec12-122">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="5ec12-123">-EncryptAndSign: 메시지가 암호화 되 고 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec12-123">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="5ec12-124">기본값은 EncryptAndSign입니다.</span><span class="sxs-lookup"><span data-stu-id="5ec12-124">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5ec12-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5ec12-125">Child Elements</span></span>  
 <span data-ttu-id="5ec12-126">없음</span><span class="sxs-lookup"><span data-stu-id="5ec12-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5ec12-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5ec12-127">Parent Elements</span></span>  
  
|<span data-ttu-id="5ec12-128">요소</span><span class="sxs-lookup"><span data-stu-id="5ec12-128">Element</span></span>|<span data-ttu-id="5ec12-129">설명</span><span class="sxs-lookup"><span data-stu-id="5ec12-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ec12-130">\<security></span><span class="sxs-lookup"><span data-stu-id="5ec12-130">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="5ec12-131">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec12-131">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ec12-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ec12-132">See Also</span></span>  
 <xref:System.ServiceModel.NamedPipeTransportSecurity>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>  
 [<span data-ttu-id="5ec12-133">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="5ec12-133">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="5ec12-134">바인딩</span><span class="sxs-lookup"><span data-stu-id="5ec12-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="5ec12-135">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="5ec12-135">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="5ec12-136">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="5ec12-136">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="5ec12-137">\<binding></span><span class="sxs-lookup"><span data-stu-id="5ec12-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
