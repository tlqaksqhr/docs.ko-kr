---
title: '&lt;transportConfigurationTypes&gt;'
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: 422de17f4c1b42579eadc16c7ec1a0037903d1a9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="lttransportconfigurationtypesgt"></a><span data-ttu-id="16eb0-102">&lt;transportConfigurationTypes&gt;</span><span class="sxs-lookup"><span data-stu-id="16eb0-102">&lt;transportConfigurationTypes&gt;</span></span>
<span data-ttu-id="16eb0-103">특정 전송의 형식을 식별하는 구성 요소 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="16eb0-103">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="16eb0-104">사용자 지정 WAS 프로토콜을 추가하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16eb0-104">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="16eb0-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="16eb0-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="16eb0-106">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="16eb0-106">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="16eb0-107">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="16eb0-107">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16eb0-108">구문</span><span class="sxs-lookup"><span data-stu-id="16eb0-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="String"  
               transportConfigurationType="String"/>   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="16eb0-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="16eb0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="16eb0-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="16eb0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="16eb0-111">특성</span><span class="sxs-lookup"><span data-stu-id="16eb0-111">Attributes</span></span>  
  
|<span data-ttu-id="16eb0-112">특성</span><span class="sxs-lookup"><span data-stu-id="16eb0-112">Attribute</span></span>|<span data-ttu-id="16eb0-113">설명</span><span class="sxs-lookup"><span data-stu-id="16eb0-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="16eb0-114">name</span><span class="sxs-lookup"><span data-stu-id="16eb0-114">name</span></span>|<span data-ttu-id="16eb0-115">전송의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="16eb0-115">The name of the transport</span></span>|  
|<span data-ttu-id="16eb0-116">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="16eb0-116">transportConfigurationType</span></span>|<span data-ttu-id="16eb0-117">전송을 구현하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="16eb0-117">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="16eb0-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="16eb0-118">Child Elements</span></span>  
  
|<span data-ttu-id="16eb0-119">요소</span><span class="sxs-lookup"><span data-stu-id="16eb0-119">Element</span></span>|<span data-ttu-id="16eb0-120">설명</span><span class="sxs-lookup"><span data-stu-id="16eb0-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="16eb0-121">\<add></span><span class="sxs-lookup"><span data-stu-id="16eb0-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="16eb0-122">특정 전송의 형식을 식별하는 구성 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="16eb0-122">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="16eb0-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="16eb0-123">Parent Elements</span></span>  
  
|<span data-ttu-id="16eb0-124">요소</span><span class="sxs-lookup"><span data-stu-id="16eb0-124">Element</span></span>|<span data-ttu-id="16eb0-125">설명</span><span class="sxs-lookup"><span data-stu-id="16eb0-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="16eb0-126">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="16eb0-126">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="16eb0-127">특정 전송을 위해 서비스 호스팅 환경에서 인스턴스화하는 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="16eb0-127">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="16eb0-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16eb0-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>  
 [<span data-ttu-id="16eb0-129">호스팅</span><span class="sxs-lookup"><span data-stu-id="16eb0-129">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
