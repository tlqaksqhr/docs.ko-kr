---
title: "&lt;appDomainManagerType&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 56d68efe176540ba82ec7b86f35678905ebc970b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltappdomainmanagertypegt-element"></a><span data-ttu-id="2d9ac-102">&lt;appDomainManagerType&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="2d9ac-102">&lt;appDomainManagerType&gt; Element</span></span>
<span data-ttu-id="2d9ac-103">기본 응용 프로그램 도메인용 응용 프로그램 도메인 관리자로 사용되는 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d9ac-103">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
 <span data-ttu-id="2d9ac-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2d9ac-104">\<configuration></span></span>  
<span data-ttu-id="2d9ac-105">\<런타임 ></span><span class="sxs-lookup"><span data-stu-id="2d9ac-105">\<runtime></span></span>  
<span data-ttu-id="2d9ac-106">\<appDomainManagerType ></span><span class="sxs-lookup"><span data-stu-id="2d9ac-106">\<appDomainManagerType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d9ac-107">구문</span><span class="sxs-lookup"><span data-stu-id="2d9ac-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d9ac-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2d9ac-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2d9ac-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2d9ac-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d9ac-110">특성</span><span class="sxs-lookup"><span data-stu-id="2d9ac-110">Attributes</span></span>  
  
|<span data-ttu-id="2d9ac-111">특성</span><span class="sxs-lookup"><span data-stu-id="2d9ac-111">Attribute</span></span>|<span data-ttu-id="2d9ac-112">설명</span><span class="sxs-lookup"><span data-stu-id="2d9ac-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="2d9ac-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9ac-113">Required attribute.</span></span> <span data-ttu-id="2d9ac-114">프로세스에서 기본 응용 프로그램 도메인에 대 한 응용 프로그램 도메인 관리자 역할을 하는 네임 스페이스를 포함 하는 형식의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d9ac-114">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2d9ac-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2d9ac-115">Child Elements</span></span>  
 <span data-ttu-id="2d9ac-116">없음</span><span class="sxs-lookup"><span data-stu-id="2d9ac-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2d9ac-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2d9ac-117">Parent Elements</span></span>  
  
|<span data-ttu-id="2d9ac-118">요소</span><span class="sxs-lookup"><span data-stu-id="2d9ac-118">Element</span></span>|<span data-ttu-id="2d9ac-119">설명</span><span class="sxs-lookup"><span data-stu-id="2d9ac-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2d9ac-120">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9ac-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="2d9ac-121">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2d9ac-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d9ac-122">설명</span><span class="sxs-lookup"><span data-stu-id="2d9ac-122">Remarks</span></span>  
 <span data-ttu-id="2d9ac-123">응용 프로그램 도메인 관리자의 종류를 지정 하려면이 두 요소를 지정 해야 하며 [ \<appDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9ac-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="2d9ac-124">이러한 요소 중 하나를 지정 하지 않은 경우 다른 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d9ac-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="2d9ac-125">기본 응용 프로그램 도메인 로드 되 면 <xref:System.TypeLoadException> 지정된 된 형식으로 지정 된 어셈블리에 없는 경우 throw 되는 [ \<appDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) 요소로 및에 프로세스 실패 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d9ac-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="2d9ac-126">기본 응용 프로그램 도메인에 대 한 응용 프로그램 도메인 관리자 유형을 지정 하면 다른 응용 프로그램 도메인은 기본 응용 프로그램 도메인에서 만든 응용 프로그램 도메인 관리자 형식을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d9ac-126">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="2d9ac-127">사용 하 여는 <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> 및 <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> 새 응용 프로그램 도메인에 대 한 다른 응용 프로그램 도메인 관리자 유형을 지정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9ac-127">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="2d9ac-128">응용 프로그램 도메인 관리자 유형을 지정 하는 응용 프로그램이 완전 신뢰 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d9ac-128">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="2d9ac-129">(예를 들어 데스크톱에서 실행 중인 응용 프로그램에 완전 신뢰.) 응용 프로그램에 완전 신뢰가 없는 경우는 <xref:System.TypeLoadException> throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d9ac-129">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="2d9ac-130">유형 및 네임 스페이스의 형식은 동일한 형식에 사용 되는 <xref:System.Type.FullName%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9ac-130">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="2d9ac-131">이 구성 요소는 에서만 사용할 수는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 이상.</span><span class="sxs-lookup"><span data-stu-id="2d9ac-131">This configuration element is available only in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d9ac-132">예제</span><span class="sxs-lookup"><span data-stu-id="2d9ac-132">Example</span></span>  
 <span data-ttu-id="2d9ac-133">다음 예제에서는 프로세스의 기본 응용 프로그램 도메인에 대 한 응용 프로그램 도메인 관리자 임을 지정 하는 방법을 보여 줍니다는 `MyMgr` 에 입력 된 `AdMgrExample` 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9ac-133">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d9ac-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2d9ac-134">See Also</span></span>  
 <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>  
 <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="2d9ac-135">\<appDomainManagerAssembly > 요소</span><span class="sxs-lookup"><span data-stu-id="2d9ac-135">\<appDomainManagerAssembly> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)  
 [<span data-ttu-id="2d9ac-136">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="2d9ac-136">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="2d9ac-137">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="2d9ac-137">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="2d9ac-138">SetAppDomainManagerType 메서드</span><span class="sxs-lookup"><span data-stu-id="2d9ac-138">SetAppDomainManagerType Method</span></span>](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
