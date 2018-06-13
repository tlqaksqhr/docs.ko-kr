---
title: .NET 보안 분석기 - .NET
description: .NET Framework 분석기 패키지에서 .NET 보안 분석기를 사용하여 보안 위험을 찾아 해결하는 방법을 알아봅니다.
author: billwagner
ms.author: billwagner
ms.date: 01/25/2018
ms.technology: dotnet-standard
ms.openlocfilehash: 904218c177ea45f82a73b4532ce3230af954aa85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33574623"
---
# <a name="the-net-framework-analyzer"></a><span data-ttu-id="c7ced-103">.NET Framework 분석기</span><span class="sxs-lookup"><span data-stu-id="c7ced-103">The .NET Framework Analyzer</span></span>

<span data-ttu-id="c7ced-104">.NET Framework 분석기를 사용하여 .NET Framework 기반 응용 프로그램 코드에서 잠재적인 문제를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-104">You can use the .NET Framework Analyzer to find potential issues in your .NET Framework-based application code.</span></span> <span data-ttu-id="c7ced-105">이 분석기는 잠재적인 문제를 찾고 해결 방법을 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-105">This analyzer finds potential issues and suggests fixes to them.</span></span>

<span data-ttu-id="c7ced-106">분석기는 코드를 작성하거나 CI 빌드의 일부와 같이 Visual Studio에서 대화형으로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-106">The analyzer runs interactively in Visual Studio as you write your code or as part of a CI build.</span></span> <span data-ttu-id="c7ced-107">개발 시 가능한 빨리 분석기를 프로젝트에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-107">You should add the analyzer to your project as early as possible in your development.</span></span> <span data-ttu-id="c7ced-108">코드의 잠재적 문제를 신속하게 발견하면 이를 쉽게 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-108">The sooner you find any potential issues in your code, the easier they are to fix.</span></span> <span data-ttu-id="c7ced-109">그러나 언제든지 개발 주기에서 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-109">However, you can add it at any time in the development cycle.</span></span> <span data-ttu-id="c7ced-110">기존 코드에 문제가 있는지 찾고 계속 개발하는 경우 새로운 문제에 대해 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-110">It finds any issues with the existing code and warns about new issues as you keep developing.</span></span>

## <a name="installing-and-configuring-the-net-framework-analyzer"></a><span data-ttu-id="c7ced-111">.NET Framework 분석기 설치 및 구성</span><span class="sxs-lookup"><span data-stu-id="c7ced-111">Installing and configuring the .NET Framework Analyzer</span></span>

<span data-ttu-id="c7ced-112">.NET 보안 분석기를 실행하려는 모든 프로젝트에서 NuGet 패키지로 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-112">The .NET Security Analyzers must be installed as a NuGet package on every project where you want them to run.</span></span> <span data-ttu-id="c7ced-113">한 명의 개발자만이 이를 프로젝트에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-113">Only one developer needs to add them to the project.</span></span> <span data-ttu-id="c7ced-114">분석기 패키지는 프로젝트에 종속된 기능이며 업데이트된 솔루션이 포함되면 모든 개발자의 컴퓨터에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-114">The analyzer package is a project dependency and will run on every developer's machine once it has the updated solution.</span></span>

