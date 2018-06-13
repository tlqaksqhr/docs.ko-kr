---
title: '&lt;serviceCertificate&gt;'
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: af59562dbf6c13970526f1665a9ba2c57c4f32ee
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32766779"
---
# <a name="ltservicecertificategt"></a><span data-ttu-id="2c32d-102">&lt;serviceCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="2c32d-102">&lt;serviceCertificate&gt;</span></span>
<span data-ttu-id="2c32d-103">암호화 및 토큰 암호 해독 하는 데 사용 되는 X.509 인증서를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c32d-103">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
 <span data-ttu-id="2c32d-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="2c32d-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="2c32d-105">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="2c32d-105">\<federationConfiguration></span></span>  
<span data-ttu-id="2c32d-106">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="2c32d-106">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c32d-107">구문</span><span class="sxs-lookup"><span data-stu-id="2c32d-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c32d-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2c32d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2c32d-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2c32d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c32d-110">특성</span><span class="sxs-lookup"><span data-stu-id="2c32d-110">Attributes</span></span>  
 <span data-ttu-id="2c32d-111">없음</span><span class="sxs-lookup"><span data-stu-id="2c32d-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2c32d-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2c32d-112">Child Elements</span></span>  
  
|<span data-ttu-id="2c32d-113">요소</span><span class="sxs-lookup"><span data-stu-id="2c32d-113">Element</span></span>|<span data-ttu-id="2c32d-114">설명</span><span class="sxs-lookup"><span data-stu-id="2c32d-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c32d-115">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="2c32d-115">\<certificateReference></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatereference.md)|<span data-ttu-id="2c32d-116">찾기 및 인증서 저장소에서 X.509 인증서의 유효성을 검사 하는 데 사용 되는 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c32d-116">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2c32d-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2c32d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="2c32d-118">요소</span><span class="sxs-lookup"><span data-stu-id="2c32d-118">Element</span></span>|<span data-ttu-id="2c32d-119">설명</span><span class="sxs-lookup"><span data-stu-id="2c32d-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c32d-120">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="2c32d-120">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="2c32d-121">구성 하는 설정이 포함 된 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) 및 <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span><span class="sxs-lookup"><span data-stu-id="2c32d-121">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2c32d-122">예제</span><span class="sxs-lookup"><span data-stu-id="2c32d-122">Example</span></span>  
 <span data-ttu-id="2c32d-123">다음 XML에서는 \<serviceCertificate > 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2c32d-123">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="2c32d-124">XML에서 가져온 것은 `CustomToken` 샘플.</span><span class="sxs-lookup"><span data-stu-id="2c32d-124">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
