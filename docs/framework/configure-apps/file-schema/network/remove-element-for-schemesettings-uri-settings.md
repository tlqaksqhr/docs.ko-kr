---
title: "&lt;제거&gt; schemeSettings (Uri 설정)에 대 한 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4095ba51-de20-4f87-b562-018abe422c91
caps.latest.revision: "5"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 7ab053937587d9cfd9353fe53fa759e58859e3da
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltremovegt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="b1a95-102">&lt;제거&gt; schemeSettings (Uri 설정)에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="b1a95-102">&lt;remove&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="b1a95-103">체계 이름에 대 한 스키마 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b1a95-103">Removes a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="b1a95-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b1a95-104">\<configuration></span></span>  
<span data-ttu-id="b1a95-105">\<uri ></span><span class="sxs-lookup"><span data-stu-id="b1a95-105">\<uri></span></span>  
<span data-ttu-id="b1a95-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="b1a95-106">\<schemeSettings></span></span>  
<span data-ttu-id="b1a95-107">\<제거 ></span><span class="sxs-lookup"><span data-stu-id="b1a95-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1a95-108">구문</span><span class="sxs-lookup"><span data-stu-id="b1a95-108">Syntax</span></span>  
  
```xml  
<remove
  name="http|https"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b1a95-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b1a95-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b1a95-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b1a95-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1a95-111">특성</span><span class="sxs-lookup"><span data-stu-id="b1a95-111">Attributes</span></span>  
  
|<span data-ttu-id="b1a95-112">특성</span><span class="sxs-lookup"><span data-stu-id="b1a95-112">Attribute</span></span>|<span data-ttu-id="b1a95-113">설명</span><span class="sxs-lookup"><span data-stu-id="b1a95-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b1a95-114">name</span><span class="sxs-lookup"><span data-stu-id="b1a95-114">name</span></span>|<span data-ttu-id="b1a95-115">이 설정은 적용 되는 체계 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b1a95-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="b1a95-116">이름에 지원 되는 값만 = "http" 및 name = "https"입니다.</span><span class="sxs-lookup"><span data-stu-id="b1a95-116">The only supported values are name="http" and name="https".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b1a95-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b1a95-117">Child Elements</span></span>  
 <span data-ttu-id="b1a95-118">없음</span><span class="sxs-lookup"><span data-stu-id="b1a95-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b1a95-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b1a95-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b1a95-120">요소</span><span class="sxs-lookup"><span data-stu-id="b1a95-120">Element</span></span>|<span data-ttu-id="b1a95-121">설명</span><span class="sxs-lookup"><span data-stu-id="b1a95-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1a95-122">\<schemeSettings> 요소 (URI 설정)</span><span class="sxs-lookup"><span data-stu-id="b1a95-122">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="b1a95-123">특정 체계에 대해 <xref:System.Uri>가 구문 분석되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b1a95-123">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1a95-124">설명</span><span class="sxs-lookup"><span data-stu-id="b1a95-124">Remarks</span></span>  
 <span data-ttu-id="b1a95-125">기본적으로는 <xref:System.Uri?displayProperty=nameWithType> 클래스 이스케이프 해제 % 인코딩된 경로 압축을 실행 하기 전에 경로 구분 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="b1a95-125">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="b1a95-126">다음과 같은 공격에 대 한 보안 메커니즘으로 구현 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b1a95-126">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="b1a95-127">이 URI에서 전달 되 모듈 %를 처리 하지 않는 인코딩된 문자를 올바르게 이벤트를 서버에서 실행 되 고 다음 명령이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1a95-127">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="b1a95-128">이러한 이유로 <xref:System.Uri?displayProperty=nameWithType> 클래스가 먼저 이스케이프 해제 경로 구분 기호 및 경로 압축을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1a95-128">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="b1a95-129">위의 악성 URL을 전달 하는 결과 <xref:System.Uri?displayProperty=nameWithType> 클래스 생성자에 다음 URI:</span><span class="sxs-lookup"><span data-stu-id="b1a95-129">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="b1a95-130">이 기본 동작 schemeSettings 구성 옵션을 사용 하 여 특정 구성표에 대 한 이스케이프 해제 백분율 인코딩된 경로 구분 되지를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1a95-130">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b1a95-131">구성 파일</span><span class="sxs-lookup"><span data-stu-id="b1a95-131">Configuration Files</span></span>  
 <span data-ttu-id="b1a95-132">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1a95-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1a95-133">예</span><span class="sxs-lookup"><span data-stu-id="b1a95-133">Example</span></span>  
 <span data-ttu-id="b1a95-134">다음 예제에서 사용 되는 구성을 <xref:System.Uri> http 체계에 대 한 한 스키마 설정을 제거 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b1a95-134">The following example shows a configuration used by the <xref:System.Uri> class that removes any scheme settings for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <remove name="http"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b1a95-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b1a95-135">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="b1a95-136">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="b1a95-136">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
