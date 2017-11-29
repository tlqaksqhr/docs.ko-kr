---
title: "&lt;cryptoClass&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses/cryptoClass
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClass
helpviewer_keywords:
- cryptoClass element
- <cryptoClass> element
ms.assetid: 03db52ef-010e-44ea-b6fd-b9c900ecad50
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 448e2c83f6897fd876bb79dfb781bcf4ddd2252b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltcryptoclassgt-element"></a><span data-ttu-id="f00bb-102">&lt;cryptoClass&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="f00bb-102">&lt;cryptoClass&gt; Element</span></span>
<span data-ttu-id="f00bb-103">[\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) 요소에 있는 이름에 매핑되는 암호화 클래스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f00bb-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="f00bb-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f00bb-104">\<configuration></span></span>  
<span data-ttu-id="f00bb-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="f00bb-105">\<mscorlib></span></span>  
<span data-ttu-id="f00bb-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="f00bb-106">\<cryptographySettings></span></span>  
<span data-ttu-id="f00bb-107">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="f00bb-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="f00bb-108">\<cryptoClasses ></span><span class="sxs-lookup"><span data-stu-id="f00bb-108">\<cryptoClasses></span></span>  
<span data-ttu-id="f00bb-109">\<cryptoClass ></span><span class="sxs-lookup"><span data-stu-id="f00bb-109">\<cryptoClass></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f00bb-110">구문</span><span class="sxs-lookup"><span data-stu-id="f00bb-110">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f00bb-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f00bb-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f00bb-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f00bb-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f00bb-113">특성</span><span class="sxs-lookup"><span data-stu-id="f00bb-113">Attributes</span></span>  
  
|<span data-ttu-id="f00bb-114">특성</span><span class="sxs-lookup"><span data-stu-id="f00bb-114">Attribute</span></span>|<span data-ttu-id="f00bb-115">설명</span><span class="sxs-lookup"><span data-stu-id="f00bb-115">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="f00bb-116">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f00bb-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="f00bb-117">암호화 클래스에 대 한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f00bb-117">Contains the information for the cryptography class.</span></span> <span data-ttu-id="f00bb-118">클래스에 대 한 간단한 이름을 제공 하기 위해이 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f00bb-118">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="f00bb-119">에 지정 된 요구 사항을 충족 하는 문자열을 지정 해야 [정규화 된 형식 이름 지정](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f00bb-119">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f00bb-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f00bb-120">Child Elements</span></span>  
 <span data-ttu-id="f00bb-121">없음</span><span class="sxs-lookup"><span data-stu-id="f00bb-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f00bb-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f00bb-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f00bb-123">요소</span><span class="sxs-lookup"><span data-stu-id="f00bb-123">Element</span></span>|<span data-ttu-id="f00bb-124">설명</span><span class="sxs-lookup"><span data-stu-id="f00bb-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f00bb-125">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f00bb-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="f00bb-126">[\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) 요소에 있는 이름에 매핑되는 암호화 클래스의 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f00bb-126">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="f00bb-127">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f00bb-127">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="f00bb-128">이름에 대한 클래스의 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f00bb-128">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="f00bb-129">[\<cryptographySettings>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md) 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f00bb-129">Contains the [\<cryptographySettings>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f00bb-130">예제</span><span class="sxs-lookup"><span data-stu-id="f00bb-130">Example</span></span>  
 <span data-ttu-id="f00bb-131">다음 방법을 보여 주는 예제는  **\<cryptoClass >** 암호화 클래스를 참조 하 고 런타임을 구성 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f00bb-131">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="f00bb-132">"RSA" 문자열을 전달할 수 있습니다는 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 메서드 및 사용법은 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> 반환 하는 메서드는 `MyCryptoRSAClass` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f00bb-132">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f00bb-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f00bb-133">See Also</span></span>  
 [<span data-ttu-id="f00bb-134">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="f00bb-134">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="f00bb-135">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="f00bb-135">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="f00bb-136">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="f00bb-136">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="f00bb-137">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="f00bb-137">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
