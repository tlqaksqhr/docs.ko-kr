---
title: -langversion(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
ms.openlocfilehash: 523636663744acbbc85a08ebe3535f066e7dc160
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="-langversion-c-compiler-options"></a><span data-ttu-id="0c358-102">-langversion(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="0c358-102">-langversion (C# Compiler Options)</span></span>
<span data-ttu-id="0c358-103">컴파일러가 선택한 C# 언어 사양에 포함된 구문만 허용하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c358-103">Causes the compiler to accept only syntax that is included in the chosen C# language specification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c358-104">구문</span><span class="sxs-lookup"><span data-stu-id="0c358-104">Syntax</span></span>  
  
```console  
-langversion:option  
```  
  
## <a name="arguments"></a><span data-ttu-id="0c358-105">인수</span><span class="sxs-lookup"><span data-stu-id="0c358-105">Arguments</span></span>  
 `option`  
 <span data-ttu-id="0c358-106">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0c358-106">The following values are valid:</span></span>  
  
|<span data-ttu-id="0c358-107">옵션</span><span class="sxs-lookup"><span data-stu-id="0c358-107">Option</span></span>|<span data-ttu-id="0c358-108">의미</span><span class="sxs-lookup"><span data-stu-id="0c358-108">Meaning</span></span>|  
|------------|-------------|  
|<span data-ttu-id="0c358-109">default</span><span class="sxs-lookup"><span data-stu-id="0c358-109">default</span></span>|<span data-ttu-id="0c358-110">컴파일러는 지원할 수 있는 최신 주 버전의 유효한 언어 구문을 모두 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="0c358-110">The compiler accepts all valid language syntax from the latest major version that it can support.</span></span> <span data-ttu-id="0c358-111"><sup id="TDefault">[Default](#FDefault)</sup></span><span class="sxs-lookup"><span data-stu-id="0c358-111"><sup id="TDefault">[Default](#FDefault)</sup></span></span>| 
|<span data-ttu-id="0c358-112">ISO-1</span><span class="sxs-lookup"><span data-stu-id="0c358-112">ISO-1</span></span>|<span data-ttu-id="0c358-113">컴파일러가 ISO/IEC 23270:2003 C#(1.0/1.1)에 포함된 구문만 허용합니다. <sup id="TISO1">[ISO1](#FISO1)</sup></span><span class="sxs-lookup"><span data-stu-id="0c358-113">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.1) <sup id="TISO1">[ISO1](#FISO1)</sup></span></span>|  
|<span data-ttu-id="0c358-114">ISO-2</span><span class="sxs-lookup"><span data-stu-id="0c358-114">ISO-2</span></span>|<span data-ttu-id="0c358-115">컴파일러가 ISO/IEC 23270:2006 C#(2.0)에 포함된 구문만 허용합니다. <sup id="TISO2">[ISO2](#FISO2)</sup></span><span class="sxs-lookup"><span data-stu-id="0c358-115">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0) <sup id="TISO2">[ISO2](#FISO2)</sup></span></span>|
|<span data-ttu-id="0c358-116">3</span><span class="sxs-lookup"><span data-stu-id="0c358-116">3</span></span>|<span data-ttu-id="0c358-117">컴파일러가 C# 3.0 또는 이전 버전에 포함된 구문만 허용합니다. <sup id="TCS3">[CS3](#FCS3)</sup></span><span class="sxs-lookup"><span data-stu-id="0c358-117">The compiler accepts only syntax that is included in C# 3.0 or lower <sup id="TCS3">[CS3](#FCS3)</sup></span></span>|
|<span data-ttu-id="0c358-118">4</span><span class="sxs-lookup"><span data-stu-id="0c358-118">4</span></span>|<span data-ttu-id="0c358-119">컴파일러가 C# 4.0 또는 이전 버전에 포함된 구문만 허용합니다. <sup id="TCS4">[CS4](#FCS4)</sup></span><span class="sxs-lookup"><span data-stu-id="0c358-119">The compiler accepts only syntax that is included in C# 4.0 or lower <sup id="TCS4">[CS4](#FCS4)</sup></span></span>|
|<span data-ttu-id="0c358-120">5</span><span class="sxs-lookup"><span data-stu-id="0c358-120">5</span></span>|<span data-ttu-id="0c358-121">컴파일러가 C# 5.0 또는 이전 버전에 포함된 구문만 허용합니다. <sup id="TCS5">[CS5](#FCS5)</sup></span><span class="sxs-lookup"><span data-stu-id="0c358-121">The compiler accepts only syntax that is included in C# 5.0 or lower <sup id="TCS5">[CS5](#FCS5)</sup></span></span>|
|<span data-ttu-id="0c358-122">6</span><span class="sxs-lookup"><span data-stu-id="0c358-122">6</span></span>|<span data-ttu-id="0c358-123">컴파일러가 C# 6.0 또는 이전 버전에 포함된 구문만 허용합니다. <sup id="TCS6">[CS6](#FCS6)</sup></span><span class="sxs-lookup"><span data-stu-id="0c358-123">The compiler accepts only syntax that is included in C# 6.0 or lower <sup id="TCS6">[CS6](#FCS6)</sup></span></span>|
|<span data-ttu-id="0c358-124">7</span><span class="sxs-lookup"><span data-stu-id="0c358-124">7</span></span>|<span data-ttu-id="0c358-125">컴파일러가 C# 7.0 또는 이전 버전에 포함된 구문만 허용합니다. <sup id="TCS7">[CS7](#FCS7)</sup></span><span class="sxs-lookup"><span data-stu-id="0c358-125">The compiler accepts only syntax that is included in C# 7.0 or lower <sup id="TCS7">[CS7](#FCS7)</sup></span></span>|
|<span data-ttu-id="0c358-126">latest</span><span class="sxs-lookup"><span data-stu-id="0c358-126">latest</span></span>|<span data-ttu-id="0c358-127">컴파일러가 지원할 수 있는 유효한 언어 구문을 모두 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="0c358-127">The compiler accepts all valid language syntax that it can support.</span></span> <span data-ttu-id="0c358-128"><sup id="TLatest">[Latest](#FLatest)</sup></span><span class="sxs-lookup"><span data-stu-id="0c358-128"><sup id="TLatest">[Latest](#FLatest)</sup></span></span>|
<!--- Uncomment and move these above
|latest| once they're officially released
|7.1|The compiler accepts only syntax that is included in C# 7.1 or lower <sup id="TCS71">[CS71](#FCS71)</sup>|
|7.2|The compiler accepts only syntax that is included in C# 7.2 or lower <sup id="TCS71">[CS72](#FCS72)</sup>|
|8|The compiler accepts only syntax that is included in C# 8 or lower <sup id="TCS71">[CS8](#FCS8)</sup>|
-->

  
## <a name="remarks"></a><span data-ttu-id="0c358-129">설명</span><span class="sxs-lookup"><span data-stu-id="0c358-129">Remarks</span></span>  
 <span data-ttu-id="0c358-130">C# 응용 프로그램에서 참조된 메타데이터에는 **-langversion** 컴파일러 옵션이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c358-130">Metadata referenced by your C# application is not subject to **-langversion** compiler option.</span></span>  
  
 <span data-ttu-id="0c358-131">각 C# 컴파일러 버전에 언어 사양의 확장이 포함되어 있으므로 **-langversion**은 이전 컴파일러 버전의 동등한 기능을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c358-131">Because each version of the C# compiler contains extensions to the language specification, **-langversion** does not give you the equivalent functionality of an earlier version of the compiler.</span></span>  
 
 <span data-ttu-id="0c358-132">또한 C# 버전 업데이트는 일반적으로 주 .NET Framework 릴리스와 일치하는 반면, 새 구문과 기능이 반드시 특정 프레임워크 버전에 연결되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c358-132">Additionally, while C# version updates generally coincide with major .Net Framework releases, the new syntax and features are not necessarily tied to that specific framework version.</span></span> <span data-ttu-id="0c358-133">새로운 기능에는 C# 버전과 함께 릴리스된 새 컴파일러 업데이트가 분명히 필요하지만, 각 특정 기능에 고유한 최소 .Net API 또는 공용 언어 런타임 요구 사항이 있으므로 NuGet 패키지 또는 다른 라이브러리를 포함하여 하위 수준 프레임워크에서 실행이 허용될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c358-133">While the new features will definitely require a new compiler update that is also released alongside the C# revision, each specific feature has its own minimum .Net API or common language runtime requirements that may allow it to run on downlevel frameworks by including NuGet packages or other libraries.</span></span>
  
 <span data-ttu-id="0c358-134">사용하는 **-langversion** 설정과 관계없이 현재 버전의 공용 언어 런타임을 사용하여 고유한 .exe 또는 .dll을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0c358-134">Regardless of which **-langversion** setting you use, you will use the current version of the common language runtime to create your .exe or .dll.</span></span> <span data-ttu-id="0c358-135">한 가지 예외는 friend 어셈블리와 [-moduleassemblyname(C# 컴파일러 옵션)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md)으로, **-langversion:ISO-1**에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="0c358-135">One exception is friend assemblies and [-moduleassemblyname (C# Compiler Option)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md), which work under **-langversion:ISO-1**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="0c358-136">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="0c358-136">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="0c358-137">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0c358-137">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="0c358-138">**빌드** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0c358-138">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="0c358-139">**고급** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0c358-139">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="0c358-140">**언어 버전** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c358-140">Modify the **Language Version** property.</span></span>  
  
 <span data-ttu-id="0c358-141">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0c358-141">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span></span>  
    
## <a name="see-also"></a><span data-ttu-id="0c358-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c358-142">See Also</span></span>  
 [<span data-ttu-id="0c358-143">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="0c358-143">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="0c358-144">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="0c358-144">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 
### <a name="c-language-specification"></a><span data-ttu-id="0c358-145">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="0c358-145">C# Language Specification</span></span>
 <span data-ttu-id="0c358-146">[C# 언어 사양 참조](../../../csharp/language-reference/language-specification/index.md): .NET Foundation</span><span class="sxs-lookup"><span data-stu-id="0c358-146">[C# Language Specification Reference](../../../csharp/language-reference/language-specification/index.md) : .NET Foundation</span></span>  
 <span data-ttu-id="0c358-147">C# 1.0/1.1 [ISO/IEC 23270:2003](https://www.iso.org/standard/36768.html) 정보 기술 - C# 언어 사양: ISO 카탈로그</span><span class="sxs-lookup"><span data-stu-id="0c358-147">C# 1.0/1.1 [ISO/IEC 23270:2003](https://www.iso.org/standard/36768.html) Information technology -- C# Language Specification : ISO Catalogue</span></span>  
 <span data-ttu-id="0c358-148">C# 2.0 [ISO/IEC 23270:2006](https://www.iso.org/standard/42926.html) 정보 기술 - C# 언어 사양: ISO 카탈로그</span><span class="sxs-lookup"><span data-stu-id="0c358-148">C# 2.0 [ISO/IEC 23270:2006](https://www.iso.org/standard/42926.html) Information technology -- C# Language Specification : ISO Catalogue</span></span>  
 <span data-ttu-id="0c358-149">C# 2.0 [c042926_ISO_IEC_23270_2006 (E).zip](http://standards.iso.org/ittf/PubliclyAvailableStandards/c042926_ISO_IEC_23270_2006(E).zip) ISO/IEC 23270:2006(PDF 형식): ISO 자유롭게 사용할 수 있는 표준</span><span class="sxs-lookup"><span data-stu-id="0c358-149">C# 2.0 [c042926_ISO_IEC_23270_2006(E).zip](http://standards.iso.org/ittf/PubliclyAvailableStandards/c042926_ISO_IEC_23270_2006(E).zip) ISO/IEC 23270:2006 in PDF format : ISO Freely Available Standards</span></span>  
 <span data-ttu-id="0c358-150">C# 3.0 [CSharp Language Specification.doc](http://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc) C# 언어 사양 버전 3.0: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="0c358-150">C# 3.0 [CSharp Language Specification.doc](http://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc) C# Language Specification Version 3.0 : Microsoft Corporation</span></span>  
 <span data-ttu-id="0c358-151">C# 4.0 [Ecma-334.pdf](https://www.ecma-international.org/publications/files/ECMA-ST/Ecma-334.pdf) 표준 ECMA-334 네 번째 버전</span><span class="sxs-lookup"><span data-stu-id="0c358-151">C# 4.0 [Ecma-334.pdf](https://www.ecma-international.org/publications/files/ECMA-ST/Ecma-334.pdf) Standard ECMA-334 4th Edition</span></span>    
 <span data-ttu-id="0c358-152">C# 5.0 [CSharp Language Specification.docx](https://www.microsoft.com/download/details.aspx?id=7029) C# 언어 사양 버전 5.0: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="0c358-152">C# 5.0 [CSharp Language Specification.docx](https://www.microsoft.com/download/details.aspx?id=7029) C# Language Specification Version 5.0 : Microsoft Corporation</span></span>  
 <span data-ttu-id="0c358-153">C# 6.0 [README.md](https://github.com/dotnet/csharplang/blob/master/spec/README.md) C# 언어 사양 버전 6 - 비공식 초안: .NET Foundation</span><span class="sxs-lookup"><span data-stu-id="0c358-153">C# 6.0 [README.md](https://github.com/dotnet/csharplang/blob/master/spec/README.md) C# Language Specification Version 6 - Unofficial Draft : .NET Foundation</span></span>  
 <span data-ttu-id="0c358-154">C# 7.0(현재 사용할 수 없음)</span><span class="sxs-lookup"><span data-stu-id="0c358-154">C# 7.0 (not currently available)</span></span>  

<!--- Uncomment and add to the above when they become officially released
 C# 7.1 (spec is not yet finished)  
 C# 7.2 (spec is not yet finished)  
 C# 8.0 (spec is not yet finished)  
-->

### <a name="minimum-compiler-version-needed-to-support-all-language-features"></a><span data-ttu-id="0c358-155">모든 언어 기능을 지원하는 데 필요한 최소 컴파일러 버전</span><span class="sxs-lookup"><span data-stu-id="0c358-155">Minimum compiler version needed to support all language features</span></span>   
<span data-ttu-id="0c358-156">[↩](#TDefault)<a name="FDefault">Default</a>, <a name="FISO1">ISO1</a>: Microsoft Visual Studio/Build Tools .Net 2002 또는 번들된 .Net Framework 1.0 컴파일러</span><span class="sxs-lookup"><span data-stu-id="0c358-156">[↩](#TDefault)<a name="FDefault">Default</a>, <a name="FISO1">ISO1</a>: Microsoft Visual Studio/Build Tools .Net 2002 or bundled .Net Framework 1.0 compiler</span></span>     
<span data-ttu-id="0c358-157">[↩](#TISO2)<a name="FISO2">ISO2</a>: Microsoft Visual Studio/Build Tools 2005 또는 번들된 .Net Framework 2.0 컴파일러</span><span class="sxs-lookup"><span data-stu-id="0c358-157">[↩](#TISO2)<a name="FISO2">ISO2</a>: Microsoft Visual Studio/Build Tools 2005 or bundled .Net Framework 2.0 compiler</span></span>    
<span data-ttu-id="0c358-158">[↩](#TCS3)<a name="FCS3">CS3</a>: Microsoft Visual Studio/Build Tools 2008 또는 번들된 .Net Framework 3.5 컴파일러</span><span class="sxs-lookup"><span data-stu-id="0c358-158">[↩](#TCS3)<a name="FCS3">CS3</a>: Microsoft Visual Studio/Build Tools 2008 or bundled .Net Framework 3.5 compiler</span></span>    
<span data-ttu-id="0c358-159">[↩](#TCS4)<a name="FCS4">CS4</a>: Microsoft Visual Studio/Build Tools 2010 또는 번들된 .Net Framework 4.0 컴파일러</span><span class="sxs-lookup"><span data-stu-id="0c358-159">[↩](#TCS4)<a name="FCS4">CS4</a>: Microsoft Visual Studio/Build Tools 2010 or bundled .Net Framework 4.0 compiler</span></span>    
<span data-ttu-id="0c358-160">[↩](#TCS5)<a name="FCS5">CS5</a>: Microsoft Visual Studio/Build Tools 2012 또는 번들된 .Net Framework 4.5 컴파일러</span><span class="sxs-lookup"><span data-stu-id="0c358-160">[↩](#TCS5)<a name="FCS5">CS5</a>: Microsoft Visual Studio/Build Tools 2012 or bundled .Net Framework 4.5 compiler</span></span>    
<span data-ttu-id="0c358-161">[↩](#TCS6)<a name="FCS6">CS6</a>: Microsoft Visual Studio/Build Tools 2015</span><span class="sxs-lookup"><span data-stu-id="0c358-161">[↩](#TCS6)<a name="FCS6">CS6</a>: Microsoft Visual Studio/Build Tools 2015</span></span>    
<span data-ttu-id="0c358-162">[↩](#TCS7)<a name="FCS7">CS7</a>, <a name="FLatest">Latest</a>: Microsoft Visual Studio/Build Tools 2017</span><span class="sxs-lookup"><span data-stu-id="0c358-162">[↩](#TCS7)<a name="FCS7">CS7</a>, <a name="FLatest">Latest</a>: Microsoft Visual Studio/Build Tools 2017</span></span>   

<!--- Uncomment and add to the above when they become officially released
[↩](#TCS71)<a name="FCS71">CS71</a>: Microsoft Visual Studio/Build Tools 20??    
[↩](#TCS72)<a name="FCS72">CS72</a>: Microsoft Visual Studio/Build Tools 20??    
[↩](#TCS8)<a name="FCS71">CS8</a>: Microsoft Visual Studio/Build Tools 20??    
-->
