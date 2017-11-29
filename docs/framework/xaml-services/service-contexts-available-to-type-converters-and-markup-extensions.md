---
title: "형식 변환기 또는 태그 확장에서 사용할 수 있는 서비스 컨텍스트"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: XAML [XAML Services], type converter services how-to
ms.assetid: b4dad00f-03da-4579-a4e9-d8d72d2ccbce
caps.latest.revision: "13"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 229601515442b5e84f6c4278b17db7ae25945a42
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="service-contexts-available-to-type-converters-and-markup-extensions"></a><span data-ttu-id="158d0-102">형식 변환기 또는 태그 확장에서 사용할 수 있는 서비스 컨텍스트</span><span class="sxs-lookup"><span data-stu-id="158d0-102">Service Contexts Available to Type Converters and Markup Extensions</span></span>
<span data-ttu-id="158d0-103">형식 변환기 및 태그 확장 사용을 지원하는 형식의 작성자에는 태그 또는 주변 개체 그래프 구조에서 사용하는 경우에 대한 컨텍스트 정보를 포함해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-103">Authors of the types that support type converter and markup extension usages must often have contextual information about where a usage is located in the markup, or in surrounding object graph structure.</span></span> <span data-ttu-id="158d0-104">제공된 개체를 올바르게 인스턴스화하거나 개체 그래프의 기존 개체에 대한 개체 참조를 만들 수 있도록 정보가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-104">Information might be needed so that the provided object is instantiated correctly or so that object references to existing objects in the object graph can be made.</span></span> <span data-ttu-id="158d0-105">.NET Framework XAML 서비스를 사용할 경우 필요할 수 있는 컨텍스트는 일련의 서비스 인터페이스로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-105">When using .NET Framework XAML Services, the context that might be required is exposed as a series of service interfaces.</span></span> <span data-ttu-id="158d0-106">형식 변환기 또는 태그 확장 지원 코드에서는 <xref:System.Xaml.XamlObjectWriter> 또는 관련 형식에서 사용 가능하고 통과되는 서비스 공급자 컨텍스트를 사용하여 서비스를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-106">Type converter or markup extension support code can query for a service by using a service provider context that is available and passed through from <xref:System.Xaml.XamlObjectWriter> or related types.</span></span> <span data-ttu-id="158d0-107">XAML 스키마 컨텍스트는 이러한 한 서비스를 통해 직접 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-107">The XAML schema context is directly available through one such service.</span></span> <span data-ttu-id="158d0-108">이 항목에서는 값 변환기 구현에서 서비스 컨텍스트에 액세스하는 방법을 설명하고 일반적으로 사용 가능한 서비스 및 해당 역할을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-108">This topic describes how to access service contexts from a value converter implementation, and lists typically available services and their roles.</span></span>  
  
<a name="obtaining_services"></a>   
## <a name="obtaining-services"></a><span data-ttu-id="158d0-109">서비스 가져오기</span><span class="sxs-lookup"><span data-stu-id="158d0-109">Obtaining Services</span></span>  
 <span data-ttu-id="158d0-110">값 변환기의 구현자는 값 변환기가 적용되는 컨텍스트의 몇몇 형식에 액세스해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-110">As an implementer of a value converter, you often need access to some type of context in which the value converter is applied.</span></span> <span data-ttu-id="158d0-111">이 컨텍스트에는 활성 XAML 스키마 컨텍스트와 같은 정보, XAML 스키마 컨텍스트 및 XAML 개체 작성기에서 제공하는 형식 매핑 시스템에 대한 액세스 권한 등이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-111">This context might include information such as the active XAML schema context, access to the type mapping system that the XAML schema context and XAML object writer provide, and so on.</span></span> <span data-ttu-id="158d0-112">태그 확장 또는 형식 변환기 구현에 사용할 수 있는 서비스는 각 가상 메서드의 서명 일부인 컨텍스트 매개 변수를 통해 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-112">The services available for a markup extension or type converter implementation are communicated through the context parameters that are part of the signature of each virtual method.</span></span> <span data-ttu-id="158d0-113">모든 경우에 컨텍스트에 <xref:System.IServiceProvider>가 구현되어 있고 <xref:System.IServiceProvider.GetService%2A?displayProperty=nameWithType>를 호출하여 서비스를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-113">In every case, you have <xref:System.IServiceProvider> implemented in the context, and can call <xref:System.IServiceProvider.GetService%2A?displayProperty=nameWithType> to request a service.</span></span>  
  
<a name="services_for_a_markup_extension"></a>   
## <a name="services-for-a-markup-extension"></a><span data-ttu-id="158d0-114">태그 확장에 대한 서비스</span><span class="sxs-lookup"><span data-stu-id="158d0-114">Services for a Markup Extension</span></span>  
 <span data-ttu-id="158d0-115"><xref:System.Windows.Markup.MarkupExtension> 에는 단 하나의 가상 메서드 <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-115"><xref:System.Windows.Markup.MarkupExtension> has only one virtual method, <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>.</span></span> <span data-ttu-id="158d0-116">입력 `serviceProvider` 매개 변수는 태그 확장이 XAML 프로세서에서 호출될 때 서비스가 구현에 전달되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-116">The input `serviceProvider` parameter is how the services are communicated to implementations when the markup extension is called by a XAML processor.</span></span> <span data-ttu-id="158d0-117">다음 의사 코드에서는 태그 확장 구현이 <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>에서 서비스를 쿼리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-117">The following pseudocode illustrates how a markup extension implementation might query for services in its <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>:</span></span>  
  
