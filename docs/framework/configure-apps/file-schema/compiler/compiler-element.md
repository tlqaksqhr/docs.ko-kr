---
title: '&lt;컴파일러&gt; 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler
helpviewer_keywords:
- compiler configuration elements, <compiler> element
- <compiler> element
- compiler configuration attributes
- compiler element
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b033e26d64f23398a4da6842bb4688cc94627d68
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754495"
---
# <a name="ltcompilergt-element"></a><span data-ttu-id="1e914-102">&lt;컴파일러&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="1e914-102">&lt;compiler&gt; Element</span></span>
<span data-ttu-id="1e914-103">언어 공급자에 대한 컴파일러 구성 특성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-103">Specifies the compiler configuration attributes for a language provider.</span></span>  
  
 <span data-ttu-id="1e914-104">\<구성 요소 ></span><span class="sxs-lookup"><span data-stu-id="1e914-104">\<configuration Element></span></span>  
<span data-ttu-id="1e914-105">\<system.codedom Element></span><span class="sxs-lookup"><span data-stu-id="1e914-105">\<system.codedom Element></span></span>  
<span data-ttu-id="1e914-106">\<컴파일러 요소 ></span><span class="sxs-lookup"><span data-stu-id="1e914-106">\<compilers Element></span></span>  
<span data-ttu-id="1e914-107">\<컴파일러 > 요소</span><span class="sxs-lookup"><span data-stu-id="1e914-107">\<compiler> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e914-108">구문</span><span class="sxs-lookup"><span data-stu-id="1e914-108">Syntax</span></span>  
  
