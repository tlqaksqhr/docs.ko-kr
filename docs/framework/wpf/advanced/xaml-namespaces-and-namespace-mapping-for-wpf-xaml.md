---
title: "WPF XAML을 위한 XAML 네임스페이스 및 네임스페이스 매핑"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom classes [WPF], mapping namespaces to
- XAML [WPF], namespaces
- namespace mapping [WPF]
- assemblies [WPF], mapping namespaces to
- mapping namespaces [WPF]
- XAML [WPF], namespace mapping
- classes [WPF], mapping namespaces to
- namespaces [WPF]
ms.assetid: 5c0854e3-7470-435d-9fe2-93eec9d3634e
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2798659d3b53cb32af8e5976d4fee69780266633
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="xaml-namespaces-and-namespace-mapping-for-wpf-xaml"></a><span data-ttu-id="8dcd6-102">WPF XAML을 위한 XAML 네임스페이스 및 네임스페이스 매핑</span><span class="sxs-lookup"><span data-stu-id="8dcd6-102">XAML Namespaces and Namespace Mapping for WPF XAML</span></span>
<span data-ttu-id="8dcd6-103">이 항목에서는 WPF XAML 파일의 루트 태그에서 주로 찾을 수 있는 두 XAML 네임스페이스 매핑과 그 용도에 대해 자세하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-103">This topic further explains the presence and purpose of the two XAML namespace mappings as often found in the root tag of a WPF XAML file.</span></span> <span data-ttu-id="8dcd6-104">또한 고유한 코드나 별도의 어셈블리에 정의된 요소에 사용할 수 있도록 유사한 매핑을 생성하는 방법에 대해서도 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-104">It also describes how to produce similar mappings for using elements that are defined in your own code, and/or within separate assemblies.</span></span>  
  
  
## <a name="what-is-a-xaml-namespace"></a><span data-ttu-id="8dcd6-105">XAML 네임스페이스의 정의</span><span class="sxs-lookup"><span data-stu-id="8dcd6-105">What is a XAML Namespace?</span></span>  
 <span data-ttu-id="8dcd6-106">XAML 네임스페이스는 XML 네임스페이스 개념을 확장한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-106">A XAML namespace is really an extension of the concept of an XML namespace.</span></span> <span data-ttu-id="8dcd6-107">XAML 네임스페이스를 지정하는 데는 XML 네임스페이스 구문, 네임스페이스 식별자로 URI를 사용하는 규칙이 적용되며 동일한 태그 소스의 여러 네임스페이스를 참조하기 위한 수단을 제공하는 접두사가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-107">The techniques of specifying a XAML namespace rely on the XML namespace syntax, the convention of using URIs as namespace identifiers, using prefixes to provide a means to reference multiple namespaces from the same markup source, and so on.</span></span> <span data-ttu-id="8dcd6-108">XML 네임스페이스의 XAML 정의에 추가된 주요 개념에 따르면 XAML 네임스페이스는 태그 사용의 고유성 범위를 보장하고, 태그 엔터티가 특정 CLR 네임스페이스 및 참조되는 어셈블리에 의해 지원되는 방식에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-108">The primary concept that is added to the XAML definition of the XML namespace is that a XAML namespace implies both a scope of uniqueness for the markup usages, and also influences how markup entities are potentially backed by specific CLR namespaces and referenced assemblies.</span></span> <span data-ttu-id="8dcd6-109">이러한 지원 방식은 XAML 스키마 컨텍스트라는 개념에 의해서도 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-109">This latter consideration is also influenced by the concept of a XAML schema context.</span></span> <span data-ttu-id="8dcd6-110">그러나 WPF에서 XAML 네임스페이스를 처리하려는 경우에는 일반적으로 기본 XAML 네임스페이스, XAML 언어 네임스페이스 및 추가적인 다른 XAML 네임스페이스 등의 XAML 네임스페이스를 XAML 태그에 의해 특정 지원 CLR 네임스페이스 및 참조되는 어셈블리에 직접 매핑되는 것으로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-110">But for purposes of how WPF works with XAML namespaces, you can generally think of XAML namespaces in terms of a default XAML namespace, the XAML language namespace, and any further XAML namespaces as mapped by your XAML markup directly to specific backing CLR namespaces and referenced assemblies.</span></span>  
  
