---
title: "&lt;cryptoNameMapping&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoNameMapping
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping
helpviewer_keywords:
- <cryptoNameMapping> element
- cryptoNameMapping element
ms.assetid: c59c9494-149b-4ce6-b38d-371f896ae85c
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 2156c6441190b530c48a70e67e93e4806d20b199
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltcryptonamemappinggt-element"></a><span data-ttu-id="14a21-102">&lt;cryptoNameMapping&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="14a21-102">&lt;cryptoNameMapping&gt; Element</span></span>
<span data-ttu-id="14a21-103">이름에 대한 클래스의 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14a21-103">Contains mappings of classes to friendly names.</span></span>  
  
 <span data-ttu-id="14a21-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="14a21-104">\<configuration></span></span>  
<span data-ttu-id="14a21-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="14a21-105">\<mscorlib></span></span>  
<span data-ttu-id="14a21-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="14a21-106">\<cryptographySettings></span></span>  
<span data-ttu-id="14a21-107">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="14a21-107">\<cryptoNameMapping></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14a21-108">구문</span><span class="sxs-lookup"><span data-stu-id="14a21-108">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>   
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14a21-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="14a21-109">Attributes and Elements</span></span>  
 <span data-ttu-id="14a21-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="14a21-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14a21-111">특성</span><span class="sxs-lookup"><span data-stu-id="14a21-111">Attributes</span></span>  
 <span data-ttu-id="14a21-112">없음</span><span class="sxs-lookup"><span data-stu-id="14a21-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="14a21-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="14a21-113">Child Elements</span></span>  
  
|<span data-ttu-id="14a21-114">요소</span><span class="sxs-lookup"><span data-stu-id="14a21-114">Element</span></span>|<span data-ttu-id="14a21-115">설명</span><span class="sxs-lookup"><span data-stu-id="14a21-115">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="14a21-116">**\<nameEntry>** 요소에 있는 이름에 매핑되는 암호화 클래스의 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14a21-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="14a21-117">클래스 이름을 알고리즘 이름에 매핑하며, 이를 통해 하나의 클래스가 여러 이름을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14a21-117">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="14a21-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="14a21-118">Parent Elements</span></span>  
  
|<span data-ttu-id="14a21-119">요소</span><span class="sxs-lookup"><span data-stu-id="14a21-119">Element</span></span>|<span data-ttu-id="14a21-120">설명</span><span class="sxs-lookup"><span data-stu-id="14a21-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="14a21-121">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="14a21-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="14a21-122">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14a21-122">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="14a21-123">이름에 대한 클래스의 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14a21-123">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="14a21-124">포함 된 \<cryptographySettings > 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="14a21-124">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="14a21-125">예제</span><span class="sxs-lookup"><span data-stu-id="14a21-125">Example</span></span>  
 <span data-ttu-id="14a21-126">사용 하는 방법을 보여 주는 다음 예제는  **\<cryptoNameMapping >** 암호화 클래스를 참조 하 고 런타임을 구성 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="14a21-126">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="14a21-127">"RSA" 문자열을 전달할 수 있습니다는 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 메서드 및 사용법은 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> 반환 하는 메서드는 `MyCryptoRSAClass` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="14a21-127">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="14a21-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="14a21-128">See Also</span></span>  
 [<span data-ttu-id="14a21-129">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="14a21-129">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="14a21-130">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="14a21-130">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="14a21-131">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="14a21-131">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="14a21-132">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="14a21-132">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
