---
title: "&lt;httpDigest&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 22c89aa69ea686274bb232eb04eec930ffc5b51d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="lthttpdigestgt-element"></a><span data-ttu-id="0ff6f-102">&lt;httpDigest&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="0ff6f-102">&lt;httpDigest&gt; Element</span></span>
<span data-ttu-id="0ff6f-103">서비스에게 클라이언트를 인증하는 데 사용되는 다이제스트 형식 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff6f-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
 <span data-ttu-id="0ff6f-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="0ff6f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0ff6f-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="0ff6f-105">\<behaviors></span></span>  
<span data-ttu-id="0ff6f-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="0ff6f-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="0ff6f-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="0ff6f-107">\<behavior></span></span>  
<span data-ttu-id="0ff6f-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="0ff6f-108">\<clientCredentials></span></span>  
<span data-ttu-id="0ff6f-109">\<httpDigest ></span><span class="sxs-lookup"><span data-stu-id="0ff6f-109">\<httpDigest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ff6f-110">구문</span><span class="sxs-lookup"><span data-stu-id="0ff6f-110">Syntax</span></span>  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ff6f-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0ff6f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0ff6f-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff6f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ff6f-113">특성</span><span class="sxs-lookup"><span data-stu-id="0ff6f-113">Attributes</span></span>  
  
|<span data-ttu-id="0ff6f-114">특성</span><span class="sxs-lookup"><span data-stu-id="0ff6f-114">Attribute</span></span>|<span data-ttu-id="0ff6f-115">설명</span><span class="sxs-lookup"><span data-stu-id="0ff6f-115">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="0ff6f-116">클라이언트가 서버에 전달하는 가장 기본 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff6f-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="0ff6f-117">클라이언트에서 선택하는 가장 모드는 서버에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff6f-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="0ff6f-118">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff6f-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0ff6f-119">-식별: 서버 id 및 클라이언트의 권한을 가져올 수 있지만 클라이언트를 가장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff6f-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="0ff6f-120">-가장: 서버는 로컬 시스템에서 클라이언트의 보안 컨텍스트를 가장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff6f-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="0ff6f-121">-Delegation: 서버는 원격 시스템에서 클라이언트의 보안 컨텍스트를 가장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff6f-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="0ff6f-122">아닌 익명이: 서버 가장 없거나 클라이언트를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff6f-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="0ff6f-123">-None: 가장 수준이 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff6f-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="0ff6f-124">기본값은 Identification입니다.</span><span class="sxs-lookup"><span data-stu-id="0ff6f-124">The default is Identification.</span></span> <span data-ttu-id="0ff6f-125">이 특성은 <xref:System.Security.Principal.TokenImpersonationLevel> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0ff6f-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0ff6f-126">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0ff6f-126">Child Elements</span></span>  
 <span data-ttu-id="0ff6f-127">없음</span><span class="sxs-lookup"><span data-stu-id="0ff6f-127">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0ff6f-128">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0ff6f-128">Parent Elements</span></span>  
  
|<span data-ttu-id="0ff6f-129">요소</span><span class="sxs-lookup"><span data-stu-id="0ff6f-129">Element</span></span>|<span data-ttu-id="0ff6f-130">설명</span><span class="sxs-lookup"><span data-stu-id="0ff6f-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0ff6f-131">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="0ff6f-131">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="0ff6f-132">클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff6f-132">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ff6f-133">설명</span><span class="sxs-lookup"><span data-stu-id="0ff6f-133">Remarks</span></span>  
 <span data-ttu-id="0ff6f-134">다이제스트는 알고리즘과 입력 집합을 통해 확인되는 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="0ff6f-134">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="0ff6f-135">인증자 및 인증된 사용자는 알고리즘에 동의하고 입력으로 사용된 데이터를 교환합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff6f-135">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="0ff6f-136">클라이언트는 해시를 계산하여 서비스로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="0ff6f-136">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="0ff6f-137">서비스에서도 해시를 계산하여 값을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff6f-137">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="0ff6f-138">값이 일치하면 클라이언트가 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff6f-138">A match validates the client.</span></span>  
  
 <span data-ttu-id="0ff6f-139">이 기능은 Windows 및 IIS(인터넷 정보 서비스)의 Active Directory를 통해 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff6f-139">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)]<span data-ttu-id="0ff6f-140">[다이제스트 인증 IIS 6.0에서에서](http://go.microsoft.com/fwlink/?LinkId=88443)합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff6f-140"> [Digest Authentication in IIS 6.0](http://go.microsoft.com/fwlink/?LinkId=88443).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ff6f-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ff6f-141">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>  
 <xref:System.ServiceModel.Configuration.HttpDigestClientElement>  
 <xref:System.ServiceModel.Security.HttpDigestClientCredential>  
 [<span data-ttu-id="0ff6f-142">보안 동작</span><span class="sxs-lookup"><span data-stu-id="0ff6f-142">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="0ff6f-143">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="0ff6f-143">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="0ff6f-144">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="0ff6f-144">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="0ff6f-145">서비스 및 클라이언트 보안 설정</span><span class="sxs-lookup"><span data-stu-id="0ff6f-145">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