<a name="The_WPF_and_XAML_Namespace_Declarations"></a>   
## <a name="the-wpf-and-xaml-namespace-declarations"></a><span data-ttu-id="8dcd6-111">WPF 및 XAML 네임스페이스 선언</span><span class="sxs-lookup"><span data-stu-id="8dcd6-111">The WPF and XAML Namespace Declarations</span></span>  
 <span data-ttu-id="8dcd6-112">많은 XAML 파일의 루트 태그에 있는 네임스페이스 선언에는 일반적으로 두 가지 XML 네임스페이스 선언이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-112">Within the namespace declarations in the root tag of many XAML files, you will see that there are typically two XML namespace declarations.</span></span> <span data-ttu-id="8dcd6-113">다음과 같은 첫 번째 선언은 전체 WPF 클라이언트/프레임워크 XAML 네임스페이스를 기본값으로 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-113">The first declaration maps the overall WPF client / framework XAML namespace as the default:</span></span>  
  
 `xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`  
  
 <span data-ttu-id="8dcd6-114">두 번째 선언은 개별 XAML 네임스페이스를 대개 `x:` 접두사에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-114">The second declaration maps a separate XAML namespace, mapping it (typically) to the `x:` prefix.</span></span>  
  
 `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 <span data-ttu-id="8dcd6-115">이러한 선언 간의 관계에서 `x:` 접두사 매핑은 XAML 언어 정의의 일부인 내장 항목을 지원하며, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 XAML을 언어로 사용하고 XAML에 대한 해당 개체의 어휘를 정의하는 하나의 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-115">The relationship between these declarations is that the `x:` prefix mapping supports the intrinsics that are part of the XAML language definition, and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] is one implementation that uses XAML as a language and defines a vocabulary of its objects for XAML.</span></span> <span data-ttu-id="8dcd6-116">WPF 어휘의 사용이 XAML 내장 항목 사용보다 훨씬 더 일반적일 것이므로 WPF 어휘가 기본값으로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-116">Because the WPF vocabulary's usages will be far more common than the XAML intrinsics usages, the WPF vocabulary is mapped as the default.</span></span>  
  
 <span data-ttu-id="8dcd6-117">이 [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)] 내에서 XAML 언어 내장 항목 지원을 매핑하기 위한 `x:` 접두사 규칙 뒤에는 프로젝트 템플릿, 샘플 코드 및 언어 기능의 설명서가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-117">The `x:` prefix convention for mapping the XAML language intrinsics support is followed by project templates, sample code, and the documentation of language features within this [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)].</span></span> <span data-ttu-id="8dcd6-118">XAML 네임스페이스는 기본적인 WPF 응용 프로그램에도 필요한 여러 가지 일반적인 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-118">The XAML namespace defines many commonly-used features that are necessary even for basic WPF  applications.</span></span> <span data-ttu-id="8dcd6-119">예를 들어 partial 클래스를 통해 코드 숨김을 XAML 파일에 결합하려면 관련 XAML 파일의 루트 요소에서 해당 클래스를 `x:Class` 특성으로 명명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-119">For instance, in order to join any code-behind to a XAML file through a partial class, you must name that class as the `x:Class` attribute in the root element of the relevant XAML file.</span></span> <span data-ttu-id="8dcd6-120">또는 XAML 페이지에 정의된 요소 중 키가 지정된 리소스로 액세스하려는 요소에는 `x:Key` 특성을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-120">Or, any element as defined in a XAML page that you wish to access as a keyed resource should have the `x:Key` attribute set on the element in question.</span></span> <span data-ttu-id="8dcd6-121">XAML의 이러한 특징과 기타 특징에 대한 자세한 내용은 [XAML 개요(WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) 또는 [XAML 구문 정보](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-121">For more information on these and other aspects of XAML see [XAML Overview (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) or [XAML Syntax In Detail](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).</span></span>  
  
<a name="Mapping_To_Custom_Classes_and_Assemblies"></a>   
## <a name="mapping-to-custom-classes-and-assemblies"></a><span data-ttu-id="8dcd6-122">사용자 지정 클래스 및 어셈블리 매핑</span><span class="sxs-lookup"><span data-stu-id="8dcd6-122">Mapping to Custom Classes and Assemblies</span></span>  
 <span data-ttu-id="8dcd6-123">표준 WPF 및 XAML 내장 XAML 네임스페이스를 접두사에 매핑하는 방식과 유사하게 `xmlns` 접두사 선언 내에서 일련의 토큰을 사용하여 XML 네임스페이스를 어셈블리에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-123">You can map XML namespaces to assemblies using a series of tokens within an `xmlns` prefix declaration, similar to how the standard WPF and XAML-intrinsics XAML namespaces are mapped to prefixes.</span></span>  
  
 <span data-ttu-id="8dcd6-124">구문에는 다음과 같은 명명된 토큰과 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-124">The syntax takes the following possible named tokens and following values:</span></span>  
  
 <span data-ttu-id="8dcd6-125">`clr-namespace:` 요소로 노출되는 공용 형식을 포함하는 어셈블리 내에서 선언된 CLR 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-125">`clr-namespace:` The CLR namespace declared within the assembly that contains the public types to expose as elements.</span></span>  
  
 <span data-ttu-id="8dcd6-126">`assembly=` 참조된 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 네임스페이스 일부 또는 전체를 포함하는 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-126">`assembly=` The assembly that contains some or all of the referenced [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] namespace.</span></span> <span data-ttu-id="8dcd6-127">이 값은 일반적으로 경로가 아니라 어셈블리의 이름이며 .dll 또는 .exe와 같은 확장명을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-127">This value is typically just the name of the assembly, not the path, and does not include the extension (such as .dll or .exe).</span></span> <span data-ttu-id="8dcd6-128">해당 어셈블리의 경로는 매핑하려는 XAML을 포함하는 프로젝트 파일에서 프로젝트 참조로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-128">The path to that assembly must be established as a project reference in the project file that contains the XAML you are trying to map.</span></span> <span data-ttu-id="8dcd6-129">버전 관리 및 강력한 이름 서명 통합 하기 위해는 `assembly` 값일 수는 문자열에 정의 된 대로 <xref:System.Reflection.AssemblyName>, 16 진수 간단한 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-129">In order to incorporate versioning and strong-name signing, the `assembly` value can be a string as defined by <xref:System.Reflection.AssemblyName>, rather than the simple string name.</span></span>  
  
 <span data-ttu-id="8dcd6-130">`clr-namespace` 토큰과 해당 값을 구분하는 문자는 콜론(:)이지만, `assembly` 토큰과 해당 값을 구분하는 문자는 등호(=)입니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-130">Note that the character separating the `clr-namespace` token from its value is a colon (:) whereas the character separating the `assembly` token from its value is an equals sign (=).</span></span> <span data-ttu-id="8dcd6-131">이 두 토큰 간을 구분하는 데 사용되는 문자는 세미콜론입니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-131">The character to use between these two tokens is a semicolon.</span></span> <span data-ttu-id="8dcd6-132">또한 선언에는 공백을 포함하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-132">Also, do not include any whitespace anywhere in the declaration.</span></span>  
  
### <a name="a-basic-custom-mapping-example"></a><span data-ttu-id="8dcd6-133">기본 사용자 지정 매핑 예제</span><span class="sxs-lookup"><span data-stu-id="8dcd6-133">A Basic Custom Mapping Example</span></span>  
 <span data-ttu-id="8dcd6-134">다음 코드에서는 예제 사용자 지정 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-134">The following code defines an example custom class:</span></span>  
  
```csharp  
namespace SDKSample {  
    public class ExampleClass : ContentControl {  
        public ExampleClass() {  
        ...  
        }  
    }  
}  
```  
  
```vb  
Namespace SDKSample  
    Public Class ExampleClass  
        Inherits ContentControl  
         ...  
        Public Sub New()  
        End Sub  
    End Class  
