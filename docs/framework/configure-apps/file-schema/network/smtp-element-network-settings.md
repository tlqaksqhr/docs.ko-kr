---
title: '&lt;smtp&gt; 요소 (네트워크 설정)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 56912e09d24fc83e93a91cc42b1d96dcc68210f2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32741895"
---
# <a name="ltsmtpgt-element-network-settings"></a><span data-ttu-id="74726-102">&lt;smtp&gt; 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="74726-102">&lt;smtp&gt; Element (Network Settings)</span></span>
<span data-ttu-id="74726-103">배달 형식, 배달 방법 구성 들어오고 보내는 전자 메일에 대 한 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="74726-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
 <span data-ttu-id="74726-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="74726-104">\<configuration></span></span>  
<span data-ttu-id="74726-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="74726-105">\<system.net></span></span>  
<span data-ttu-id="74726-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="74726-106">\<mailSettings></span></span>  
<span data-ttu-id="74726-107">\<smtp></span><span class="sxs-lookup"><span data-stu-id="74726-107">\<smtp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74726-108">구문</span><span class="sxs-lookup"><span data-stu-id="74726-108">Syntax</span></span>  
  
```xml  
      <smtp  
        deliveryFormat="format"   
        deliveryMethod="method"   
        from="from address">
          <specifiedPickupDirectory> … </ specifiedPickupDirectory >  
          <network> … </network>  
      </smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74726-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="74726-109">Attributes and Elements</span></span>  
 <span data-ttu-id="74726-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="74726-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74726-111">특성</span><span class="sxs-lookup"><span data-stu-id="74726-111">Attributes</span></span>  
  
|<span data-ttu-id="74726-112">특성</span><span class="sxs-lookup"><span data-stu-id="74726-112">Attribute</span></span>|<span data-ttu-id="74726-113">설명</span><span class="sxs-lookup"><span data-stu-id="74726-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="74726-114">보내는 전자 메일 배달 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="74726-114">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="74726-115">허용 가능한 값은 SevenBit와 International입니다.</span><span class="sxs-lookup"><span data-stu-id="74726-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="74726-116">메일에 대 한 배달 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="74726-116">Specifies the delivery method for emails.</span></span> <span data-ttu-id="74726-117">허용 되는 값은 네트워크, pickupDirectoryFromIis, 및 specifiedPickupDirectory입니다.</span><span class="sxs-lookup"><span data-stu-id="74726-117">Acceptable values are network, pickupDirectoryFromIis, and specifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="74726-118">지정 된 보낸 사람 주소를 나가는 전자 메일이 합니다.</span><span class="sxs-lookup"><span data-stu-id="74726-118">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="74726-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="74726-119">Child Elements</span></span>  
  
|<span data-ttu-id="74726-120">특성</span><span class="sxs-lookup"><span data-stu-id="74726-120">Attribute</span></span>|<span data-ttu-id="74726-121">설명</span><span class="sxs-lookup"><span data-stu-id="74726-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="74726-122">전송 프로토콜 SMTP (Simple Mail) 서버에 대 한 로컬 디렉터리를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="74726-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="74726-123">외부 SMTP 서버에 대 한 네트워크 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="74726-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="74726-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="74726-124">Parent Elements</span></span>  
  
|<span data-ttu-id="74726-125">**요소**</span><span class="sxs-lookup"><span data-stu-id="74726-125">**Element**</span></span>|<span data-ttu-id="74726-126">**설명**</span><span class="sxs-lookup"><span data-stu-id="74726-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="74726-127">\<mailSettings> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="74726-127">\<mailSettings> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="74726-128">메일 보내기 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="74726-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="74726-129">예제</span><span class="sxs-lookup"><span data-stu-id="74726-129">Example</span></span>  
 <span data-ttu-id="74726-130">다음 예제에서는 기본 네트워크 자격 증명을 사용 하 여 전자 메일을 보내는 적절 한 SMTP 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74726-130">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
        <network  
          host="localhost"  
          port="25"  
          defaultCredentials="true"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="74726-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="74726-131">See Also</span></span>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpDeliveryFormat>  
 <xref:System.Net.Mail.SmtpDeliveryMethod>  
 [<span data-ttu-id="74726-132">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="74726-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
