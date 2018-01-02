---
title: "&lt;지우기&gt; authenticationModules (네트워크 설정)에 대 한 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, authenticationModules
- <authenticationModules>, clear element
- <clear> element, authenticationModules
- authenticationModules, clear element
ms.assetid: dc522c45-4a80-4831-8955-f7b68a47edfd
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: b1c27ba6cdae88a36813dcf67ffc386c94403c1f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltcleargt-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="fb4de-102">&lt;지우기&gt; authenticationModules (네트워크 설정)에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="fb4de-102">&lt;clear&gt; Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="fb4de-103">응용 프로그램에서 인증 모듈을 모두 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="fb4de-103">Clears all authentication modules from the application.</span></span>  
  
 <span data-ttu-id="fb4de-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="fb4de-104">\<configuration></span></span>  
<span data-ttu-id="fb4de-105">\<system.net ></span><span class="sxs-lookup"><span data-stu-id="fb4de-105">\<system.net></span></span>  
<span data-ttu-id="fb4de-106">\<authenticationModules ></span><span class="sxs-lookup"><span data-stu-id="fb4de-106">\<authenticationModules></span></span>  
<span data-ttu-id="fb4de-107">\<지우기 ></span><span class="sxs-lookup"><span data-stu-id="fb4de-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb4de-108">구문</span><span class="sxs-lookup"><span data-stu-id="fb4de-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fb4de-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fb4de-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fb4de-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fb4de-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fb4de-111">특성</span><span class="sxs-lookup"><span data-stu-id="fb4de-111">Attributes</span></span>  
 <span data-ttu-id="fb4de-112">없음</span><span class="sxs-lookup"><span data-stu-id="fb4de-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fb4de-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fb4de-113">Child Elements</span></span>  
 <span data-ttu-id="fb4de-114">없음</span><span class="sxs-lookup"><span data-stu-id="fb4de-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fb4de-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fb4de-115">Parent Elements</span></span>  
  
|<span data-ttu-id="fb4de-116">**요소**</span><span class="sxs-lookup"><span data-stu-id="fb4de-116">**Element**</span></span>|<span data-ttu-id="fb4de-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="fb4de-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fb4de-118">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="fb4de-118">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="fb4de-119">네트워크 요청을 인증 하는 데 사용 되는 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb4de-119">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb4de-120">설명</span><span class="sxs-lookup"><span data-stu-id="fb4de-120">Remarks</span></span>  
 <span data-ttu-id="fb4de-121">`clear` 요소 또는 구성 계층 구조의 상위 수준에서 구성 파일에서 이전 정의 된 인증 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb4de-121">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="fb4de-122">구성 파일</span><span class="sxs-lookup"><span data-stu-id="fb4de-122">Configuration Files</span></span>  
 <span data-ttu-id="fb4de-123">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb4de-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb4de-124">예</span><span class="sxs-lookup"><span data-stu-id="fb4de-124">Example</span></span>  
 <span data-ttu-id="fb4de-125">다음 예에서는 모든 구성 된 인증 모듈을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="fb4de-125">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fb4de-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb4de-126">See Also</span></span>  
 <xref:System.Net.IAuthenticationModule>  
 <xref:System.Net.AuthenticationManager>  
 [<span data-ttu-id="fb4de-127">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="fb4de-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