```  
public override object ProvideValue(IServiceProvider serviceProvider)  
{  
...  
    // Get the IXamlTypeResolver from the service provider  
    if (serviceProvider == null)  
    {  
        throw new ArgumentNullException("serviceProvider");  
    }  
    IXamlTypeResolver xamlTypeResolver = serviceProvider.GetService(typeof(IXamlTypeResolver)) as IXamlTypeResolver;  
    if (xamlTypeResolver == null)  
   {  
        throw new ArgumentException("IXamlTypeResolver"));  
    }  
...  
}  
```  
  
<a name="services_for_a_type_converter"></a>   
## <a name="services-for-a-type-converter"></a><span data-ttu-id="158d0-118">형식 변환기에 대한 서비스</span><span class="sxs-lookup"><span data-stu-id="158d0-118">Services for a Type Converter</span></span>  
 <span data-ttu-id="158d0-119"><xref:System.ComponentModel.TypeConverter> 에는 서비스 컨텍스트를 사용하고 XAML 사용을 지원하는 가상 메서드 4개가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-119"><xref:System.ComponentModel.TypeConverter> has four virtual methods that use a service context and that support XAML usages.</span></span> <span data-ttu-id="158d0-120">이들 메서드는 각각 입력 `context` 매개 변수를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-120">Each of these methods passes an input `context` parameter.</span></span> <span data-ttu-id="158d0-121">이 매개 변수는 <xref:System.ComponentModel.ITypeDescriptorContext>형식이지만 해당 인터페이스는 <xref:System.IServiceProvider>를 상속하므로 형식 컨버터 구현에 <xref:System.IServiceProvider.GetService%2A> 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-121">This parameter is of type <xref:System.ComponentModel.ITypeDescriptorContext>, but that interface inherits <xref:System.IServiceProvider>, and therefore, there is a <xref:System.IServiceProvider.GetService%2A> method available to type converter implementations.</span></span>  
  
 <span data-ttu-id="158d0-122">다음 의사 코드에서는 XAML 사용에 대한 형식 변환기 구현이 재정의의 하나에서 서비스를 쿼리할 수 있습니다(이 경우 <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>).</span><span class="sxs-lookup"><span data-stu-id="158d0-122">The following pseudocode illustrates how a type converter implementation for XAML usages might query for services in one of its overrides, in this case <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>:</span></span>  
  
```  
public override object ConvertFrom(ITypeDescriptorContext typeDescriptorContext,  
  CultureInfo cultureInfo,  
  object source)  
{  
    IRootObjectProvider rootProvider = typeDescriptorContext.GetService(typeof(IRootObjectProvider)) as IRootObjectProvider;  
    if (rootProvider != null && source is String)  
    {  
        //return something, else ...  
    }  
    throw GetConvertFromException(source);  
}  
```  
  
<a name="services_for_a_value_serializer"></a>   
## <a name="services-for-a-value-serializer"></a><span data-ttu-id="158d0-123">값 Serializer에 대한 서비스</span><span class="sxs-lookup"><span data-stu-id="158d0-123">Services for a Value Serializer</span></span>  
 <span data-ttu-id="158d0-124">값 serializer 컨텍스트의 경우 <xref:System.Windows.Markup.ValueSerializer> 클래스, <xref:System.Windows.Markup.IValueSerializerContext>에 특정한 서비스 공급자 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-124">For value serializer context, you use a service provider type that is specific to the <xref:System.Windows.Markup.ValueSerializer> class, <xref:System.Windows.Markup.IValueSerializerContext>.</span></span> <span data-ttu-id="158d0-125">해당 컨텍스트는 <xref:System.Windows.Markup.ValueSerializer> 가상 메서드 4개의 재정의에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-125">That context is passed to overrides of the four <xref:System.Windows.Markup.ValueSerializer> virtual methods.</span></span> <span data-ttu-id="158d0-126">컨텍스트에서 <xref:System.IServiceProvider.GetService%2A> 를 호출하여 서비스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-126">Call <xref:System.IServiceProvider.GetService%2A> from the context to obtain services.</span></span>  
  
