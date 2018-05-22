---
title: msxsl:script를 사용하는 스크립트 블록
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: fde6f43f-c594-486f-abcb-2211197fae20
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 23961caa7b307df46b20b3811d0883d4c702a357
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="script-blocks-using-msxslscript"></a><span data-ttu-id="bec71-102">msxsl:script를 사용하는 스크립트 블록</span><span class="sxs-lookup"><span data-stu-id="bec71-102">Script Blocks Using msxsl:script</span></span>
<span data-ttu-id="bec71-103"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스는 `msxsl:script` 요소를 사용하여 포함 스크립트를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-103">The <xref:System.Xml.Xsl.XslCompiledTransform> class supports embedded scripts using the `msxsl:script` element.</span></span> <span data-ttu-id="bec71-104">스타일시트가 로드될 때 정의된 모든 함수는 CodeDOM(코드 문서 개체 모델)에 의해 MSIL(Microsoft Intermediate Language)로 컴파일되며 런타임 동안 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-104">When the style sheet is loaded, any defined functions are compiled to Microsoft intermediate language (MSIL) by the Code Document Object Model (CodeDOM) and are executed during run time.</span></span> <span data-ttu-id="bec71-105">포함된 스크립트 블록에서 생성된 어셈블리는 스타일시트에 대해 생성된 어셈블리와는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-105">The assembly generated from the embedded script block is separate than the assembly generated for the style sheet.</span></span>  
  
## <a name="enable-xslt-script"></a><span data-ttu-id="bec71-106">XSLT 스크립트 사용</span><span class="sxs-lookup"><span data-stu-id="bec71-106">Enable XSLT Script</span></span>  
 <span data-ttu-id="bec71-107">포함된 스크립트 지원은 <xref:System.Xml.Xsl.XslCompiledTransform> 클래스에서 선택적 XSLT 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-107">Support for embedded scripts is an optional XSLT setting on the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="bec71-108">스크립트 지원은 기본적으로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-108">Script support is disabled by default.</span></span> <span data-ttu-id="bec71-109">스크립트 지원을 사용하려면 <xref:System.Xml.Xsl.XsltSettings> 속성을 <xref:System.Xml.Xsl.XsltSettings.EnableScript%2A>로 설정하여 `true` 개체를 만들고 이 개체를 <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> 메서드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-109">To enable script support, create an <xref:System.Xml.Xsl.XsltSettings> object with the <xref:System.Xml.Xsl.XsltSettings.EnableScript%2A> property set to `true` and pass the object to the <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bec71-110">XSLT 스크립트는 스크립트 지원이 필요하거나 완전히 신뢰할 수 있는 환경에서 작업하는 경우에만 활성화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-110">XSLT scripting should be enabled only if you require script support and you are working in a fully trusted environment.</span></span>  
  
## <a name="msxslscript-element-definition"></a><span data-ttu-id="bec71-111">msxsl:script 요소 정의</span><span class="sxs-lookup"><span data-stu-id="bec71-111">msxsl:script Element Definition</span></span>  
 <span data-ttu-id="bec71-112">`msxsl:script` 요소는 XSLT 1.0 권장 사항에 대한 Microsoft 확장으로, 다음 정의를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-112">The `msxsl:script` element is a Microsoft extension to the XSLT 1.0 recommendation and has the following definition:</span></span>  
  
