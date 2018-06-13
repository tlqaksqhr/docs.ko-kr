---
title: 공용 XAML 언어 기본 형식에 대한 기본 제공 형식
ms.date: 03/30/2017
helpviewer_keywords:
- XAML language primitives [XAML Services]
- XAML [XAML Services], built-in types
- x:String [XAML Services]
- x:TimeSpan [XAML Services]
- x:Byte [XAML Services]
- x:Double [XAML Services]
- XAML [XAML Services], types
- x:Uri [XAML Services]
- XAML built-in types [XAML Services]
- x:Int64 [XAML Services]
- x:Single [XAML Services]
- x:Int32 [XAML Services]
ms.assetid: 11de2f08-5b95-4989-b5ec-5178eb968184
ms.openlocfilehash: 15c359a9a7f9797fc03ce20c453905af01f925d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564354"
---
# <a name="built-in-types-for-common-xaml-language-primitives"></a><span data-ttu-id="8ee07-102">공용 XAML 언어 기본 형식에 대한 기본 제공 형식</span><span class="sxs-lookup"><span data-stu-id="8ee07-102">Built-in Types for Common XAML Language Primitives</span></span>
<span data-ttu-id="8ee07-103">XAML 2009에서는 CLR(공용 언어 런타임) 및 다른 프로그래밍 언어에서 자주 사용되는 기본 형식인 여러 가지 데이터 형식에 대해 XAML 언어 수준 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-103">XAML 2009 introduces XAML language-level support for several data types that are frequently used primitives in the common language runtime (CLR) and in other programming languages.</span></span> <span data-ttu-id="8ee07-104">XAML 2009는 `x:Object`, `x:Boolean`, `x:Char`, `x:String`, `x:Decimal`, `x:Single`, `x:Double`, `x:Int16`, `x:Int32`, `x:Int64`, `x:TimeSpan`, `x:Uri`, `x:Byte`및 `x:Array`같은 기본 형식에 대한 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-104">XAML 2009 adds support for these primitives: `x:Object`, `x:Boolean`, `x:Char`, `x:String`, `x:Decimal`, `x:Single`, `x:Double`, `x:Int16`, `x:Int32`, `x:Int64`, `x:TimeSpan`, `x:Uri`, `x:Byte`, and `x:Array`</span></span>  
  
<a name="previous_techniques_for_language_primitives_in_xaml_markup"></a>   
## <a name="previous-techniques-for-language-primitives-in-xaml-markup"></a><span data-ttu-id="8ee07-105">XAML 태그의 언어 기본 형식에 대한 이전 기술</span><span class="sxs-lookup"><span data-stu-id="8ee07-105">Previous Techniques for Language Primitives in XAML Markup</span></span>  
 <span data-ttu-id="8ee07-106">이전 WPF 버전에 대한 XAML에서는 .NET Framework에 대한 CLR 기본 형식 정의 클래스가 포함된 어셈블리 및 네임스페이스를 매핑하여 CLR 언어 기본 형식을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-106">In XAML for previous WPF versions, you could reference the CLR language primitives by mapping the assembly and namespace that contained a CLR primitive definition class for the .NET Framework.</span></span> <span data-ttu-id="8ee07-107">대부분이 mscorlib 어셈블리 및 <xref:System> 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-107">Most of these are in the mscorlib assembly and <xref:System> namespace.</span></span> <span data-ttu-id="8ee07-108">예를 들어 <xref:System.Int32>를 사용하려면 다음에 표시된 사용 예제를 사용하여 다음과 같은 매핑을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-108">For example, to use <xref:System.Int32>, you could declare the following mapping (with an example usage shown thereafter):</span></span>  
  
```  
<Application xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"   
xmlns:sys="clr-namespace:System;assembly=mscorlib">  
  <Application.Resources>  
    <sys:Int32 x:Key="intMeaning">42</sys:Int32>  
  </Application.Resources>  
</Application>  
```  
  
<a name="xaml_2009_language_primitives"></a>   
## <a name="xaml-2009-language-primitives"></a><span data-ttu-id="8ee07-109">XAML 2009 언어 기본 형식</span><span class="sxs-lookup"><span data-stu-id="8ee07-109">XAML 2009 Language Primitives</span></span>  
 <span data-ttu-id="8ee07-110">규칙에 따라 `x:` 접두사를 포함하여 XAML 및 다른 모든 XAML 언어 요소에 대한 언어 기본 형식이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-110">By convention, the language primitives for XAML and all other XAML language elements are shown, including the `x:` prefix.</span></span> <span data-ttu-id="8ee07-111">이 규칙은 XAML 언어 요소가 실제 태그에서 일반적으로 사용되는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-111">This is how XAML language elements are typically used in real-world markup.</span></span> <span data-ttu-id="8ee07-112">WPF의 XAML에 대한 개념 설명서 및 XAML 사양에서도 이 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-112">This convention is followed in the conceptual documentation for XAML in WPF and also in the XAML specification.</span></span>  
  
