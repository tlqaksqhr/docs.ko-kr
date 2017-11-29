---
title: "&lt;mailSettings&gt; 요소 (네트워크 설정)"
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
caps.latest.revision: "20"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a42b10574a1f44d310f86fe3fa99490f2f1981c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltmailsettingsgt-element-network-settings"></a><span data-ttu-id="fd85d-102">&lt;mailSettings&gt; 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="fd85d-102">&lt;mailSettings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="fd85d-103">메일 보내기 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd85d-103">Configures mail sending options.</span></span>  

<span data-ttu-id="fd85d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="fd85d-104">\<configuration></span></span>  
<span data-ttu-id="fd85d-105">\<system.net ></span><span class="sxs-lookup"><span data-stu-id="fd85d-105">\<system.net></span></span>  
<span data-ttu-id="fd85d-106">\<mailSettings ></span><span class="sxs-lookup"><span data-stu-id="fd85d-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd85d-107">구문</span><span class="sxs-lookup"><span data-stu-id="fd85d-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp> … </smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd85d-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fd85d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fd85d-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd85d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd85d-110">특성</span><span class="sxs-lookup"><span data-stu-id="fd85d-110">Attributes</span></span>  
 <span data-ttu-id="fd85d-111">없음</span><span class="sxs-lookup"><span data-stu-id="fd85d-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fd85d-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fd85d-112">Child Elements</span></span>  
  
|<span data-ttu-id="fd85d-113">특성</span><span class="sxs-lookup"><span data-stu-id="fd85d-113">Attribute</span></span>|<span data-ttu-id="fd85d-114">설명</span><span class="sxs-lookup"><span data-stu-id="fd85d-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="fd85d-115">\<smtp > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="fd85d-115">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="fd85d-116">간단한 메일 전송 프로토콜 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fd85d-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fd85d-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fd85d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="fd85d-118">**요소**</span><span class="sxs-lookup"><span data-stu-id="fd85d-118">**Element**</span></span>|<span data-ttu-id="fd85d-119">**설명**</span><span class="sxs-lookup"><span data-stu-id="fd85d-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fd85d-120">\<system.Net> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="fd85d-120">\<system.Net> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="fd85d-121">.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fd85d-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fd85d-122">예제</span><span class="sxs-lookup"><span data-stu-id="fd85d-122">Example</span></span>  
 <span data-ttu-id="fd85d-123">다음 예제에서는 기본 네트워크 자격 증명을 사용 하 여 전자 메일을 보낼 적절 한 SMTP 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd85d-123">The following example specifies the appropriate SMTP parameters to send e-mail using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network">  
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
  
## <a name="see-also"></a><span data-ttu-id="fd85d-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd85d-124">See Also</span></span>  
 <xref:System.Net.Mail.SmtpClient>  
 [<span data-ttu-id="fd85d-125">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="fd85d-125">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