End Namespace  
```  
  
 <span data-ttu-id="8dcd6-135">이 사용자 지정 클래스는 라이브러리로 컴파일되며 라이브러리의 이름은 프로젝트 설정(표시되지 않음)별로 `SDKSampleLibrary`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-135">This custom class is then compiled into a library, which per the project settings (not shown) is named `SDKSampleLibrary`.</span></span>  
  
 <span data-ttu-id="8dcd6-136">이 사용자 지정 클래스를 참조하려면 이 클래스를 현재 프로젝트의 참조로도 포함해야 합니다. 이 작업은 일반적으로 Visual Studio에서 솔루션 탐색기 UI를 사용하여 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-136">In order to reference this custom class, you also need to include it as a reference for your current project, which you would typically do using the Solution Explorer UI in Visual Studio.</span></span>  
  
 <span data-ttu-id="8dcd6-137">이제 클래스가 포함된 라이브러리가 있고, 프로젝트 설정에 이 라이브러리에 대한 참조가 있으므로 다음 접두사 매핑을 XAML에서 루트 요소의 일부로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-137">Now that you have a library containing a class, and a reference to it in project settings, you can add the following prefix mapping as part of your root element in XAML:</span></span>  
  
 `xmlns:custom="clr-namespace:SDKSample;assembly=SDKSampleLibrary"`  
  
 <span data-ttu-id="8dcd6-138">이 모두를 결합하면 다음과 같이 루트 태그에 일반적인 기본 및 x: 매핑과 함께 사용자 지정 매핑을 포함하고 접두사가 지정된 참조를 사용하여 해당 UI의 `ExampleClass`를 인스턴스화하는 XAML이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-138">To put it all together, the following is XAML that includes the custom mapping along with the typical default and x: mappings in the root tag, then uses a prefixed reference to instantiate `ExampleClass` in that UI:</span></span>  
  
```xaml  
<Page x:Class="WPFApplication1.MainPage"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"   
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:custom="clr-namespace:SDKSample;assembly=SDKSampleLibrary">  
  ...  
  <custom:ExampleClass/>  
