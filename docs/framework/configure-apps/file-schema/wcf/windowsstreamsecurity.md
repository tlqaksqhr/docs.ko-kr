---
title: '&lt;windowsStreamSecurity&gt;'
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: a089a6fb61e8f7fac4116b2280a5c2fe0b703f94
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755112"
---
# <a name="ltwindowsstreamsecuritygt"></a><span data-ttu-id="457eb-102">&lt;windowsStreamSecurity&gt;</span><span class="sxs-lookup"><span data-stu-id="457eb-102">&lt;windowsStreamSecurity&gt;</span></span>
<span data-ttu-id="457eb-103">사용자 지정의 바인딩에 대한 Windows 스트림 보안 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="457eb-103">Specify Windows stream security settings of the custom binding.</span></span>  
  
 <span data-ttu-id="457eb-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="457eb-104">\<system.serviceModel></span></span>  
<span data-ttu-id="457eb-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="457eb-105">\<bindings></span></span>  
<span data-ttu-id="457eb-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="457eb-106">\<customBinding></span></span>  
<span data-ttu-id="457eb-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="457eb-107">\<binding></span></span>  
<span data-ttu-id="457eb-108">\<windowsStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="457eb-108">\<windowsStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="457eb-109">구문</span><span class="sxs-lookup"><span data-stu-id="457eb-109">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="457eb-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="457eb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="457eb-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="457eb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="457eb-112">특성</span><span class="sxs-lookup"><span data-stu-id="457eb-112">Attributes</span></span>  
  
|<span data-ttu-id="457eb-113">특성</span><span class="sxs-lookup"><span data-stu-id="457eb-113">Attribute</span></span>|<span data-ttu-id="457eb-114">설명</span><span class="sxs-lookup"><span data-stu-id="457eb-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="457eb-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="457eb-115">protectionLevel</span></span>|<span data-ttu-id="457eb-116">메시지 보안 수준을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="457eb-116">Defines message-level security.</span></span> <span data-ttu-id="457eb-117">메시지 서명은 메시지 전송 과정에서 제3자가 메시지를 위조할 수 있는 위험을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="457eb-117">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="457eb-118">암호화는 전송 과정에서 데이터 수준의 개인 정보 보호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="457eb-118">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="457eb-119">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="457eb-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="457eb-120">-None: 보호 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="457eb-120">-   None: No protection.</span></span><br /><span data-ttu-id="457eb-121">-Sign: 메시지가 서명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="457eb-121">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="457eb-122">-EncryptAndSign: 메시지가 서명 및 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="457eb-122">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="457eb-123">기본값은 EncryptAndSign입니다.</span><span class="sxs-lookup"><span data-stu-id="457eb-123">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="457eb-124">이 특성은 <xref:System.Net.Security.ProtectionLevel> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="457eb-124">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="457eb-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="457eb-125">Child Elements</span></span>  
 <span data-ttu-id="457eb-126">없음</span><span class="sxs-lookup"><span data-stu-id="457eb-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="457eb-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="457eb-127">Parent Elements</span></span>  
  
|<span data-ttu-id="457eb-128">요소</span><span class="sxs-lookup"><span data-stu-id="457eb-128">Element</span></span>|<span data-ttu-id="457eb-129">설명</span><span class="sxs-lookup"><span data-stu-id="457eb-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="457eb-130">\<binding></span><span class="sxs-lookup"><span data-stu-id="457eb-130">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="457eb-131">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="457eb-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="457eb-132">설명</span><span class="sxs-lookup"><span data-stu-id="457eb-132">Remarks</span></span>  
 <span data-ttu-id="457eb-133">TCP 및 명명된 파이프와 같은 스트림 지향 프로토콜을 사용하는 전송은 스트림 기반 전송 업그레이드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="457eb-133">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="457eb-134">특히 WCF는 보안 업그레이드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="457eb-134">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="457eb-135">이 전송 보안의 구성은 뿐이 구성 요소에 의해 캡슐화 됩니다 [ \<sslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), 구성 및 사용자 지정 바인딩에 추가할 수 있으며</span><span class="sxs-lookup"><span data-stu-id="457eb-135">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="457eb-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="457eb-136">See Also</span></span>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>  
 <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
 [<span data-ttu-id="457eb-137">바인딩</span><span class="sxs-lookup"><span data-stu-id="457eb-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="457eb-138">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="457eb-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="457eb-139">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="457eb-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="457eb-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="457eb-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