```xml  
<msxsl:script language = "language-name" implements-prefix = "prefix of user namespace"> </msxsl:script>  
```  
  
 <span data-ttu-id="bec71-113">`msxsl` 접두사는 `urn:schemas-microsoft-com:xslt` 네임스페이스 URI에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-113">The `msxsl` prefix is bound to the `urn:schemas-microsoft-com:xslt` namespace URI.</span></span> <span data-ttu-id="bec71-114">스타일시트는 `xmlns:msxsl=urn:schemas-microsoft-com:xslt` 네임스페이스 선언을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-114">The style sheet must include the `xmlns:msxsl=urn:schemas-microsoft-com:xslt` namespace declaration.</span></span>  
  
 <span data-ttu-id="bec71-115">`language` 특성은 선택 사항이며</span><span class="sxs-lookup"><span data-stu-id="bec71-115">The `language` attribute is optional.</span></span> <span data-ttu-id="bec71-116">해당 값은 포함된 코드 블록의 코드 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-116">Its value is the code language of the embedded code block.</span></span> <span data-ttu-id="bec71-117">이 언어는 <xref:System.CodeDom.Compiler.CodeDomProvider.CreateProvider%2A?displayProperty=nameWithType> 메서드를 사용하여 적합한 CodeDOM 컴파일러에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-117">The language is mapped to the appropriate CodeDOM compiler using the <xref:System.CodeDom.Compiler.CodeDomProvider.CreateProvider%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="bec71-118"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스는 모든 Microsoft .NET 언어를 지원할 수 있습니다. 이때 적합한 공급자가 컴퓨터에 설치되어 있으며 machine.config 파일의 system.codedom 섹션에 등록되어 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-118">The <xref:System.Xml.Xsl.XslCompiledTransform> class can support any Microsoft .NET language, assuming the appropriate provider is installed on the machine and is registered in the system.codedom section of the machine.config file.</span></span> <span data-ttu-id="bec71-119">`language` 특성을 지정하지 않을 경우 언어 기본값은 JScript입니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-119">If a `language` attribute is not specified, the language defaults to JScript.</span></span> <span data-ttu-id="bec71-120">언어 이름은 대/소문자를 구분하지 않으므로 'JavaScript'와 'javascript'는 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-120">The language name is not case-sensitive so 'JavaScript' and 'javascript' are equivalent.</span></span>  
  
 <span data-ttu-id="bec71-121">`implements-prefix` 특성은 필수 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-121">The `implements-prefix` attribute is mandatory.</span></span> <span data-ttu-id="bec71-122">이 특성은 네임스페이스를 선언하고 스크립트 블록에 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-122">This attribute is used to declare a namespace and associate it with the script block.</span></span> <span data-ttu-id="bec71-123">이 특성 값은 네임스페이스를 나타내는 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-123">The value of this attribute is the prefix that represents the namespace.</span></span> <span data-ttu-id="bec71-124">이 접두사는 스타일시트에서 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-124">This prefix can be defined somewhere in a style sheet.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bec71-125">`msxsl:script` 요소를 사용하는 경우에는 언어에 관계없이 스크립트를 CDATA 섹션에 배치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-125">When using the `msxsl:script` element, we strongly recommend that the script, regardless of language, be placed inside a CDATA section.</span></span> <span data-ttu-id="bec71-126">스크립트에는 지정된 언어에 대한 연산자, 식별자 또는 구분자가 포함될 수 있으므로 스크립트를 CDATA 섹션에 포함하지 않으면 XML로 잘못 해석될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-126">Because the script can contain operators, identifiers, or delimiters for a given language, if it is not contained within a CDATA section, it has the potential of being misinterpreted as XML.</span></span> <span data-ttu-id="bec71-127">다음 XML에서는 코드를 배치할 수 있는 CDATA 섹션 템플릿을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-127">The following XML shows a template of the CDATA section where code can be placed.</span></span>  
  
```xml  
<msxsl:script implements-prefix='your-prefix' language='CSharp'>  
<![CDATA[  
// Code block.  
]]>  
</msxsl:script>  
```  
  
## <a name="script-functions"></a><span data-ttu-id="bec71-128">스크립트 함수</span><span class="sxs-lookup"><span data-stu-id="bec71-128">Script Functions</span></span>  
 <span data-ttu-id="bec71-129">함수는 `msxsl:script` 요소 내에서 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-129">Functions can be declared within the `msxsl:script` element.</span></span> <span data-ttu-id="bec71-130">함수를 선언하면 해당 함수는 스크립트 블록 내에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-130">When a function is declared, it is contained in a script block.</span></span> <span data-ttu-id="bec71-131">스타일시트에는 여러 스크립트 블록이 포함될 수 있으며 각 블록은 서로 독립적으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-131">Style sheets can contain multiple script blocks, each operating independent of the other.</span></span> <span data-ttu-id="bec71-132">즉, 스크립트 블록 내부에서 실행할 경우 같은 네임스페이스와 같은 스크립트 언어를 사용하도록 선언된 경우에만 다른 스크립트 블록에 정의된 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-132">That means that if you are executing inside a script block, you cannot call a function that you defined in another script block unless it is declared to have the same namespace and the same scripting language.</span></span> <span data-ttu-id="bec71-133">각 스크립트 블록에서는 서로 다른 언어를 사용할 수 있고, 블록은 해당 언어 파서의 문법 규칙에 따라 구문 분석되기 때문에 사용하는 언어의 올바른 구문을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-133">Because each script block can be in its own language, and the block is parsed according to the grammar rules of that language parser we recommend that you use the correct syntax for the language in use.</span></span> <span data-ttu-id="bec71-134">예를 들어, Microsoft C# 스크립트 블록에서는 C# 주석 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-134">For example, if you are in a Microsoft C# script block, use the C# comment syntax.</span></span>  
  
 <span data-ttu-id="bec71-135">함수에 제공된 인수 및 반환 값에는 어떤 형식도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-135">The supplied arguments and return values to the function can be of any type.</span></span> <span data-ttu-id="bec71-136">W3C XPath 형식은 CLR(공용 언어 런타임) 형식의 하위 집합이므로 XPath 형식으로 간주되지 않는 형식에서 형식 변환이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-136">Because the W3C XPath types are a subset of the common language runtime (CLR) types, type conversion takes place on types that are not considered to be an XPath type.</span></span> <span data-ttu-id="bec71-137">다음 표에서는 해당 W3C 형식 및 CLR 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-137">The following table shows the corresponding W3C types and the equivalent CLR type.</span></span>  
  
