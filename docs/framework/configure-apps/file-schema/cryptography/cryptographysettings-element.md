---
title: "&lt;cryptographySettings&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptographySettings
helpviewer_keywords:
- cryptographySettings element
- <cryptographySettings> element
ms.assetid: 6201b7da-bcb7-49f7-b9f5-ba1fe05573b9
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 73a4f362be1612658e6911b7e7ea7a6c3e670e01
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltcryptographysettingsgt-element"></a><span data-ttu-id="a2821-102">&lt;cryptographySettings&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="a2821-102">&lt;cryptographySettings&gt; Element</span></span>
<span data-ttu-id="a2821-103">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2821-103">Contains cryptography settings.</span></span>  
  
 <span data-ttu-id="a2821-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a2821-104">\<configuration></span></span>  
<span data-ttu-id="a2821-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="a2821-105">\<mscorlib></span></span>  
<span data-ttu-id="a2821-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="a2821-106">\<cryptographySettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2821-107">구문</span><span class="sxs-lookup"><span data-stu-id="a2821-107">Syntax</span></span>  
  
```xml  
      <cryptographySettings>   
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2821-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a2821-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a2821-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a2821-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2821-110">특성</span><span class="sxs-lookup"><span data-stu-id="a2821-110">Attributes</span></span>  
 <span data-ttu-id="a2821-111">없음</span><span class="sxs-lookup"><span data-stu-id="a2821-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a2821-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a2821-112">Child Elements</span></span>  
  
|<span data-ttu-id="a2821-113">요소</span><span class="sxs-lookup"><span data-stu-id="a2821-113">Element</span></span>|<span data-ttu-id="a2821-114">설명</span><span class="sxs-lookup"><span data-stu-id="a2821-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2821-115">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="a2821-115">\<cryptoNameMapping></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)|<span data-ttu-id="a2821-116">이름에 대한 클래스의 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2821-116">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="a2821-117">\<oidMap ></span><span class="sxs-lookup"><span data-stu-id="a2821-117">\<oidMap></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)|<span data-ttu-id="a2821-118">클래스에 ASN.1 개체 식별자 (OID) 매핑을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a2821-118">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a2821-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a2821-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a2821-120">요소</span><span class="sxs-lookup"><span data-stu-id="a2821-120">Element</span></span>|<span data-ttu-id="a2821-121">설명</span><span class="sxs-lookup"><span data-stu-id="a2821-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a2821-122">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a2821-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`mscorlib`|<span data-ttu-id="a2821-123">포함 된 `cryptographySettings` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a2821-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a2821-124">예</span><span class="sxs-lookup"><span data-stu-id="a2821-124">Example</span></span>  
 <span data-ttu-id="a2821-125">다음 방법을 보여 주는 예제는  **\<cryptographySettings >** 암호화 이름 매핑 및 OID 매핑을 포함 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a2821-125">The following example shows how use the **\<cryptographySettings>** element to contain cryptography name mappings and OID mappings.</span></span> <span data-ttu-id="a2821-126">이 예제에서는 런타임에 구성 되도록 <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> 반환는 `MyHashClass` 개체 및 `MyCryptoClass` 클래스 1.3.36.2.1 개체 식별자에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2821-126">This example configures the runtime so that <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> returns a `MyHashClass` object and the `MyCryptoClass` class maps to the object identifier 1.3.36.2.1.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyHash="MyHashClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MyHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a2821-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2821-127">See Also</span></span>  
 [<span data-ttu-id="a2821-128">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="a2821-128">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="a2821-129">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="a2821-129">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="a2821-130">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="a2821-130">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
