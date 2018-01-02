---
title: '&lt;allowAccounts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a1716aa77808b2a9f8f3ca903dabf81b21b8f709
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltallowaccountsgt"></a><span data-ttu-id="49551-102">&lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="49551-102">&lt;allowAccounts&gt;</span></span>
<span data-ttu-id="49551-103">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 서비스를 호스트하고 공유 서비스에 대한 연결 액세스 권한이 부여된 프로세스의 사용자 계정을 지정하는 구성 요소 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="49551-103">Contains a collection of configuration elements that specify user accounts for processes that host [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="49551-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="49551-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49551-105">구문</span><span class="sxs-lookup"><span data-stu-id="49551-105">Syntax</span></span>  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="49551-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="49551-106">Attributes and Elements</span></span>  
 <span data-ttu-id="49551-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="49551-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="49551-108">특성</span><span class="sxs-lookup"><span data-stu-id="49551-108">Attributes</span></span>  
 <span data-ttu-id="49551-109">없음</span><span class="sxs-lookup"><span data-stu-id="49551-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="49551-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="49551-110">Child Elements</span></span>  
  
|<span data-ttu-id="49551-111">특성</span><span class="sxs-lookup"><span data-stu-id="49551-111">Attribute</span></span>|<span data-ttu-id="49551-112">설명</span><span class="sxs-lookup"><span data-stu-id="49551-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="49551-113">\<add></span><span class="sxs-lookup"><span data-stu-id="49551-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="49551-114">[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스를 호스트하고 공유 서비스에 대한 연결 액세스 권한이 부여된 프로세스를 수행할 수 있는 사용자 계정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="49551-114">Adds a user account for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="49551-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="49551-115">Parent Elements</span></span>  
  
|<span data-ttu-id="49551-116">요소</span><span class="sxs-lookup"><span data-stu-id="49551-116">Element</span></span>|<span data-ttu-id="49551-117">설명</span><span class="sxs-lookup"><span data-stu-id="49551-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="49551-118">[\<net.pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) 또는 [ \<net.tcp >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="49551-118">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="49551-119">Net Pipe 또는 TCP 공유 서비스의 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="49551-119">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="49551-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49551-120">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
