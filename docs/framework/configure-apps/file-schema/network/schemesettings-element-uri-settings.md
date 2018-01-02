---
title: "&lt;schemeSettings&gt; 요소 (Uri 설정)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
caps.latest.revision: "6"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 19bcb64beb7b022d20bbde1210ae6d844690d891
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltschemesettingsgt-element-uri-settings"></a><span data-ttu-id="590e4-102">&lt;schemeSettings&gt; 요소 (Uri 설정)</span><span class="sxs-lookup"><span data-stu-id="590e4-102">&lt;schemeSettings&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="590e4-103">특정 체계에 대해 <xref:System.Uri>가 구문 분석되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="590e4-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
 <span data-ttu-id="590e4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="590e4-104">\<configuration></span></span>  
<span data-ttu-id="590e4-105">\<uri ></span><span class="sxs-lookup"><span data-stu-id="590e4-105">\<uri></span></span>  
<span data-ttu-id="590e4-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="590e4-106">\<schemeSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="590e4-107">구문</span><span class="sxs-lookup"><span data-stu-id="590e4-107">Syntax</span></span>  
  
```xml  
<schemeSettings>   
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="590e4-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="590e4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="590e4-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="590e4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="590e4-110">특성</span><span class="sxs-lookup"><span data-stu-id="590e4-110">Attributes</span></span>  
 <span data-ttu-id="590e4-111">없음</span><span class="sxs-lookup"><span data-stu-id="590e4-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="590e4-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="590e4-112">Child Elements</span></span>  
  
|<span data-ttu-id="590e4-113">**요소**</span><span class="sxs-lookup"><span data-stu-id="590e4-113">**Element**</span></span>|<span data-ttu-id="590e4-114">**설명**</span><span class="sxs-lookup"><span data-stu-id="590e4-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="590e4-115">add</span><span class="sxs-lookup"><span data-stu-id="590e4-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="590e4-116">체계 이름에 대 한 스키마 설정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="590e4-116">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="590e4-117">clear</span><span class="sxs-lookup"><span data-stu-id="590e4-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="590e4-118">모든 기존 스키마 설정을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="590e4-118">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="590e4-119">remove</span><span class="sxs-lookup"><span data-stu-id="590e4-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="590e4-120">체계 이름에 대 한 스키마 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="590e4-120">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="590e4-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="590e4-121">Parent Elements</span></span>  
  
|<span data-ttu-id="590e4-122">**요소**</span><span class="sxs-lookup"><span data-stu-id="590e4-122">**Element**</span></span>|<span data-ttu-id="590e4-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="590e4-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="590e4-124">uri</span><span class="sxs-lookup"><span data-stu-id="590e4-124">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="590e4-125">.NET Framework 웹 주소 (Uri) uniform resource identifier를 사용 하 여 표시를 처리 하는 방법을 지정 하는 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="590e4-125">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="590e4-126">설명</span><span class="sxs-lookup"><span data-stu-id="590e4-126">Remarks</span></span>  
 <span data-ttu-id="590e4-127">기본적으로는 <xref:System.Uri?displayProperty=nameWithType> 클래스 이스케이프 해제 % 인코딩된 경로 압축을 실행 하기 전에 경로 구분 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="590e4-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="590e4-128">다음과 같은 공격에 대 한 보안 메커니즘으로 구현 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="590e4-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="590e4-129">이 URI에서 전달 되 모듈 %를 처리 하지 않는 인코딩된 문자를 올바르게 이벤트를 서버에서 실행 되 고 다음 명령이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="590e4-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="590e4-130">이러한 이유로 <xref:System.Uri?displayProperty=nameWithType> 클래스가 먼저 이스케이프 해제 경로 구분 기호 및 경로 압축을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="590e4-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="590e4-131">위의 악성 URL을 전달 하는 결과 <xref:System.Uri?displayProperty=nameWithType> 클래스 생성자에 다음 URI:</span><span class="sxs-lookup"><span data-stu-id="590e4-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="590e4-132">이 기본 동작 schemeSettings 구성 옵션을 사용 하 여 특정 구성표에 대 한 이스케이프 해제 백분율 인코딩된 경로 구분 되지를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="590e4-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="590e4-133">구성 파일</span><span class="sxs-lookup"><span data-stu-id="590e4-133">Configuration Files</span></span>  
 <span data-ttu-id="590e4-134">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="590e4-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="590e4-135">예</span><span class="sxs-lookup"><span data-stu-id="590e4-135">Example</span></span>  
 <span data-ttu-id="590e4-136">다음 예제에서 사용 되는 구성을 <xref:System.Uri> http 체계에 대 한 퍼센트 인코딩 경로 구분 기호를 이스케이프 하지 않아도 되도록 지원 하기 위해 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="590e4-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="590e4-137">요소 정보</span><span class="sxs-lookup"><span data-stu-id="590e4-137">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="590e4-138">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="590e4-138">Namespace</span></span>|<span data-ttu-id="590e4-139">시스템</span><span class="sxs-lookup"><span data-stu-id="590e4-139">System</span></span>|  
|<span data-ttu-id="590e4-140">스키마 이름</span><span class="sxs-lookup"><span data-stu-id="590e4-140">Schema Name</span></span>||  
|<span data-ttu-id="590e4-141">유효성 검사 파일</span><span class="sxs-lookup"><span data-stu-id="590e4-141">Validation File</span></span>||  
|<span data-ttu-id="590e4-142">비워 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="590e4-142">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="590e4-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="590e4-143">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="590e4-144">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="590e4-144">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