### <a name="xobject"></a><span data-ttu-id="8ee07-113">x:Object</span><span class="sxs-lookup"><span data-stu-id="8ee07-113">x:Object</span></span>  
 <span data-ttu-id="8ee07-114">CLR 백업의 경우 `x:Object` 기본 형식은 <xref:System.Object>에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-114">For CLR backing, the `x:Object` primitive corresponds to <xref:System.Object>.</span></span>  
  
 <span data-ttu-id="8ee07-115">이 기본 형식은 일반적으로 응용 프로그램 태그에서 사용되지 않지만 XAML 형식 시스템에서 할당 가능성을 확인하는 경우와 같은 일부 시나리오에는 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-115">This primitive is not typically used in application markup, but might be useful for some scenarios such as checking assignability in a XAML type system.</span></span>  
  
### <a name="xboolean"></a><span data-ttu-id="8ee07-116">x:Boolean</span><span class="sxs-lookup"><span data-stu-id="8ee07-116">x:Boolean</span></span>  
 <span data-ttu-id="8ee07-117">CLR 백업의 경우 `x:Boolean` 기본 형식은 <xref:System.Boolean>에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-117">For CLR backing, the `x:Boolean` primitive corresponds to <xref:System.Boolean>.</span></span>  
  
 <span data-ttu-id="8ee07-118">XAML은 `x:Boolean`에 대한 값을 대/소문자 구분 없이 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-118">XAML parses values for `x:Boolean` as case insensitive.</span></span> <span data-ttu-id="8ee07-119">이때 `x:Bool` 로 대체할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-119">Note that `x:Bool` is not an accepted alternative.</span></span> <span data-ttu-id="8ee07-120">XAML 언어 사양 정의 대 한 참조 [ \[MS-XAML\] 섹션 5.2.17 및 5.4.11](http://go.microsoft.com/fwlink/?LinkId=114525)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-120">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.17 and 5.4.11](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
### <a name="xchar"></a><span data-ttu-id="8ee07-121">x:Char</span><span class="sxs-lookup"><span data-stu-id="8ee07-121">x:Char</span></span>  
 <span data-ttu-id="8ee07-122">CLR 백업의 경우 `x:Char` 기본 형식은 <xref:System.Char>에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-122">For CLR backing, the `x:Char` primitive corresponds to <xref:System.Char>.</span></span>  
  
 <span data-ttu-id="8ee07-123">String 및 char 형식은 XML 수준에서 파일의 전체 인코딩과 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-123">String and char types have interaction with the overall encoding of the file at the XML level.</span></span> <span data-ttu-id="8ee07-124">XAML 언어 사양 정의 대 한 참조 [ \[MS-XAML\] 섹션 5.2.7 및 5.4.1](http://go.microsoft.com/fwlink/?LinkId=114525)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-124">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.7 and 5.4.1](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
### <a name="xstring"></a><span data-ttu-id="8ee07-125">x:String</span><span class="sxs-lookup"><span data-stu-id="8ee07-125">x:String</span></span>  
 <span data-ttu-id="8ee07-126">CLR 백업의 경우 `x:String` 기본 형식은 <xref:System.String>에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-126">For CLR backing, the `x:String` primitive corresponds to <xref:System.String>.</span></span>  
  
 <span data-ttu-id="8ee07-127">String 및 char 형식은 XML 수준에서 파일의 전체 인코딩과 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-127">String and char types have interaction with the overall encoding of the file at the XML level.</span></span> <span data-ttu-id="8ee07-128">XAML 언어 사양 정의 대 한 참조 [ \[MS-XAML\] 섹션 5.2.6](http://go.microsoft.com/fwlink/?LinkId=114525)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-128">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.6](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
### <a name="xdecimal"></a><span data-ttu-id="8ee07-129">x:Decimal</span><span class="sxs-lookup"><span data-stu-id="8ee07-129">x:Decimal</span></span>  
 <span data-ttu-id="8ee07-130">CLR 백업의 경우 `x:Decimal` 기본 형식은 <xref:System.Decimal>에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-130">For CLR backing, the `x:Decimal` primitive corresponds to <xref:System.Decimal>.</span></span>  
  
 <span data-ttu-id="8ee07-131">XAML 구문 분석은 기본적으로 `en-US` 문화권에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-131">Note that XAML parsing is inherently done under `en-US` culture.</span></span> <span data-ttu-id="8ee07-132">`en-US` 문화권에서 10진수의 구성 요소에 올바른 구분 기호는 개발 환경의 문화권 설정이나 런타임에 XAML이 로드되는 최종 클라이언트 대상에 관계없이 항상 마침표(`.`)입니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-132">Under `en-US` culture, the correct separator for the components of a decimal is always a period (`.`) regardless of culture settings of the development environment, or of the eventual client target where the XAML is loaded at run time.</span></span>  
  
 <span data-ttu-id="8ee07-133">XAML 언어 사양 정의 대 한 참조 [ \[MS-XAML\] 섹션 5.2.14 및 5.4.8](http://go.microsoft.com/fwlink/?LinkId=114525)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-133">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.14 and 5.4.8](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
### <a name="xsingle"></a><span data-ttu-id="8ee07-134">x:Single</span><span class="sxs-lookup"><span data-stu-id="8ee07-134">x:Single</span></span>  
 <span data-ttu-id="8ee07-135">CLR 백업의 경우 `x:Single` 기본 형식은 <xref:System.Single>에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-135">For CLR backing, the `x:Single` primitive corresponds to <xref:System.Single>.</span></span>  
  
 <span data-ttu-id="8ee07-136">숫자 값뿐만 아니라 `x:Single`에 대한 텍스트 구문도 `Infinity`, `-Infinity` 및 `NaN` 토큰을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-136">In addition to the numeric values, text syntax for `x:Single` also permits the tokens `Infinity`, `-Infinity`, and `NaN`.</span></span> <span data-ttu-id="8ee07-137">이러한 토큰은 대/소문자를 구분하여 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-137">These tokens are treated as case sensitive.</span></span>  
  
 <span data-ttu-id="8ee07-138">텍스트 구문의 첫 번째 문자가`x:Single` 또는 `e` 인 경우 `E`은 과학적 표기법 형식의 값을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-138">`x:Single` can support values in scientific notation form, if the first character in text syntax is `e` or `E`.</span></span>  
  
 <span data-ttu-id="8ee07-139">XAML 언어 사양 정의 대 한 참조 [ \[MS-XAML\] 섹션 5.2.8 및 5.4.2](http://go.microsoft.com/fwlink/?LinkId=114525)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-139">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.8 and 5.4.2](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
### <a name="xdouble"></a><span data-ttu-id="8ee07-140">x:Double</span><span class="sxs-lookup"><span data-stu-id="8ee07-140">x:Double</span></span>  
 <span data-ttu-id="8ee07-141">CLR 백업의 경우 `x:Double` 기본 형식은 <xref:System.Double>에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-141">For CLR backing, the `x:Double` primitive corresponds to <xref:System.Double>.</span></span>  
  
 <span data-ttu-id="8ee07-142">숫자 값뿐만 아니라 `x:Double`에 대한 텍스트 구문도 `Infinity`, `-Infinity` 및 `NaN` 토큰을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-142">In addition to the numeric values, text syntax for `x:Double` permits the tokens `Infinity`, `-Infinity`, and `NaN`.</span></span> <span data-ttu-id="8ee07-143">이러한 토큰은 대/소문자를 구분하여 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-143">These tokens are treated as case sensitive.</span></span>  
  
 <span data-ttu-id="8ee07-144">`x:Double` 은 과학적 표기법 형식의 값을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-144">`x:Double` can support values in scientific notation form.</span></span> <span data-ttu-id="8ee07-145">`e` 또는 `E` 문자를 사용하여 지수 부분을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-145">Use the character `e` or `E` to introduce the exponent portion.</span></span>  
  
 <span data-ttu-id="8ee07-146">XAML 언어 사양 정의 대 한 참조 [ \[MS-XAML\] 섹션 5.2.9 및 5.4.3](http://go.microsoft.com/fwlink/?LinkId=114525)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-146">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.9 and 5.4.3](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
### <a name="xint16"></a><span data-ttu-id="8ee07-147">x:Int16</span><span class="sxs-lookup"><span data-stu-id="8ee07-147">x:Int16</span></span>  
 <span data-ttu-id="8ee07-148">CLR 백업의 경우 `x:Int16` 기본 형식은 <xref:System.Int16> 에 해당하고 `x:Int16` 은 부호가 있는 것으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-148">For CLR backing, the `x:Int16` primitive corresponds to <xref:System.Int16> and `x:Int16` is treated as signed.</span></span> <span data-ttu-id="8ee07-149">XAML에서는 텍스트 구문에 더하기(`+`) 부호가 없으면 부호 있는 양수 값을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-149">In XAML, the absence of a plus (`+`) sign in text syntax is implied as a positive signed value.</span></span>  
  
 <span data-ttu-id="8ee07-150">XAML 언어 사양 정의 대 한 참조 [ \[MS-XAML\] 섹션 5.2.11 및 5.4.5](http://go.microsoft.com/fwlink/?LinkId=114525)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-150">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.11 and 5.4.5](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
### <a name="xint32"></a><span data-ttu-id="8ee07-151">x:Int32</span><span class="sxs-lookup"><span data-stu-id="8ee07-151">x:Int32</span></span>  
 <span data-ttu-id="8ee07-152">CLR 백업의 경우 `x:Int32` 기본 형식은 <xref:System.Int32>에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-152">For CLR backing, the `x:Int32` primitive corresponds to <xref:System.Int32>.</span></span> <span data-ttu-id="8ee07-153">`x:Int32`는 부호가 있는 것으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-153">`x:Int32` is treated as signed.</span></span> <span data-ttu-id="8ee07-154">XAML에서는 텍스트 구문에 더하기(`+`) 부호가 없으면 부호 있는 양수 값을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-154">In XAML, the absence of a plus (`+`) sign in text syntax is implied as a positive signed value.</span></span>  
  
 <span data-ttu-id="8ee07-155">XAML 언어 사양 정의 대 한 참조 [ \[MS-XAML\] 섹션 5.2.12 및 5.4.6](http://go.microsoft.com/fwlink/?LinkId=114525)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-155">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.12 and 5.4.6](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
### <a name="xint64"></a><span data-ttu-id="8ee07-156">x:Int64</span><span class="sxs-lookup"><span data-stu-id="8ee07-156">x:Int64</span></span>  
 <span data-ttu-id="8ee07-157">CLR 백업의 경우 `x:Int64` 기본 형식은 <xref:System.Int64>에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-157">For CLR backing, the `x:Int64` primitive corresponds to <xref:System.Int64>.</span></span> <span data-ttu-id="8ee07-158">`x:Int64`는 부호가 있는 것으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-158">`x:Int64` is treated as signed.</span></span> <span data-ttu-id="8ee07-159">XAML에서는 텍스트 구문에 더하기(`+`) 부호가 없으면 부호 있는 양수 값을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-159">In XAML, the absence of a plus (`+`) sign in text syntax is implied as a positive signed value.</span></span>  
  
 <span data-ttu-id="8ee07-160">XAML 언어 사양 정의 대 한 참조 [ \[MS-XAML\] 섹션 5.2.13 및 5.4.7](http://go.microsoft.com/fwlink/?LinkId=114525)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-160">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.13 and 5.4.7](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
### <a name="xtimespan"></a><span data-ttu-id="8ee07-161">x:TimeSpan</span><span class="sxs-lookup"><span data-stu-id="8ee07-161">x:TimeSpan</span></span>  
 <span data-ttu-id="8ee07-162">CLR 백업의 경우 `x:TimeSpan` 기본 형식은 <xref:System.TimeSpan>에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-162">For CLR backing, the `x:TimeSpan` primitive corresponds to <xref:System.TimeSpan>.</span></span>  
  
 <span data-ttu-id="8ee07-163">날짜/시간 형식에 대한 XAML 구문 분석은 기본적으로 `en-US` 문화권에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-163">Note that XAML parsing for time-date format is inherently done under `en-US` culture.</span></span>  
  
 <span data-ttu-id="8ee07-164">XAML 언어 사양 정의 대 한 참조 [ \[MS-XAML\] 섹션 5.2.16 및 5.4.10](http://go.microsoft.com/fwlink/?LinkId=114525)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-164">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.16 and 5.4.10](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
### <a name="xuri"></a><span data-ttu-id="8ee07-165">x:Uri</span><span class="sxs-lookup"><span data-stu-id="8ee07-165">x:Uri</span></span>  
 <span data-ttu-id="8ee07-166">CLR 백업의 경우 `x:Uri` 기본 형식은 <xref:System.Uri>에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-166">For CLR backing, the `x:Uri` primitive corresponds to <xref:System.Uri>.</span></span>  
  
 <span data-ttu-id="8ee07-167">프로토콜 확인은 `x:Uri`에 대한 XAML 정의의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-167">Checking for protocols is not part of the XAML definition for `x:Uri`.</span></span>  
  
 <span data-ttu-id="8ee07-168">XAML 언어 사양 정의 대 한 참조 [ \[MS-XAML\] 섹션 5.2.15 및 5.4.9](http://go.microsoft.com/fwlink/?LinkId=114525)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-168">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.15 and 5.4.9](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
### <a name="xbyte"></a><span data-ttu-id="8ee07-169">x:Byte</span><span class="sxs-lookup"><span data-stu-id="8ee07-169">x:Byte</span></span>  
 <span data-ttu-id="8ee07-170">CLR 백업의 경우 `x:Byte` 기본 형식은 <xref:System.Byte>에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-170">For CLR backing, the `x:Byte` primitive corresponds to <xref:System.Byte>.</span></span> <span data-ttu-id="8ee07-171">A <xref:System.Byte>  /  `x:Byte` 처리으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-171">A <xref:System.Byte> / `x:Byte` is treated as unsigned.</span></span>  
  
 <span data-ttu-id="8ee07-172">XAML 언어 사양 정의 대 한 참조 [ \[MS-XAML\] 섹션 5.2.10 및 5.4.4](http://go.microsoft.com/fwlink/?LinkId=114525)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-172">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.10 and 5.4.4](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
### <a name="xarray"></a><span data-ttu-id="8ee07-173">x:Array</span><span class="sxs-lookup"><span data-stu-id="8ee07-173">x:Array</span></span>  
 <span data-ttu-id="8ee07-174">CLR 백업의 경우 `x:Array` 기본 형식은 <xref:System.Array>에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-174">For CLR backing, the `x:Array` primitive corresponds to <xref:System.Array>.</span></span>  
  
 <span data-ttu-id="8ee07-175">XAML 2006에서는 태그 확장 구문을 사용하여 배열을 정의할 수 있습니다. 그러나 XAML 2009 구문은 태그 확장에 액세스할 필요가 없는 언어로 정의된 기본 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-175">You can define an array in XAML 2006  by using a markup extension syntax; however, the XAML 2009 syntax is a language-defined primitive that does not require accessing a markup extension.</span></span> <span data-ttu-id="8ee07-176">XAML 2006 지원에 대한 자세한 내용은 [x:Array Markup Extension](../../../docs/framework/xaml-services/x-array-markup-extension.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ee07-176">For more information about XAML 2006 support, see [x:Array Markup Extension](../../../docs/framework/xaml-services/x-array-markup-extension.md).</span></span>  
  
 <span data-ttu-id="8ee07-177">XAML 언어 사양 정의 대 한 참조 [ \[MS-XAML\] 섹션 5.2.18](http://go.microsoft.com/fwlink/?LinkId=114525)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-177">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.18](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
<a name="wpf_support"></a>   
## <a name="wpf-support"></a><span data-ttu-id="8ee07-178">WPF 지원</span><span class="sxs-lookup"><span data-stu-id="8ee07-178">WPF Support</span></span>  
 <span data-ttu-id="8ee07-179">WPF에서 XAML 2009 기능을 사용할 수 있지만 태그로 컴파일되지 않은 XAML에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-179">In WPF, you can use XAML 2009 features but only for XAML that is not markup-compiled.</span></span> <span data-ttu-id="8ee07-180">WPF에 대한 태그로 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 키워드 및 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-180">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>  
  
 <span data-ttu-id="8ee07-181">WPF와 함께 XAML 2009 기능을 사용할 수 있는 시나리오는 느슨한 XAML을 작성 하 고 그런 다음 해당 XAML을 WPF 런타임 및 개체 그래프로 로드 하는 경우 <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-181">A scenario where you can use XAML 2009 features together with WPF is if you author loose XAML and you then load that XAML into a WPF runtime and object graph with <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="8ee07-182">WPF <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> 및 해당 <xref:System.Windows.Markup.XamlReader.Load%2A> XAML 2009 언어 키워드 및 기능을 유효한 개체 그래프 표현으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee07-182">The WPF <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> and its <xref:System.Windows.Markup.XamlReader.Load%2A> can process XAML 2009 language keywords and features into a valid object graph representation.</span></span>
