---
title: '&lt;cryptoNameMapping&gt; 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoNameMapping
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping
helpviewer_keywords:
- <cryptoNameMapping> element
- cryptoNameMapping element
ms.assetid: c59c9494-149b-4ce6-b38d-371f896ae85c
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f6811a2dbd8859a8765c5e855e0fe423bd31f287
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33359389"
---
# <a name="ltcryptonamemappinggt-element"></a><span data-ttu-id="8c56c-102">&lt;cryptoNameMapping&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="8c56c-102">&lt;cryptoNameMapping&gt; Element</span></span>
<span data-ttu-id="8c56c-103">이름에 대한 클래스의 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c56c-103">Contains mappings of classes to friendly names.</span></span>  
  
 <span data-ttu-id="8c56c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8c56c-104">\<configuration></span></span>  
<span data-ttu-id="8c56c-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="8c56c-105">\<mscorlib></span></span>  
<span data-ttu-id="8c56c-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="8c56c-106">\<cryptographySettings></span></span>  
<span data-ttu-id="8c56c-107">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="8c56c-107">\<cryptoNameMapping></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c56c-108">구문</span><span class="sxs-lookup"><span data-stu-id="8c56c-108">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>   
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c56c-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8c56c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8c56c-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c56c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c56c-111">특성</span><span class="sxs-lookup"><span data-stu-id="8c56c-111">Attributes</span></span>  
 <span data-ttu-id="8c56c-112">없음</span><span class="sxs-lookup"><span data-stu-id="8c56c-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8c56c-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8c56c-113">Child Elements</span></span>  
  
|<span data-ttu-id="8c56c-114">요소</span><span class="sxs-lookup"><span data-stu-id="8c56c-114">Element</span></span>|<span data-ttu-id="8c56c-115">설명</span><span class="sxs-lookup"><span data-stu-id="8c56c-115">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="8c56c-116">**\<nameEntry>** 요소에 있는 이름에 매핑되는 암호화 클래스의 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c56c-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="8c56c-117">클래스 이름을 알고리즘 이름에 매핑하며, 이를 통해 하나의 클래스가 여러 이름을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c56c-117">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8c56c-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8c56c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="8c56c-119">요소</span><span class="sxs-lookup"><span data-stu-id="8c56c-119">Element</span></span>|<span data-ttu-id="8c56c-120">설명</span><span class="sxs-lookup"><span data-stu-id="8c56c-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8c56c-121">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8c56c-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="8c56c-122">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c56c-122">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="8c56c-123">이름에 대한 클래스의 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c56c-123">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="8c56c-124">포함 된 \<cryptographySettings > 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8c56c-124">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8c56c-125">예제</span><span class="sxs-lookup"><span data-stu-id="8c56c-125">Example</span></span>  
 <span data-ttu-id="8c56c-126">사용 하는 방법을 보여 주는 다음 예제는  **\<cryptoNameMapping >** 암호화 클래스를 참조 하 고 런타임을 구성 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8c56c-126">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="8c56c-127">"RSA" 문자열을 전달할 수 있습니다는 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 메서드 및 사용법은 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> 반환 하는 메서드는 `MyCryptoRSAClass` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8c56c-127">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8c56c-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c56c-128">See Also</span></span>  
 [<span data-ttu-id="8c56c-129">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="8c56c-129">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="8c56c-130">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="8c56c-130">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="8c56c-131">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="8c56c-131">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="8c56c-132">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="8c56c-132">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