|<span data-ttu-id="bec71-138">W3C 형식</span><span class="sxs-lookup"><span data-stu-id="bec71-138">W3C type</span></span>|<span data-ttu-id="bec71-139">CLR 형식</span><span class="sxs-lookup"><span data-stu-id="bec71-139">CLR type</span></span>|  
|--------------|--------------|  
|`String`|<xref:System.String>|  
|`Boolean`|<xref:System.Boolean>|  
|`Number`|<xref:System.Double>|  
|`Result Tree Fragment`|<xref:System.Xml.XPath.XPathNavigator>|  
|`Node Set`|<xref:System.Xml.XPath.XPathNodeIterator>|  
  
 <span data-ttu-id="bec71-140">CLR 숫자 형식은 <xref:System.Double>로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-140">CLR numeric types are converted to <xref:System.Double>.</span></span> <span data-ttu-id="bec71-141"><xref:System.DateTime> 형식은 <xref:System.String>으로 변환되고,</span><span class="sxs-lookup"><span data-stu-id="bec71-141">The <xref:System.DateTime> type is converted to <xref:System.String>.</span></span> <span data-ttu-id="bec71-142"><xref:System.Xml.XPath.IXPathNavigable> 형식은 <xref:System.Xml.XPath.XPathNavigator>로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-142"><xref:System.Xml.XPath.IXPathNavigable> types are converted to <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="bec71-143">**XPathNavigator[]** 는 <xref:System.Xml.XPath.XPathNodeIterator>로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-143">**XPathNavigator[]** is converted to <xref:System.Xml.XPath.XPathNodeIterator>.</span></span>  
  
 <span data-ttu-id="bec71-144">다른 모든 형식은 오류를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-144">All other types throw an error.</span></span>  
  
### <a name="importing-namespaces-and-assemblies"></a><span data-ttu-id="bec71-145">네임스페이스 및 어셈블리 가져오기</span><span class="sxs-lookup"><span data-stu-id="bec71-145">Importing Namespaces and Assemblies</span></span>  
 <span data-ttu-id="bec71-146"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스는 `msxsl:script` 요소에서 기본적으로 지원하는 어셈블리 및 네임스페이스 집합을 미리 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-146">The <xref:System.Xml.Xsl.XslCompiledTransform> class predefines a set of assemblies and namespaces that are supported by default by the `msxsl:script` element.</span></span> <span data-ttu-id="bec71-147">그러나 `msxsl:script` 블록에 어셈블리 및 네임스페이스를 가져오면 미리 정의된 목록에 없는 네임스페이스에 속한 클래스 및 멤버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-147">However, you can use classes and members belonging to a namespace that is not on the predefined list by importing the assembly and namespace in `msxsl:script` block.</span></span>  
  
#### <a name="assemblies"></a><span data-ttu-id="bec71-148">어셈블리</span><span class="sxs-lookup"><span data-stu-id="bec71-148">Assemblies</span></span>  
 <span data-ttu-id="bec71-149">기본적으로 다음 두 어셈블리가 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-149">The following two assemblies are referenced by default:</span></span>  
  
-   <span data-ttu-id="bec71-150">System.dll</span><span class="sxs-lookup"><span data-stu-id="bec71-150">System.dll</span></span>  
  
-   <span data-ttu-id="bec71-151">System.Xml.dll</span><span class="sxs-lookup"><span data-stu-id="bec71-151">System.Xml.dll</span></span>  
  
-   <span data-ttu-id="bec71-152">Microsoft.VisualBasic.dll(스크립트 언어가 VB인 경우)</span><span class="sxs-lookup"><span data-stu-id="bec71-152">Microsoft.VisualBasic.dll (when the script language is VB)</span></span>  
  
 <span data-ttu-id="bec71-153">`msxsl:assembly` 요소를 사용하여 추가 어셈블리를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-153">You can import the additional assemblies using the `msxsl:assembly` element.</span></span> <span data-ttu-id="bec71-154">여기에는 스타일시트를 컴파일할 때 어셈블리가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-154">This includes the assembly when the style sheet is compiled.</span></span> <span data-ttu-id="bec71-155">`msxsl:assembly` 요소에는 다음 정의가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-155">The `msxsl:assembly` element has the following definition:</span></span>  
  
