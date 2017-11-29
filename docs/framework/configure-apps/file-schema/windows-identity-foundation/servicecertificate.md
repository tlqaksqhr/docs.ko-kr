---
title: '&lt;serviceCertificate&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 177639b973bf8c597bc8b994d37c99647c72feb8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltservicecertificategt"></a><span data-ttu-id="8a39a-102">&lt;serviceCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="8a39a-102">&lt;serviceCertificate&gt;</span></span>
<span data-ttu-id="8a39a-103">암호화 및 토큰 암호 해독 하는 데 사용 되는 X.509 인증서를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a39a-103">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
 <span data-ttu-id="8a39a-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="8a39a-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="8a39a-105">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="8a39a-105">\<federationConfiguration></span></span>  
<span data-ttu-id="8a39a-106">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="8a39a-106">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a39a-107">구문</span><span class="sxs-lookup"><span data-stu-id="8a39a-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a39a-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8a39a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8a39a-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8a39a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a39a-110">특성</span><span class="sxs-lookup"><span data-stu-id="8a39a-110">Attributes</span></span>  
 <span data-ttu-id="8a39a-111">없음</span><span class="sxs-lookup"><span data-stu-id="8a39a-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8a39a-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8a39a-112">Child Elements</span></span>  
  
|<span data-ttu-id="8a39a-113">요소</span><span class="sxs-lookup"><span data-stu-id="8a39a-113">Element</span></span>|<span data-ttu-id="8a39a-114">설명</span><span class="sxs-lookup"><span data-stu-id="8a39a-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a39a-115">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="8a39a-115">\<certificateReference></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatereference.md)|<span data-ttu-id="8a39a-116">찾기 및 인증서 저장소에서 X.509 인증서의 유효성을 검사 하는 데 사용 되는 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a39a-116">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8a39a-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8a39a-117">Parent Elements</span></span>  
  
|<span data-ttu-id="8a39a-118">요소</span><span class="sxs-lookup"><span data-stu-id="8a39a-118">Element</span></span>|<span data-ttu-id="8a39a-119">설명</span><span class="sxs-lookup"><span data-stu-id="8a39a-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a39a-120">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="8a39a-120">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="8a39a-121">구성 하는 설정이 포함 된 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) 및 <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span><span class="sxs-lookup"><span data-stu-id="8a39a-121">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8a39a-122">예제</span><span class="sxs-lookup"><span data-stu-id="8a39a-122">Example</span></span>  
 <span data-ttu-id="8a39a-123">다음 XML에서는 \<serviceCertificate > 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8a39a-123">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="8a39a-124">XML에서 가져온 것은 `CustomToken` 샘플.</span><span class="sxs-lookup"><span data-stu-id="8a39a-124">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
