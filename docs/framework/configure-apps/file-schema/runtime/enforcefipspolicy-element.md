---
title: '&lt;enforceFIPSPolicy&gt; 요소'
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9040bf2548964cf6df5f4fd87ee9f6d979c7df1e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltenforcefipspolicygt-element"></a><span data-ttu-id="4293a-102">&lt;enforceFIPSPolicy&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="4293a-102">&lt;enforceFIPSPolicy&gt; Element</span></span>
<span data-ttu-id="4293a-103">암호화 알고리즘이 FIPS(Federal Information Processing Standards)를 준수해야 하는 컴퓨터 구성 요구 사항을 적용할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4293a-103">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
 <span data-ttu-id="4293a-104">\<구성 > 요소</span><span class="sxs-lookup"><span data-stu-id="4293a-104">\<configuration> Element</span></span>  
<span data-ttu-id="4293a-105">\<런타임 > 요소</span><span class="sxs-lookup"><span data-stu-id="4293a-105">\<runtime> Element</span></span>  
<span data-ttu-id="4293a-106">\<enforceFIPSPolicy > 요소</span><span class="sxs-lookup"><span data-stu-id="4293a-106">\<enforceFIPSPolicy> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4293a-107">구문</span><span class="sxs-lookup"><span data-stu-id="4293a-107">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4293a-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4293a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4293a-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4293a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4293a-110">특성</span><span class="sxs-lookup"><span data-stu-id="4293a-110">Attributes</span></span>  
  
|<span data-ttu-id="4293a-111">특성</span><span class="sxs-lookup"><span data-stu-id="4293a-111">Attribute</span></span>|<span data-ttu-id="4293a-112">설명</span><span class="sxs-lookup"><span data-stu-id="4293a-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4293a-113">사용</span><span class="sxs-lookup"><span data-stu-id="4293a-113">enabled</span></span>|<span data-ttu-id="4293a-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="4293a-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="4293a-115">암호화 알고리즘이 FIPS와 호환 되도록 컴퓨터 구성 요구 사항의 적용을 사용할 것인지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4293a-115">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="4293a-116">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="4293a-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="4293a-117">값</span><span class="sxs-lookup"><span data-stu-id="4293a-117">Value</span></span>|<span data-ttu-id="4293a-118">설명</span><span class="sxs-lookup"><span data-stu-id="4293a-118">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="4293a-119">컴퓨터가 fips 호환 암호화 알고리즘을 요구 하도록 구성 하는 경우 해당 요구 사항이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4293a-119">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="4293a-120">클래스에 FIPS를 생성자와 호환 되지 않는 알고리즘을 구현 하는 경우 또는 `Create` 해당 클래스에 대 한 메서드는 해당 컴퓨터에서 실행 될 때 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="4293a-120">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="4293a-121">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="4293a-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="4293a-122">응용 프로그램에서 사용 되는 암호화 알고리즘 컴퓨터 구성에 관계 없이 FIPS와 호환 되도록 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4293a-122">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4293a-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4293a-123">Child Elements</span></span>  
 <span data-ttu-id="4293a-124">없음</span><span class="sxs-lookup"><span data-stu-id="4293a-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4293a-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4293a-125">Parent Elements</span></span>  
  
|<span data-ttu-id="4293a-126">요소</span><span class="sxs-lookup"><span data-stu-id="4293a-126">Element</span></span>|<span data-ttu-id="4293a-127">설명</span><span class="sxs-lookup"><span data-stu-id="4293a-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4293a-128">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4293a-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4293a-129">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4293a-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4293a-130">설명</span><span class="sxs-lookup"><span data-stu-id="4293a-130">Remarks</span></span>  
 <span data-ttu-id="4293a-131">.NET Framework 2.0 부터는 암호화 알고리즘을 구현 하는 클래스의 생성 하는 컴퓨터의 구성에 의해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4293a-131">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="4293a-132">컴퓨터 FIPS를 준수 해야 하는 알고리즘을 요구 하도록 구성 된 FIPS와 호환 되지 않는 알고리즘을 구현 하는 클래스를 해당 클래스의 인스턴스를 만들려고 시도 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4293a-132">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="4293a-133">생성자를 throw는 <xref:System.InvalidOperationException> 예외를 및 `Create` 메서드에서 throw 한 <xref:System.Reflection.TargetInvocationException> 예외는 내부 조인 된 <xref:System.InvalidOperationException> 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="4293a-133">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="4293a-134">경우 응용 프로그램이 해당 구성을 사용 해야 하는 컴퓨터에서 실행 응용 프로그램을 사용 하 여 FIPS와 호환 되지 않는 알고리즘을 사용할 수 있습니다이 요소 프로그램 구성 파일에서에서 공용 언어 런타임 (CLR)을 방지 하기 위해 FIPS 준수를 강제 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4293a-134">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="4293a-135">에 도입 된이 요소는 [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="4293a-135">This element was introduced in the [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="4293a-136">예제</span><span class="sxs-lookup"><span data-stu-id="4293a-136">Example</span></span>  
 <span data-ttu-id="4293a-137">다음 예제에는 CLR FIPS 준수를 강제 적용 하지 못하도록 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4293a-137">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4293a-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4293a-138">See Also</span></span>  
 [<span data-ttu-id="4293a-139">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="4293a-139">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="4293a-140">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="4293a-140">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="4293a-141">암호화 모델</span><span class="sxs-lookup"><span data-stu-id="4293a-141">Cryptography Model</span></span>](../../../../../docs/standard/security/cryptography-model.md)