...  
</Page>  
```  
  
### <a name="mapping-to-current-assemblies"></a><span data-ttu-id="8dcd6-139">현재 어셈블리에 매핑</span><span class="sxs-lookup"><span data-stu-id="8dcd6-139">Mapping to Current Assemblies</span></span>  
 <span data-ttu-id="8dcd6-140">사용자 지정 클래스를 참조하는 응용 프로그램 코드와 동일한 어셈블리 내에서 `clr-namespace` 참조를 정의하는 경우에는 `assembly`를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-140">`assembly` can be omitted if the `clr-namespace` referenced is being defined within the same assembly as the application code that is referencing the custom classes.</span></span> <span data-ttu-id="8dcd6-141">등호 다음에 문자열 토큰 없이 `assembly=`를 지정하는 구문도 이와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-141">Or, an equivalent syntax for this case is to specify `assembly=`, with no string token following the equals sign.</span></span>  
  
 <span data-ttu-id="8dcd6-142">사용자 지정 클래스는 동일한 어셈블리에 정의된 경우 페이지의 루트 요소로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-142">Custom classes cannot be used as the root element of a page if defined in the same assembly.</span></span> <span data-ttu-id="8dcd6-143">partial 클래스는 매핑할 필요가 없으며 응용 프로그램에서 페이지의 partial 클래스가 아닌 클래스 중 XAML에서 요소로 참조하려는 클래스만 매핑하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-143">Partial classes do not need to be mapped; only classes that are not the partial class of a page in your application need to be mapped if you intend to reference them as elements in XAML.</span></span>  
  
<a name="Mapping_CLR_Namespaces_to_XML_Namespaces_in_an"></a>   
## <a name="mapping-clr-namespaces-to-xml-namespaces-in-an-assembly"></a><span data-ttu-id="8dcd6-144">CLR 네임스페이스를 어셈블리의 XML 네임스페이스에 매핑</span><span class="sxs-lookup"><span data-stu-id="8dcd6-144">Mapping CLR Namespaces to XML Namespaces in an Assembly</span></span>  
 <span data-ttu-id="8dcd6-145">WPF는 여러 CLR 네임스페이스를 단일 XAML 네임스페이스에 매핑하기 위해 XAML 프로세서에서 사용되는 CLR 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-145">WPF defines a CLR attribute that is consumed by XAML processors in order to map multiple CLR namespaces to a single XAML namespace.</span></span> <span data-ttu-id="8dcd6-146">이 특성을 <xref:System.Windows.Markup.XmlnsDefinitionAttribute>, 어셈블리를 생성 하는 소스 코드에서 어셈블리 수준에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-146">This attribute, <xref:System.Windows.Markup.XmlnsDefinitionAttribute>, is placed at the assembly level in the source code that produces the assembly.</span></span> <span data-ttu-id="8dcd6-147">WPF 어셈블리의 소스 코드에서이 특성을 사용 하 여와 같은 다양 한 공통 네임 스페이스를 매핑할 <xref:System.Windows> 및 <xref:System.Windows.Controls>을 [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)] 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-147">The WPF assembly source code uses this attribute to map the various common namespaces, such as <xref:System.Windows> and <xref:System.Windows.Controls>, to the [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)] namespace.</span></span>  
  
 <span data-ttu-id="8dcd6-148"><xref:System.Windows.Markup.XmlnsDefinitionAttribute> 두 개의 매개 변수: XML/XAML 네임 스페이스 이름 및 CLR 네임 스페이스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-148">The <xref:System.Windows.Markup.XmlnsDefinitionAttribute> takes two parameters: the XML/XAML namespace name, and the CLR namespace name.</span></span> <span data-ttu-id="8dcd6-149">둘 이상의 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 동일한 XML 네임 스페이스에 여러 CLR 네임 스페이스를 매핑할 존재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-149">More than one <xref:System.Windows.Markup.XmlnsDefinitionAttribute> can exist to map multiple CLR namespaces to the same XML namespace.</span></span> <span data-ttu-id="8dcd6-150">매핑한 후에는 partial 클래스의 코드 숨김 페이지에서 적절한 `using` 문을 사용하여 정규화된 이름 없이도 이러한 네임스페이스의 멤버를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-150">Once mapped, members of those namespaces can also be referenced without full qualification if desired by providing the appropriate `using` statement in the partial-class code-behind page.</span></span> <span data-ttu-id="8dcd6-151">자세한 내용은 <xref:System.Windows.Markup.XmlnsDefinitionAttribute>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-151">For more details, see <xref:System.Windows.Markup.XmlnsDefinitionAttribute>.</span></span>  
  
## <a name="designer-namespaces-and-other-prefixes-from-xaml-templates"></a><span data-ttu-id="8dcd6-152">XAML 템플릿의 디자이너 네임스페이스 및 기타 접두사</span><span class="sxs-lookup"><span data-stu-id="8dcd6-152">Designer Namespaces and Other Prefixes From XAML Templates</span></span>  
 <span data-ttu-id="8dcd6-153">여러 가지 WPF XAML 개발 환경 및/또는 디자인 도구를 사용하는 경우 XAML 태그 내에 다른 XAML 네임스페이스 및 접두사가 정의되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-153">If you are working with development environments and/or design tools for WPF XAML, you may notice that there are other defined XAML namespaces / prefixes within the XAML markup.</span></span>  
  
 [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)]<span data-ttu-id="8dcd6-154">에서는 일반적으로 접두사 `d:`에 매핑되는 디자이너 네임스페이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-154"> uses a designer namespace that is typically mapped to the prefix `d:`.</span></span> <span data-ttu-id="8dcd6-155">최신 WPF용 프로젝트 템플릿의 경우 [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)]와 다른 디자인 환경 간의 XAML 교환을 지원하기 위해 이 XAML 네임스페이스가 미리 매핑되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-155">More recent project templates for WPF might pre-map this XAML namespace to support interchange of the XAML between [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] and other design environments.</span></span> <span data-ttu-id="8dcd6-156">이 디자인 XAML 네임스페이스는 디자이너에서 XAML 기반 UI를 왕복하는 동안 디자인 상태를 계속 유지하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-156">This design XAML namespace is used to perpetuate design state while roundtripping XAML-based UI in the designer.</span></span> <span data-ttu-id="8dcd6-157">또한 디자이너에서 런타임 데이터 소스를 사용할 수 있게 하는 `d:IsDataSource` 등의 기능에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-157">It is also used for features such as `d:IsDataSource`, which enable runtime data sources in a designer.</span></span>  
  
 <span data-ttu-id="8dcd6-158">매핑되는 또 다른 접두사로 `mc:`이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-158">Another prefix you might see mapped is `mc:`.</span></span> <span data-ttu-id="8dcd6-159">`mc:`은 태그 호환성을 위해 사용되며, XAML에 반드시 필요하지는 않은 태그 호환성 패턴을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-159">`mc:` is for markup compatibility, and is leveraging a markup compatibility pattern that is not necessarily XAML-specific.</span></span> <span data-ttu-id="8dcd6-160">일정 범위 내에서 태그 호환성 기능은 프레임워크 간 또는 지원 구현의 여러 경계를 넘어 XAML을 교환하는 데 사용될 수 있으며, XAML 스키마 컨텍스트 간에 작업하고 디자이너에서 제한된 모드에 대해 호환성을 제공하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-160">To some extent, the markup compatibility features can be used to exchange XAML between frameworks or across other boundaries of backing implementation, work between XAML schema contexts, provide compatibility for limited modes in designers, and so on.</span></span> <span data-ttu-id="8dcd6-161">태그 호환성 개념 및 이 개념과 WPF의 관련성에 대한 자세한 내용은 [태그 호환성(mc:) 언어 기능](../../../../docs/framework/wpf/advanced/markup-compatibility-mc-language-features.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-161">For more information on markup compatibility concepts and how they relate to WPF, see  [Markup Compatibility (mc:) Language Features](../../../../docs/framework/wpf/advanced/markup-compatibility-mc-language-features.md).</span></span>  
  
## <a name="wpf-and-assembly-loading"></a><span data-ttu-id="8dcd6-162">WPF 및 어셈블리 로딩</span><span class="sxs-lookup"><span data-stu-id="8dcd6-162">WPF and Assembly Loading</span></span>  
 <span data-ttu-id="8dcd6-163">WPF는 XAML 스키마 컨텍스트와의 개념을 CLR 정의 사용 하는 WPF 응용 프로그램 모델와 통합 되어 <xref:System.AppDomain>합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-163">The XAML schema context for WPF integrates with the WPF application model, which in turn uses the CLR-defined concept of <xref:System.AppDomain>.</span></span> <span data-ttu-id="8dcd6-164">다음 순서 대로 XAML 스키마 컨텍스트 WPF 사용법에 따라 런타임 또는 디자인 타임에 형식을 찾을 또는 어셈블리를 로드 하는 방법을 해석 하는 방법을 설명 <xref:System.AppDomain> 및 기타 요인입니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-164">The following sequence describes how XAML schema context interprets how to either load assemblies or find types at run time or design time, based on the WPF use of <xref:System.AppDomain> and other factors.</span></span>  
  
1.  <span data-ttu-id="8dcd6-165">반복은 <xref:System.AppDomain>, 해당 이름의 모든 요소를 일치 하는 이미 로드 된 어셈블리를 찾고, 로드 된 어셈블리에서 가장 최근에 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-165">Iterate through the <xref:System.AppDomain>, looking for an already-loaded assembly that matches all aspects of the name, starting from the most recently loaded assembly.</span></span>  
  
2.  <span data-ttu-id="8dcd6-166">이름이 정규화 된 경우 호출 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> 정규화 된 이름에서.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-166">If the name is qualified, call <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> on the qualified name.</span></span>  
  
3.  <span data-ttu-id="8dcd6-167">약식 이름 + 정규화된 이름의 공개 키 토큰이 로드한 태그의 소스 어셈블리와 일치하는 경우 이 어셈블리를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-167">If the short name + public key token of a qualified name matches the assembly that the markup was loaded from, return that assembly.</span></span>  
  
4.  <span data-ttu-id="8dcd6-168">짧은 이름 + 공개 키 토큰을 사용 하 여 호출 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-168">Use the short name + public key token to call <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.</span></span>  
  
5.  <span data-ttu-id="8dcd6-169">이름을 정규화 되지 않은 경우 호출 <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-169">If the name is unqualified, call <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="8dcd6-170">느슨한 XAML에서는 로드할 소스 어셈블리가 없으므로 3단계가 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-170">Loose XAML does not use Step 3; there is no loaded-from assembly.</span></span>  
  
 <span data-ttu-id="8dcd6-171">WPF (XamlBuildTask를 통해 생성 된)에 대 한 컴파일된 XAML에서 이미 로드 된 어셈블리를 사용 하지 않는 <xref:System.AppDomain> (1 단계).</span><span class="sxs-lookup"><span data-stu-id="8dcd6-171">Compiled XAML for WPF (generated via XamlBuildTask) does not use the already-loaded assemblies from <xref:System.AppDomain> (Step 1).</span></span> <span data-ttu-id="8dcd6-172">또한 XamlBuildTask 출력에서 이름이 정규화되지 않아서는 안되므로 5단계가 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-172">Also, the name should never be unqualified from XamlBuildTask output, so Step 5 does not apply.</span></span>  
  
 <span data-ttu-id="8dcd6-173">BAML도 정규화되지 않은 어셈블리 이름을 포함해서는 안되지만 PresentationBuildTask를 통해 생성된 컴파일된 BAML에서는 모든 단계를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8dcd6-173">Compiled BAML (generated via PresentationBuildTask) uses all steps, although BAML also should not contain unqualified assembly names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dcd6-174">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8dcd6-174">See Also</span></span>  
 [<span data-ttu-id="8dcd6-175">XML 네임 스페이스 이해</span><span class="sxs-lookup"><span data-stu-id="8dcd6-175">Understanding XML Namespaces</span></span>](http://go.microsoft.com/fwlink/?LinkId=98069)  
 [<span data-ttu-id="8dcd6-176">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="8dcd6-176">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
