---
title: '&lt;providerOption&gt; 요소'
ms.date: 03/30/2017
f1_keywords:
- provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: fa3410cc2c8812c59528676bfad6cd7e887c5f73
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746399"
---
# <a name="ltprovideroptiongt-element"></a><span data-ttu-id="74cb2-102">&lt;providerOption&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="74cb2-102">&lt;providerOption&gt; Element</span></span>
<span data-ttu-id="74cb2-103">언어 공급자에 대 한 컴파일러 버전 특성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="74cb2-103">Specifies the compiler version attributes for a language provider.</span></span>  
  
 <span data-ttu-id="74cb2-104">\<구성 요소 ></span><span class="sxs-lookup"><span data-stu-id="74cb2-104">\<configuration Element></span></span>  
<span data-ttu-id="74cb2-105">\<system.codedom Element></span><span class="sxs-lookup"><span data-stu-id="74cb2-105">\<system.codedom Element></span></span>  
<span data-ttu-id="74cb2-106">\<컴파일러 요소 ></span><span class="sxs-lookup"><span data-stu-id="74cb2-106">\<compilers Element></span></span>  
<span data-ttu-id="74cb2-107">\<컴파일러 > 요소</span><span class="sxs-lookup"><span data-stu-id="74cb2-107">\<compiler> Element</span></span>  
<span data-ttu-id="74cb2-108">\<providerOption > 요소</span><span class="sxs-lookup"><span data-stu-id="74cb2-108">\<providerOption> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74cb2-109">구문</span><span class="sxs-lookup"><span data-stu-id="74cb2-109">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74cb2-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="74cb2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="74cb2-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="74cb2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74cb2-112">특성</span><span class="sxs-lookup"><span data-stu-id="74cb2-112">Attributes</span></span>  
  
|<span data-ttu-id="74cb2-113">특성</span><span class="sxs-lookup"><span data-stu-id="74cb2-113">Attribute</span></span>|<span data-ttu-id="74cb2-114">설명</span><span class="sxs-lookup"><span data-stu-id="74cb2-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="74cb2-115">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="74cb2-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="74cb2-116">옵션;의 이름을 지정합니다. 예를 들어 "CompilerVersion"가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74cb2-116">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="74cb2-117">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="74cb2-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="74cb2-118">옵션;에 대 한 값을 지정합니다. 예를 들어 "v3.5"가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74cb2-118">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="74cb2-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="74cb2-119">Child Elements</span></span>  
 <span data-ttu-id="74cb2-120">없음</span><span class="sxs-lookup"><span data-stu-id="74cb2-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="74cb2-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="74cb2-121">Parent Elements</span></span>  
  
|<span data-ttu-id="74cb2-122">요소</span><span class="sxs-lookup"><span data-stu-id="74cb2-122">Element</span></span>|<span data-ttu-id="74cb2-123">설명</span><span class="sxs-lookup"><span data-stu-id="74cb2-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74cb2-124">\<configuration> 요소</span><span class="sxs-lookup"><span data-stu-id="74cb2-124">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="74cb2-125">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="74cb2-125">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="74cb2-126">\<system.codedom > 요소</span><span class="sxs-lookup"><span data-stu-id="74cb2-126">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="74cb2-127">사용 가능한 언어 공급자에 대한 컴파일러 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="74cb2-127">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="74cb2-128">\<컴파일러 > 요소</span><span class="sxs-lookup"><span data-stu-id="74cb2-128">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="74cb2-129">컴파일러 구성 요소;에 대 한 컨테이너 0 개 이상 포함 되어 있는 `<compiler>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="74cb2-129">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|[<span data-ttu-id="74cb2-130">\<compiler> 요소</span><span class="sxs-lookup"><span data-stu-id="74cb2-130">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|<span data-ttu-id="74cb2-131">언어 공급자에 대한 컴파일러 구성 특성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="74cb2-131">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74cb2-132">설명</span><span class="sxs-lookup"><span data-stu-id="74cb2-132">Remarks</span></span>  
 <span data-ttu-id="74cb2-133">.NET Framework 버전 3.5 코드 문서 개체 모델 (CodeDOM) 코드 공급자를 지원할 수 있습니다 공급자별 옵션 사용 하 여는 `<providerOption>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="74cb2-133">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="74cb2-134">.NET Framework 3.5는.NET Framework 2.0 어셈블리 업데이트를 포함 하 고 새 형식을 포함 하는 새 버전 3.5 어셈블리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="74cb2-134">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="74cb2-135">Microsoft C# 및 Visual Basic 코드 공급자는.NET Framework 2.0 어셈블리에 포함 되어 있지만 컴파일러 버전 3.5 지원 하도록 업데이트 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="74cb2-135">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="74cb2-136">기본적으로 업데이트 된 코드 공급자 버전 2.0 컴파일러에 대 한 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="74cb2-136">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="74cb2-137">사용할 수는 `<providerOption>` 3.5를 대상 컴파일러 버전을 변경 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="74cb2-137">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="74cb2-138">이 작업을 수행 하려면 "CompilerVersion"를 지정 하는 `name` 특성과 "v3.5"에 대 한는 `value` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="74cb2-138">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="74cb2-139">소문자 "v" 버전 번호를 앞에 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74cb2-139">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="74cb2-140">가능 버전 사양을 글로벌 추가 하 여는 `<providerOption>` 요소는.NET Framework 2.0 Machine.config 또는 루트 Web.config 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="74cb2-140">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="74cb2-141">Machine.config 파일에 3.5로 기본 컴파일러 버전을 업데이트 하는 경우 변경할 수 있습니다 응용 프로그램별 별로 2.0으로 다시 사용 하 여는 `<providerOption>` 응용 프로그램 구성 파일의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="74cb2-141">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="74cb2-142">CodeDOM 코드 공급자 구현자를 취하는 생성자를 제공 하 여 사용자 지정 옵션을 처리할 수는 `providerOptions` 형식의 매개 변수 <xref:System.Collections.Generic.IDictionary%602>합니다.</span><span class="sxs-lookup"><span data-stu-id="74cb2-142">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74cb2-143">예제</span><span class="sxs-lookup"><span data-stu-id="74cb2-143">Example</span></span>  
 <span data-ttu-id="74cb2-144">다음 예제에서는 C# 코드 공급자의 버전 3.5를 사용할지를 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="74cb2-144">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler  
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=2.0.3600.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions="/optimize"  
        warningLevel="1" >  
          <providerOption  
            name="CompilerVersion"  
            value="v3.5" />  
      </compiler>  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="74cb2-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="74cb2-145">See Also</span></span>  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [<span data-ttu-id="74cb2-146">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="74cb2-146">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="74cb2-147">\<컴파일러 > 요소</span><span class="sxs-lookup"><span data-stu-id="74cb2-147">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
 [<span data-ttu-id="74cb2-148">정규화된 형식 이름 지정</span><span class="sxs-lookup"><span data-stu-id="74cb2-148">Specifying Fully Qualified Type Names</span></span>](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)  
 [<span data-ttu-id="74cb2-149">요소 (ASP.NET 설정 스키마) 컴파일에 대 한 컴파일러에 대 한 컴파일러</span><span class="sxs-lookup"><span data-stu-id="74cb2-149">compiler Element for compilers for compilation (ASP.NET Settings Schema)</span></span>](http://msdn.microsoft.com/library/f7d6b078-5d42-4134-b3f7-62e1aba1df1e)
