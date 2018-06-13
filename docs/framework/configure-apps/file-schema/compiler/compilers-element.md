---
title: '&lt;컴파일러&gt; 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compilers
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers
helpviewer_keywords:
- compiler configuration elements, <compilers> element
- <compilers> element
- compilers element
ms.assetid: d40fba59-98f9-4783-ae0c-2ebea27ce77b
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: fc85610f5c3db7929f824fda2dd211300d9b05c1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32742993"
---
# <a name="ltcompilersgt-element"></a><span data-ttu-id="bb592-102">&lt;컴파일러&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="bb592-102">&lt;compilers&gt; Element</span></span>
<span data-ttu-id="bb592-103">컴파일러 구성 요소용 컨테이너입니다. 0개 이상의 [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb592-103">Container for compiler configuration elements; contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span>  
  
 <span data-ttu-id="bb592-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bb592-104">\<configuration></span></span>  
<span data-ttu-id="bb592-105">\<system.codedom ></span><span class="sxs-lookup"><span data-stu-id="bb592-105">\<system.codedom></span></span>  
<span data-ttu-id="bb592-106">\<컴파일러 > 요소</span><span class="sxs-lookup"><span data-stu-id="bb592-106">\<compilers> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb592-107">구문</span><span class="sxs-lookup"><span data-stu-id="bb592-107">Syntax</span></span>  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb592-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bb592-108">Attributes and Elements</span></span>  
 <span data-ttu-id="bb592-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb592-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb592-110">특성</span><span class="sxs-lookup"><span data-stu-id="bb592-110">Attributes</span></span>  
 <span data-ttu-id="bb592-111">없음</span><span class="sxs-lookup"><span data-stu-id="bb592-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bb592-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bb592-112">Child Elements</span></span>  
  
|<span data-ttu-id="bb592-113">요소</span><span class="sxs-lookup"><span data-stu-id="bb592-113">Element</span></span>|<span data-ttu-id="bb592-114">설명</span><span class="sxs-lookup"><span data-stu-id="bb592-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bb592-115">\<compiler> 요소</span><span class="sxs-lookup"><span data-stu-id="bb592-115">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|<span data-ttu-id="bb592-116">언어 공급자에 대한 컴파일러 구성 특성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bb592-116">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bb592-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bb592-117">Parent Elements</span></span>  
  
|<span data-ttu-id="bb592-118">요소</span><span class="sxs-lookup"><span data-stu-id="bb592-118">Element</span></span>|<span data-ttu-id="bb592-119">설명</span><span class="sxs-lookup"><span data-stu-id="bb592-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bb592-120">\<configuration> 요소</span><span class="sxs-lookup"><span data-stu-id="bb592-120">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="bb592-121">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="bb592-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="bb592-122">\<system.codedom > 요소</span><span class="sxs-lookup"><span data-stu-id="bb592-122">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="bb592-123">사용 가능한 언어 공급자에 대한 컴파일러 구성 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bb592-123">Specifies compiler configuration settings for available language providers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb592-124">설명</span><span class="sxs-lookup"><span data-stu-id="bb592-124">Remarks</span></span>  
 <span data-ttu-id="bb592-125">[ \<컴파일러 >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) 요소는 컴퓨터의 언어 공급자에 대 한 컴파일러 구성 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb592-125">The [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="bb592-126">각 [ \<컴파일러 >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) 요소는 특정 언어 공급자에 대 한 컴파일러 구성 특성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb592-126">Each [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="bb592-127">.NET Framework 컴퓨터 구성 파일 (Machine.config)에서 초기 컴파일러 및 언어 공급자 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bb592-127">The .NET Framework defines the initial compiler and language provider settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="bb592-128">개발자 및 컴파일러 공급업체는 새로운 <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> 구현에 대한 구성 설정을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb592-128">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="bb592-129"><xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> 메서드를 사용하여 컴퓨터에서 언어 공급자 및 컴파일러 구성 설정을 프로그래밍 방식으로 열거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb592-129">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="bb592-130">구성 파일</span><span class="sxs-lookup"><span data-stu-id="bb592-130">Configuration File</span></span>  
 <span data-ttu-id="bb592-131">컴퓨터 구성 파일 및 응용 프로그램 구성 파일에서이 요소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb592-131">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb592-132">예제</span><span class="sxs-lookup"><span data-stu-id="bb592-132">Example</span></span>  
 <span data-ttu-id="bb592-133">다음 예제는 일반적인 컴파일러 구성 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb592-133">The following example illustrates a typical compiler configuration element.</span></span>  
  
```xml  
<configuration>  
   <system.codedom>  
     <compilers>  
       <!-- zero or more compiler elements -->  
       <compiler   
          language="c#;cs;csharp"   
          extension=".cs"  
          type="Microsoft.CSharp.CSharpCodeProvider, System, Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
          compilerOptions=""    
          warningLevel="1" />  
     </compilers>  
   </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bb592-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb592-134">See Also</span></span>  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [<span data-ttu-id="bb592-135">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="bb592-135">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="bb592-136">컴파일러 및 언어 공급자 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="bb592-136">Compiler and Language Provider Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/index.md)  
 [<span data-ttu-id="bb592-137">\<compiler> 요소</span><span class="sxs-lookup"><span data-stu-id="bb592-137">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)
