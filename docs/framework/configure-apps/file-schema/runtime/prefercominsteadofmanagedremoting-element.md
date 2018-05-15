---
title: '&lt;PreferComInsteadOfManagedRemoting&gt; 요소'
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4cac4ebb46fabad49e2e4e6a7d566522ca027094
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltprefercominsteadofmanagedremotinggt-element"></a><span data-ttu-id="8ba93-102">&lt;PreferComInsteadOfManagedRemoting&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="8ba93-102">&lt;PreferComInsteadOfManagedRemoting&gt; Element</span></span>
<span data-ttu-id="8ba93-103">여부를 런타임에서 COM interop를 사용 원격 서비스 대신 모든 호출에 대 한 응용 프로그램 도메인 경계를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba93-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
 <span data-ttu-id="8ba93-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8ba93-104">\<configuration></span></span>  
<span data-ttu-id="8ba93-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="8ba93-105">\<runtime></span></span>  
<span data-ttu-id="8ba93-106">\<PreferComInsteadOfManagedRemoting ></span><span class="sxs-lookup"><span data-stu-id="8ba93-106">\<PreferComInsteadOfManagedRemoting></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ba93-107">구문</span><span class="sxs-lookup"><span data-stu-id="8ba93-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ba93-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8ba93-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8ba93-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba93-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ba93-110">특성</span><span class="sxs-lookup"><span data-stu-id="8ba93-110">Attributes</span></span>  
  
|<span data-ttu-id="8ba93-111">특성</span><span class="sxs-lookup"><span data-stu-id="8ba93-111">Attribute</span></span>|<span data-ttu-id="8ba93-112">설명</span><span class="sxs-lookup"><span data-stu-id="8ba93-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="8ba93-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8ba93-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="8ba93-114">런타임에 사용할지 여부를 COM interop 원격 서비스 대신 응용 프로그램 도메인 경계를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ba93-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="8ba93-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="8ba93-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="8ba93-116">값</span><span class="sxs-lookup"><span data-stu-id="8ba93-116">Value</span></span>|<span data-ttu-id="8ba93-117">설명</span><span class="sxs-lookup"><span data-stu-id="8ba93-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="8ba93-118">런타임에 응용 프로그램 도메인 경계를 넘어 remoting을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba93-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="8ba93-119">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="8ba93-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="8ba93-120">런타임에 응용 프로그램 도메인 경계를 넘어 COM interop를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba93-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8ba93-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8ba93-121">Child Elements</span></span>  
 <span data-ttu-id="8ba93-122">없음</span><span class="sxs-lookup"><span data-stu-id="8ba93-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8ba93-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8ba93-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8ba93-124">요소</span><span class="sxs-lookup"><span data-stu-id="8ba93-124">Element</span></span>|<span data-ttu-id="8ba93-125">설명</span><span class="sxs-lookup"><span data-stu-id="8ba93-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8ba93-126">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8ba93-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="8ba93-127">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba93-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ba93-128">설명</span><span class="sxs-lookup"><span data-stu-id="8ba93-128">Remarks</span></span>  
 <span data-ttu-id="8ba93-129">설정 하는 경우는 `enabled` 특성을 `true`, 런타임에서 다음과 같이 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba93-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
-   <span data-ttu-id="8ba93-130">런타임에서 호출 하지 않습니다 [iunknown:: Queryinterface](http://go.microsoft.com/fwlink/?LinkID=144867) 에 대 한 프로그램 [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) 인터페이스는 [IUnknown](http://go.microsoft.com/fwlink/?LinkId=148003) 인터페이스가 COM 인터페이스를 통해 도메인을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba93-130">The runtime does not call [IUnknown::QueryInterface](http://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](http://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="8ba93-131">대신, 생성 한 [런타임 호출 가능 래퍼](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) 개체 주위 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba93-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
-   <span data-ttu-id="8ba93-132">런타임에 받을 때 하면 e_nointerface가 반환는 `QueryInterface` 에 대 한 호출는 [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) 인터페이스에 대 한 [COM 호출 가능 래퍼](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW)이이 도메인에서 만든 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba93-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="8ba93-133">이러한 두 가지 동작 응용 프로그램 도메인 경계 사용 COM에서 관리 되는 개체 및 원격 서비스 대신 COM interop 사이 COM에 대 한 모든 호출 인터페이스 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ba93-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ba93-134">예제</span><span class="sxs-lookup"><span data-stu-id="8ba93-134">Example</span></span>  
 <span data-ttu-id="8ba93-135">다음 예제에서는 격리 경계를 넘어 런타임에서 COM을 사용 하도록 지정 하는 방법을 interop 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8ba93-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8ba93-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ba93-136">See Also</span></span>  
 [<span data-ttu-id="8ba93-137">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="8ba93-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="8ba93-138">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="8ba93-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
