---
title: "&lt;모듈&gt; 요소 (네트워크 설정)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#module
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/module
helpviewer_keywords:
- module element
- <module> element
ms.assetid: 10318725-9666-4d65-ab61-b94c64e59f13
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a039f6ed985997c5557659abd299fe0fc7699a1b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltmodulegt-element-network-settings"></a><span data-ttu-id="2e418-102">&lt;모듈&gt; 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="2e418-102">&lt;module&gt; Element (Network Settings)</span></span>
<span data-ttu-id="2e418-103">응용 프로그램에 새 프록시 모듈을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2e418-103">Adds a new proxy module to the application.</span></span>  
  
 <span data-ttu-id="2e418-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2e418-104">\<configuration></span></span>  
<span data-ttu-id="2e418-105">\<system.net ></span><span class="sxs-lookup"><span data-stu-id="2e418-105">\<system.net></span></span>  
<span data-ttu-id="2e418-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="2e418-106">\<defaultProxy></span></span>  
<span data-ttu-id="2e418-107">\<모듈 ></span><span class="sxs-lookup"><span data-stu-id="2e418-107">\<module></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e418-108">구문</span><span class="sxs-lookup"><span data-stu-id="2e418-108">Syntax</span></span>  
  
```xml  
<module   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e418-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2e418-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2e418-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2e418-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e418-111">특성</span><span class="sxs-lookup"><span data-stu-id="2e418-111">Attributes</span></span>  
  
|<span data-ttu-id="2e418-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="2e418-112">**Attribute**</span></span>|<span data-ttu-id="2e418-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="2e418-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="2e418-114">정규화 된 형식 이름 (으로 표시는 <xref:System.Type.FullName%2A> 속성)와 어셈블리 이름 (으로 표시는 <xref:System.Reflection.Assembly.FullName%2A> 속성)을 프록시를 구현 하는 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e418-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2e418-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2e418-115">Child Elements</span></span>  
 <span data-ttu-id="2e418-116">없음</span><span class="sxs-lookup"><span data-stu-id="2e418-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2e418-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2e418-117">Parent Elements</span></span>  
  
|<span data-ttu-id="2e418-118">**요소**</span><span class="sxs-lookup"><span data-stu-id="2e418-118">**Element**</span></span>|<span data-ttu-id="2e418-119">**설명**</span><span class="sxs-lookup"><span data-stu-id="2e418-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2e418-120">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="2e418-120">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="2e418-121">HTTP(Hypertext Transfer Protocol) 프록시 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2e418-121">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e418-122">설명</span><span class="sxs-lookup"><span data-stu-id="2e418-122">Remarks</span></span>  
 <span data-ttu-id="2e418-123">`module` 구현 하는 프록시 클래스를 등록 하는 요소는 <xref:System.Net.IWebProxy> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2e418-123">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="2e418-124">프록시 클래스를 등록한 다음에는 `module`을 사용하여 지원 프록시를 통해 정보를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e418-124">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="2e418-125">에 대 한 값은 `type` 특성은 모듈의 클래스 이름 및의 해당 동적 연결 라이브러리 (DLL) 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e418-125">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2e418-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="2e418-126">Configuration Files</span></span>  
 <span data-ttu-id="2e418-127">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e418-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e418-128">예제</span><span class="sxs-lookup"><span data-stu-id="2e418-128">Example</span></span>  
 <span data-ttu-id="2e418-129">다음 예제에서는 사용자 지정 프록시 클래스를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e418-129">The following example registers a custom proxy class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <module  
        type="Test.CustomWebProxy, TestProxy, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b23a5c561934e385"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2e418-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2e418-130">See Also</span></span>  
 <xref:System.Net.IWebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="2e418-131">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="2e418-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
