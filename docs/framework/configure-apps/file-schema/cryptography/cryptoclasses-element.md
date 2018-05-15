---
title: '&lt;cryptoClasses&gt; 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClasses
helpviewer_keywords:
- <cryptoClasses> element
- cryptoClasses element
ms.assetid: 290d5f96-946d-4f02-babb-1d31ec0b8295
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 2706d2466bd7139d8a6c20802c32dd19f64abb40
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltcryptoclassesgt-element"></a><span data-ttu-id="fa453-102">&lt;cryptoClasses&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="fa453-102">&lt;cryptoClasses&gt; Element</span></span>
<span data-ttu-id="fa453-103">[\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) 요소에 있는 이름에 매핑되는 암호화 클래스의 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa453-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="fa453-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="fa453-104">\<configuration></span></span>  
<span data-ttu-id="fa453-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="fa453-105">\<mscorlib></span></span>  
<span data-ttu-id="fa453-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="fa453-106">\<cryptographySettings></span></span>  
<span data-ttu-id="fa453-107">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="fa453-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="fa453-108">\<cryptoClasses ></span><span class="sxs-lookup"><span data-stu-id="fa453-108">\<cryptoClasses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa453-109">구문</span><span class="sxs-lookup"><span data-stu-id="fa453-109">Syntax</span></span>  
  
```xml  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa453-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fa453-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fa453-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa453-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa453-112">특성</span><span class="sxs-lookup"><span data-stu-id="fa453-112">Attributes</span></span>  
 <span data-ttu-id="fa453-113">없음</span><span class="sxs-lookup"><span data-stu-id="fa453-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fa453-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fa453-114">Child Elements</span></span>  
  
|<span data-ttu-id="fa453-115">요소</span><span class="sxs-lookup"><span data-stu-id="fa453-115">Element</span></span>|<span data-ttu-id="fa453-116">설명</span><span class="sxs-lookup"><span data-stu-id="fa453-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa453-117">\<cryptoClass ></span><span class="sxs-lookup"><span data-stu-id="fa453-117">\<cryptoClass></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|<span data-ttu-id="fa453-118">**\<nameEntry>** 요소에 있는 이름에 매핑되는 암호화 클래스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa453-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fa453-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fa453-119">Parent Elements</span></span>  
  
|<span data-ttu-id="fa453-120">요소</span><span class="sxs-lookup"><span data-stu-id="fa453-120">Element</span></span>|<span data-ttu-id="fa453-121">설명</span><span class="sxs-lookup"><span data-stu-id="fa453-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fa453-122">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fa453-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="fa453-123">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa453-123">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="fa453-124">이름에 대한 클래스의 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa453-124">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="fa453-125">포함 된 `cryptographySettings` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fa453-125">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fa453-126">예제</span><span class="sxs-lookup"><span data-stu-id="fa453-126">Example</span></span>  
 <span data-ttu-id="fa453-127">다음 방법을 보여 주는 예제는  **\<cryptoClass >** 암호화 클래스를 참조 하 고 런타임을 구성 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fa453-127">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="fa453-128">"RSA" 문자열을 전달할 수 있습니다는 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 메서드 및 사용법은 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> 반환 하는 메서드는 `MyCryptoRSAClass` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fa453-128">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <!-- Other cryptography classes go here. -->  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
             <!-- Mappings to other cryptography classes go here. -->  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fa453-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa453-129">See Also</span></span>  
 <xref:System.Security.Cryptography>  
 [<span data-ttu-id="fa453-130">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="fa453-130">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="fa453-131">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="fa453-131">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="fa453-132">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="fa453-132">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="fa453-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span><span class="sxs-lookup"><span data-stu-id="fa453-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](Overload:System.Security.Cryptography.CryptoConfig.CreateFromName)  
 [<span data-ttu-id="fa453-134">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="fa453-134">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
