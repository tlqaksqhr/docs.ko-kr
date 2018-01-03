---
title: "WIF 구성 스키마 규칙"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7864356-f72f-4cae-995c-18e0431f8a58
caps.latest.revision: "3"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: e327b45ddd260d1a52066b5bf53e7114100ff45c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="wif-configuration-schema-conventions"></a><span data-ttu-id="13aaf-102">WIF 구성 스키마 규칙</span><span class="sxs-lookup"><span data-stu-id="13aaf-102">WIF Configuration Schema Conventions</span></span>
<span data-ttu-id="13aaf-103">이 항목에서는 WIF(Windows Identity Foundation) 구성 항목 전체에서 사용되는 규칙을 설명하고 [\<system.identityModel>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) 및 [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) 섹션에서 사용되는 몇 가지 일반적인 기능과 특성을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="13aaf-103">This topic discusses conventions used throughout the Windows Identity Foundation (WIF) configuration topics and describes some common features and attributes used in the [\<system.identityModel>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) and the [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) sections.</span></span>  
  
<a name="BKMK_Modes"></a>   
## <a name="modes"></a><span data-ttu-id="13aaf-104">모드</span><span class="sxs-lookup"><span data-stu-id="13aaf-104">Modes</span></span>  
 <span data-ttu-id="13aaf-105">WIF 구성 요소에는 대부분 `mode` 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13aaf-105">Many of the WIF configuration elements have a `mode` attribute.</span></span> <span data-ttu-id="13aaf-106">이 특성은 일반적으로 처리의 특정 부분을 수행하는 데 사용되는 클래스 및 현재 요소의 자식 요소로 허용되는 구성 요소를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="13aaf-106">This attribute typically controls which class is used to do a particular part of the processing and which configuration elements are allowed as child elements of the current element.</span></span> <span data-ttu-id="13aaf-107">구성 파일에 포함된 요소가 모드 설정 때문에 무시되는 경우 구성 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="13aaf-107">A configuration error will be raised if elements that are included in the configuration file are ignored because of the mode settings.</span></span>  
  
<a name="BKMK_TimespanValues"></a>   
## <a name="timespan-values"></a><span data-ttu-id="13aaf-108">Timespan 값</span><span class="sxs-lookup"><span data-stu-id="13aaf-108">Timespan Values</span></span>  
 <span data-ttu-id="13aaf-109">여기서 <xref:System.TimeSpan>은 특성의 형식으로 사용됩니다. 허용되는 형식을 확인하려면 <xref:System.TimeSpan.Parse%28System.String%29> 메서드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13aaf-109">Where <xref:System.TimeSpan> is used as the type of an attribute, see the <xref:System.TimeSpan.Parse%28System.String%29> method to see the allowed format.</span></span> <span data-ttu-id="13aaf-110">이 형식은 다음 사양을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="13aaf-110">This format conforms to the following specification.</span></span>  
  
```  
[ws][-]{ d | [d.]hh:mm[:ss[.ff]] }[ws]  
```  
  
 <span data-ttu-id="13aaf-111">예를 들어 “30”, “30.00:00”, “30.00:00:00”은 모두 30일을 의미하고 “00:05”, “00:05:00”, “0.00:05:00.00”은 모두 5분을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="13aaf-111">For example, "30", "30.00:00", "30.00:00:00" all mean 30 days; and "00:05", "00:05:00", "0.00:05:00.00" all mean 5 minutes.</span></span>  
  
<a name="BKMK_CertificateReferences"></a>   
## <a name="certificate-references"></a><span data-ttu-id="13aaf-112">인증서 참조</span><span class="sxs-lookup"><span data-stu-id="13aaf-112">Certificate References</span></span>  
 <span data-ttu-id="13aaf-113">몇 가지 요소는 `<certificateReference>` 요소를 사용하여 인증서를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="13aaf-113">Several elements take references to certificates using the `<certificateReference>` element.</span></span> <span data-ttu-id="13aaf-114">인증서를 참조하는 경우 다음 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13aaf-114">When referencing a certificate, the following attributes are available.</span></span>  
  
