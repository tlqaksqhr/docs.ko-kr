---
title: '&lt;serviceActivations&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 43461f23476d1c387cec06f9aee893defa634201
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltserviceactivationsgt"></a><span data-ttu-id="73466-102">&lt;serviceActivations&gt;</span><span class="sxs-lookup"><span data-stu-id="73466-102">&lt;serviceActivations&gt;</span></span>
<span data-ttu-id="73466-103">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 서비스 형식에 매핑되는 가상 서비스 활성화 설정을 정의하는 설정을 추가할 수 있는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="73466-103">A configuration element that allows you to add settings that define virtual service activation settings that map to your [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service types.</span></span> <span data-ttu-id="73466-104">.svc 파일 없이도 WAS/IIS에서 호스트되는 서비스를 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73466-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>  
  
 <span data-ttu-id="73466-105">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="73466-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="73466-106">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="73466-106">\<serviceHostingEnvironment></span></span>  
<span data-ttu-id="73466-107">\<serviceActivations ></span><span class="sxs-lookup"><span data-stu-id="73466-107">\<serviceActivations></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73466-108">구문</span><span class="sxs-lookup"><span data-stu-id="73466-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <serviceActivations>  
      <add factory="String"  
           service="String"/>  
   </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73466-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="73466-109">Attributes and Elements</span></span>  
 <span data-ttu-id="73466-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="73466-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73466-111">특성</span><span class="sxs-lookup"><span data-stu-id="73466-111">Attributes</span></span>  
 <span data-ttu-id="73466-112">없음</span><span class="sxs-lookup"><span data-stu-id="73466-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="73466-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="73466-113">Child Elements</span></span>  
  
|<span data-ttu-id="73466-114">요소</span><span class="sxs-lookup"><span data-stu-id="73466-114">Element</span></span>|<span data-ttu-id="73466-115">설명</span><span class="sxs-lookup"><span data-stu-id="73466-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73466-116">\<add></span><span class="sxs-lookup"><span data-stu-id="73466-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-serviceactivations.md)|<span data-ttu-id="73466-117">서비스 응용 프로그램의 활성화를 지정하는 구성 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="73466-117">Adds a configuration element that specifies the activation of a service application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="73466-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="73466-118">Parent Elements</span></span>  
  
|<span data-ttu-id="73466-119">요소</span><span class="sxs-lookup"><span data-stu-id="73466-119">Element</span></span>|<span data-ttu-id="73466-120">설명</span><span class="sxs-lookup"><span data-stu-id="73466-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73466-121">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="73466-121">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="73466-122">특정 전송을 위해 서비스 호스팅 환경에서 인스턴스화하는 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="73466-122">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73466-123">설명</span><span class="sxs-lookup"><span data-stu-id="73466-123">Remarks</span></span>  
 <span data-ttu-id="73466-124">다음 예제에서는 web.config 파일 내에서 활성화 설정을 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="73466-124">The following example shows how to configure activation settings within your web.config file.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <serviceHostingEnvironment>  
      <serviceActivations>  
        <add service="GreetingService"/>  
      </serviceActivations>  
    </serviceHostingEnvironment>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="73466-125">이 구성을 사용하여 .svc 파일을 사용하지 않고도 GreetingService를 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73466-125">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>  
  
 <span data-ttu-id="73466-126">`<serviceHostingEnvironment>`는 응용 프로그램 수준 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="73466-126">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="73466-127">구성을 포함하는 `web.config`를 가상 응용 프로그램의 루트 아래에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73466-127">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="73466-128">또한 `serviceHostingEnvironment`는 machinetoApplication 상속 가능 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="73466-128">In addition, `serviceHostingEnvironment` is a machinetoApplication inheritable section.</span></span> <span data-ttu-id="73466-129">컴퓨터의 루트에 단일 서비스를 등록하는 경우 응용 프로그램의 모든 서비스가 이 서비스를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="73466-129">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>  
  
 <span data-ttu-id="73466-130">구성 기반 활성화는 http 및 http가 아닌 프로토콜을 통한 활성화를 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="73466-130">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="73466-131">이를 위해 relatativeAddress의 확장 즉 .svc, .xoml 또는 .xamlx가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="73466-131">It requires extensions in the relatativeAddress i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="73466-132">직접 작성한 확장을 알려진 buildProviders에 매핑할 수 있으며, 이렇게 하면 모든 확장에서 서비스를 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73466-132">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="73466-133">충돌이 발생하면 `<serviceActivations>` 섹션이 .svc 등록을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="73466-133">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73466-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73466-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>
