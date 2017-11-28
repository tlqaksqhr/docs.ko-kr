---
title: '&lt;mexNamedPipeBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 193412fa-3260-414c-92c6-b32ed3b94a34
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e786d2f18fca2b04e0a46536e539895890fc67d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltmexnamedpipebindinggt"></a><span data-ttu-id="b5abe-102">&lt;mexNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="b5abe-102">&lt;mexNamedPipeBinding&gt;</span></span>
<span data-ttu-id="b5abe-103">명명된 파이프를 통한 WS-MEX(WS-MetadataExchange) 메시지 교환에 사용되는 바인딩의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abe-103">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over named pipe.</span></span>  
  
 <span data-ttu-id="b5abe-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="b5abe-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b5abe-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="b5abe-105">\<bindings></span></span>  
<span data-ttu-id="b5abe-106">\<mexNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="b5abe-106">\<mexNamedPipeBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5abe-107">구문</span><span class="sxs-lookup"><span data-stu-id="b5abe-107">Syntax</span></span>  
  
```xml  
<mexNamedPipeBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan">  
   </binding>  
</mexNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5abe-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b5abe-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b5abe-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abe-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5abe-110">특성</span><span class="sxs-lookup"><span data-stu-id="b5abe-110">Attributes</span></span>  
  
|<span data-ttu-id="b5abe-111">특성</span><span class="sxs-lookup"><span data-stu-id="b5abe-111">Attribute</span></span>|<span data-ttu-id="b5abe-112">설명</span><span class="sxs-lookup"><span data-stu-id="b5abe-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="b5abe-113">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b5abe-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="b5abe-114">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abe-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b5abe-115">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="b5abe-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="b5abe-116">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b5abe-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="b5abe-117">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abe-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="b5abe-118">각 바인딩에는 서비스의 메타데이터에서 함께 바인딩을 고유하게 식별하는 `name` 및 `namespace` 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5abe-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="b5abe-119">또한 이 이름은 동일한 형식의 바인딩 간에 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abe-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="b5abe-120">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b5abe-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="b5abe-121">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 [단순화 된 구성](../../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스에 대 한 구성을 단순화](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abe-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="b5abe-122">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b5abe-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="b5abe-123">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abe-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b5abe-124">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="b5abe-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="b5abe-125">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b5abe-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="b5abe-126">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abe-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b5abe-127">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="b5abe-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="b5abe-128">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b5abe-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="b5abe-129">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abe-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b5abe-130">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="b5abe-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b5abe-131">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b5abe-131">Child Elements</span></span>  
 <span data-ttu-id="b5abe-132">없음</span><span class="sxs-lookup"><span data-stu-id="b5abe-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b5abe-133">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b5abe-133">Parent Elements</span></span>  
  
|<span data-ttu-id="b5abe-134">요소</span><span class="sxs-lookup"><span data-stu-id="b5abe-134">Element</span></span>|<span data-ttu-id="b5abe-135">설명</span><span class="sxs-lookup"><span data-stu-id="b5abe-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5abe-136">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="b5abe-136">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="b5abe-137">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abe-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b5abe-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b5abe-138">See Also</span></span>  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexNamedPipeBinding%2A>  
 <xref:System.ServiceModel.Configuration.MexNamedPipeBindingElement>  
 [<span data-ttu-id="b5abe-139">방법: 구성 파일을 사용 하 여 서비스에 대 한 메타 데이터를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abe-139">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="b5abe-140">게시 하 고 사용자 지정 바인딩을 통해 메타 데이터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5abe-140">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 [<span data-ttu-id="b5abe-141">메타 데이터</span><span class="sxs-lookup"><span data-stu-id="b5abe-141">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="b5abe-142">바인딩</span><span class="sxs-lookup"><span data-stu-id="b5abe-142">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="b5abe-143">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="b5abe-143">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="b5abe-144">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="b5abe-144">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="b5abe-145">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="b5abe-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