```xml  
<compiler  
  language="languageName[;...;...]"  
  extension="fileExtension[;...;...]"  
  type="typeName, assemblyName"  
  warningLevel="number"  
  compilerOptions="option1 option2"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e914-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1e914-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1e914-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e914-111">특성</span><span class="sxs-lookup"><span data-stu-id="1e914-111">Attributes</span></span>  
  
|<span data-ttu-id="1e914-112">특성</span><span class="sxs-lookup"><span data-stu-id="1e914-112">Attribute</span></span>|<span data-ttu-id="1e914-113">설명</span><span class="sxs-lookup"><span data-stu-id="1e914-113">Description</span></span>|  
|---------------|-----------------|  
|`compilerOptions`|<span data-ttu-id="1e914-114">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="1e914-115">컴파일에 대 한 추가 컴파일러 관련 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-115">Specifies additional compiler-specific arguments for compilation.</span></span> <span data-ttu-id="1e914-116">에 대 한 값은 `compilerOptions` 특성은 일반적으로 컴파일러에 대 한 컴파일러 옵션 항목에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-116">The values for the `compilerOptions` attribute are typically listed in a compiler options topic for the compiler.</span></span> <span data-ttu-id="1e914-117">Visual Studio 2005 설명서 색인에서 "컴파일러 옵션"을 검색 하 여 컴파일러에 대 한 옵션을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-117">In the Visual Studio 2005 documentation, you can locate the options for the compiler by looking for "compiler options" in the index.</span></span>|  
|`extension`|<span data-ttu-id="1e914-118">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="1e914-119">언어 공급자에 대 한 소스 파일에서 사용 하는 파일 이름 확장명의 세미콜론으로 구분 된 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-119">Provides a semicolon-separated list of file name extensions used by source files for the language provider.</span></span> <span data-ttu-id="1e914-120">예를 들어 ".cs"가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-120">For example, ".cs".</span></span>|  
|`language`|<span data-ttu-id="1e914-121">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-121">Required attribute.</span></span><br /><br /> <span data-ttu-id="1e914-122">언어 공급자에서 지 원하는 언어 이름의 세미콜론으로 구분 된 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-122">Provides a semicolon-separated list of language names supported by the language provider.</span></span> <span data-ttu-id="1e914-123">예, "c#, cs, csharp"입니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-123">For example, "c#;cs;csharp".</span></span>|  
|`type`|<span data-ttu-id="1e914-124">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-124">Required attribute.</span></span><br /><br /> <span data-ttu-id="1e914-125">공급자 구현을 포함 하는 어셈블리의 이름을 포함 하 여 언어 공급자의 유형 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-125">Specifies the type name of the language provider, including the name of the assembly containing the provider implementation.</span></span> <span data-ttu-id="1e914-126">형식 이름에 정의 된 요구 사항에 맞아야 [정규화 된 형식 이름 지정](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-126">The type name must meet the requirements defined in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`warningLevel`|<span data-ttu-id="1e914-127">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-127">Optional attribute.</span></span><br /><br /> <span data-ttu-id="1e914-128">기본 컴파일러 경고 수준을;를 지정합니다. 컴파일 경고를 오류로 언어 공급자는 처리 수준을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-128">Specifies the default compiler warning level; determines the level at which the language provider treats compilation warnings as errors.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1e914-129">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1e914-129">Child Elements</span></span>  
  
|<span data-ttu-id="1e914-130">요소</span><span class="sxs-lookup"><span data-stu-id="1e914-130">Element</span></span>|<span data-ttu-id="1e914-131">설명</span><span class="sxs-lookup"><span data-stu-id="1e914-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e914-132">\<providerOption > 요소</span><span class="sxs-lookup"><span data-stu-id="1e914-132">\<providerOption> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/provideroption-element.md)|<span data-ttu-id="1e914-133">언어 공급자에 대 한 컴파일러 버전 특성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-133">Specifies compiler version attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1e914-134">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1e914-134">Parent Elements</span></span>  
  
|<span data-ttu-id="1e914-135">요소</span><span class="sxs-lookup"><span data-stu-id="1e914-135">Element</span></span>|<span data-ttu-id="1e914-136">설명</span><span class="sxs-lookup"><span data-stu-id="1e914-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e914-137">\<configuration> 요소</span><span class="sxs-lookup"><span data-stu-id="1e914-137">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="1e914-138">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="1e914-139">\<system.codedom > 요소</span><span class="sxs-lookup"><span data-stu-id="1e914-139">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="1e914-140">사용 가능한 언어 공급자에 대한 컴파일러 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-140">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="1e914-141">\<컴파일러 > 요소</span><span class="sxs-lookup"><span data-stu-id="1e914-141">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="1e914-142">컴파일러 구성 요소;에 대 한 컨테이너 0 개 이상 포함 되어 있는 `<compiler>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-142">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e914-143">설명</span><span class="sxs-lookup"><span data-stu-id="1e914-143">Remarks</span></span>  
 <span data-ttu-id="1e914-144">각 `<compiler>` 요소는 특정 언어 공급자에 대 한 컴파일러 구성 특성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-144">Each `<compiler>` element specifies the compiler configuration attributes for a specific language provider.</span></span> <span data-ttu-id="1e914-145">공급자 확장는 <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> ; 특정 언어에 대 한 클래스는 `<compiler>` 요소 컴파일러 및 언어 공급자에 대 한 코드 생성기 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-145">The provider extends the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> class for a specific language; the `<compiler>` element defines the compiler and code generator settings for the language provider.</span></span>  
  
 <span data-ttu-id="1e914-146">.NET Framework는 컴퓨터 구성 파일(Machine.config)의 초기 컴파일러 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-146">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="1e914-147">개발자 및 컴파일러 공급업체는 새로운 <xref:System.CodeDom.Compiler.CodeDomProvider> 구현에 대한 구성 설정을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-147">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="1e914-148"><xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> 메서드를 사용하여 컴퓨터에서 언어 공급자 및 컴파일러 구성 설정을 프로그래밍 방식으로 열거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-148">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
 <span data-ttu-id="1e914-149">응용 프로그램 또는 웹 구성 파일에서 컴파일러 요소 보완 하거나 컴퓨터 구성 파일의 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-149">Compiler elements in the application or Web configuration file can supplement or override the settings in the machine configuration file.</span></span> <span data-ttu-id="1e914-150">둘 이상의 공급자 구현의 같은 언어 이름 또는 파일 확장명에 대해 구성 된 경우 마지막으로 일치 하는 구성을 해당 언어 이름 또는 파일 확장명에 대 한 모든 이전 구성 된 공급자를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-150">If more than one provider implementation is configured for the same language name or the same file extension, the last matching configuration overrides any previous configured providers for that language name or file extension.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="1e914-151">구성 파일</span><span class="sxs-lookup"><span data-stu-id="1e914-151">Configuration File</span></span>  
 <span data-ttu-id="1e914-152">컴퓨터 구성 파일 및 응용 프로그램 구성 파일에서이 요소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-152">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e914-153">예제</span><span class="sxs-lookup"><span data-stu-id="1e914-153">Example</span></span>  
 <span data-ttu-id="1e914-154">다음 예제는 일반적인 컴파일러 구성 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1e914-154">The following example illustrates a typical compiler configuration element.</span></span>  
  
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
        warningLevel="1" />  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1e914-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e914-155">See Also</span></span>  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [<span data-ttu-id="1e914-156">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="1e914-156">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="1e914-157">\<컴파일러 > 요소</span><span class="sxs-lookup"><span data-stu-id="1e914-157">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
 [<span data-ttu-id="1e914-158">정규화된 형식 이름 지정</span><span class="sxs-lookup"><span data-stu-id="1e914-158">Specifying Fully Qualified Type Names</span></span>](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)  
 <span data-ttu-id="1e914-159">[요소 (ASP.NET 설정 스키마) 컴파일에 대 한 컴파일러에 대 한 컴파일러](https://msdn.microsoft.com/library/f7d6b078-5d42-4134-b3f7-62e1aba1df1e(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1e914-159">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://msdn.microsoft.com/library/f7d6b078-5d42-4134-b3f7-62e1aba1df1e(v=vs.100))</span></span>
