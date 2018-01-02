---
title: "&lt;allowAccounts&gt;의 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 064c9d438832142e1f761d0d33db528dbe73ef2a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltallowaccountsgt"></a><span data-ttu-id="8ff1f-102">&lt;allowAccounts&gt;의 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="8ff1f-102">&lt;add&gt; of &lt;allowAccounts&gt;</span></span>
<span data-ttu-id="8ff1f-103">[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스를 호스트하고 공유 서비스에 대한 연결 액세스 권한이 부여된 프로세스를 수행할 수 있는 사용자 계정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ff1f-103">Specifies a user account for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="8ff1f-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="8ff1f-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ff1f-105">구문</span><span class="sxs-lookup"><span data-stu-id="8ff1f-105">Syntax</span></span>  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ff1f-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8ff1f-106">Attributes and Elements</span></span>  
 <span data-ttu-id="8ff1f-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8ff1f-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ff1f-108">특성</span><span class="sxs-lookup"><span data-stu-id="8ff1f-108">Attributes</span></span>  
  
|<span data-ttu-id="8ff1f-109">특성</span><span class="sxs-lookup"><span data-stu-id="8ff1f-109">Attribute</span></span>|<span data-ttu-id="8ff1f-110">설명</span><span class="sxs-lookup"><span data-stu-id="8ff1f-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8ff1f-111">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="8ff1f-111">securityIdentifier</span></span>|<span data-ttu-id="8ff1f-112">사용자 계정을 식별하는 데 사용하는 고유 식별자를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8ff1f-112">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="8ff1f-113">반환되는 기본값은 LocalSystem, Administrators, NS, LS 및 IIS_USRS입니다.</span><span class="sxs-lookup"><span data-stu-id="8ff1f-113">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8ff1f-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8ff1f-114">Child Elements</span></span>  
 <span data-ttu-id="8ff1f-115">없음</span><span class="sxs-lookup"><span data-stu-id="8ff1f-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8ff1f-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8ff1f-116">Parent Elements</span></span>  
  
|<span data-ttu-id="8ff1f-117">요소</span><span class="sxs-lookup"><span data-stu-id="8ff1f-117">Element</span></span>|<span data-ttu-id="8ff1f-118">설명</span><span class="sxs-lookup"><span data-stu-id="8ff1f-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ff1f-119">\<allowAccounts ></span><span class="sxs-lookup"><span data-stu-id="8ff1f-119">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="8ff1f-120">`securityIdentifier` 서비스를 호스트하고 공유 서비스에 대한 연결 액세스가 부여된 프로세스의 사용자 계정을 지정하기 위한 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 특성이 포함된 구성 요소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8ff1f-120">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8ff1f-121">예</span><span class="sxs-lookup"><span data-stu-id="8ff1f-121">Example</span></span>  
 <span data-ttu-id="8ff1f-122">다음 구성 예제에서는 사용자 계정에 대한 다섯 가지 기본 식별자를 이 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8ff1f-122">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
```xml  
<allowAccounts>  
   // LocalSystem account  
   <add securityIdentifier="S-1-5-18"/>  
   // LocalService account  
   <add securityIdentifier="S-1-5-19"/>  
   // Administrators account  
   <add securityIdentifier="S-1-5-20"/>  
   // Network Service account  
   <add securityIdentifier="S-1-5-32-544" />  
   // IIS_IUSRS account (Vista only)  
   <add securityIdentifier="S-1-5-32-568"/>  
</allowAccounts>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8ff1f-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ff1f-123">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