|||  
|-|-|  
|`storeLocation`|<span data-ttu-id="13aaf-115"><xref:System.Security.Cryptography.X509Certificates.StoreLocation> 열거형 값 `CurrentUser` 또는 `CurrentMachine`입니다.</span><span class="sxs-lookup"><span data-stu-id="13aaf-115">A value of the <xref:System.Security.Cryptography.X509Certificates.StoreLocation> enumeration: `CurrentUser` or `CurrentMachine`.</span></span>|  
|`storeName`|<span data-ttu-id="13aaf-116"><xref:System.Security.Cryptography.X509Certificates.StoreName> 열거형의 값. 이 컨텍스트에서 가장 유용한 값은 `My` 및 `TrustedPeople`입니다.</span><span class="sxs-lookup"><span data-stu-id="13aaf-116">A value of the <xref:System.Security.Cryptography.X509Certificates.StoreName> enumeration; the most useful for this context are `My` and `TrustedPeople`.</span></span>|  
|`x509FindType`|<span data-ttu-id="13aaf-117"><xref:System.Security.Cryptography.X509Certificates.X509FindType> 열거형의 값. 이 컨텍스트에서 가장 유용한 값은 `FindBySubjectName` 및 `FindByThumbprint`입니다.</span><span class="sxs-lookup"><span data-stu-id="13aaf-117">A value of the <xref:System.Security.Cryptography.X509Certificates.X509FindType> enumeration; the most useful for this context are `FindBySubjectName` and `FindByThumbprint`.</span></span> <span data-ttu-id="13aaf-118">오류 발생 가능성을 제거하려면 `FindByThumbprint` 형식을 프로덕션 환경에서 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="13aaf-118">To eliminate the chance of error, it is recommended that the `FindByThumbprint` type be used in production environments.</span></span>|  
|`findValue`|<span data-ttu-id="13aaf-119">`x509FindType` 특성에 따라 인증서를 찾는 데 사용되는 값.</span><span class="sxs-lookup"><span data-stu-id="13aaf-119">The value used to find the certificate, based on the `x509FindType` attribute.</span></span> <span data-ttu-id="13aaf-120">오류 발생 가능성을 제거하려면 `FindByThumbprint` 형식을 프로덕션 환경에서 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="13aaf-120">To eliminate the chance of error, it is recommended that the `FindByThumbprint` type be used in production environments.</span></span> <span data-ttu-id="13aaf-121">`FindByThumbPrint`가 지정된 경우 이 특성은 16진수 문자열 형식의 인증서 지문인 값을 사용합니다(예: “97249e1a5fa6bee5e515b82111ef524a4c91583f”).</span><span class="sxs-lookup"><span data-stu-id="13aaf-121">When `FindByThumbPrint` is specified, this attribute takes a value that is the hexadecimal-string form of the certificate thumbprint; for example, "97249e1a5fa6bee5e515b82111ef524a4c91583f".</span></span>|  
  
<a name="BKMK_CustomTypeReferences"></a>   
## <a name="custom-type-references"></a><span data-ttu-id="13aaf-122">사용자 지정 형식 참조</span><span class="sxs-lookup"><span data-stu-id="13aaf-122">Custom Type References</span></span>  
 <span data-ttu-id="13aaf-123">여러 요소는 `type` 특성을 사용하여 사용자 지정 형식을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="13aaf-123">Several elements reference custom types using the `type` attribute.</span></span> <span data-ttu-id="13aaf-124">이 특성은 사용자 지정 형식의 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13aaf-124">This attribute should specify the name of the custom type.</span></span> <span data-ttu-id="13aaf-125">GAC(전역 어셈블리 캐시)의 형식을 참조하려면 강력한 이름을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13aaf-125">To reference a type from the Global Assembly Cache (GAC), a strong name should be used.</span></span> <span data-ttu-id="13aaf-126">Bin/ 디렉터리에 있는 어셈블리의 형식을 참조하려면 간단한 어셈블리 정규화된 참조를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13aaf-126">To reference a type from an assembly in the Bin/ directory, a simple assembly-qualified reference may be used.</span></span> <span data-ttu-id="13aaf-127">App_Code/ 디렉터리에 정의된 형식은 한정하는 어셈블리 없이 형식 이름만 지정하여 참조할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13aaf-127">Types defined in the App_Code/ directory may also be referenced by simply specifying the type name with no qualifying assembly.</span></span>  
  
 <span data-ttu-id="13aaf-128">사용자 지정 형식은 지정된 형식에서 파생되어야 하며 `public` 기본(0 인수) 생성자를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13aaf-128">Custom types must be derived from the type specified and they must provide a `public` default (0 argument) constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13aaf-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="13aaf-129">See Also</span></span>  
 [<span data-ttu-id="13aaf-130">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="13aaf-130">\<system.identityModel></span></span>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)  
 [<span data-ttu-id="13aaf-131">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="13aaf-131">\<system.identityModel.services></span></span>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)
