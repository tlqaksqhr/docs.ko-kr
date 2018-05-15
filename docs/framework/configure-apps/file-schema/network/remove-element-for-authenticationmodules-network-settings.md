---
title: '&lt;제거&gt; authenticationModules (네트워크 설정)에 대 한 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, authenticationModules
- <authenticationModules>, remove element
- <remove> element, authenticationModules
- authenticationModules, remove element
ms.assetid: abf79949-b05c-465a-b51c-bbeda9a74173
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a22ddbada0162ba38589b244cab9123f33d7cf45
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltremovegt-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="ce95a-102">&lt;제거&gt; authenticationModules (네트워크 설정)에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="ce95a-102">&lt;remove&gt; Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="ce95a-103">응용 프로그램에서 사용자 지정 인증 모듈을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ce95a-103">Removes an authentication module from the application.</span></span>  
  
 <span data-ttu-id="ce95a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ce95a-104">\<configuration></span></span>  
<span data-ttu-id="ce95a-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="ce95a-105">\<system.net></span></span>  
<span data-ttu-id="ce95a-106">\<authenticationModules ></span><span class="sxs-lookup"><span data-stu-id="ce95a-106">\<authenticationModules></span></span>  
<span data-ttu-id="ce95a-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="ce95a-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce95a-108">구문</span><span class="sxs-lookup"><span data-stu-id="ce95a-108">Syntax</span></span>  
  
```xml  
<remove   
   type="authentication module name"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce95a-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ce95a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ce95a-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ce95a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce95a-111">특성</span><span class="sxs-lookup"><span data-stu-id="ce95a-111">Attributes</span></span>  
  
|<span data-ttu-id="ce95a-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="ce95a-112">**Attribute**</span></span>|<span data-ttu-id="ce95a-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="ce95a-113">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="ce95a-114">**type**</span><span class="sxs-lookup"><span data-stu-id="ce95a-114">**type**</span></span>|<span data-ttu-id="ce95a-115">제거할 인증 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ce95a-115">The name of the authentication module to remove.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ce95a-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ce95a-116">Child Elements</span></span>  
 <span data-ttu-id="ce95a-117">없음</span><span class="sxs-lookup"><span data-stu-id="ce95a-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ce95a-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ce95a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="ce95a-119">**요소**</span><span class="sxs-lookup"><span data-stu-id="ce95a-119">**Element**</span></span>|<span data-ttu-id="ce95a-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="ce95a-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ce95a-121">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="ce95a-121">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="ce95a-122">네트워크 요청을 인증 하는 데 사용 되는 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce95a-122">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce95a-123">설명</span><span class="sxs-lookup"><span data-stu-id="ce95a-123">Remarks</span></span>  
 <span data-ttu-id="ce95a-124">`remove` 요소 또는 구성 계층 구조의 상위 수준에서 구성 파일에서 이전 정의 된 인증 모듈을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce95a-124">The `remove` element removes authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="ce95a-125">에 대 한 값은 `type` 특성은 유효한 클래스 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce95a-125">The value for the `type` attribute should be a valid class name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ce95a-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="ce95a-126">Configuration Files</span></span>  
 <span data-ttu-id="ce95a-127">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce95a-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce95a-128">예제</span><span class="sxs-lookup"><span data-stu-id="ce95a-128">Example</span></span>  
 <span data-ttu-id="ce95a-129">다음 예제에서는 사용자 지정 인증 모듈을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ce95a-129">The following example removes an authentication module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ce95a-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce95a-130">See Also</span></span>  
 <xref:System.Net.IAuthenticationModule>  
 <xref:System.Net.AuthenticationManager>  
 [<span data-ttu-id="ce95a-131">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="ce95a-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