<span data-ttu-id="c7ced-115">.NET Framework 분석기는 [Microsoft.NetFramework.Analyzers](https://www.nuget.org/packages/Microsoft.NetFramework.Analyzers/) NuGet 패키지에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-115">The .NET Framework Analyzer is delivered in the [Microsoft.NetFramework.Analyzers](https://www.nuget.org/packages/Microsoft.NetFramework.Analyzers/) NuGet package.</span></span> <span data-ttu-id="c7ced-116">이 패키지는 보안 분석기를 포함하는 .NET Framework에 특정 분석기만을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-116">This package provides only the analyzers specific to the .NET Framework, which includes security analyzers.</span></span> <span data-ttu-id="c7ced-117">대부분의 경우에 [Microsoft.CodeAnalysis.FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers) NuGet 패키지가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-117">In most cases, you'll want the [Microsoft.CodeAnalysis.FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers) NuGet package.</span></span> <span data-ttu-id="c7ced-118">FxCopAnalyzers 집계 패키지에는 다음 분석기뿐만 아니라 Framework.Analyzers 패키지에 포함된 모든 프레임워크 분석기가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-118">The FxCopAnalyzers aggregate package contains all the framework analyzers included in the Framework.Analyzers package as well as the following analyzers:</span></span>
- <span data-ttu-id="c7ced-119">[Microsoft.CodeQuality.Analyzers](https://www.nuget.org/packages/Microsoft.CodeQuality.Analyzers): .NET Standard API에 대한 일반 지침 및 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-119">[Microsoft.CodeQuality.Analyzers](https://www.nuget.org/packages/Microsoft.CodeQuality.Analyzers): Provides general guidance and guidance for .NET Standard APIs</span></span>
- <span data-ttu-id="c7ced-120">[Microsoft.NetCore.Analyzers](https://www.nuget.org/packages/Microsoft.NetCore.Analyzers): .NET Core API에 특정된 분석기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-120">[Microsoft.NetCore.Analyzers](https://www.nuget.org/packages/Microsoft.NetCore.Analyzers): Provides analyzers specific to .NET Core APIs.</span></span>
- <span data-ttu-id="c7ced-121">[Text.Analyzers](https://www.nuget.org/packages/Text.Analyzers): 주석을 비롯하여 코드로 포함된 텍스트의 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-121">[Text.Analyzers](https://www.nuget.org/packages/Text.Analyzers): Provides guidance for text included as code, including comments.</span></span>

<span data-ttu-id="c7ced-122">이를 설치하려면 프로젝트를 마우스 오른쪽 단추로 클릭하고, "종속성 관리"를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-122">To install it, right-click on the project, and select "Manage Dependencies".</span></span>
<span data-ttu-id="c7ced-123">NuGet 탐색기에서 "NetFramework 분석기"를 검색하거나 선호하는 경우 "Fx Cop 분석기"를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-123">From the NuGet explorer, search for "NetFramework Analyzer", or if you prefer, "Fx Cop Analyzer".</span></span> <span data-ttu-id="c7ced-124">솔루션의 모든 프로젝트에 안정적인 최신 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-124">Install the latest stable version in all projects in your solution.</span></span>

## <a name="using-the-net-framework-analyzer"></a><span data-ttu-id="c7ced-125">.NET Framework 분석기 사용</span><span class="sxs-lookup"><span data-stu-id="c7ced-125">Using the .NET Framework Analyzer</span></span>

<span data-ttu-id="c7ced-126">NuGet 패키지를 설치하면 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-126">Once the NuGet package is installed, build your solution.</span></span> <span data-ttu-id="c7ced-127">분석기는 코드베이스에서 찾은 모든 문제를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-127">The analyzer will report any issues it locates in your codebase.</span></span> <span data-ttu-id="c7ced-128">다음 그림에 표시된 대로 문제는 Visual Studio 오류 목록 창에 경고로 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-128">The issues are reported as warnings in the Visual Studio Error List window, as shown in the following image:</span></span>

![프레임워크 분석기에서 보고한 문제](./media/framework-analyzers-2.png)

<span data-ttu-id="c7ced-130">코드를 작성할 때 코드에 있는 잠재적 문제 아래에 물결선이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-130">As you write code, you see squiggles underneath any potential issue in your code.</span></span>
<span data-ttu-id="c7ced-131">다음 이미지에 표시된 대로 문제를 마우스로 가리키고 문제에 대한 세부 정보 및 가능한 수정 제안 사항을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-131">Hover over any issue and you see details about the issue, and suggestions for any possible fix, as shown in the following image:</span></span>

![프레임워크 분석기에 의해 발견된 문제의 대화형 보고서](./media/framework-analyzers-1.png)

<span data-ttu-id="c7ced-133">분석기는 솔루션에서 코드를 검사하고 이러한 문제 중 하나에 대한 경고 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-133">The analyzers examine the code in your solution and provide you with a list of warnings for any of these issues:</span></span>

### <a name="ca1058-types-should-not-extend-certain-base-types"></a><span data-ttu-id="c7ced-134">CA1058: 형식은 특정 기본 형식을 확장하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-134">CA1058: Types should not extend certain base types</span></span>

<span data-ttu-id="c7ced-135">.NET Framework에 직접 파생하지 않은 몇몇 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-135">There are a small number of types in the .NET Framework that you should not derived from directly.</span></span> 

<span data-ttu-id="c7ced-136">**범주:** 디자인</span><span class="sxs-lookup"><span data-stu-id="c7ced-136">**Category:** Design</span></span>

<span data-ttu-id="c7ced-137">**심각도:** 경고</span><span class="sxs-lookup"><span data-stu-id="c7ced-137">**Severity:** Warning</span></span>

<span data-ttu-id="c7ced-138">추가 정보: [CA:1058: 형식은 특정 기본 형식을 확장하지 않습니다.](/visualstudio/code-quality/ca1058-types-should-not-extend-certain-base-types)</span><span class="sxs-lookup"><span data-stu-id="c7ced-138">Additional information: [CA:1058: Types should not extend certain base types](/visualstudio/code-quality/ca1058-types-should-not-extend-certain-base-types)</span></span>

### <a name="ca2153-do-not-catch-corrupted-state-exceptions"></a><span data-ttu-id="c7ced-139">CA2153: 손상된 상태 예외를 catch하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-139">CA2153: Do not catch corrupted state exceptions</span></span>

<span data-ttu-id="c7ced-140">손상된 상태 예외를 catch하면 오류(예: 액세스 위반)를 마스킹할 수 있습니다. 그러면 실행의 일관성이 없는 상태가 발생하거나 공격자가 쉽게 시스템을 손상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-140">Catching corrupted state exceptions could mask errors (such as access violations), resulting in an inconsistent state of execution or making it easier for attackers to compromise a system.</span></span> <span data-ttu-id="c7ced-141">대신 구체적인 예외 형식을 catch하고 처리하거나 예외를 다시 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-141">Instead, catch and handle a more specific set of exception type(s) or re-throw the exception</span></span>

<span data-ttu-id="c7ced-142">**범주:** 보안</span><span class="sxs-lookup"><span data-stu-id="c7ced-142">**Category:** Security</span></span>

<span data-ttu-id="c7ced-143">**심각도:** 경고</span><span class="sxs-lookup"><span data-stu-id="c7ced-143">**Severity:** Warning</span></span>

<span data-ttu-id="c7ced-144">추가 정보: [## CA2153: 손상된 상태 예외를 catch하지 않습니다.](/visualstudio/code-quality/ca2153-avoid-handling-corrupted-state-exceptions)</span><span class="sxs-lookup"><span data-stu-id="c7ced-144">Additional information: [## CA2153: Do not catch corrupted state exceptions](/visualstudio/code-quality/ca2153-avoid-handling-corrupted-state-exceptions)</span></span>

### <a name="ca2229-implement-serialization-constructors"></a><span data-ttu-id="c7ced-145">CA2229: serialization 생성자를 구현하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7ced-145">CA2229: Implement serialization constructors</span></span>

<span data-ttu-id="c7ced-146">분석기는 <xref:System.Runtime.Serialization.ISerializable> 인터페이스를 구현지만 필요한 serialization 생성자를 정의하지 않는 형식을 만들 때 이 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-146">The analyzer generates this warning when you create a type that implements the <xref:System.Runtime.Serialization.ISerializable> interface but does not define the required serialization constructor.</span></span> <span data-ttu-id="c7ced-147">이 규칙 위반 문제를 해결하려면 serialization 생성자를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-147">To fix a violation of this rule, implement the serialization constructor.</span></span> <span data-ttu-id="c7ced-148">봉인 클래스의 경우에는 생성자를 private으로 만들고, 그 밖의 경우에는 protected로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-148">For a sealed class, make the constructor private; otherwise, make it protected.</span></span> <span data-ttu-id="c7ced-149">Serialization 생성자에는 다음 서명이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-149">The serialization constructor has the following signature:</span></span>

```csharp
public class MyItemType
{
    // The special constructor is used to deserialize values.
    public MyItemType(SerializationInfo info, StreamingContext context)
    {
        // implementation removed.
    }
}
```

<span data-ttu-id="c7ced-150">**범주:** 사용량</span><span class="sxs-lookup"><span data-stu-id="c7ced-150">**Category:** Usage</span></span>

<span data-ttu-id="c7ced-151">**심각도:** 경고</span><span class="sxs-lookup"><span data-stu-id="c7ced-151">**Severity:** Warning</span></span>

<span data-ttu-id="c7ced-152">추가 정보: [CA2229: serialization 생성자를 구현하세요.](/visualstudio/code-quality/ca2229-implement-serialization-constructors)</span><span class="sxs-lookup"><span data-stu-id="c7ced-152">Additional information: [CA2229: Implement serialization constructors](/visualstudio/code-quality/ca2229-implement-serialization-constructors)</span></span>

### <a name="ca2235-mark-all-non-serializable-fields"></a><span data-ttu-id="c7ced-153">CA2235: 모두 serialize할 수 없는 필드로 표시하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7ced-153">CA2235: Mark all non-serializable fields</span></span>

<span data-ttu-id="c7ced-154">serialize할 수 없는 형식의 인스턴스 필드가 serialize할 수 있는 형식에 정의되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-154">An instance field of a type that is not serializable is declared in a type that is serializable.</span></span> <span data-ttu-id="c7ced-155">해당 필드를 <xref:System.NonSerializedAttribute>로 명시적으로 표시하여 이 경고를 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-155">You must explicitly mark that field with the <xref:System.NonSerializedAttribute> to fix this warning.</span></span>

<span data-ttu-id="c7ced-156">**범주:** 사용량</span><span class="sxs-lookup"><span data-stu-id="c7ced-156">**Category:** Usage</span></span>

<span data-ttu-id="c7ced-157">**심각도:** 경고</span><span class="sxs-lookup"><span data-stu-id="c7ced-157">**Severity:** Warning</span></span>

<span data-ttu-id="c7ced-158">추가 정보: [CA2235: 모두 serialize할 수 없는 필드로 표시하세요.](/visualstudio/code-quality/ca2235-mark-all-non-serializable-fields)</span><span class="sxs-lookup"><span data-stu-id="c7ced-158">Additional information: [CA2235: Mark all non-serializable fields](/visualstudio/code-quality/ca2235-mark-all-non-serializable-fields)</span></span>

### <a name="ca2237-mark-iserializable-types-with-serializable"></a><span data-ttu-id="c7ced-159">CA2237: ISerializable 형식을 Serialize 가능으로 표시하세요.</span><span class="sxs-lookup"><span data-stu-id="c7ced-159">CA2237: Mark ISerializable types with serializable</span></span>

<span data-ttu-id="c7ced-160">공용 언어 런타임에서 serializable로 인식되도록 하려면 형식이 <xref:System.Runtime.Serialization.ISerializable> 인터페이스를 구현하여 사용자 지정 serialization 루틴을 사용하는 경우에도 <xref:System.SerializableAttribute> 특성을 사용하여 형식을 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-160">To be recognized by the common language runtime as serializable, types must be marked by using the <xref:System.SerializableAttribute> attribute even when the type uses a custom serialization routine by implementing the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span>

<span data-ttu-id="c7ced-161">**범주:** 사용량</span><span class="sxs-lookup"><span data-stu-id="c7ced-161">**Category:** Usage</span></span>

<span data-ttu-id="c7ced-162">**심각도:** 경고</span><span class="sxs-lookup"><span data-stu-id="c7ced-162">**Severity:** Warning</span></span>

<span data-ttu-id="c7ced-163">추가 정보: [CA2237: ISerializable 형식을 Serialize 가능으로 표시하세요.](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)</span><span class="sxs-lookup"><span data-stu-id="c7ced-163">Additional information: [CA2237: Mark ISerializable types with serializable](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)</span></span>

### <a name="ca3075-insecure-dtd-processing-in-xml"></a><span data-ttu-id="c7ced-164">CA3075: XML에서 안전하지 않은 DTD 처리</span><span class="sxs-lookup"><span data-stu-id="c7ced-164">CA3075: Insecure DTD processing in XML</span></span>

<span data-ttu-id="c7ced-165">안전하지 않은 <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> 인스턴스를 사용하거나 외부 엔터티 소스를 참조하면 파서는 신뢰할 수 없는 입력을 허용하고 공격자에게 중요 한 정보를 공개할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-165">If you use insecure <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> instances or reference external entity sources, the parser may accept untrusted input and disclose sensitive information to attackers.</span></span>  

<span data-ttu-id="c7ced-166">**범주:** 보안</span><span class="sxs-lookup"><span data-stu-id="c7ced-166">**Category:** Security</span></span>

<span data-ttu-id="c7ced-167">**심각도:** 경고</span><span class="sxs-lookup"><span data-stu-id="c7ced-167">**Severity:** Warning</span></span>

<span data-ttu-id="c7ced-168">추가 정보: [A3075: XML에서 안전하지 않은 DTD 처리](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)</span><span class="sxs-lookup"><span data-stu-id="c7ced-168">Additional information: [A3075: Insecure DTD processing in XML](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)</span></span>


### <a name="ca5350-do-not-use-weak-cryptographic-algorithms"></a><span data-ttu-id="c7ced-169">CA5350: 취약한 암호화 알고리즘 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="c7ced-169">CA5350: Do not use weak cryptographic algorithms</span></span>

<span data-ttu-id="c7ced-170">공격이 발전할수록 암호화 알고리즘은 시간이 지남에 따라 저하됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-170">Cryptographic algorithms degrade over time as attacks become more advanced.</span></span> <span data-ttu-id="c7ced-171">해당 암호화 능력이 더욱 저하되면 이 암호화 알고리즘의 형식 및 응용 프로그램에 따라 공격자가 암호화된 메시지를 읽거나, 암호화된 메시지를 조작하거나, 디지털 서명을 위조하거나, 해시된 콘텐츠를 조작하거나, 이 알고리즘을 기반으로 하는 모든 암호화 시스템을 손상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-171">Depending on the type and application of this cryptographic algorithm, further degradation of its cryptographic strength may allow attackers to read enciphered messages, tamper with enciphered messages, forge digital signatures, tamper with hashed content, or otherwise compromise any cryptosystem based on this algorithm.</span></span> <span data-ttu-id="c7ced-172">암호화의 경우 키 길이가 128비트 이상인 AES 알고리즘(AES-256, AES-192 및 AES-128 허용 가능함)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-172">For encryption, use an AES algorithm (AES-256, AES-192 and AES-128 are acceptable) with a key length greater than or equal to 128 bits.</span></span> <span data-ttu-id="c7ced-173">해시의 경우 SHA-2 512, SHA-2 384 또는 SHA-2 256 등 SHA-2 제품군의 해시 함수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-173">For hashing, use a hashing function in the SHA-2 family, such as SHA-2 512, SHA-2 384, or SHA-2 256.</span></span>

<span data-ttu-id="c7ced-174">**범주:** 보안</span><span class="sxs-lookup"><span data-stu-id="c7ced-174">**Category:** Security</span></span>

<span data-ttu-id="c7ced-175">**심각도:** 경고</span><span class="sxs-lookup"><span data-stu-id="c7ced-175">**Severity:** Warning</span></span>

<span data-ttu-id="c7ced-176">추가 정보: [CA5350: 취약한 암호화 알고리즘 사용 안 함](/visualstudio/code-quality/ca5350-do-not-use-weak-cryptographic-algorithms)</span><span class="sxs-lookup"><span data-stu-id="c7ced-176">Additional information: [CA5350: Do not use weak cryptographic algorithms](/visualstudio/code-quality/ca5350-do-not-use-weak-cryptographic-algorithms)</span></span>

### <a name="ca5351-do-not-use-broken-cryptographic-algorithms"></a><span data-ttu-id="c7ced-177">CA5351: 끊어진 암호화 알고리즘 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="c7ced-177">CA5351: Do not use broken cryptographic algorithms</span></span>

<span data-ttu-id="c7ced-178">이 알고리즘을 중단하지 못하게 만드는 공격이 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-178">An attack making it computationally feasible to break this algorithm exists.</span></span> <span data-ttu-id="c7ced-179">이렇게 하면 제공하도록 디자인된 암호화 보장을 공격자가 무너뜨릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-179">This allows attackers to break the cryptographic guarantees it is designed to provide.</span></span> <span data-ttu-id="c7ced-180">그러면 이 암호화 알고리즘의 형식 및 응용 프로그램에 따라 공격자가 암호화된 메시지를 읽거나, 암호화된 메시지를 조작하거나, 디지털 서명을 위조하거나, 해시된 콘텐츠를 조작하거나, 이 알고리즘을 기반으로 하는 모든 암호화 시스템을 손상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-180">Depending on the type and application of this cryptographic algorithm, this may allow attackers to read enciphered messages, tamper with enciphered messages, forge digital signatures, tamper with hashed content, or otherwise compromise any cryptosystem based on this algorithm.</span></span> <span data-ttu-id="c7ced-181">암호화의 경우 키 길이가 128비트 이상인 AES 알고리즘(AES-256, AES-192 및 AES-128 허용 가능함)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-181">For encryption, use an AES algorithm (AES-256, AES-192 and AES-128 are acceptable) with a key length greater than or equal to 128 bits.</span></span> <span data-ttu-id="c7ced-182">해시의 경우 SHA512, SHA384 또는 SHA256 등 SHA-2 제품군의 해시 함수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-182">For hashing, use a hashing function in the SHA-2 family, such as SHA512, SHA384, or SHA256.</span></span> <span data-ttu-id="c7ced-183">디지털 서명의 경우 키 길이가 2048비트 이상인 RSA를 사용하거나 키 길이가 256비트 이상인 ECDSA를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c7ced-183">For digital signatures, use RSA with a key length greater than or equal to 2048-bits, or ECDSA with a key length greater than or equal to 256 bits.</span></span>

<span data-ttu-id="c7ced-184">**범주:** 보안</span><span class="sxs-lookup"><span data-stu-id="c7ced-184">**Category:** Security</span></span>

<span data-ttu-id="c7ced-185">**심각도:** 경고</span><span class="sxs-lookup"><span data-stu-id="c7ced-185">**Severity:** Warning</span></span>

<span data-ttu-id="c7ced-186">추가 정보: [CA5351: 손상된 암호화 알고리즘 사용 안 함](/visualstudio/code-quality/ca5351-do-not-use-broken-cryptographic-algorithms)</span><span class="sxs-lookup"><span data-stu-id="c7ced-186">Additional Information: [CA5351: Do not use broken cryptographic algorithms](/visualstudio/code-quality/ca5351-do-not-use-broken-cryptographic-algorithms)</span></span>