```xml  
<msxsl:script>  
  <msxsl:assembly name="system.assemblyName" />  
  <msxsl:assembly href="path-name" />  
    <![CDATA[  
    // User code  
    ]]>  
</msxsl:script>  
```  
  
 <span data-ttu-id="bec71-156">`name` 특성에는 어셈블리 이름이 포함되며 `href` 특성에는 어셈블리 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-156">The `name` attribute contains the name of the assembly and the `href` attribute contains the path to the assembly.</span></span> <span data-ttu-id="bec71-157">어셈블리 이름은 "System.Data, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" 등의 전체 이름이거나 "System.Web"과 같은 약식 이름일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-157">The assembly name can be a full name, such as "System.Data, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b77a5c561934e089", or a short name, such as "System.Web".</span></span>  
  
#### <a name="namespaces"></a><span data-ttu-id="bec71-158">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="bec71-158">Namespaces</span></span>  
 <span data-ttu-id="bec71-159">기본적으로 다음 네임스페이스가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-159">The following namespaces are included by default:</span></span>  
  
-   <span data-ttu-id="bec71-160">시스템</span><span class="sxs-lookup"><span data-stu-id="bec71-160">System</span></span>  
  
-   <span data-ttu-id="bec71-161">System.Collection</span><span class="sxs-lookup"><span data-stu-id="bec71-161">System.Collection</span></span>  
  
-   <span data-ttu-id="bec71-162">System.Text</span><span class="sxs-lookup"><span data-stu-id="bec71-162">System.Text</span></span>  
  
-   <span data-ttu-id="bec71-163">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="bec71-163">System.Text.RegularExpressions</span></span>  
  
-   <span data-ttu-id="bec71-164">System.Xml</span><span class="sxs-lookup"><span data-stu-id="bec71-164">System.Xml</span></span>  
  
-   <span data-ttu-id="bec71-165">System.Xml.Xsl</span><span class="sxs-lookup"><span data-stu-id="bec71-165">System.Xml.Xsl</span></span>  
  
-   <span data-ttu-id="bec71-166">System.Xml.XPath</span><span class="sxs-lookup"><span data-stu-id="bec71-166">System.Xml.XPath</span></span>  
  
-   <span data-ttu-id="bec71-167">Microsoft.VisualBasic(스크립트 언어가 VB인 경우)</span><span class="sxs-lookup"><span data-stu-id="bec71-167">Microsoft.VisualBasic (when the script language is VB)</span></span>  
  
 <span data-ttu-id="bec71-168">`namespace` 특성을 사용하여 추가 네임스페이스에 대한 지원을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-168">You can add support for additional namespaces using the `namespace` attribute.</span></span> <span data-ttu-id="bec71-169">특성 값은 네임스페이스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-169">The attribute value is the name of the namespace.</span></span>  
  
```xml  
<msxsl:script>  
  <msxsl:using namespace="system.namespaceName" />  
    <![CDATA[  
    // User code  
    ]]>  
</msxsl:script>  
```  
  
## <a name="example"></a><span data-ttu-id="bec71-170">예</span><span class="sxs-lookup"><span data-stu-id="bec71-170">Example</span></span>  
 <span data-ttu-id="bec71-171">다음 예제에서는 포함 스크립트를 사용하여 주어진 반지름으로 원의 원주를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="bec71-171">The following example uses an embedded script to calculate the circumference of a circle given its radius.</span></span>  
  
 [!code-csharp[XSLT_Script#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_Script/CS/xslt_script.cs#1)]
 [!code-vb[XSLT_Script#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_Script/VB/xslt_script.vb#1)]  
  
#### <a name="numberxml"></a><span data-ttu-id="bec71-172">number.xml</span><span class="sxs-lookup"><span data-stu-id="bec71-172">number.xml</span></span>  
 [!code-xml[XSLT_Script#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Script/XML/number.xml#2)]  
  
#### <a name="calcxsl"></a><span data-ttu-id="bec71-173">calc.xsl</span><span class="sxs-lookup"><span data-stu-id="bec71-173">calc.xsl</span></span>  
 [!code-xml[XSLT_Script#3](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Script/XML/calc.xsl#3)]  
  
### <a name="output"></a><span data-ttu-id="bec71-174">출력</span><span class="sxs-lookup"><span data-stu-id="bec71-174">Output</span></span>  
  
```xml  
<circles xmlns:msxsl="urn:schemas-microsoft-com:xslt" xmlns:user="urn:my-scripts">  
  <circle>  
    <radius>12</radius>  
    <circumference>75.36</circumference>  
  </circle>  
  <circle>  
    <radius>37.5</radius>  
    <circumference>235.5</circumference>  
  </circle>  
</circles>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bec71-175">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bec71-175">See Also</span></span>  
 [<span data-ttu-id="bec71-176">XSLT 변환</span><span class="sxs-lookup"><span data-stu-id="bec71-176">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)  
 [<span data-ttu-id="bec71-177">동적 소스 코드 생성 및 컴파일</span><span class="sxs-lookup"><span data-stu-id="bec71-177">Dynamic Source Code Generation and Compilation</span></span>](../../../../docs/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)
