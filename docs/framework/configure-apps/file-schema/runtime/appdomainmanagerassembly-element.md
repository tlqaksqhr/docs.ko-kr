---
title: "&lt;appDomainManagerAssembly&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0e07b7bd18f19439f64ed8eaef5bda3bad5cef77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltappdomainmanagerassemblygt-element"></a><span data-ttu-id="fa636-102">&lt;appDomainManagerAssembly&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="fa636-102">&lt;appDomainManagerAssembly&gt; Element</span></span>
<span data-ttu-id="fa636-103">프로세스의 기본 응용 프로그램 도메인용 응용 프로그램 도메인 관리자를 제공하는 어셈블리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa636-103">Specifies the assembly that provides the application domain manager for the default application domain in the process.</span></span>  
  
 <span data-ttu-id="fa636-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="fa636-104">\<configuration></span></span>  
<span data-ttu-id="fa636-105">\<런타임 ></span><span class="sxs-lookup"><span data-stu-id="fa636-105">\<runtime></span></span>  
<span data-ttu-id="fa636-106">\<appDomainManagerAssembly ></span><span class="sxs-lookup"><span data-stu-id="fa636-106">\<appDomainManagerAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa636-107">구문</span><span class="sxs-lookup"><span data-stu-id="fa636-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa636-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fa636-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fa636-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa636-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa636-110">특성</span><span class="sxs-lookup"><span data-stu-id="fa636-110">Attributes</span></span>  
  
|<span data-ttu-id="fa636-111">특성</span><span class="sxs-lookup"><span data-stu-id="fa636-111">Attribute</span></span>|<span data-ttu-id="fa636-112">설명</span><span class="sxs-lookup"><span data-stu-id="fa636-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="fa636-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="fa636-113">Required attribute.</span></span> <span data-ttu-id="fa636-114">프로세스에서 기본 응용 프로그램 도메인에 대 한 응용 프로그램 도메인 관리자가 제공 하는 어셈블리의 표시 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa636-114">Specifies the display name of the assembly that provides the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa636-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fa636-115">Child Elements</span></span>  
 <span data-ttu-id="fa636-116">없음</span><span class="sxs-lookup"><span data-stu-id="fa636-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fa636-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fa636-117">Parent Elements</span></span>  
  
|<span data-ttu-id="fa636-118">요소</span><span class="sxs-lookup"><span data-stu-id="fa636-118">Element</span></span>|<span data-ttu-id="fa636-119">설명</span><span class="sxs-lookup"><span data-stu-id="fa636-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fa636-120">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fa636-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="fa636-121">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fa636-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa636-122">설명</span><span class="sxs-lookup"><span data-stu-id="fa636-122">Remarks</span></span>  
 <span data-ttu-id="fa636-123">응용 프로그램 도메인 관리자의 종류를 지정 하려면이 두 요소를 지정 해야 하며 [ \<appDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fa636-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerType>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) element.</span></span> <span data-ttu-id="fa636-124">이러한 요소 중 하나를 지정 하지 않은 경우 다른 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa636-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="fa636-125">기본 응용 프로그램 도메인 로드 되 면 <xref:System.TypeLoadException> 또는 어셈블리에서 지정 된 형식의 포함 되어 있지 않으면 지정된 된 어셈블리가 없는 경우 throw 되는 [ \<appDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) 요소로 및 프로세스가 시작 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa636-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified assembly does not exist or if the assembly does not contain the type specified by the [\<appDomainManagerType>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) element; and the process fails to start.</span></span> <span data-ttu-id="fa636-126">어셈블리를 찾았지만 버전 정보가 일치 하지 않는 한 <xref:System.IO.FileLoadException> throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa636-126">If the assembly is found but the version information does not match, a <xref:System.IO.FileLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="fa636-127">기본 응용 프로그램 도메인에 대 한 응용 프로그램 도메인 관리자 유형을 지정 하면 다른 응용 프로그램 도메인은 기본 응용 프로그램 도메인에서 만든 응용 프로그램 도메인 관리자 형식을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa636-127">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="fa636-128">사용 하 여는 <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> 및 <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> 새 응용 프로그램 도메인에 대 한 다른 응용 프로그램 도메인 관리자 유형을 지정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="fa636-128">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="fa636-129">응용 프로그램 도메인 관리자 유형을 지정 하는 응용 프로그램이 완전 신뢰 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa636-129">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="fa636-130">(예를 들어 데스크톱에서 실행 중인 응용 프로그램에 완전 신뢰.) 응용 프로그램에 완전 신뢰가 없는 경우는 <xref:System.TypeLoadException> throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa636-130">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="fa636-131">형식의 어셈블리 표시 이름에 대 한 참조는 <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="fa636-131">For the format of the assembly display name, see the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="fa636-132">이 구성 요소는 에서만 사용할 수는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 이상.</span><span class="sxs-lookup"><span data-stu-id="fa636-132">This configuration element is available only in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa636-133">예제</span><span class="sxs-lookup"><span data-stu-id="fa636-133">Example</span></span>  
 <span data-ttu-id="fa636-134">다음 예제에서는 프로세스의 기본 응용 프로그램 도메인에 대 한 응용 프로그램 도메인 관리자 임을 지정 하는 방법을 보여 줍니다는 `MyMgr` 에 입력 된 `AdMgrExample` 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="fa636-134">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fa636-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa636-135">See Also</span></span>  
 <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>  
 <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="fa636-136">\<appDomainManagerType > 요소</span><span class="sxs-lookup"><span data-stu-id="fa636-136">\<appDomainManagerType> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)  
 [<span data-ttu-id="fa636-137">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="fa636-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="fa636-138">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="fa636-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="fa636-139">SetAppDomainManagerType 메서드</span><span class="sxs-lookup"><span data-stu-id="fa636-139">SetAppDomainManagerType Method</span></span>](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
