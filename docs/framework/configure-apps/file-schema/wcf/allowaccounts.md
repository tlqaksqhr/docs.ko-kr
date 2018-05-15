---
title: '&lt;allowAccounts&gt;'
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: bbfe0d5d531cf61c01f95d0e82ce0f894031d6f3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltallowaccountsgt"></a><span data-ttu-id="479c4-102">&lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="479c4-102">&lt;allowAccounts&gt;</span></span>
<span data-ttu-id="479c4-103">해당 호스트 Windows Communication Foundation (WCF) 서비스, 프로세스에 대 한 계정 사용자를 지정 하 고 공유 서비스에 대 한 연결 액세스가 부여 된 하는 구성 요소의 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="479c4-103">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="479c4-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="479c4-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="479c4-105">구문</span><span class="sxs-lookup"><span data-stu-id="479c4-105">Syntax</span></span>  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="479c4-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="479c4-106">Attributes and Elements</span></span>  
 <span data-ttu-id="479c4-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="479c4-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="479c4-108">특성</span><span class="sxs-lookup"><span data-stu-id="479c4-108">Attributes</span></span>  
 <span data-ttu-id="479c4-109">없음</span><span class="sxs-lookup"><span data-stu-id="479c4-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="479c4-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="479c4-110">Child Elements</span></span>  
  
|<span data-ttu-id="479c4-111">특성</span><span class="sxs-lookup"><span data-stu-id="479c4-111">Attribute</span></span>|<span data-ttu-id="479c4-112">설명</span><span class="sxs-lookup"><span data-stu-id="479c4-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="479c4-113">\<add></span><span class="sxs-lookup"><span data-stu-id="479c4-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="479c4-114">[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스를 호스트하고 공유 서비스에 대한 연결 액세스 권한이 부여된 프로세스를 수행할 수 있는 사용자 계정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="479c4-114">Adds a user account for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="479c4-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="479c4-115">Parent Elements</span></span>  
  
|<span data-ttu-id="479c4-116">요소</span><span class="sxs-lookup"><span data-stu-id="479c4-116">Element</span></span>|<span data-ttu-id="479c4-117">설명</span><span class="sxs-lookup"><span data-stu-id="479c4-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="479c4-118">[\<net.pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) 또는 [ \<net.tcp >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="479c4-118">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="479c4-119">Net Pipe 또는 TCP 공유 서비스의 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="479c4-119">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="479c4-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="479c4-120">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
