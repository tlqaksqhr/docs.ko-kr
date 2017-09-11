---
title: "공통 특성 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 11fe4894-1bf9-4525-a36b-cddcd3a5d22b
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9adb5cb378701c8d06a3fa28bad44dc857026b5a
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="common-attributes-visual-basic"></a><span data-ttu-id="45447-102">공통 특성 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="45447-102">Common Attributes (Visual Basic)</span></span>
<span data-ttu-id="45447-103">이 항목에서는 Visual Basic 프로그램에서 가장 일반적으로 사용 되는 특성을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-103">This topic describes the attributes that are most commonly used in Visual Basic programs.</span></span>  
  
-   [<span data-ttu-id="45447-104">전역 특성</span><span class="sxs-lookup"><span data-stu-id="45447-104">Global Attributes</span></span>](#Global)  
  
-   [<span data-ttu-id="45447-105">사용 되지 않는 특성</span><span class="sxs-lookup"><span data-stu-id="45447-105">Obsolete Attribute</span></span>](#Obsolete)  
  
-   [<span data-ttu-id="45447-106">조건부 특성</span><span class="sxs-lookup"><span data-stu-id="45447-106">Conditional Attribute</span></span>](#Conditional)  
  
-   [<span data-ttu-id="45447-107">호출자 정보 특성</span><span class="sxs-lookup"><span data-stu-id="45447-107">Caller Info Attributes</span></span>](#CallerInfo)  
  
-   [<span data-ttu-id="45447-108">Visual Basic 특성</span><span class="sxs-lookup"><span data-stu-id="45447-108">Visual Basic Attributes</span></span>](#VB)  
  
##  <span data-ttu-id="45447-109"><a name="Global"></a>전역 특성</span><span class="sxs-lookup"><span data-stu-id="45447-109"><a name="Global"></a> Global Attributes</span></span>  
 <span data-ttu-id="45447-110">대부분의 특성은 클래스 또는 메서드;와 같은 특정 언어 요소에 적용 됩니다. 그러나 일부 특성은 전역-전체 어셈블리 또는 모듈에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-110">Most attributes are applied to specific language elements such as classes or methods; however, some attributes are global—they apply to an entire assembly or module.</span></span> <span data-ttu-id="45447-111">예를 들어는 <xref:System.Reflection.AssemblyVersionAttribute>를 다음과 같이 어셈블리에 버전 정보를 포함 시킬 특성을 사용할 수 있습니다:</xref:System.Reflection.AssemblyVersionAttribute></span><span class="sxs-lookup"><span data-stu-id="45447-111">For example, the <xref:System.Reflection.AssemblyVersionAttribute> attribute can be used to embed version information into an assembly, like this:</span></span>  
  
```vb  
<Assembly: AssemblyVersion("1.0.0.0")>  
```  
  
 <span data-ttu-id="45447-112">전역 특성 후 소스 코드에 표시 합니다. 최상위`Imports` 문 및 유형, 모듈 또는 네임 스페이스 선언 앞입니다.</span><span class="sxs-lookup"><span data-stu-id="45447-112">Global attributes appear in the source code after any top-level`Imports` statements and before any type, module, or namespace declarations.</span></span> <span data-ttu-id="45447-113">전역 특성은 여러 소스 파일에 나타날 수 있지만 단일 컴파일 단계에서 파일을 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-113">Global attributes can appear in multiple source files, but the files must be compiled in a single compilation pass.</span></span> <span data-ttu-id="45447-114">Visual Basic 프로젝트에 대 한 전역 특성 (파일이 만들어집니다 자동으로 Visual Studio에서 프로젝트를 만들 때) AssemblyInfo.vb 파일에 일반적으로 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45447-114">For Visual Basic projects, global attributes are generally put in the AssemblyInfo.vb file (the file is created automatically when you create a project in Visual Studio).</span></span>  
  
 <span data-ttu-id="45447-115">어셈블리 특성은 어셈블리에 대한 정보를 제공하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="45447-115">Assembly attributes are values that provide information about an assembly.</span></span> <span data-ttu-id="45447-116">다음과 같은 범주로 분류 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45447-116">They fall into the following categories:</span></span>  
  
-   <span data-ttu-id="45447-117">어셈블리 id 특성</span><span class="sxs-lookup"><span data-stu-id="45447-117">Assembly identity attributes</span></span>  
  
-   <span data-ttu-id="45447-118">정보 특성</span><span class="sxs-lookup"><span data-stu-id="45447-118">Informational attributes</span></span>  
  
-   <span data-ttu-id="45447-119">어셈블리 매니페스트 특성</span><span class="sxs-lookup"><span data-stu-id="45447-119">Assembly manifest attributes</span></span>  
  
### <a name="assembly-identity-attributes"></a><span data-ttu-id="45447-120">어셈블리 ID 특성</span><span class="sxs-lookup"><span data-stu-id="45447-120">Assembly Identity Attributes</span></span>  
 <span data-ttu-id="45447-121">어셈블리의 id를 확인 하는 세 가지 특성 (강력한 이름으로, 해당 하는 경우): 이름, 버전 및 culture입니다.</span><span class="sxs-lookup"><span data-stu-id="45447-121">Three attributes (with a strong name, if applicable) determine the identity of an assembly: name, version, and culture.</span></span> <span data-ttu-id="45447-122">이러한 특성은 어셈블리의 전체 이름을 구성 및 코드에서 참조 하는 경우에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-122">These attributes form the full name of the assembly and are required when you reference it in code.</span></span> <span data-ttu-id="45447-123">어셈블리의 버전 및 특성을 사용 하 여 문화권을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45447-123">You can set an assembly's version and culture using attributes.</span></span> <span data-ttu-id="45447-124">그러나 이름 값은 Visual Studio IDE에서 컴파일러에 의해 설정 됩니다는 [어셈블리 정보 대화 상자](https://docs.microsoft.com/visualstudio/ide/reference/assembly-information-dialog-box), 어셈블리 매니페스트가 포함 된 파일을 기반으로 하는 어셈블리 링커 (Al.exe)는 어셈블리를 만들 때 또는 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-124">However, the name value is set by the compiler, the Visual Studio IDE in the [Assembly Information Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/assembly-information-dialog-box), or the Assembly Linker (Al.exe) when the assembly is created, based on the file that contains the assembly manifest.</span></span> <span data-ttu-id="45447-125"><xref:System.Reflection.AssemblyFlagsAttribute>특성은 어셈블리의 여러 복사본을 함께 사용할 수 있는지 여부를 지정 합니다.</xref:System.Reflection.AssemblyFlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="45447-125">The <xref:System.Reflection.AssemblyFlagsAttribute> attribute specifies whether multiple copies of the assembly can coexist.</span></span>  
  
 <span data-ttu-id="45447-126">다음 표에서 id 특성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="45447-126">The following table shows the identity attributes.</span></span>  
  
|<span data-ttu-id="45447-127">특성</span><span class="sxs-lookup"><span data-stu-id="45447-127">Attribute</span></span>|<span data-ttu-id="45447-128">용도</span><span class="sxs-lookup"><span data-stu-id="45447-128">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="45447-129"><xref:System.Reflection.AssemblyName></xref:System.Reflection.AssemblyName></span><span class="sxs-lookup"><span data-stu-id="45447-129"><xref:System.Reflection.AssemblyName></span></span>|<span data-ttu-id="45447-130">어셈블리의 id를 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-130">Fully describes the identity of an assembly.</span></span>|  
|<span data-ttu-id="45447-131"><xref:System.Reflection.AssemblyVersionAttribute></xref:System.Reflection.AssemblyVersionAttribute></span><span class="sxs-lookup"><span data-stu-id="45447-131"><xref:System.Reflection.AssemblyVersionAttribute></span></span>|<span data-ttu-id="45447-132">어셈블리의 버전을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-132">Specifies the version of an assembly.</span></span>|  
|<span data-ttu-id="45447-133"><xref:System.Reflection.AssemblyCultureAttribute></xref:System.Reflection.AssemblyCultureAttribute></span><span class="sxs-lookup"><span data-stu-id="45447-133"><xref:System.Reflection.AssemblyCultureAttribute></span></span>|<span data-ttu-id="45447-134">어셈블리에서 지원하는 문화권을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-134">Specifies which culture the assembly supports.</span></span>|  
|<span data-ttu-id="45447-135"><xref:System.Reflection.AssemblyFlagsAttribute></xref:System.Reflection.AssemblyFlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="45447-135"><xref:System.Reflection.AssemblyFlagsAttribute></span></span>|<span data-ttu-id="45447-136">동일한 컴퓨터, 동일한 프로세스에서 또는 동일한 응용 프로그램 도메인에서 어셈블리-병렬 실행을 지원 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-136">Specifies whether an assembly supports side-by-side execution on the same computer, in the same process, or in the same application domain.</span></span>|  
  
### <a name="informational-attributes"></a><span data-ttu-id="45447-137">정보 특성</span><span class="sxs-lookup"><span data-stu-id="45447-137">Informational Attributes</span></span>  
 <span data-ttu-id="45447-138">정보 특성을 사용하여 어셈블리에 대한 추가 회사 또는 제품 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45447-138">You can use informational attributes to provide additional company or product information for an assembly.</span></span> <span data-ttu-id="45447-139">다음 표에서에 정의 된 추가 특성은 <xref:System.Reflection?displayProperty=fullName>네임 스페이스.</xref:System.Reflection?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="45447-139">The following table shows the informational attributes defined in the <xref:System.Reflection?displayProperty=fullName> namespace.</span></span>  
  
|<span data-ttu-id="45447-140">특성</span><span class="sxs-lookup"><span data-stu-id="45447-140">Attribute</span></span>|<span data-ttu-id="45447-141">용도</span><span class="sxs-lookup"><span data-stu-id="45447-141">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="45447-142"><xref:System.Reflection.AssemblyProductAttribute></xref:System.Reflection.AssemblyProductAttribute></span><span class="sxs-lookup"><span data-stu-id="45447-142"><xref:System.Reflection.AssemblyProductAttribute></span></span>|<span data-ttu-id="45447-143">어셈블리 매니페스트에 대 한 제품 이름을 지정 하는 사용자 지정 특성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-143">Defines a custom attribute that specifies a product name for an assembly manifest.</span></span>|  
|<span data-ttu-id="45447-144"><xref:System.Reflection.AssemblyTrademarkAttribute></xref:System.Reflection.AssemblyTrademarkAttribute></span><span class="sxs-lookup"><span data-stu-id="45447-144"><xref:System.Reflection.AssemblyTrademarkAttribute></span></span>|<span data-ttu-id="45447-145">어셈블리 매니페스트에 대 상표를 지정 하는 사용자 지정 특성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-145">Defines a custom attribute that specifies a trademark for an assembly manifest.</span></span>|  
|<span data-ttu-id="45447-146"><xref:System.Reflection.AssemblyInformationalVersionAttribute></xref:System.Reflection.AssemblyInformationalVersionAttribute></span><span class="sxs-lookup"><span data-stu-id="45447-146"><xref:System.Reflection.AssemblyInformationalVersionAttribute></span></span>|<span data-ttu-id="45447-147">어셈블리 매니페스트에 대 한 정보 버전을 지정 하는 사용자 지정 특성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-147">Defines a custom attribute that specifies an informational version for an assembly manifest.</span></span>|  
|<span data-ttu-id="45447-148"><xref:System.Reflection.AssemblyCompanyAttribute></xref:System.Reflection.AssemblyCompanyAttribute></span><span class="sxs-lookup"><span data-stu-id="45447-148"><xref:System.Reflection.AssemblyCompanyAttribute></span></span>|<span data-ttu-id="45447-149">어셈블리 매니페스트에 대 한 회사 이름을 지정 하는 사용자 지정 특성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-149">Defines a custom attribute that specifies a company name for an assembly manifest.</span></span>|  
|<span data-ttu-id="45447-150"><xref:System.Reflection.AssemblyCopyrightAttribute></xref:System.Reflection.AssemblyCopyrightAttribute></span><span class="sxs-lookup"><span data-stu-id="45447-150"><xref:System.Reflection.AssemblyCopyrightAttribute></span></span>|<span data-ttu-id="45447-151">어셈블리 매니페스트에 대 한 저작권 정보를 지정 하는 사용자 지정 특성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-151">Defines a custom attribute that specifies a copyright for an assembly manifest.</span></span>|  
|<span data-ttu-id="45447-152"><xref:System.Reflection.AssemblyFileVersionAttribute></xref:System.Reflection.AssemblyFileVersionAttribute></span><span class="sxs-lookup"><span data-stu-id="45447-152"><xref:System.Reflection.AssemblyFileVersionAttribute></span></span>|<span data-ttu-id="45447-153">Win32 파일 버전 리소스에 대 한 특정 버전 번호를 사용 하도록 컴파일러에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-153">Instructs the compiler to use a specific version number for the Win32 file version resource.</span></span>|  
|<span data-ttu-id="45447-154"><xref:System.CLSCompliantAttribute></xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="45447-154"><xref:System.CLSCompliantAttribute></span></span>|<span data-ttu-id="45447-155">어셈블리의 공용 언어 사양 (CLS 규격) 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="45447-155">Indicates whether the assembly is compliant with the Common Language Specification (CLS).</span></span>|  
  
### <a name="assembly-manifest-attributes"></a><span data-ttu-id="45447-156">어셈블리 매니페스트 특성</span><span class="sxs-lookup"><span data-stu-id="45447-156">Assembly Manifest Attributes</span></span>  
 <span data-ttu-id="45447-157">어셈블리 매니페스트에 있는 정보를 제공 하도록 어셈블리 매니페스트 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45447-157">You can use assembly manifest attributes to provide information in the assembly manifest.</span></span> <span data-ttu-id="45447-158">여기에 제목, 설명, 기본 별칭 및 구성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45447-158">This includes title, description, default alias, and configuration.</span></span> <span data-ttu-id="45447-159">다음 표에서 어셈블리 매니페스트 특성에 정의 된 <xref:System.Reflection?displayProperty=fullName>네임 스페이스.</xref:System.Reflection?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="45447-159">The following table shows the assembly manifest attributes defined in the <xref:System.Reflection?displayProperty=fullName> namespace.</span></span>  
  
|<span data-ttu-id="45447-160">특성</span><span class="sxs-lookup"><span data-stu-id="45447-160">Attribute</span></span>|<span data-ttu-id="45447-161">용도</span><span class="sxs-lookup"><span data-stu-id="45447-161">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="45447-162"><xref:System.Reflection.AssemblyTitleAttribute></xref:System.Reflection.AssemblyTitleAttribute></span><span class="sxs-lookup"><span data-stu-id="45447-162"><xref:System.Reflection.AssemblyTitleAttribute></span></span>|<span data-ttu-id="45447-163">어셈블리 매니페스트에 대 한 어셈블리 제목을 지정 하는 사용자 지정 특성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-163">Defines a custom attribute that specifies an assembly title for an assembly manifest.</span></span>|  
|<span data-ttu-id="45447-164"><xref:System.Reflection.AssemblyDescriptionAttribute></xref:System.Reflection.AssemblyDescriptionAttribute></span><span class="sxs-lookup"><span data-stu-id="45447-164"><xref:System.Reflection.AssemblyDescriptionAttribute></span></span>|<span data-ttu-id="45447-165">어셈블리 매니페스트에 대 한 어셈블리 설명을 지정 하는 사용자 지정 특성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-165">Defines a custom attribute that specifies an assembly description for an assembly manifest.</span></span>|  
|<span data-ttu-id="45447-166"><xref:System.Reflection.AssemblyConfigurationAttribute></xref:System.Reflection.AssemblyConfigurationAttribute></span><span class="sxs-lookup"><span data-stu-id="45447-166"><xref:System.Reflection.AssemblyConfigurationAttribute></span></span>|<span data-ttu-id="45447-167">어셈블리 매니페스트에 대 한 어셈블리 구성 (예: 정식 또는 디버그)를 지정 하는 사용자 지정 특성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-167">Defines a custom attribute that specifies an assembly configuration (such as retail or debug) for an assembly manifest.</span></span>|  
|<span data-ttu-id="45447-168"><xref:System.Reflection.AssemblyDefaultAliasAttribute></xref:System.Reflection.AssemblyDefaultAliasAttribute></span><span class="sxs-lookup"><span data-stu-id="45447-168"><xref:System.Reflection.AssemblyDefaultAliasAttribute></span></span>|<span data-ttu-id="45447-169">어셈블리 매니페스트에 대 한 기본 별칭을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-169">Defines a friendly default alias for an assembly manifest</span></span>|  
  
##  <span data-ttu-id="45447-170"><a name="Obsolete"></a>사용 되지 않는 특성</span><span class="sxs-lookup"><span data-stu-id="45447-170"><a name="Obsolete"></a> Obsolete Attribute</span></span>  
 <span data-ttu-id="45447-171">`Obsolete` 특성은 프로그램 엔터티는 더 이상 사용 하 여 좋은 것으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-171">The `Obsolete` attribute marks a program entity as one that is no longer recommended for use.</span></span> <span data-ttu-id="45447-172">각각의 것으로 표시 하는 엔터티 사용 경고 또는 오류가 특성 구성 된 방식에 따라 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45447-172">Each use of an entity marked obsolete will subsequently generate a warning or an error, depending on how the attribute is configured.</span></span> <span data-ttu-id="45447-173">예:</span><span class="sxs-lookup"><span data-stu-id="45447-173">For example:</span></span>  
  
```vb  
<System.Obsolete("use class B")>   
Class A  
    Sub Method()  
    End Sub  
End Class  
  
Class B  
    <System.Obsolete("use NewMethod", True)>   
    Sub OldMethod()  
    End Sub  
  
    Sub NewMethod()  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="45447-174">이 예제는 `Obsolete` 특성은 클래스에 적용 `A` 및 메서드에 `B.OldMethod`합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-174">In this example the `Obsolete` attribute is applied to class `A` and to method `B.OldMethod`.</span></span> <span data-ttu-id="45447-175">특성 생성자의 두 번째 인수에 적용 되므로 `B.OldMethod` 로 설정 된 `true`,이 메서드는 컴파일러 오류는 발생 클래스를 사용 하 여 반면 `A` 경고가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45447-175">Because the second argument of the attribute constructor applied to `B.OldMethod` is set to `true`, this method will cause a compiler error, whereas using class `A` will just produce a warning.</span></span> <span data-ttu-id="45447-176">그러나 호출 `B.NewMethod`, 없는 경고 또는 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-176">Calling `B.NewMethod`, however, produces no warning or error.</span></span>  
  
 <span data-ttu-id="45447-177">특성 생성자의 첫 번째 인수로 제공 하는 문자열 경고 또는 오류의 일부로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45447-177">The string provided as the first argument to attribute constructor will be displayed as part of the warning or error.</span></span> <span data-ttu-id="45447-178">예를 들어 이전 정의 사용 하면 다음 코드는 두 개의 경고와 하나 이상의 오류가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45447-178">For example, when you use it with the previous definitions, the following code generates two warnings and one error:</span></span>  
  
```vb  
' Generates 2 warnings:  
' Dim a As New A  
' Generate no errors or warnings:  
  
Dim b As New B  
b.NewMethod()  
  
' Generates an error, terminating compilation:  
' b.OldMethod()  
```  
  
 <span data-ttu-id="45447-179">클래스에 대 한 두 가지 경고가 `A` 생성: 클래스 생성자에 대 한 여러 개 있는 클래스 참조의 선언에 대 한 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-179">Two warnings for class `A` are generated: one for the declaration of the class reference, and one for the class constructor.</span></span>  
  
 <span data-ttu-id="45447-180">`Obsolete` 특성 인수 없이 사용할 수 있지만 때문에 대 한 설명을 포함 하 여 항목 사용 되지 않으며 대신 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="45447-180">The `Obsolete` attribute can be used without arguments, but including an explanation of why the item is obsolete and what to use instead is recommended.</span></span>  
  
 <span data-ttu-id="45447-181">`Obsolete` 특성은&1; 회용 특성 및 특성을 허용 하는 모든 엔터티에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45447-181">The `Obsolete` attribute is a single-use attribute and can be applied to any entity that allows attributes.</span></span> <span data-ttu-id="45447-182">`Obsolete`<xref:System.ObsoleteAttribute>.</xref:System.ObsoleteAttribute> 별칭은</span><span class="sxs-lookup"><span data-stu-id="45447-182">`Obsolete` is an alias for <xref:System.ObsoleteAttribute>.</span></span>  
  
##  <span data-ttu-id="45447-183"><a name="Conditional"></a>조건부 특성</span><span class="sxs-lookup"><span data-stu-id="45447-183"><a name="Conditional"></a> Conditional Attribute</span></span>  
 <span data-ttu-id="45447-184">`Conditional` 이 특성은 메서드의 실행을 전처리 식별자에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="45447-184">The `Conditional` attribute makes the execution of a method dependent on a preprocessing identifier.</span></span> <span data-ttu-id="45447-185">`Conditional` 특성에 대 한 별칭은 <xref:System.Diagnostics.ConditionalAttribute>, 메서드 또는 특성 클래스에 적용할 수 및</xref:System.Diagnostics.ConditionalAttribute></span><span class="sxs-lookup"><span data-stu-id="45447-185">The `Conditional` attribute is an alias for <xref:System.Diagnostics.ConditionalAttribute>, and can be applied to a method or an attribute class.</span></span>  
  
 <span data-ttu-id="45447-186">이 예제에서는 `Conditional` 프로그램 관련 진단 정보의 표시를 사용할지 여부를 메서드에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45447-186">In this example, `Conditional` is applied to a method to enable or disable the display of program-specific diagnostic information:</span></span>  
  
```vb  
#Const TRACE_ON = True  
Imports System  
Imports System.Diagnostics  
Module TestConditionalAttribute  
    Public Class Trace  
        <Conditional("TRACE_ON")>   
        Public Shared Sub Msg(ByVal msg As String)  
            Console.WriteLine(msg)  
        End Sub  
  
    End Class  
  
    Sub Main()  
        Trace.Msg("Now in Main...")  
        Console.WriteLine("Done.")  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="45447-187">하는 경우는 `TRACE_ON` 식별자가 정의 추적 출력이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45447-187">If the `TRACE_ON` identifier is not defined, no trace output will be displayed.</span></span>  
  
 <span data-ttu-id="45447-188">`Conditional` 특성은 자주 사용 된 `DEBUG` 다음과 같은 추적 및 디버그를 작성 하지만 속하지 않은 릴리스 빌드에 대 한 로깅 기능을 사용 하도록 설정 하는 식별자:</span><span class="sxs-lookup"><span data-stu-id="45447-188">The `Conditional` attribute is often used with the `DEBUG` identifier to enable trace and logging features for debug builds but not in release builds, like this:</span></span>  
  
```vb  
<Conditional("DEBUG")>   
Shared Sub DebugMethod()  
  
End Sub  
```  
  
 <span data-ttu-id="45447-189">조건부로 표시 된 메서드를 호출 하는 경우 지정된 된 전처리 기호 유무 호출 생략 포함 여부 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-189">When a method marked as conditional is called, the presence or absence of the specified preprocessing symbol determines whether the call is included or omitted.</span></span> <span data-ttu-id="45447-190">기호가 정의 된 경우는 호출이 포함; 됩니다. 그렇지 않으면 호출을 생략 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-190">If the symbol is defined, the call is included; otherwise, the call is omitted.</span></span> <span data-ttu-id="45447-191">사용 하 여 `Conditional` 깔끔하고 더 세련 되 고 오류 발생 우려가 적은 내부 메서드를 포함 하는 대체 항목 `#if…#endif` 블록을 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-191">Using `Conditional` is a cleaner, more elegant, and less error-prone alternative to enclosing methods inside `#if…#endif` blocks, like this:</span></span>  
  
```vb  
#If DEBUG Then  
    Sub ConditionalMethod()  
    End Sub  
#End If  
```  
  
 <span data-ttu-id="45447-192">조건부 메서드는 클래스 또는 구조체 선언의 하며 반환 값이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-192">A conditional method must be a method in a class or struct declaration and must not have a return value.</span></span>  
  
### <a name="using-multiple-identifiers"></a><span data-ttu-id="45447-193">여러 식별자를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="45447-193">Using Multiple Identifiers</span></span>  
 <span data-ttu-id="45447-194">메서드에 있는 경우 여러 `Conditional` 특성을 조건부 기호 중 하나 이상 정의 되어 있으면 메서드에 대 한 호출이 포함 됩니다 (즉, 기호 논리적으로 연결 되는 OR 연산자를 사용 하 여).</span><span class="sxs-lookup"><span data-stu-id="45447-194">If a method has multiple `Conditional` attributes, a call to the method is included if at least one of the conditional symbols is defined (in other words, the symbols are logically linked together by using the OR operator).</span></span> <span data-ttu-id="45447-195">이 예제에서는 하나 있는지 `A` 또는 `B` 메서드 호출에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-195">In this example, the presence of either `A` or `B` will result in a method call:</span></span>  
  
```vb  
<Conditional("A"), Conditional("B")>   
Shared Sub DoIfAorB()  
  
End Sub  
```  
  
 <span data-ttu-id="45447-196">논리적 AND 연산자를 사용 하 여 기호를 연결 하는 효과 얻으려면 순차적인 조건부 메서드를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45447-196">To achieve the effect of logically linking symbols by using the AND operator, you can define serial conditional methods.</span></span> <span data-ttu-id="45447-197">두 경우에 아래의 두 번째 메서드는 실행 하는 예를 들어 `A` 및 `B` 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45447-197">For example, the second method below will execute only if both `A` and `B` are defined:</span></span>  
  
```vb  
<Conditional("A")>   
Shared Sub DoIfA()  
    DoIfAandB()  
End Sub  
  
<Conditional("B")>   
Shared Sub DoIfAandB()  
    ' Code to execute when both A and B are defined...  
End Sub  
```  
  
### <a name="using-conditional-with-attribute-classes"></a><span data-ttu-id="45447-198">조건부를 사용 하 여 특성 클래스</span><span class="sxs-lookup"><span data-stu-id="45447-198">Using Conditional with Attribute Classes</span></span>  
 <span data-ttu-id="45447-199">`Conditional` 특성은 특성 클래스 정의에 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45447-199">The `Conditional` attribute can also be applied to an attribute class definition.</span></span> <span data-ttu-id="45447-200">이 예제에서는 사용자 지정 특성 `Documentation` 디버그 정의 된 경우 메타 데이터 정보를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-200">In this example, the custom attribute `Documentation` will only add information to the metadata if DEBUG is defined.</span></span>  
  
```vb  
<Conditional("DEBUG")>   
Public Class Documentation  
    Inherits System.Attribute  
    Private text As String  
    Sub New(ByVal doc_text As String)  
        text = doc_text  
    End Sub  
End Class  
  
Class SampleClass  
    ' This attribute will only be included if DEBUG is defined.  
    <Documentation("This method displays an integer.")>   
    Shared Sub DoWork(ByVal i As Integer)  
        System.Console.WriteLine(i)  
    End Sub  
End Class  
```  
  
##  <span data-ttu-id="45447-201"><a name="CallerInfo"></a>호출자 정보 특성</span><span class="sxs-lookup"><span data-stu-id="45447-201"><a name="CallerInfo"></a> Caller Info Attributes</span></span>  
 <span data-ttu-id="45447-202">호출자 정보 특성을 사용하여 메서드 호출자에 대한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45447-202">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="45447-203">소스 코드의 파일 경로, 소스 코드와 호출자의 멤버 이름에 줄 번호를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45447-203">You can obtain the file path of the source code, the line number in the source code, and the member name of the caller.</span></span>  
  
 <span data-ttu-id="45447-204">멤버 호출자 정보를 사용 하 여 선택적 매개 변수에 적용 되는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="45447-204">To obtain member caller information, you use attributes that are applied to optional parameters.</span></span> <span data-ttu-id="45447-205">각 선택적 매개 변수 기본값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-205">Each optional parameter specifies a default value.</span></span> <span data-ttu-id="45447-206">에 정의 된 호출자 정보 특성을 나열 하는 다음 표에 <xref:System.Runtime.CompilerServices?displayProperty=fullName>네임 스페이스:</xref:System.Runtime.CompilerServices?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="45447-206">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=fullName> namespace:</span></span>  
  
|<span data-ttu-id="45447-207">특성</span><span class="sxs-lookup"><span data-stu-id="45447-207">Attribute</span></span>|<span data-ttu-id="45447-208">설명</span><span class="sxs-lookup"><span data-stu-id="45447-208">Description</span></span>|<span data-ttu-id="45447-209">형식</span><span class="sxs-lookup"><span data-stu-id="45447-209">Type</span></span>|  
|---|---|---|  
|<span data-ttu-id="45447-210"><xref:System.Runtime.CompilerServices.CallerFilePathAttribute></xref:System.Runtime.CompilerServices.CallerFilePathAttribute></span><span class="sxs-lookup"><span data-stu-id="45447-210"><xref:System.Runtime.CompilerServices.CallerFilePathAttribute></span></span>|<span data-ttu-id="45447-211">호출자를 포함한 소스 파일의 전체 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="45447-211">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="45447-212">컴파일 타임에는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="45447-212">This is the path at compile time.</span></span>|`String`|  
|<span data-ttu-id="45447-213"><xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></span><span class="sxs-lookup"><span data-stu-id="45447-213"><xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></span></span>|<span data-ttu-id="45447-214">메서드는 소스 파일의 줄 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="45447-214">Line number in the source file from which the method is called.</span></span>|`Integer`|  
|<span data-ttu-id="45447-215"><xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></span><span class="sxs-lookup"><span data-stu-id="45447-215"><xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></span></span>|<span data-ttu-id="45447-216">메서드 이름 또는 호출자의 속성 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="45447-216">Method name or property name of the caller.</span></span> <span data-ttu-id="45447-217">자세한 내용은 참조 [호출자 정보 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-217">For more information, see [Caller Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).</span></span>|`String`|  
  
 <span data-ttu-id="45447-218">호출자 정보 특성에 대 한 자세한 내용은 참조 [호출자 정보 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-218">For more information about the Caller Info attributes, see [Caller Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).</span></span>  
  
##  <span data-ttu-id="45447-219"><a name="VB"></a>Visual Basic 특성</span><span class="sxs-lookup"><span data-stu-id="45447-219"><a name="VB"></a> Visual Basic Attributes</span></span>  
 <span data-ttu-id="45447-220">다음 표에서 Visual Basic에 관련 된 특성을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-220">The following table lists the attributes that are specific to Visual Basic.</span></span>  
  
|<span data-ttu-id="45447-221">특성</span><span class="sxs-lookup"><span data-stu-id="45447-221">Attribute</span></span>|<span data-ttu-id="45447-222">용도</span><span class="sxs-lookup"><span data-stu-id="45447-222">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="45447-223"><xref:Microsoft.VisualBasic.ComClassAttribute></xref:Microsoft.VisualBasic.ComClassAttribute></span><span class="sxs-lookup"><span data-stu-id="45447-223"><xref:Microsoft.VisualBasic.ComClassAttribute></span></span>|<span data-ttu-id="45447-224">컴파일러에 알리는 클래스를 COM 개체로 노출 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-224">Indicates to the compiler that the class should be exposed as a COM object.</span></span>|  
|<span data-ttu-id="45447-225"><xref:Microsoft.VisualBasic.HideModuleNameAttribute></xref:Microsoft.VisualBasic.HideModuleNameAttribute></span><span class="sxs-lookup"><span data-stu-id="45447-225"><xref:Microsoft.VisualBasic.HideModuleNameAttribute></span></span>|<span data-ttu-id="45447-226">모듈 멤버를에 모듈에 필요한 정규화를 사용 하 여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45447-226">Allows module members to be accessed using only the qualification needed for the module.</span></span>|  
|<span data-ttu-id="45447-227"><xref:Microsoft.VisualBasic.VBFixedStringAttribute></xref:Microsoft.VisualBasic.VBFixedStringAttribute></span><span class="sxs-lookup"><span data-stu-id="45447-227"><xref:Microsoft.VisualBasic.VBFixedStringAttribute></span></span>|<span data-ttu-id="45447-228">파일 입력 및 출력으로 사용 하기 위해 구조에는 고정 길이 문자열의 크기를 지정 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="45447-228">Specifies the size of a fixed-length string in a structure for use with file input and output functions.</span></span>|  
|<span data-ttu-id="45447-229"><xref:Microsoft.VisualBasic.VBFixedArrayAttribute></xref:Microsoft.VisualBasic.VBFixedArrayAttribute></span><span class="sxs-lookup"><span data-stu-id="45447-229"><xref:Microsoft.VisualBasic.VBFixedArrayAttribute></span></span>|<span data-ttu-id="45447-230">파일 입력 및 출력으로 사용 하기 위해 구조의 고정 배열의 크기를 지정 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="45447-230">Specifies the size of a fixed array in a structure for use with file input and output functions.</span></span>|  
  
### <a name="comclassattribute"></a><span data-ttu-id="45447-231">COMClassAttribute</span><span class="sxs-lookup"><span data-stu-id="45447-231">COMClassAttribute</span></span>  
 <span data-ttu-id="45447-232">사용 하 여 `COMClassAttribute` Visual Basic에서 COM 구성 요소를 만드는 과정을 간소화 하기 위해.</span><span class="sxs-lookup"><span data-stu-id="45447-232">Use `COMClassAttribute` to simplify the process of creating COM components from Visual Basic.</span></span> <span data-ttu-id="45447-233">COM 개체는.NET Framework 어셈블리에서 및 없이 상당히 다른 `COMClassAttribute`를 위해 다양 한 Visual Basic에서 COM 개체를 생성 하는 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-233">COM objects are considerably different from .NET Framework assemblies, and without `COMClassAttribute`, you need to follow a number of steps to generate a COM object from Visual Basic.</span></span> <span data-ttu-id="45447-234">로 표시 된 클래스 `COMClassAttribute`, 컴파일러 여러이 단계를 자동으로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-234">For classes marked with `COMClassAttribute`, the compiler performs many of these steps automatically.</span></span>  
  
### <a name="hidemodulenameattribute"></a><span data-ttu-id="45447-235">HideModuleNameAttribute</span><span class="sxs-lookup"><span data-stu-id="45447-235">HideModuleNameAttribute</span></span>  
 <span data-ttu-id="45447-236">사용 하 여 `HideModuleNameAttribute` 모듈 멤버에 필요한 모듈에 대 한 한정만을 사용 하 여 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-236">Use `HideModuleNameAttribute` to allow module members to be accessed by using only the qualification needed for the module.</span></span>  
  
### <a name="vbfixedstringattribute"></a><span data-ttu-id="45447-237">VBFixedStringAttribute</span><span class="sxs-lookup"><span data-stu-id="45447-237">VBFixedStringAttribute</span></span>  
 <span data-ttu-id="45447-238">사용 하 여 `VBFixedStringAttribute` 고정 길이의 문자열을 만들려면 Visual Basic을 강제 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-238">Use `VBFixedStringAttribute` to force Visual Basic to create a fixed-length string.</span></span> <span data-ttu-id="45447-239">문자열에는 기본적으로 가변 길이 및이 특성은 문자열을 파일을 저장할 때 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-239">Strings are of variable length by default, and this attribute is useful when storing strings to files.</span></span> <span data-ttu-id="45447-240">다음 코드에서는이 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="45447-240">The following code demonstrates this:</span></span>  
  
```vb  
Structure Worker  
    ' The runtime uses VBFixedString to determine   
    ' if the field should be written out as a fixed size.  
    <VBFixedString(10)> Public LastName As String  
    <VBFixedString(7)> Public Title As String  
    <VBFixedString(2)> Public Rank As String  
End Structure  
```  
  
### <a name="vbfixedarrayattribute"></a><span data-ttu-id="45447-241">VBFixedArrayAttribute</span><span class="sxs-lookup"><span data-stu-id="45447-241">VBFixedArrayAttribute</span></span>  
 <span data-ttu-id="45447-242">사용 하 여 `VBFixedArrayAttribute` 크기가 고정 된 배열을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45447-242">Use `VBFixedArrayAttribute` to declare arrays that are fixed in size.</span></span> <span data-ttu-id="45447-243">배열은 Visual Basic 문자열 처럼 기본적으로 가변 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="45447-243">Like Visual Basic strings, arrays are of variable length by default.</span></span> <span data-ttu-id="45447-244">이 특성은 직렬화 또는 데이터 파일에 쓰는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="45447-244">This attribute is useful when serializing or writing data to files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45447-245">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45447-245">See Also</span></span>  
 <span data-ttu-id="45447-246"><xref:System.Reflection></xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="45447-246"><xref:System.Reflection></span></span>   
 <span data-ttu-id="45447-247"><xref:System.Attribute></xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="45447-247"><xref:System.Attribute></span></span>   
<span data-ttu-id="45447-248"> [Visual Basic 프로그래밍 가이드](../../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="45447-248"> [Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md) </span></span>  
<span data-ttu-id="45447-249"> [특성](https://msdn.microsoft.com/library/5x6cd29c) </span><span class="sxs-lookup"><span data-stu-id="45447-249"> [Attributes](https://msdn.microsoft.com/library/5x6cd29c) </span></span>  
<span data-ttu-id="45447-250"> [리플렉션 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="45447-250"> [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span></span>  
<span data-ttu-id="45447-251"> [(Visual Basic) 리플렉션을 사용 하 여 특성 액세스](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span><span class="sxs-lookup"><span data-stu-id="45447-251"> [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span></span>
