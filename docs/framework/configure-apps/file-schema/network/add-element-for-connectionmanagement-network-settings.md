---
title: '&lt;추가&gt; connectionManagement (네트워크 설정)에 대 한 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/add
helpviewer_keywords:
- <add> element, connectionManagement
- <connectionManagement>, add element
- add element, connectionManagement
- connectionManagement, add element
ms.assetid: 856bf57d-1c63-46c7-a178-03d97b0a4149
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: c6cfd036a98c345da23fc7b3699987c9678e149d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753744"
---
# <a name="ltaddgt-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="beae5-102">&lt;추가&gt; connectionManagement (네트워크 설정)에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="beae5-102">&lt;add&gt; Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="beae5-103">연결 관리 목록에 IP 주소 또는 DNS 이름을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="beae5-103">Adds an IP address or DNS name to the connection management list.</span></span>  
  
 <span data-ttu-id="beae5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="beae5-104">\<configuration></span></span>  
<span data-ttu-id="beae5-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="beae5-105">\<system.net></span></span>  
<span data-ttu-id="beae5-106">\<connectionManagement ></span><span class="sxs-lookup"><span data-stu-id="beae5-106">\<connectionManagement></span></span>  
<span data-ttu-id="beae5-107">\<add></span><span class="sxs-lookup"><span data-stu-id="beae5-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beae5-108">구문</span><span class="sxs-lookup"><span data-stu-id="beae5-108">Syntax</span></span>  
  
```xml  
<add   
  address="address expression"   
  maxconnection="integer"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="beae5-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="beae5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="beae5-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="beae5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="beae5-111">특성</span><span class="sxs-lookup"><span data-stu-id="beae5-111">Attributes</span></span>  
  
|<span data-ttu-id="beae5-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="beae5-112">**Attribute**</span></span>|<span data-ttu-id="beae5-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="beae5-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="beae5-114">IP 주소 또는 DNS 이름을 설명하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="beae5-114">A string describing an IP address or DNS name.</span></span>|  
|`maxconnection`|<span data-ttu-id="beae5-115">서버에 허용되는 최대 연결 수입니다.</span><span class="sxs-lookup"><span data-stu-id="beae5-115">The maximum number of connections allowed to a server.</span></span> <span data-ttu-id="beae5-116">제공되지 않은 경우 기본값은 2입니다.</span><span class="sxs-lookup"><span data-stu-id="beae5-116">If not supplied, the default is 2.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="beae5-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="beae5-117">Child Elements</span></span>  
 <span data-ttu-id="beae5-118">없음</span><span class="sxs-lookup"><span data-stu-id="beae5-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="beae5-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="beae5-119">Parent Elements</span></span>  
  
|<span data-ttu-id="beae5-120">**요소**</span><span class="sxs-lookup"><span data-stu-id="beae5-120">**Element**</span></span>|<span data-ttu-id="beae5-121">**설명**</span><span class="sxs-lookup"><span data-stu-id="beae5-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="beae5-122">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="beae5-122">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="beae5-123">네트워크 호스트에 대한 최대 연결 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="beae5-123">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="beae5-124">설명</span><span class="sxs-lookup"><span data-stu-id="beae5-124">Remarks</span></span>  
 <span data-ttu-id="beae5-125">`address` 특성의 값은 모든 연결을 나타내는 별표 또는 `<schema>://<idn_hostname>[:<port>]` 형식의 문자열이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="beae5-125">The value of the `address` attribute should be either an asterisk to indicate all connections, or a string of the form `<schema>://<idn_hostname>[:<port>]`.</span></span>  
  
 <span data-ttu-id="beae5-126">HTTP API에 전달된 URI가 유니코드를 포함하는 경우 punicode 문자열을 반환할 수 있는 <xref:System.Uri.DnsSafeHost%2A>를 통해 이름이 내부적으로 변환됩니다(현재 IDN 구성에 따라 동작이 달라짐).</span><span class="sxs-lookup"><span data-stu-id="beae5-126">If the URI passed to any HTTP APIs contains Unicode, the name will be converted internally using <xref:System.Uri.DnsSafeHost%2A> which might return a punicode string (behavior dependent on the current IDN configuration).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="beae5-127">구성 파일</span><span class="sxs-lookup"><span data-stu-id="beae5-127">Configuration Files</span></span>  
 <span data-ttu-id="beae5-128">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beae5-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="beae5-129">예제</span><span class="sxs-lookup"><span data-stu-id="beae5-129">Example</span></span>  
 <span data-ttu-id="beae5-130">다음 예제에서는 www.contoso.com 서버에 대 한 연결 4 개와 다른 모든 서버에 두 개의 연결이 사용 하도록 응용을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="beae5-130">The following example configures an application to use four connections to the server www.contoso.com and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="beae5-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="beae5-131">See Also</span></span>  
 <xref:System.Net.ServicePoint>  
 <xref:System.Net.ServicePointManager>  
 [<span data-ttu-id="beae5-132">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="beae5-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