<a name="using_the_xaml_service_provider_contexts"></a>   
## <a name="using-the-xaml-service-provider-contexts"></a><span data-ttu-id="158d0-127">XAML 서비스 공급자 컨텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="158d0-127">Using the XAML Service Provider Contexts</span></span>  
 <span data-ttu-id="158d0-128">태그 확장 또는 형식 변환기에 사용할 수 있는 XAML 서비스에 대한 <xref:System.IServiceProvider.GetService%2A> 액세스의 서비스 공급자는 내부 클래스로 구현되고, 관련 컨텍스트에 전달된 방법 및 인터페이스를 통해서만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-128">The service provider for <xref:System.IServiceProvider.GetService%2A> access to XAML services available to markup extensions or type converters is implemented as an internal class, with exposure only through the interface and how it is passed into the relevant context .</span></span> <span data-ttu-id="158d0-129">로드 경로 또는 저장 경로의 기본 .NET Framework XAML 서비스 구현에서 XAML 처리 작업이 서비스 컨텍스트에 필요한 관련 태그 확장 또는 형식 변환기 메서드를 호출할 때마다 이 내부 개체가 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-129">Whenever a XAML processing operation in the default .NET Framework XAML Services implementations of load path or save path invokes the relevant markup extension or type converter methods that require a service context, this internal object is passed.</span></span> <span data-ttu-id="158d0-130">상황에 따라 시스템 서비스 컨텍스트는 `MarkupExtensionContext` 또는 `TextSyntaxContext`를 제공하지만 이들 두 클래스의 고유 정보는 내부용입니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-130">Depending on the circumstance, the system service context provides either `MarkupExtensionContext` or `TextSyntaxContext`, but the specifics of both of these classes are internal.</span></span> <span data-ttu-id="158d0-131">이들 클래스와의 상호 작용은 <xref:System.IServiceProvider.GetService%2A>를 통해 클래스에서 서비스를 요청하는 것으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-131">Your interaction with these classes is limited to requesting services from them, through <xref:System.IServiceProvider.GetService%2A>.</span></span>  
  
<a name="available_systemxaml_services"></a>   
## <a name="available-services-from-the-net-framework-xaml-service-context"></a><span data-ttu-id="158d0-132">.NET Framework XAML 서비스 컨텍스트에서 사용 가능한 서비스</span><span class="sxs-lookup"><span data-stu-id="158d0-132">Available Services from the .NET Framework XAML Service Context</span></span>  
 <span data-ttu-id="158d0-133">.NET Framework XAML 서비스에서는 태그 확장, 형식 변환기, 값 serializer 및 잠재적으로 기타 사용에 대한 서비스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-133">.NET Framework XAML Services defines services for markup extensions, type converters, value serializers, and potentially other usages.</span></span> <span data-ttu-id="158d0-134">다음 섹션에서는 이들 서비스를 각각 설명하고 서비스가 구현에서 사용하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-134">The following sections describe each of these services and provide guidance about how the service might be used in an implementation.</span></span>  
  
### <a name="iserviceprovider"></a><span data-ttu-id="158d0-135">IServiceProvider</span><span class="sxs-lookup"><span data-stu-id="158d0-135">IServiceProvider</span></span>  
 <span data-ttu-id="158d0-136">**참조 설명서**: <xref:System.IServiceProvider></span><span class="sxs-lookup"><span data-stu-id="158d0-136">**Reference documentation**: <xref:System.IServiceProvider></span></span>  
  
 <span data-ttu-id="158d0-137">**와 관련 된:** .NET Framework에 있는 서비스 기반 인프라의 기본적인 작업을 호출할 수 있도록 <xref:System.IServiceProvider.GetService%2A?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-137">**Relevant to:** Basic operation of a service-based infrastructure in the .NET Framework so that you can call <xref:System.IServiceProvider.GetService%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="itypedescriptorcontext"></a><span data-ttu-id="158d0-138">ITypeDescriptorContext</span><span class="sxs-lookup"><span data-stu-id="158d0-138">ITypeDescriptorContext</span></span>  
 <span data-ttu-id="158d0-139">**참조 설명서**: <xref:System.ComponentModel.ITypeDescriptorContext></span><span class="sxs-lookup"><span data-stu-id="158d0-139">**Reference documentation**: <xref:System.ComponentModel.ITypeDescriptorContext></span></span>  
  
 <span data-ttu-id="158d0-140"><xref:System.IServiceProvider>에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-140">Derives from <xref:System.IServiceProvider>.</span></span> <span data-ttu-id="158d0-141">이 클래스는 표준 <xref:System.ComponentModel.TypeConverter> 서명, <xref:System.ComponentModel.TypeConverter> 의 컨텍스트가 .NET Framework 1.0부터 있었던 클래스임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-141">This class represents context in the standard <xref:System.ComponentModel.TypeConverter> signatures; <xref:System.ComponentModel.TypeConverter> is a class that has existed since .NET Framework 1.0.</span></span> <span data-ttu-id="158d0-142">이 클래스는 문자열-값 형식 변환을 위한 XAML 및 XAML <xref:System.ComponentModel.TypeConverter> 시나리오보다 오래되었습니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-142">It predates XAML and the XAML <xref:System.ComponentModel.TypeConverter> scenario for string-value type conversion.</span></span> <span data-ttu-id="158d0-143">.NET Framework XAML 서비스 컨텍스트에서 <xref:System.ComponentModel.TypeConverter> 의 메서드는 명시적으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-143">In the .NET Framework XAML Services context, methods of <xref:System.ComponentModel.TypeConverter> are implemented explicitly.</span></span> <span data-ttu-id="158d0-144">명시적 구현의 동작은 호출자에게 <xref:System.ComponentModel.ITypeDescriptorContext> API가 XAML 형식 시스템과 관련되거나 XAML에서 개체 읽기 또는 쓰기와 관련되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-144">The explicit implementation's behavior indicates to callers that the <xref:System.ComponentModel.ITypeDescriptorContext> API is not relevant for XAML type systems, or for reading or writing objects from XAML.</span></span> <span data-ttu-id="158d0-145"><xref:System.ComponentModel.ITypeDescriptorContext.Container%2A>, <xref:System.ComponentModel.ITypeDescriptorContext.Instance%2A>, 및 <xref:System.ComponentModel.ITypeDescriptorContext.PropertyDescriptor%2A> 는 일반적으로 .NET Framework XAML 서비스 컨텍스트에서 `null` 을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-145"><xref:System.ComponentModel.ITypeDescriptorContext.Container%2A>, <xref:System.ComponentModel.ITypeDescriptorContext.Instance%2A>, and <xref:System.ComponentModel.ITypeDescriptorContext.PropertyDescriptor%2A> generally return `null` from .NET Framework XAML Services contexts.</span></span>  
  
