---
title: -langversion(C# 컴파일러 옵션)
ms.date: 05/14/2018
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
ms.openlocfilehash: 299ff121bab87482b7cdcaebc8b43cb8a1b559ec
ms.sourcegitcommit: 895c7602386a6dfe7ca4facce3d965b27e5c6e87
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2018
---
# <a name="-langversion-c-compiler-options"></a><span data-ttu-id="1249a-102">-langversion(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="1249a-102">-langversion (C# Compiler Options)</span></span>
<span data-ttu-id="1249a-103">컴파일러가 선택한 C# 언어 사양에 포함된 구문만 허용하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1249a-103">Causes the compiler to accept only syntax that is included in the chosen C# language specification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1249a-104">구문</span><span class="sxs-lookup"><span data-stu-id="1249a-104">Syntax</span></span>  
  
```console  
-langversion:option  
```  
  
## <a name="arguments"></a><span data-ttu-id="1249a-105">인수</span><span class="sxs-lookup"><span data-stu-id="1249a-105">Arguments</span></span>  
 `option`  
 <span data-ttu-id="1249a-106">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1249a-106">The following values are valid:</span></span>  
  
|<span data-ttu-id="1249a-107">옵션</span><span class="sxs-lookup"><span data-stu-id="1249a-107">Option</span></span>|<span data-ttu-id="1249a-108">의미</span><span class="sxs-lookup"><span data-stu-id="1249a-108">Meaning</span></span>|  
|------------|-------------|  
|<span data-ttu-id="1249a-109">default</span><span class="sxs-lookup"><span data-stu-id="1249a-109">default</span></span>|<span data-ttu-id="1249a-110">컴파일러는 지원할 수 있는 최신 주 버전의 유효한 언어 구문을 모두 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="1249a-110">The compiler accepts all valid language syntax from the latest major version that it can support.</span></span>|
|<span data-ttu-id="1249a-111">ISO-1</span><span class="sxs-lookup"><span data-stu-id="1249a-111">ISO-1</span></span>|<span data-ttu-id="1249a-112">컴파일러가 ISO/IEC 23270:2003 C#(1.0/1.2)에 포함된 구문만 허용합니다. <sup id="TISO1">[ISO1](#FISO1)</sup></span><span class="sxs-lookup"><span data-stu-id="1249a-112">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2) <sup id="TISO1">[ISO1](#FISO1)</sup></span></span>|  
|<span data-ttu-id="1249a-113">ISO-2</span><span class="sxs-lookup"><span data-stu-id="1249a-113">ISO-2</span></span>|<span data-ttu-id="1249a-114">컴파일러가 ISO/IEC 23270:2006 C#(2.0)에 포함된 구문만 허용합니다. <sup id="TISO2">[ISO2](#FISO2)</sup></span><span class="sxs-lookup"><span data-stu-id="1249a-114">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0) <sup id="TISO2">[ISO2](#FISO2)</sup></span></span>|
|<span data-ttu-id="1249a-115">3</span><span class="sxs-lookup"><span data-stu-id="1249a-115">3</span></span>|<span data-ttu-id="1249a-116">컴파일러가 C# 3.0 또는 이전 버전에 포함된 구문만 허용합니다. <sup id="TCS3">[CS3](#FCS3)</sup></span><span class="sxs-lookup"><span data-stu-id="1249a-116">The compiler accepts only syntax that is included in C# 3.0 or lower <sup id="TCS3">[CS3](#FCS3)</sup></span></span>|
|<span data-ttu-id="1249a-117">4</span><span class="sxs-lookup"><span data-stu-id="1249a-117">4</span></span>|<span data-ttu-id="1249a-118">컴파일러가 C# 4.0 또는 이전 버전에 포함된 구문만 허용합니다. <sup id="TCS4">[CS4](#FCS4)</sup></span><span class="sxs-lookup"><span data-stu-id="1249a-118">The compiler accepts only syntax that is included in C# 4.0 or lower <sup id="TCS4">[CS4](#FCS4)</sup></span></span>|
|<span data-ttu-id="1249a-119">5</span><span class="sxs-lookup"><span data-stu-id="1249a-119">5</span></span>|<span data-ttu-id="1249a-120">컴파일러가 C# 5.0 또는 이전 버전에 포함된 구문만 허용합니다. <sup id="TCS5">[CS5](#FCS5)</sup></span><span class="sxs-lookup"><span data-stu-id="1249a-120">The compiler accepts only syntax that is included in C# 5.0 or lower <sup id="TCS5">[CS5](#FCS5)</sup></span></span>|
|<span data-ttu-id="1249a-121">6</span><span class="sxs-lookup"><span data-stu-id="1249a-121">6</span></span>|<span data-ttu-id="1249a-122">컴파일러가 C# 6.0 또는 이전 버전에 포함된 구문만 허용합니다. <sup id="TCS6">[CS6](#FCS6)</sup></span><span class="sxs-lookup"><span data-stu-id="1249a-122">The compiler accepts only syntax that is included in C# 6.0 or lower <sup id="TCS6">[CS6](#FCS6)</sup></span></span>|
|<span data-ttu-id="1249a-123">7</span><span class="sxs-lookup"><span data-stu-id="1249a-123">7</span></span>|<span data-ttu-id="1249a-124">컴파일러가 C# 7.0 또는 이전 버전에 포함된 구문만 허용합니다. <sup id="TCS7">[CS7](#FCS7)</sup></span><span class="sxs-lookup"><span data-stu-id="1249a-124">The compiler accepts only syntax that is included in C# 7.0 or lower <sup id="TCS7">[CS7](#FCS7)</sup></span></span>|
|<span data-ttu-id="1249a-125">7.1</span><span class="sxs-lookup"><span data-stu-id="1249a-125">7.1</span></span>|<span data-ttu-id="1249a-126">컴파일러가 C# 7.1 또는 이전 버전에 포함된 구문만 허용합니다. <sup id="TCS71">[CS71](#FCS71)</sup></span><span class="sxs-lookup"><span data-stu-id="1249a-126">The compiler accepts only syntax that is included in C# 7.1 or lower <sup id="TCS71">[CS71](#FCS71)</sup></span></span>|
|<span data-ttu-id="1249a-127">7.2</span><span class="sxs-lookup"><span data-stu-id="1249a-127">7.2</span></span>|<span data-ttu-id="1249a-128">컴파일러가 C# 7.2 또는 이전 버전에 포함된 구문만 허용합니다. <sup id="TCS72">[CS72](#FCS72)</sup></span><span class="sxs-lookup"><span data-stu-id="1249a-128">The compiler accepts only syntax that is included in C# 7.2 or lower <sup id="TCS72">[CS72](#FCS72)</sup></span></span>|
|<span data-ttu-id="1249a-129">7.3</span><span class="sxs-lookup"><span data-stu-id="1249a-129">7.3</span></span>|<span data-ttu-id="1249a-130">컴파일러가 C# 7.3 또는 이전 버전에 포함된 구문만 허용합니다. <sup id="TCS73">[CS73](#FCS73)</sup></span><span class="sxs-lookup"><span data-stu-id="1249a-130">The compiler accepts only syntax that is included in C# 7.3 or lower <sup id="TCS73">[CS73](#FCS73)</sup></span></span>|
|<span data-ttu-id="1249a-131">latest</span><span class="sxs-lookup"><span data-stu-id="1249a-131">latest</span></span>|<span data-ttu-id="1249a-132">컴파일러가 지원할 수 있는 유효한 언어 구문을 모두 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="1249a-132">The compiler accepts all valid language syntax that it can support.</span></span>|

<!--- Uncomment and move these above
|8|The compiler accepts only syntax that is included in C# 8 or lower <sup id="TCS8">[CS8](#FCS8)</sup>|
-->

  
## <a name="remarks"></a><span data-ttu-id="1249a-133">설명</span><span class="sxs-lookup"><span data-stu-id="1249a-133">Remarks</span></span>  
 <span data-ttu-id="1249a-134">C# 응용 프로그램에서 참조된 메타데이터에는 **-langversion** 컴파일러 옵션이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1249a-134">Metadata referenced by your C# application is not subject to **-langversion** compiler option.</span></span>  
  
 <span data-ttu-id="1249a-135">각 C# 컴파일러 버전에 언어 사양의 확장이 포함되어 있으므로 **-langversion**은 이전 컴파일러 버전의 동등한 기능을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1249a-135">Because each version of the C# compiler contains extensions to the language specification, **-langversion** does not give you the equivalent functionality of an earlier version of the compiler.</span></span>  
 
 <span data-ttu-id="1249a-136">또한 C# 버전 업데이트는 일반적으로 주 .NET Framework 릴리스와 일치하는 반면, 새 구문과 기능이 반드시 특정 프레임워크 버전에 연결되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1249a-136">Additionally, while C# version updates generally coincide with major .Net Framework releases, the new syntax and features are not necessarily tied to that specific framework version.</span></span> <span data-ttu-id="1249a-137">새로운 기능에는 C# 버전과 함께 릴리스된 새 컴파일러 업데이트가 분명히 필요하지만, 각 특정 기능에 고유한 최소 .Net API 또는 공용 언어 런타임 요구 사항이 있으므로 NuGet 패키지 또는 다른 라이브러리를 포함하여 하위 수준 프레임워크에서 실행이 허용될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1249a-137">While the new features will definitely require a new compiler update that is also released alongside the C# revision, each specific feature has its own minimum .Net API or common language runtime requirements that may allow it to run on downlevel frameworks by including NuGet packages or other libraries.</span></span>
  
 <span data-ttu-id="1249a-138">사용하는 **-langversion** 설정과 관계없이 현재 버전의 공용 언어 런타임을 사용하여 고유한 .exe 또는 .dll을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1249a-138">Regardless of which **-langversion** setting you use, you will use the current version of the common language runtime to create your .exe or .dll.</span></span> <span data-ttu-id="1249a-139">한 가지 예외는 friend 어셈블리와 [-moduleassemblyname(C# 컴파일러 옵션)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md)으로, **-langversion:ISO-1**에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="1249a-139">One exception is friend assemblies and [-moduleassemblyname (C# Compiler Option)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md), which work under **-langversion:ISO-1**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="1249a-140">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="1249a-140">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="1249a-141">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1249a-141">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="1249a-142">**빌드** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1249a-142">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="1249a-143">**고급** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1249a-143">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="1249a-144">**언어 버전** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="1249a-144">Modify the **Language Version** property.</span></span>  
  
 <span data-ttu-id="1249a-145">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1249a-145">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span></span>  
    
## <a name="see-also"></a><span data-ttu-id="1249a-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1249a-146">See Also</span></span>  
 [<span data-ttu-id="1249a-147">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="1249a-147">C# Compiler Options</span></span>](index.md)  
 [<span data-ttu-id="1249a-148">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="1249a-148">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 
### <a name="c-language-specification"></a><span data-ttu-id="1249a-149">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="1249a-149">C# Language Specification</span></span>

|<span data-ttu-id="1249a-150">버전</span><span class="sxs-lookup"><span data-stu-id="1249a-150">Version</span></span>|<span data-ttu-id="1249a-151">링크</span><span class="sxs-lookup"><span data-stu-id="1249a-151">Link</span></span>|<span data-ttu-id="1249a-152">설명</span><span class="sxs-lookup"><span data-stu-id="1249a-152">Description</span></span>|
|-------|----|-----------|
|<span data-ttu-id="1249a-153">C# 1.0</span><span class="sxs-lookup"><span data-stu-id="1249a-153">C# 1.0</span></span>|[<span data-ttu-id="1249a-154">DOC 다운로드</span><span class="sxs-lookup"><span data-stu-id="1249a-154">Download DOC</span></span>](http://download.microsoft.com/download/a/9/e/a9e229b9-fee5-4c3e-8476-917dee385062/csharp%20language%20specification%20v1.0.doc)|<span data-ttu-id="1249a-155">C# 언어 사양 버전 1.0: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="1249a-155">C# Language Specification Version 1.0: Microsoft Corporation</span></span>|
|<span data-ttu-id="1249a-156">C# 1.2</span><span class="sxs-lookup"><span data-stu-id="1249a-156">C# 1.2</span></span>|[<span data-ttu-id="1249a-157">DOC 다운로드</span><span class="sxs-lookup"><span data-stu-id="1249a-157">Download DOC</span></span>](http://download.microsoft.com/download/5/e/5/5e58be0a-b02b-41ac-a4a3-7a22286214ff/csharp%20language%20specification%20v1.2.doc)|<span data-ttu-id="1249a-158">C# 언어 사양 버전 1.2: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="1249a-158">C# Language Specification Version 1.2: Microsoft Corporation</span></span>|
|<span data-ttu-id="1249a-159">C# 2.0</span><span class="sxs-lookup"><span data-stu-id="1249a-159">C# 2.0</span></span>|[<span data-ttu-id="1249a-160">PDF 다운로드</span><span class="sxs-lookup"><span data-stu-id="1249a-160">Download PDF</span></span>](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/Ecma-334%204th%20edition%20June%202006.pdf)|<span data-ttu-id="1249a-161">표준 ECMA-334 네 번째 버전</span><span class="sxs-lookup"><span data-stu-id="1249a-161">Standard ECMA-334 4th Edition</span></span>|
|<span data-ttu-id="1249a-162">C# 3.0</span><span class="sxs-lookup"><span data-stu-id="1249a-162">C# 3.0</span></span>|[<span data-ttu-id="1249a-163">DOC 다운로드</span><span class="sxs-lookup"><span data-stu-id="1249a-163">Download DOC</span></span>](http://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc)|<span data-ttu-id="1249a-164">C# 언어 사양 버전 3.0: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="1249a-164">C# Language Specification Version 3.0: Microsoft Corporation</span></span>|
|<span data-ttu-id="1249a-165">C# 5.0</span><span class="sxs-lookup"><span data-stu-id="1249a-165">C# 5.0</span></span>|[<span data-ttu-id="1249a-166">PDF 다운로드</span><span class="sxs-lookup"><span data-stu-id="1249a-166">Download PDF</span></span>](https://www.ecma-international.org/publications/files/ECMA-ST/Ecma-334.pdf)|<span data-ttu-id="1249a-167">표준 ECMA-334 다섯 번째 버전</span><span class="sxs-lookup"><span data-stu-id="1249a-167">Standard ECMA-334 5th Edition</span></span>|
|<span data-ttu-id="1249a-168">C# 6.0</span><span class="sxs-lookup"><span data-stu-id="1249a-168">C# 6.0</span></span>|[<span data-ttu-id="1249a-169">링크</span><span class="sxs-lookup"><span data-stu-id="1249a-169">Link</span></span>](../language-specification/index.md)|<span data-ttu-id="1249a-170">C# 언어 사양 버전 6 - 비공식 초안: .NET Foundation</span><span class="sxs-lookup"><span data-stu-id="1249a-170">C# Language Specification Version 6 - Unofficial Draft: .NET Foundation</span></span>|
|<span data-ttu-id="1249a-171">C# 7.0 이상</span><span class="sxs-lookup"><span data-stu-id="1249a-171">C# 7.0 and later</span></span>||<span data-ttu-id="1249a-172">현재 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="1249a-172">not currently available</span></span>|

### <a name="minimum-compiler-version-needed-to-support-all-language-features"></a><span data-ttu-id="1249a-173">모든 언어 기능을 지원하는 데 필요한 최소 컴파일러 버전</span><span class="sxs-lookup"><span data-stu-id="1249a-173">Minimum compiler version needed to support all language features</span></span>   
<span data-ttu-id="1249a-174">[↩](#TISO1)<a name="FISO1">ISO1</a>: Microsoft Visual Studio/Build Tools .NET 2002 또는 번들된 .NET Framework 1.0 컴파일러</span><span class="sxs-lookup"><span data-stu-id="1249a-174">[↩](#TISO1)<a name="FISO1">ISO1</a>: Microsoft Visual Studio/Build Tools .Net 2002 or bundled .Net Framework 1.0 compiler</span></span>     
<span data-ttu-id="1249a-175">[↩](#TISO2)<a name="FISO2">ISO2</a>: Microsoft Visual Studio/Build Tools 2005 또는 번들된 .Net Framework 2.0 컴파일러</span><span class="sxs-lookup"><span data-stu-id="1249a-175">[↩](#TISO2)<a name="FISO2">ISO2</a>: Microsoft Visual Studio/Build Tools 2005 or bundled .Net Framework 2.0 compiler</span></span>    
<span data-ttu-id="1249a-176">[↩](#TCS3)<a name="FCS3">CS3</a>: Microsoft Visual Studio/Build Tools 2008 또는 번들된 .Net Framework 3.5 컴파일러</span><span class="sxs-lookup"><span data-stu-id="1249a-176">[↩](#TCS3)<a name="FCS3">CS3</a>: Microsoft Visual Studio/Build Tools 2008 or bundled .Net Framework 3.5 compiler</span></span>    
<span data-ttu-id="1249a-177">[↩](#TCS4)<a name="FCS4">CS4</a>: Microsoft Visual Studio/Build Tools 2010 또는 번들된 .Net Framework 4.0 컴파일러</span><span class="sxs-lookup"><span data-stu-id="1249a-177">[↩](#TCS4)<a name="FCS4">CS4</a>: Microsoft Visual Studio/Build Tools 2010 or bundled .Net Framework 4.0 compiler</span></span>    
<span data-ttu-id="1249a-178">[↩](#TCS5)<a name="FCS5">CS5</a>: Microsoft Visual Studio/Build Tools 2012 또는 번들된 .Net Framework 4.5 컴파일러</span><span class="sxs-lookup"><span data-stu-id="1249a-178">[↩](#TCS5)<a name="FCS5">CS5</a>: Microsoft Visual Studio/Build Tools 2012 or bundled .Net Framework 4.5 compiler</span></span>    
<span data-ttu-id="1249a-179">[↩](#TCS6)<a name="FCS6">CS6</a>: Microsoft Visual Studio/Build Tools 2015</span><span class="sxs-lookup"><span data-stu-id="1249a-179">[↩](#TCS6)<a name="FCS6">CS6</a>: Microsoft Visual Studio/Build Tools 2015</span></span>    
<span data-ttu-id="1249a-180">[↩](#TCS7)<a name="FCS7">CS7</a>: Microsoft Visual Studio/Build Tools 2017</span><span class="sxs-lookup"><span data-stu-id="1249a-180">[↩](#TCS7)<a name="FCS7">CS7</a>: Microsoft Visual Studio/Build Tools 2017</span></span>   
<span data-ttu-id="1249a-181">[↩](#TCS71)<a name="FCS71">CS71</a>: Microsoft Visual Studio/Build Tools 2017 버전 15.3</span><span class="sxs-lookup"><span data-stu-id="1249a-181">[↩](#TCS71)<a name="FCS71">CS71</a>: Microsoft Visual Studio/Build Tools 2017, version 15.3</span></span>    
<span data-ttu-id="1249a-182">[↩](#TCS72)<a name="FCS72">CS72</a>: Microsoft Visual Studio/Build Tools 2017 버전 15.5</span><span class="sxs-lookup"><span data-stu-id="1249a-182">[↩](#TCS72)<a name="FCS72">CS72</a>: Microsoft Visual Studio/Build Tools 2017, version 15.5</span></span>    
<span data-ttu-id="1249a-183">[↩](#TCS73)<a name="FCS73">CS73</a>: Microsoft Visual Studio/Build Tools 2017 버전 15.7</span><span class="sxs-lookup"><span data-stu-id="1249a-183">[↩](#TCS73)<a name="FCS73">CS73</a>: Microsoft Visual Studio/Build Tools 2017, version 15.7</span></span>    

<!--- Uncomment and add to the above when they become officially released
[↩](#TCS8)<a name="FCS8">CS8</a>: Microsoft Visual Studio/Build Tools 20??    
-->
