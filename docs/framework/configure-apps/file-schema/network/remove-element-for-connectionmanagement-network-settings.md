---
title: '&lt;제거&gt; connectionManagement (네트워크 설정)에 대 한 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- connectionManagement, remove element
- <remove> element, connectionManagement
- <connectionManagement>, remove element
- remove element, connectionManagement
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 8d503e06139fc6ce14f4d2c50c46e4bcfeb1b860
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltremovegt-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="41f71-102">&lt;제거&gt; connectionManagement (네트워크 설정)에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="41f71-102">&lt;remove&gt; Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="41f71-103">연결 관리 목록에서 IP 주소 또는 DNS 이름을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="41f71-103">Removes an IP address or DNS name from the connection management list.</span></span>  
  
 <span data-ttu-id="41f71-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="41f71-104">\<configuration></span></span>  
<span data-ttu-id="41f71-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="41f71-105">\<system.net></span></span>  
<span data-ttu-id="41f71-106">\<connectionManagement ></span><span class="sxs-lookup"><span data-stu-id="41f71-106">\<connectionManagement></span></span>  
<span data-ttu-id="41f71-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="41f71-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41f71-108">구문</span><span class="sxs-lookup"><span data-stu-id="41f71-108">Syntax</span></span>  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41f71-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="41f71-109">Attributes and Elements</span></span>  
 <span data-ttu-id="41f71-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="41f71-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41f71-111">특성</span><span class="sxs-lookup"><span data-stu-id="41f71-111">Attributes</span></span>  
  
|<span data-ttu-id="41f71-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="41f71-112">**Attribute**</span></span>|<span data-ttu-id="41f71-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="41f71-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="41f71-114">IP 주소 또는 DNS 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="41f71-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="41f71-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="41f71-115">Child Elements</span></span>  
 <span data-ttu-id="41f71-116">없음</span><span class="sxs-lookup"><span data-stu-id="41f71-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="41f71-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="41f71-117">Parent Elements</span></span>  
  
|<span data-ttu-id="41f71-118">**요소**</span><span class="sxs-lookup"><span data-stu-id="41f71-118">**Element**</span></span>|<span data-ttu-id="41f71-119">**설명**</span><span class="sxs-lookup"><span data-stu-id="41f71-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="41f71-120">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="41f71-120">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="41f71-121">네트워크 호스트에 대한 최대 연결 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="41f71-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41f71-122">설명</span><span class="sxs-lookup"><span data-stu-id="41f71-122">Remarks</span></span>  
 <span data-ttu-id="41f71-123">`remove` 요소는 지정된 된 서버에 대 한 연결 관리 목록 항목을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f71-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="41f71-124">값은 `address` 특성에 유효한 IP 주소 또는 호스트 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f71-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="41f71-125">구성 파일</span><span class="sxs-lookup"><span data-stu-id="41f71-125">Configuration Files</span></span>  
 <span data-ttu-id="41f71-126">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41f71-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="41f71-127">예제</span><span class="sxs-lookup"><span data-stu-id="41f71-127">Example</span></span>  
 <span data-ttu-id="41f71-128">다음 예에서는 서버 www.adventure-works.com에 대 한 모든 연결 관리 목록 항목을 제거 하 고 www.contoso.com 서버에 대 한 연결 4 개와 다른 모든 서버에 두 개의 연결이 사용 하도록 응용을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f71-128">The following example removes any connection management list entries for the server www.adventure-works.com and then configures an application to use four connections to the server www.contoso.com and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <remove address="http://www.adventure-works.com" />  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="41f71-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="41f71-129">See Also</span></span>  
 <xref:System.Net.ServicePoint>  
 <xref:System.Net.ServicePointManager>  
 [<span data-ttu-id="41f71-130">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="41f71-130">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