### <a name="ivalueserializercontext"></a><span data-ttu-id="158d0-146">IValueSerializerContext</span><span class="sxs-lookup"><span data-stu-id="158d0-146">IValueSerializerContext</span></span>  
 <span data-ttu-id="158d0-147">**참조 설명서**: <xref:System.Windows.Markup.IValueSerializerContext></span><span class="sxs-lookup"><span data-stu-id="158d0-147">**Reference documentation**: <xref:System.Windows.Markup.IValueSerializerContext></span></span>  
  
 <span data-ttu-id="158d0-148"><xref:System.ComponentModel.ITypeDescriptorContext> 에서 파생되고 명시적 구현을 사용하여 XAML 형식 시스템에 대한 거짓 의미를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-148">Derives from <xref:System.ComponentModel.ITypeDescriptorContext> and also relies on explicit implementations to suppress false implications about the XAML type system.</span></span> <span data-ttu-id="158d0-149"><xref:System.Windows.Markup.ValueSerializer>에서 정적 조회 도우미 메서드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-149">Supports the static lookup helper methods on <xref:System.Windows.Markup.ValueSerializer>.</span></span>  
  
### <a name="ixamltyperesolver"></a><span data-ttu-id="158d0-150">IXamlTypeResolver</span><span class="sxs-lookup"><span data-stu-id="158d0-150">IXamlTypeResolver</span></span>  
 <span data-ttu-id="158d0-151">**참조 설명서**: <xref:System.Windows.Markup.IXamlTypeResolver></span><span class="sxs-lookup"><span data-stu-id="158d0-151">**Reference documentation**: <xref:System.Windows.Markup.IXamlTypeResolver></span></span>  
  
 <span data-ttu-id="158d0-152">**정의 방법:**  <xref:System.Windows.Markup> 네임스페이스, System.Xaml 어셈블리</span><span class="sxs-lookup"><span data-stu-id="158d0-152">**Defined by:**  <xref:System.Windows.Markup> namespace, System.Xaml assembly</span></span>  
  
 <span data-ttu-id="158d0-153">**관련 항목:** 로드 경로 시나리오 및 XAML 스키마 컨텍스트와의 상호 작용</span><span class="sxs-lookup"><span data-stu-id="158d0-153">**Relevant to:** Load path scenarios, and interaction with XAML schema context</span></span>  
  
 <span data-ttu-id="158d0-154">**서비스 API:**  <xref:System.Windows.Markup.IXamlTypeResolver.Resolve%2A></span><span class="sxs-lookup"><span data-stu-id="158d0-154">**Service API:**  <xref:System.Windows.Markup.IXamlTypeResolver.Resolve%2A></span></span>  
  
 <span data-ttu-id="158d0-155">XAML 작성기가 개체 그래프에서 CLR 개체를 생성할 때 필요한 XAML-CLR 형식 매핑에 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-155">Can influence the XAML-to-CLR type mapping that is necessary when the XAML writer constructs a CLR object in an object graph.</span></span> <span data-ttu-id="158d0-156"><xref:System.Windows.Markup.IXamlTypeResolver.Resolve%2A>는 XAML 형식 이름(<xref:System.Xaml.XamlType.Name%2A?displayProperty=nameWithType>)에 해당하는 잠재적으로 접두사로 한정된 문자열을 처리하고 CLR <xref:System.Type>을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-156"><xref:System.Windows.Markup.IXamlTypeResolver.Resolve%2A> processes a potentially prefix-qualified string that corresponds to a XAML type name (<xref:System.Xaml.XamlType.Name%2A?displayProperty=nameWithType>), and returns a CLR <xref:System.Type>.</span></span> <span data-ttu-id="158d0-157">형식 확인은 일반적으로 XAML 스키마 컨텍스트에 따라 크게 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-157">Resolving types is typically heavily dependent on XAML schema context.</span></span> <span data-ttu-id="158d0-158">XAML 스키마 컨텍스트는 어떤 어셈블리가 로드되는지, 그리고 형식 확인을 위해 어떤 어셈블리에 액세스할 수 있거나 액세스해야 하는지 등의 고려 사항만 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-158">Only the XAML schema context is aware of considerations such as which assemblies are loaded, and which of these assemblies can or should be accessed for type resolution.</span></span>  
  
