---
title: "공통 특성(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 785a0526-6c0e-4599-8c61-ccdc88dd9965
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: aded9c9b2e8c253eebd6c71782f0bff6ca0104ea
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="common-attributes-c"></a><span data-ttu-id="901f9-102">공통 특성(C#)</span><span class="sxs-lookup"><span data-stu-id="901f9-102">Common Attributes (C#)</span></span>
<span data-ttu-id="901f9-103">이 항목에서는 C# 프로그램에서 가장 일반적으로 사용되는 특성을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-103">This topic describes the attributes that are most commonly used in C# programs.</span></span>  
  
-   [<span data-ttu-id="901f9-104">전역 특성</span><span class="sxs-lookup"><span data-stu-id="901f9-104">Global Attributes</span></span>](#Global)  
  
-   [<span data-ttu-id="901f9-105">사용되지 않는 특성</span><span class="sxs-lookup"><span data-stu-id="901f9-105">Obsolete Attribute</span></span>](#Obsolete)  
  
-   [<span data-ttu-id="901f9-106">조건부 특성</span><span class="sxs-lookup"><span data-stu-id="901f9-106">Conditional Attribute</span></span>](#Conditional)  
  
-   [<span data-ttu-id="901f9-107">호출자 정보 특성</span><span class="sxs-lookup"><span data-stu-id="901f9-107">Caller Info Attributes</span></span>](#CallerInfo)  
  
##  <a name="Global"></a> <span data-ttu-id="901f9-108">전역 특성</span><span class="sxs-lookup"><span data-stu-id="901f9-108">Global Attributes</span></span>  
 <span data-ttu-id="901f9-109">대부분의 특성은 클래스나 메서드와 같은 특정 언어 요소에 적용되지만 일부 특성은 전체 어셈블리나 모듈에 적용되는 전역 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-109">Most attributes are applied to specific language elements such as classes or methods; however, some attributes are global—they apply to an entire assembly or module.</span></span> <span data-ttu-id="901f9-110">예를 들어 다음과 같이 <xref:System.Reflection.AssemblyVersionAttribute> 특성을 사용하여 버전 정보를 어셈블리에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-110">For example, the <xref:System.Reflection.AssemblyVersionAttribute> attribute can be used to embed version information into an assembly, like this:</span></span>  
  
```csharp  
[assembly: AssemblyVersion("1.0.0.0")]  
```  
  
 <span data-ttu-id="901f9-111">전역 특성은 소스 코드에서 최상위 `using` 지시문 뒤와 형식, 모듈 또는 네임스페이스 선언 앞에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-111">Global attributes appear in the source code after any top-level `using` directives and before any type, module, or namespace declarations.</span></span> <span data-ttu-id="901f9-112">전역 특성은 여러 소스 파일에 나타날 수 있지만 파일은 하나의 컴파일 패스에서 컴파일되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-112">Global attributes can appear in multiple source files, but the files must be compiled in a single compilation pass.</span></span> <span data-ttu-id="901f9-113">C# 프로젝트에서 전역 특성은 AssemblyInfo.cs 파일에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-113">In C# projects, global attributes are put in the AssemblyInfo.cs file.</span></span>  
  
 <span data-ttu-id="901f9-114">어셈블리 특성은 어셈블리에 대한 정보를 제공하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-114">Assembly attributes are values that provide information about an assembly.</span></span> <span data-ttu-id="901f9-115">어셈블리 특성은 다음 범주로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-115">They fall into the following categories:</span></span>  
  
-   <span data-ttu-id="901f9-116">어셈블리 ID 특성</span><span class="sxs-lookup"><span data-stu-id="901f9-116">Assembly identity attributes</span></span>  
  
-   <span data-ttu-id="901f9-117">정보 특성</span><span class="sxs-lookup"><span data-stu-id="901f9-117">Informational attributes</span></span>  
  
-   <span data-ttu-id="901f9-118">어셈블리 매니페스트 특성</span><span class="sxs-lookup"><span data-stu-id="901f9-118">Assembly manifest attributes</span></span>  
  
### <a name="assembly-identity-attributes"></a><span data-ttu-id="901f9-119">어셈블리 ID 특성</span><span class="sxs-lookup"><span data-stu-id="901f9-119">Assembly Identity Attributes</span></span>  
 <span data-ttu-id="901f9-120">name, version 및 culture의 세 가지 특성(해당하는 경우 강력한 이름 포함)이 어셈블리의 ID를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-120">Three attributes (with a strong name, if applicable) determine the identity of an assembly: name, version, and culture.</span></span> <span data-ttu-id="901f9-121">이러한 특성은 어셈블리의 전체 이름을 구성하며 코드에서 어셈블리를 참조할 때 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-121">These attributes form the full name of the assembly and are required when you reference it in code.</span></span> <span data-ttu-id="901f9-122">특성을 사용하여 어셈블리의 버전 및 문화권을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-122">You can set an assembly's version and culture using attributes.</span></span> <span data-ttu-id="901f9-123">그러나 이름 값은 어셈블리가 만들어질 때 어셈블리 매니페스트가 포함된 파일에 따라 컴파일러, [어셈블리 정보 대화 상자](/visualstudio/ide/reference/assembly-information-dialog-box)의 Visual Studio IDE 또는 어셈블리 링커(Al.exe)에서 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-123">However, the name value is set by the compiler, the Visual Studio IDE in the [Assembly Information Dialog Box](/visualstudio/ide/reference/assembly-information-dialog-box), or the Assembly Linker (Al.exe) when the assembly is created, based on the file that contains the assembly manifest.</span></span> <span data-ttu-id="901f9-124"><xref:System.Reflection.AssemblyFlagsAttribute> 특성은 어셈블리의 여러 복사본이 공존할 수 있는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-124">The <xref:System.Reflection.AssemblyFlagsAttribute> attribute specifies whether multiple copies of the assembly can coexist.</span></span>  
  
 <span data-ttu-id="901f9-125">다음 표에서는 ID 특성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-125">The following table shows the identity attributes.</span></span>  
  
|<span data-ttu-id="901f9-126">특성</span><span class="sxs-lookup"><span data-stu-id="901f9-126">Attribute</span></span>|<span data-ttu-id="901f9-127">용도</span><span class="sxs-lookup"><span data-stu-id="901f9-127">Purpose</span></span>|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyName>|<span data-ttu-id="901f9-128">어셈블리의 ID를 완전히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-128">Fully describes the identity of an assembly.</span></span>|  
|<xref:System.Reflection.AssemblyVersionAttribute>|<span data-ttu-id="901f9-129">어셈블리의 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-129">Specifies the version of an assembly.</span></span>|  
|<xref:System.Reflection.AssemblyCultureAttribute>|<span data-ttu-id="901f9-130">어셈블리에서 지원하는 문화권을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-130">Specifies which culture the assembly supports.</span></span>|  
|<xref:System.Reflection.AssemblyFlagsAttribute>|<span data-ttu-id="901f9-131">어셈블리가 같은 컴퓨터, 같은 프로세스 또는 같은 응용 프로그램 도메인에서 Side-by-side 실행을 지원하는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-131">Specifies whether an assembly supports side-by-side execution on the same computer, in the same process, or in the same application domain.</span></span>|  
  
### <a name="informational-attributes"></a><span data-ttu-id="901f9-132">정보 특성</span><span class="sxs-lookup"><span data-stu-id="901f9-132">Informational Attributes</span></span>  
 <span data-ttu-id="901f9-133">정보 특성을 사용하여 어셈블리에 대한 추가 회사 또는 제품 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-133">You can use informational attributes to provide additional company or product information for an assembly.</span></span> <span data-ttu-id="901f9-134">다음 표에서는 <xref:System.Reflection?displayProperty=nameWithType> 네임스페이스에 정의된 정보 특성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-134">The following table shows the informational attributes defined in the <xref:System.Reflection?displayProperty=nameWithType> namespace.</span></span>  
  
|<span data-ttu-id="901f9-135">특성</span><span class="sxs-lookup"><span data-stu-id="901f9-135">Attribute</span></span>|<span data-ttu-id="901f9-136">용도</span><span class="sxs-lookup"><span data-stu-id="901f9-136">Purpose</span></span>|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyProductAttribute>|<span data-ttu-id="901f9-137">어셈블리 매니페스트에 대한 제품 이름을 지정하는 사용자 지정 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-137">Defines a custom attribute that specifies a product name for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyTrademarkAttribute>|<span data-ttu-id="901f9-138">어셈블리 매니페스트에 대한 상표를 지정하는 사용자 지정 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-138">Defines a custom attribute that specifies a trademark for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|<span data-ttu-id="901f9-139">어셈블리 매니페스트에 대한 정보 버전을 지정하는 사용자 지정 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-139">Defines a custom attribute that specifies an informational version for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyCompanyAttribute>|<span data-ttu-id="901f9-140">어셈블리 매니페스트에 대한 회사 이름을 지정하는 사용자 지정 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-140">Defines a custom attribute that specifies a company name for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyCopyrightAttribute>|<span data-ttu-id="901f9-141">어셈블리 매니페스트에 대한 저작권을 지정하는 사용자 지정 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-141">Defines a custom attribute that specifies a copyright for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyFileVersionAttribute>|<span data-ttu-id="901f9-142">Win32 파일 버전 리소스에 대한 특정 버전 번호를 사용하도록 컴파일러에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-142">Instructs the compiler to use a specific version number for the Win32 file version resource.</span></span>|  
|<xref:System.CLSCompliantAttribute>|<span data-ttu-id="901f9-143">어셈블리가 CLS(공용 언어 사양)을 준수하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-143">Indicates whether the assembly is compliant with the Common Language Specification (CLS).</span></span>|  
  
### <a name="assembly-manifest-attributes"></a><span data-ttu-id="901f9-144">어셈블리 매니페스트 특성</span><span class="sxs-lookup"><span data-stu-id="901f9-144">Assembly Manifest Attributes</span></span>  
 <span data-ttu-id="901f9-145">어셈블리 매니페스트 특성을 사용하여 어셈블리 매니페스트의 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-145">You can use assembly manifest attributes to provide information in the assembly manifest.</span></span> <span data-ttu-id="901f9-146">정보에는 제목, 설명, 기본 별칭 및 구성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-146">This includes title, description, default alias, and configuration.</span></span> <span data-ttu-id="901f9-147">다음 표에서는 <xref:System.Reflection?displayProperty=nameWithType> 네임스페이스에 정의된 어셈블리 매니페스트 특성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-147">The following table shows the assembly manifest attributes defined in the <xref:System.Reflection?displayProperty=nameWithType> namespace.</span></span>  
  
|<span data-ttu-id="901f9-148">특성</span><span class="sxs-lookup"><span data-stu-id="901f9-148">Attribute</span></span>|<span data-ttu-id="901f9-149">용도</span><span class="sxs-lookup"><span data-stu-id="901f9-149">Purpose</span></span>|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyTitleAttribute>|<span data-ttu-id="901f9-150">어셈블리 매니페스트에 대한 어셈블리 제목을 지정하는 사용자 지정 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-150">Defines a custom attribute that specifies an assembly title for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyDescriptionAttribute>|<span data-ttu-id="901f9-151">어셈블리 매니페스트에 대한 어셈블리 설명을 지정하는 사용자 지정 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-151">Defines a custom attribute that specifies an assembly description for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyConfigurationAttribute>|<span data-ttu-id="901f9-152">어셈블리 매니페스트에 대한 어셈블리 구성(예: 정품 또는 디버그)을 지정하는 사용자 지정 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-152">Defines a custom attribute that specifies an assembly configuration (such as retail or debug) for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|<span data-ttu-id="901f9-153">어셈블리 매니페스트에 대한 친숙한 기본 별칭을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-153">Defines a friendly default alias for an assembly manifest</span></span>|  
  
##  <a name="Obsolete"></a> <span data-ttu-id="901f9-154">사용되지 않는 특성</span><span class="sxs-lookup"><span data-stu-id="901f9-154">Obsolete Attribute</span></span>  
 <span data-ttu-id="901f9-155">`Obsolete` 특성은 프로그램 엔터티를 더 이상 사용이 권장되지 않는 항목으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-155">The `Obsolete` attribute marks a program entity as one that is no longer recommended for use.</span></span> <span data-ttu-id="901f9-156">나중에 사용되지 않음으로 표시된 엔터티를 사용할 때마다 특성 구성 방법에 따라 경고나 오류가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-156">Each use of an entity marked obsolete will subsequently generate a warning or an error, depending on how the attribute is configured.</span></span> <span data-ttu-id="901f9-157">예:</span><span class="sxs-lookup"><span data-stu-id="901f9-157">For example:</span></span>  
  
```csharp  
[System.Obsolete("use class B")]  
class A  
{  
    public void Method() { }  
}  
class B  
{  
    [System.Obsolete("use NewMethod", true)]  
    public void OldMethod() { }  
    public void NewMethod() { }  
}  
```  
  
 <span data-ttu-id="901f9-158">이 예제에서는 `Obsolete` 특성이 `A` 클래스 및 `B.OldMethod` 메서드에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-158">In this example the `Obsolete` attribute is applied to class `A` and to method `B.OldMethod`.</span></span> <span data-ttu-id="901f9-159">`B.OldMethod`에 적용된 특성 생성자의 두 번째 인수가 `true`로 설정되므로 이 메서드는 컴파일러 오류를 일으키지만, `A` 클래스를 사용하면 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-159">Because the second argument of the attribute constructor applied to `B.OldMethod` is set to `true`, this method will cause a compiler error, whereas using class `A` will just produce a warning.</span></span> <span data-ttu-id="901f9-160">그러나 `B.NewMethod`를 호출하면 경고나 오류가 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-160">Calling `B.NewMethod`, however, produces no warning or error.</span></span>  
  
 <span data-ttu-id="901f9-161">특성 생성자에 첫 번째 인수로 제공된 문자열은 경고 또는 오류의 일부로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-161">The string provided as the first argument to attribute constructor will be displayed as part of the warning or error.</span></span> <span data-ttu-id="901f9-162">예를 들어 이전 정의와 함께 사용할 경우 다음 코드에서는 두 개의 경고 및 하나의 오류가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-162">For example, when you use it with the previous definitions, the following code generates two warnings and one error:</span></span>  
  
```csharp  
// Generates 2 warnings:  
// A a = new A();  
  
// Generate no errors or warnings:  
B b = new B();  
b.NewMethod();  
  
// Generates an error, terminating compilation:  
// b.OldMethod();  
```  
  
 <span data-ttu-id="901f9-163">`A` 클래스에 대한 두 개의 경고가 각각 클래스 참조 선언 및 클래스 생성자에 대해 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-163">Two warnings for class `A` are generated: one for the declaration of the class reference, and one for the class constructor.</span></span>  
  
 <span data-ttu-id="901f9-164">`Obsolete` 특성은 인수 없이 사용할 수 있지만 항목이 사용되지 않는 이유와 대신 사용이 권장되는 항목에 대한 설명을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-164">The `Obsolete` attribute can be used without arguments, but including an explanation of why the item is obsolete and what to use instead is recommended.</span></span>  
  
 <span data-ttu-id="901f9-165">`Obsolete` 특성은 단일 사용 특성이고 특성을 허용하는 모든 엔터티에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-165">The `Obsolete` attribute is a single-use attribute and can be applied to any entity that allows attributes.</span></span> <span data-ttu-id="901f9-166">`Obsolete`는 <xref:System.ObsoleteAttribute>의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-166">`Obsolete` is an alias for <xref:System.ObsoleteAttribute>.</span></span>  
  
##  <a name="Conditional"></a> <span data-ttu-id="901f9-167">조건부 특성</span><span class="sxs-lookup"><span data-stu-id="901f9-167">Conditional Attribute</span></span>  
 <span data-ttu-id="901f9-168">`Conditional` 특성을 사용하면 메서드 실행이 전처리 식별자에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-168">The `Conditional` attribute makes the execution of a method dependent on a preprocessing identifier.</span></span> <span data-ttu-id="901f9-169">`Conditional` 특성은 <xref:System.Diagnostics.ConditionalAttribute>의 별칭이고 메서드 또는 특성 클래스에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-169">The `Conditional` attribute is an alias for <xref:System.Diagnostics.ConditionalAttribute>, and can be applied to a method or an attribute class.</span></span>  
  
 <span data-ttu-id="901f9-170">이 예제에서 `Conditional`은 프로그램 관련 진단 정보 표시를 사용하거나 사용하지 않도록 설정하는 메서드에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-170">In this example, `Conditional` is applied to a method to enable or disable the display of program-specific diagnostic information:</span></span>  
  
```csharp  
#define TRACE_ON  
using System;  
using System.Diagnostics;  
  
public class Trace  
{  
    [Conditional("TRACE_ON")]  
    public static void Msg(string msg)  
    {  
        Console.WriteLine(msg);  
    }  
}  
  
public class ProgramClass  
{  
    static void Main()  
    {  
        Trace.Msg("Now in Main...");  
        Console.WriteLine("Done.");  
    }  
}  
```  
  
 <span data-ttu-id="901f9-171">`TRACE_ON` 식별자가 정의되지 않으면 추적 출력이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-171">If the `TRACE_ON` identifier is not defined, no trace output will be displayed.</span></span>  
  
 <span data-ttu-id="901f9-172">`Conditional` 특성은 보통 `DEBUG` 식별자와 함께 사용하여 다음과 같이 릴리스 빌드가 아닌 디버그 빌드의 추적 및 로깅 기능을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-172">The `Conditional` attribute is often used with the `DEBUG` identifier to enable trace and logging features for debug builds but not in release builds, like this:</span></span>  
  
```csharp  
[Conditional("DEBUG")]  
static void DebugMethod()  
{  
}  
```  
  
 <span data-ttu-id="901f9-173">조건부로 표시된 메서드를 호출하면 지정된 전처리 기호가 있는지 여부에 따라 호출을 포함 또는 생략할지 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-173">When a method marked as conditional is called, the presence or absence of the specified preprocessing symbol determines whether the call is included or omitted.</span></span> <span data-ttu-id="901f9-174">기호가 정의되면 호출이 포함되고, 정의되지 않으면 호출이 생략됩니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-174">If the symbol is defined, the call is included; otherwise, the call is omitted.</span></span> <span data-ttu-id="901f9-175">다음과 같이 메서드를 `#if…#endif` 블록 내부에 포함하는 것보다 `Conditional`을 사용하는 것이 더 분명하고 더 정교하며 오류 가능성이 더 적습니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-175">Using `Conditional` is a cleaner, more elegant, and less error-prone alternative to enclosing methods inside `#if…#endif` blocks, like this:</span></span>  
  
```csharp  
#if DEBUG  
    void ConditionalMethod()  
    {  
    }  
#endif  
```  
  
 <span data-ttu-id="901f9-176">조건부 메서드는 클래스 또는 구조체 선언의 메서드여야 하고 반환 값을 포함하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-176">A conditional method must be a method in a class or struct declaration and must not have a return value.</span></span>  
  
### <a name="using-multiple-identifiers"></a><span data-ttu-id="901f9-177">여러 식별자 사용</span><span class="sxs-lookup"><span data-stu-id="901f9-177">Using Multiple Identifiers</span></span>  
 <span data-ttu-id="901f9-178">한 메서드에 여러 `Conditional` 특성이 있을 경우 조건부 기호 중 하나 이상이 정의되면(즉, 기호가 OR 연산자를 통해 논리적으로 함께 연결되면) 메서드 호출이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-178">If a method has multiple `Conditional` attributes, a call to the method is included if at least one of the conditional symbols is defined (in other words, the symbols are logically linked together by using the OR operator).</span></span> <span data-ttu-id="901f9-179">이 예제에서는 `A` 또는 `B`가 있으면 메서드 호출이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-179">In this example, the presence of either `A` or `B` will result in a method call:</span></span>  
  
```csharp  
[Conditional("A"), Conditional("B")]  
static void DoIfAorB()  
{  
    // ...  
}  
```  
  
 <span data-ttu-id="901f9-180">AND 연산자를 통해 기호를 논리적으로 연결하는 결과를 얻으려면 순차적 조건부 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-180">To achieve the effect of logically linking symbols by using the AND operator, you can define serial conditional methods.</span></span> <span data-ttu-id="901f9-181">예를 들어 아래 두 번째 메서드는 `A` 및 `B`가 둘 다 정의된 경우에만 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-181">For example, the second method below will execute only if both `A` and `B` are defined:</span></span>  
  
```csharp
[Conditional("A")]  
static void DoIfA()  
{  
    DoIfAandB();  
}  
  
[Conditional("B")]  
static void DoIfAandB()  
{  
    // Code to execute when both A and B are defined...  
}  
```  
  
### <a name="using-conditional-with-attribute-classes"></a><span data-ttu-id="901f9-182">특성 클래스와 함께 조건부 사용</span><span class="sxs-lookup"><span data-stu-id="901f9-182">Using Conditional with Attribute Classes</span></span>  
 <span data-ttu-id="901f9-183">`Conditional` 특성을 특성 클래스 정의에 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-183">The `Conditional` attribute can also be applied to an attribute class definition.</span></span> <span data-ttu-id="901f9-184">이 예제에서 사용자 지정 특성 `Documentation`은 DEBUG가 정의된 경우에만 메타데이터에 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-184">In this example, the custom attribute `Documentation` will only add information to the metadata if DEBUG is defined.</span></span>  
  
```csharp  
[Conditional("DEBUG")]  
public class Documentation : System.Attribute  
{  
    string text;  
  
    public Documentation(string text)  
    {  
        this.text = text;  
    }  
}  
  
class SampleClass  
{  
    // This attribute will only be included if DEBUG is defined.  
    [Documentation("This method displays an integer.")]  
    static void DoWork(int i)  
    {  
        System.Console.WriteLine(i.ToString());  
    }  
}  
```  
  
##  <a name="CallerInfo"></a> <span data-ttu-id="901f9-185">호출자 정보 특성</span><span class="sxs-lookup"><span data-stu-id="901f9-185">Caller Info Attributes</span></span>  
 <span data-ttu-id="901f9-186">호출자 정보 특성을 사용하여 메서드 호출자에 대한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-186">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="901f9-187">소스 코드 파일 경로, 소스 코드 줄 번호 및 호출자의 멤버 이름을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-187">You can obtain the file path of the source code, the line number in the source code, and the member name of the caller.</span></span>  
  
 <span data-ttu-id="901f9-188">멤버 호출자 정보를 얻으려면 선택적 매개 변수에 적용되는 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-188">To obtain member caller information, you use attributes that are applied to optional parameters.</span></span> <span data-ttu-id="901f9-189">각 선택적 매개 변수는 기본값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-189">Each optional parameter specifies a default value.</span></span> <span data-ttu-id="901f9-190">다음 표에서는 <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> 네임스페이스에 정의된 호출자 정보 특성을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-190">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace:</span></span>  
  
|<span data-ttu-id="901f9-191">특성</span><span class="sxs-lookup"><span data-stu-id="901f9-191">Attribute</span></span>|<span data-ttu-id="901f9-192">설명</span><span class="sxs-lookup"><span data-stu-id="901f9-192">Description</span></span>|<span data-ttu-id="901f9-193">형식</span><span class="sxs-lookup"><span data-stu-id="901f9-193">Type</span></span>|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|<span data-ttu-id="901f9-194">호출자를 포함한 소스 파일의 전체 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-194">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="901f9-195">컴파일 시간의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-195">This is the path at compile time.</span></span>|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|<span data-ttu-id="901f9-196">메서드가 호출되는 소스 파일의 줄 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-196">Line number in the source file from which the method is called.</span></span>|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|<span data-ttu-id="901f9-197">호출자의 메서드 이름 또는 속성 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="901f9-197">Method name or property name of the caller.</span></span> <span data-ttu-id="901f9-198">자세한 내용은 [호출자 정보(C#)](../../../../csharp/programming-guide/concepts/caller-information.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="901f9-198">For more information, see [Caller Information (C#)](../../../../csharp/programming-guide/concepts/caller-information.md).</span></span>|`String`|  
  
 <span data-ttu-id="901f9-199">호출자 정보 특성에 대한 자세한 내용은 [호출자 정보(C#)](../../../../csharp/programming-guide/concepts/caller-information.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="901f9-199">For more information about the Caller Info attributes, see [Caller Information (C#)](../../../../csharp/programming-guide/concepts/caller-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="901f9-200">참고 항목</span><span class="sxs-lookup"><span data-stu-id="901f9-200">See Also</span></span>  
 <xref:System.Reflection>  
 <xref:System.Attribute>  
 [<span data-ttu-id="901f9-201">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="901f9-201">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="901f9-202">특성</span><span class="sxs-lookup"><span data-stu-id="901f9-202">Attributes</span></span>](https://msdn.microsoft.com/library/5x6cd29c)  
 [<span data-ttu-id="901f9-203">리플렉션(C#)</span><span class="sxs-lookup"><span data-stu-id="901f9-203">Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/reflection.md)  
 [<span data-ttu-id="901f9-204">리플렉션을 사용하여 특성 액세스(C#)</span><span class="sxs-lookup"><span data-stu-id="901f9-204">Accessing Attributes by Using Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