### <a name="iuricontext"></a><span data-ttu-id="158d0-159">IUriContext</span><span class="sxs-lookup"><span data-stu-id="158d0-159">IUriContext</span></span>  
 <span data-ttu-id="158d0-160">**참조 설명서**: <xref:System.Windows.Markup.IUriContext></span><span class="sxs-lookup"><span data-stu-id="158d0-160">**Reference documentation**: <xref:System.Windows.Markup.IUriContext></span></span>  
  
 <span data-ttu-id="158d0-161">**정의 방법:**  <xref:System.Windows.Markup> 네임스페이스, System.Xaml 어셈블리</span><span class="sxs-lookup"><span data-stu-id="158d0-161">**Defined by:**  <xref:System.Windows.Markup> namespace, System.Xaml assembly</span></span>  
  
 <span data-ttu-id="158d0-162">**관련 항목:** URI이거나 `x:Uri` 값인 멤버 값의 로드 경로 및 저장 경로 처리.</span><span class="sxs-lookup"><span data-stu-id="158d0-162">**Relevant to:** Load path and save path handling of member values that are URIs or `x:Uri` values.</span></span>  
  
 <span data-ttu-id="158d0-163">**서비스 API:**  <xref:System.Windows.Markup.IUriContext.BaseUri%2A></span><span class="sxs-lookup"><span data-stu-id="158d0-163">**Service API:**  <xref:System.Windows.Markup.IUriContext.BaseUri%2A></span></span>  
  
 <span data-ttu-id="158d0-164">이 서비스에서는 전체적으로 사용 가능한 URI 루트를 보고합니다(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="158d0-164">This service reports a globally available URI root, if any.</span></span> <span data-ttu-id="158d0-165">URI 루트를 사용하여 상대 URI를 절대 URI로 확인하거나 그 반대로 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-165">The URI root can be used to resolve relative URIs to absolute URIs or vice versa.</span></span> <span data-ttu-id="158d0-166">이 시나리오는 주로 특정 프레임워크를 통해 노출되거나 프레임워크에서 자주 사용되는 루트 요소 클래스의 기능을 통해 노출되는 응용 프로그램 서비스와 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-166">This scenario is mainly relevant to application services that are exposed by a particular framework, or capabilities of a frequently used root element class in a framework.</span></span> <span data-ttu-id="158d0-167">기본 URI는 XAML 판독기 설정으로 설정될 수 있고, 이후 이 URL은 XAML 개체 작성기에 전달되고 이 서비스에 의해 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-167">The base URI can be established as a XAML reader setting, which is then passed through to the XAML object writer and reported by this service.</span></span>  
  
### <a name="iambientprovider"></a><span data-ttu-id="158d0-168">IAmbientProvider</span><span class="sxs-lookup"><span data-stu-id="158d0-168">IAmbientProvider</span></span>  
 <span data-ttu-id="158d0-169">**참조 설명서**: <xref:System.Xaml.IAmbientProvider></span><span class="sxs-lookup"><span data-stu-id="158d0-169">**Reference documentation**: <xref:System.Xaml.IAmbientProvider></span></span>  
  
 <span data-ttu-id="158d0-170">**정의 방법:**  <xref:System.Xaml> 네임스페이스, System.Xaml 어셈블리</span><span class="sxs-lookup"><span data-stu-id="158d0-170">**Defined by:**  <xref:System.Xaml> namespace, System.Xaml assembly</span></span>  
  
 <span data-ttu-id="158d0-171">**관련 항목:** 로드 경로 처리 및 형식 조회 지연 또는 최적화.</span><span class="sxs-lookup"><span data-stu-id="158d0-171">**Relevant to:** Load path handling and type lookup deferrals or optimizations.</span></span>  
  
 <span data-ttu-id="158d0-172">**서비스 APIs:**  <xref:System.Xaml.IAmbientProvider.GetAllAmbientValues%2A>, 기타 3개.</span><span class="sxs-lookup"><span data-stu-id="158d0-172">**Service APIs:**  <xref:System.Xaml.IAmbientProvider.GetAllAmbientValues%2A>, 3 others.</span></span>  
  
 <span data-ttu-id="158d0-173">XAML의 외계 개념은 형식의 특정 멤버를 앰비언트로 표시하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-173">The ambience concept in XAML is a technique for marking a particular member of a type as ambient.</span></span> <span data-ttu-id="158d0-174">또는 형식 인스턴스를 포함하는 모든 속성 값을 앰비언트 속성으로 간주하도록 형식이 앰비언트일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-174">Alternatively, a type can be ambient so that all property values that hold an instance of the type should be considered ambient properties.</span></span> <span data-ttu-id="158d0-175">추가로 XAML 노드 스트림을 따라가고 개체 그래프에서 하위 항목인 태그 확장 또는 형식 변환기는 로드 시 앰비언트 속성 또는 형식 인스턴스에 액세스할 수 있거나 저장 시 앰비언트 구조의 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-175">Markup extensions or type converters that are further along the XAML node stream and that are descendants in the object graph can access the ambient property or type instance at load time; or they can use knowledge of the ambient structure at save time.</span></span> <span data-ttu-id="158d0-176">이는 <xref:System.Windows.Markup.IXamlTypeResolver> 또는 `x:Type`과 같은 다른 서비스에 대한 형식을 확인하는 데 필요한 한정 정도에 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-176">This can affect the degree of qualification that is needed to resolve types for other services, such as for <xref:System.Windows.Markup.IXamlTypeResolver> or for `x:Type`.</span></span> <span data-ttu-id="158d0-177"><xref:System.Xaml.AmbientPropertyValue>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="158d0-177">See also <xref:System.Xaml.AmbientPropertyValue>.</span></span>  
  
### <a name="ixamlschemacontextprovider"></a><span data-ttu-id="158d0-178">IXamlSchemaContextProvider</span><span class="sxs-lookup"><span data-stu-id="158d0-178">IXamlSchemaContextProvider</span></span>  
 <span data-ttu-id="158d0-179">**참조 설명서**: <xref:System.Xaml.IXamlSchemaContextProvider></span><span class="sxs-lookup"><span data-stu-id="158d0-179">**Reference documentation**: <xref:System.Xaml.IXamlSchemaContextProvider></span></span>  
  
 <span data-ttu-id="158d0-180">**정의 방법:**  <xref:System.Xaml> 네임스페이스, System.Xaml 어셈블리</span><span class="sxs-lookup"><span data-stu-id="158d0-180">**Defined by:**  <xref:System.Xaml> namespace, System.Xaml assembly</span></span>  
  
 <span data-ttu-id="158d0-181">**관련 항목:** 로드 경로 및 XAML 형식을 지원 형식으로 확인해야 하는 모든 작업.</span><span class="sxs-lookup"><span data-stu-id="158d0-181">**Relevant to:** Load path, and any operation that must resolve a XAML type to a backing type.</span></span>  
  
 <span data-ttu-id="158d0-182">**서비스 API:**  <xref:System.Xaml.IXamlSchemaContextProvider.SchemaContext%2A></span><span class="sxs-lookup"><span data-stu-id="158d0-182">**Service API:**  <xref:System.Xaml.IXamlSchemaContextProvider.SchemaContext%2A></span></span>  
  
 <span data-ttu-id="158d0-183">지연된 콘텐츠를 통합하기 위해 지연된 영역에서 같은 스키마 컨텍스트가 작동해야 하므로 XAML 스키마 컨텍스트는 모든 지연 로드 작업에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-183">XAML schema context is necessary for any defer load operations, because the same schema context must act on the deferred area in order to integrate the deferred content.</span></span> <span data-ttu-id="158d0-184">XAML 스키마 컨텍스트 역할에 대한 자세한 내용은 [XAML Services](../../../docs/framework/xaml-services/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="158d0-184">For more information about the role of the XAML schema context, see [XAML Services](../../../docs/framework/xaml-services/index.md).</span></span>  
  
### <a name="irootobjectprovider"></a><span data-ttu-id="158d0-185">IRootObjectProvider</span><span class="sxs-lookup"><span data-stu-id="158d0-185">IRootObjectProvider</span></span>  
 <span data-ttu-id="158d0-186">**참조 설명서**: <xref:System.Xaml.IRootObjectProvider></span><span class="sxs-lookup"><span data-stu-id="158d0-186">**Reference documentation**: <xref:System.Xaml.IRootObjectProvider></span></span>  
  
 <span data-ttu-id="158d0-187">**정의 방법:**  <xref:System.Xaml> 네임스페이스, System.Xaml 어셈블리</span><span class="sxs-lookup"><span data-stu-id="158d0-187">**Defined by:**  <xref:System.Xaml> namespace, System.Xaml assembly</span></span>  
  
 <span data-ttu-id="158d0-188">**관련 항목:** 로드 경로.</span><span class="sxs-lookup"><span data-stu-id="158d0-188">**Relevant to:** Load path.</span></span>  
  
 <span data-ttu-id="158d0-189">**서비스 API:**  <xref:System.Xaml.IRootObjectProvider.RootObject%2A></span><span class="sxs-lookup"><span data-stu-id="158d0-189">**Service API:**  <xref:System.Xaml.IRootObjectProvider.RootObject%2A></span></span>  
  
 <span data-ttu-id="158d0-190">서비스는 특정 프레임워크를 통해 노출되거나 프레임워크에서 자주 사용되는 루트 요소 클래스의 기능을 통해 노출되는 응용 프로그램 서비스와 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-190">The service is relevant to application services that are exposed by a particular framework or by capabilities of a frequently used root element class in a framework.</span></span> <span data-ttu-id="158d0-191">루트 개체를 가져오기 위한 한 가지 시나리오는 코드 숨김 및 이벤트 배선을 연결하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-191">One scenario for obtaining the root object is connecting code-behind and event wiring.</span></span> <span data-ttu-id="158d0-192">예를 들어 `x:Class` 의 WPF 구현은 XAML 태그의 다른 위치에 있는 모든 이벤트 처리기 특성의 태그 컴파일 및 배선에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-192">For example, the WPF implementation of `x:Class` is used for markup compile and wiring of any event handler attribute that is found at any other position in the XAML markup.</span></span> <span data-ttu-id="158d0-193">태그 연결 지점 및 태그 컴파일에 대한 코드 숨김 정의 부분 클래스는 루트 요소에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-193">The connection point of markup and code-behind defined partial classes for markup compile is at the root element.</span></span>  
  
### <a name="ixamlnamespaceresolver"></a><span data-ttu-id="158d0-194">IXamlNamespaceResolver</span><span class="sxs-lookup"><span data-stu-id="158d0-194">IXamlNamespaceResolver</span></span>  
 <span data-ttu-id="158d0-195">**참조 설명서**: <xref:System.Xaml.IXamlNamespaceResolver></span><span class="sxs-lookup"><span data-stu-id="158d0-195">**Reference documentation**: <xref:System.Xaml.IXamlNamespaceResolver></span></span>  
  
 <span data-ttu-id="158d0-196">**정의 방법:**  <xref:System.Xaml> 네임스페이스, System.Xaml 어셈블리</span><span class="sxs-lookup"><span data-stu-id="158d0-196">**Defined by:**  <xref:System.Xaml> namespace, System.Xaml assembly</span></span>  
  
 <span data-ttu-id="158d0-197">**관련 항목:** 로드 경로, 저장 경로.</span><span class="sxs-lookup"><span data-stu-id="158d0-197">**Relevant to:** Load path, save path.</span></span>  
  
 <span data-ttu-id="158d0-198">**서비스 API:** <xref:System.Xaml.IXamlNamespaceResolver.GetNamespace%2A> , 저장 경로에 대한 <xref:System.Xaml.IXamlNamespaceResolver.GetNamespacePrefixes%2A> .</span><span class="sxs-lookup"><span data-stu-id="158d0-198">**Service API:** <xref:System.Xaml.IXamlNamespaceResolver.GetNamespace%2A> for load path, <xref:System.Xaml.IXamlNamespaceResolver.GetNamespacePrefixes%2A> for save path.</span></span>  
  
 <span data-ttu-id="158d0-199"><xref:System.Xaml.IXamlNamespaceResolver> 는 원래 XAML 태그에 매핑된 대로 접두사에 따라 XAML 네임스페이스 식별자/URI를 반환할 수 있는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-199"><xref:System.Xaml.IXamlNamespaceResolver> is a service that can return a XAML namespace identifier / URI based on its prefix as mapped in the originating XAML markup.</span></span>  
  
### <a name="iprovidevaluetarget"></a><span data-ttu-id="158d0-200">IProvideValueTarget</span><span class="sxs-lookup"><span data-stu-id="158d0-200">IProvideValueTarget</span></span>  
 <span data-ttu-id="158d0-201">**참조 설명서**: <xref:System.Windows.Markup.IProvideValueTarget></span><span class="sxs-lookup"><span data-stu-id="158d0-201">**Reference documentation**: <xref:System.Windows.Markup.IProvideValueTarget></span></span>  
  
 <span data-ttu-id="158d0-202">**정의 방법:**  <xref:System.Windows.Markup> 네임스페이스, System.Xaml 어셈블리</span><span class="sxs-lookup"><span data-stu-id="158d0-202">**Defined by:**  <xref:System.Windows.Markup> namespace, System.Xaml assembly</span></span>  
  
 <span data-ttu-id="158d0-203">**관련 항목:** 로드 경로 및 저장 경로.</span><span class="sxs-lookup"><span data-stu-id="158d0-203">**Relevant to:** Load path and save path.</span></span>  
  
 <span data-ttu-id="158d0-204">**서비스 API:**  <xref:System.Windows.Markup.IProvideValueTarget.TargetObject%2A>, <xref:System.Windows.Markup.IProvideValueTarget.TargetProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="158d0-204">**Service APIs:**  <xref:System.Windows.Markup.IProvideValueTarget.TargetObject%2A>, <xref:System.Windows.Markup.IProvideValueTarget.TargetProperty%2A>.</span></span>  
  
 <span data-ttu-id="158d0-205"><xref:System.Windows.Markup.IProvideValueTarget> 을 사용하면 형식 변환기 또는 태그 확장이 로드 시 작동할 위치에 대한 컨텍스트를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-205"><xref:System.Windows.Markup.IProvideValueTarget> enables a type converter or markup extension to obtain context about where it is acting at load time.</span></span> <span data-ttu-id="158d0-206">구현에서 이 컨텍스트를 사용하여 사용을 무효화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-206">Implementations might use this context to invalidate a usage.</span></span> <span data-ttu-id="158d0-207">예를 들어 WPF에는 몇몇 태그 확장 내부에 <xref:System.Windows.DynamicResourceExtension>과 같은 논리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-207">For example, WPF has logic inside some of its markup extensions such as <xref:System.Windows.DynamicResourceExtension>.</span></span> <span data-ttu-id="158d0-208">이 논리에서는 <xref:System.Windows.Markup.IProvideValueTarget.TargetProperty%2A> 를 확인하여 확장이 종속성 속성을 설정하거나 기타 비종속성 속성의 짧은 목록을 설정하는 데만 사용되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-208">The logic checks the <xref:System.Windows.Markup.IProvideValueTarget.TargetProperty%2A> to make sure that the extension is only used to set dependency properties (or a short list of other non-dependency properties).</span></span>  
  
### <a name="ixamlnameresolver"></a><span data-ttu-id="158d0-209">IXamlNameResolver</span><span class="sxs-lookup"><span data-stu-id="158d0-209">IXamlNameResolver</span></span>  
 <span data-ttu-id="158d0-210">**참조 설명서**: <xref:System.Xaml.IXamlNameResolver></span><span class="sxs-lookup"><span data-stu-id="158d0-210">**Reference documentation**: <xref:System.Xaml.IXamlNameResolver></span></span>  
  
 <span data-ttu-id="158d0-211">**정의 방법:**  <xref:System.Xaml> 네임스페이스, System.Xaml 어셈블리</span><span class="sxs-lookup"><span data-stu-id="158d0-211">**Defined by:**  <xref:System.Xaml> namespace, System.Xaml assembly</span></span>  
  
 <span data-ttu-id="158d0-212">**관련 항목:** 로드 경로 개체 그래프 정의, `x:Name`으로 식별된 개체 확인, `x:Reference`또는 프레임워크 관련 방법.</span><span class="sxs-lookup"><span data-stu-id="158d0-212">**Relevant to:** Load path object graph definition, resolving objects identified by `x:Name`, `x:Reference`, or framework-specific techniques.</span></span>  
  
 <span data-ttu-id="158d0-213">**서비스 API:**  <xref:System.Xaml.IXamlNameResolver.Resolve%2A>, 전방 참조 처리와 같은 더 고급 시나리오를 위한 기타 API.</span><span class="sxs-lookup"><span data-stu-id="158d0-213">**Service APIs:**  <xref:System.Xaml.IXamlNameResolver.Resolve%2A>; other APIs for more advanced scenarios such as dealing with forward references.</span></span>  
  
 <span data-ttu-id="158d0-214">`x:Reference` 처리의 .NET Framework XAML 서비스 구현에는 이 서비스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-214">The .NET Framework XAML Services implementation of `x:Reference` handling relies on this service.</span></span> <span data-ttu-id="158d0-215">프레임워크를 지원하는 특정 프레임워크 또는 도구는 `x:Name` 처리나 동등한 항목(<xref:System.Windows.Markup.RuntimeNamePropertyAttribute> 특성 사용) 속성 처리에 이 서비스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="158d0-215">Specific frameworks or tools that support the framework use this service for `x:Name` handling or equivalent (<xref:System.Windows.Markup.RuntimeNamePropertyAttribute> attributed) property handling.</span></span>  
  
### <a name="idestinationtypeprovider"></a><span data-ttu-id="158d0-216">IDestinationTypeProvider</span><span class="sxs-lookup"><span data-stu-id="158d0-216">IDestinationTypeProvider</span></span>  
 <span data-ttu-id="158d0-217">**참조 설명서**: <xref:System.Xaml.IDestinationTypeProvider></span><span class="sxs-lookup"><span data-stu-id="158d0-217">**Reference documentation**: <xref:System.Xaml.IDestinationTypeProvider></span></span>  
  
 <span data-ttu-id="158d0-218">**정의 방법:**  <xref:System.Xaml> 네임스페이스, System.Xaml 어셈블리</span><span class="sxs-lookup"><span data-stu-id="158d0-218">**Defined by:**  <xref:System.Xaml> namespace, System.Xaml assembly</span></span>  
  
 <span data-ttu-id="158d0-219">**관련 항목:** 간접 CLR 형식 정보의 로드 경로 확인.</span><span class="sxs-lookup"><span data-stu-id="158d0-219">**Relevant to:** Load path resolution of indirect CLR type information.</span></span>  
  
 <span data-ttu-id="158d0-220">**서비스 API:** <xref:System.Xaml.IDestinationTypeProvider.GetDestinationType%2A></span><span class="sxs-lookup"><span data-stu-id="158d0-220">**Service API:** <xref:System.Xaml.IDestinationTypeProvider.GetDestinationType%2A></span></span>  
  
 <span data-ttu-id="158d0-221">자세한 내용은 <xref:System.Xaml.IDestinationTypeProvider>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="158d0-221">For more information, see <xref:System.Xaml.IDestinationTypeProvider>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="158d0-222">참고 항목</span><span class="sxs-lookup"><span data-stu-id="158d0-222">See Also</span></span>  
 <xref:System.Windows.Markup.MarkupExtension>  
 <xref:System.Xaml.XamlObjectWriter>  
 [<span data-ttu-id="158d0-223">XAML 태그 확장명 개요</span><span class="sxs-lookup"><span data-stu-id="158d0-223">Markup Extensions for XAML Overview</span></span>](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md)  
 [<span data-ttu-id="158d0-224">XAML을 위한 형식 변환기 개요</span><span class="sxs-lookup"><span data-stu-id="158d0-224">Type Converters for XAML Overview</span></span>](../../../docs/framework/xaml-services/type-converters-for-xaml-overview.md)
