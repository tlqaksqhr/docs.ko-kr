---
title: WPF에서 System.Xaml로 마이그레이션된 형식
ms.date: 03/30/2017
helpviewer_keywords:
- WPF XAML [XAML Services], migration to System.Xaml
- XAML [XAML Services], System.Xaml and WPF
- System.Xaml [XAML Services], types migrated from WPF
ms.assetid: d79dabf5-a2ec-4e8d-a37a-67c4ba8a2b91
ms.openlocfilehash: d59ff8657f7750db8908aac15936f12838b27eaf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565836"
---
# <a name="types-migrated-from-wpf-to-systemxaml"></a>WPF에서 System.Xaml로 마이그레이션된 형식
[!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)] 및 [!INCLUDE[net_v30_long](../../../includes/net-v30-long-md.md)]모두 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] Windows Workflow Foundation XAML 언어 구현이 포함 합니다. WPF XAML 구현에 대해 확장성을 제공한 공용 형식은 대부분 WindowsBase, PresentationCore 및 PresentationFramework 어셈블리에 있었습니다. 마찬가지로, Windows Workflow Foundation XAML에 대 한 확장성을 제공한 공용 형식은 System.Workflow.ComponentModel 어셈블리에 존재 합니다. [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]에서는 XAML 관련 형식 중 일부가 System.Xaml 어셈블리로 마이그레이션되었습니다. XAML 언어 서비스의 공용 .NET Framework 구현은 원래 특정 프레임워크의 XAML 구현에서 정의되었지만 현재 전반적인 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] XAML 언어 지원의 일부인 많은 XAML 확장성 시나리오를 사용할 수 있게 합니다. 이 항목에서는 마이그레이션되는 형식을 나열하고 마이그레이션과 관련된 문제를 논의합니다.  
  
<a name="assemblies_and_namespaces"></a>   
## <a name="assemblies-and-namespaces"></a>어셈블리 및 네임스페이스  
 [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] 및 [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)]에서는 XAML을 지원하기 위해 WPF에서 구현한 형식이 일반적으로 <xref:System.Windows.Markup> 네임스페이스에 있었습니다. 이러한 형식은 대부분 WindowsBase 어셈블리에 있었습니다.  
  
 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]에서는 새로운 <xref:System.Xaml> 네임스페이스와 새로운 System.Xaml 어셈블리가 있습니다. 원래 WPF XAML에 대해 구현된 많은 형식이 이제 XAML 구현에 대한 확장성 지점 또는 서비스로 제공됩니다. 보다 일반적인 시나리오에 사용할 수 있도록 하는 작업의 일부로 원래의 WPF 어셈블리에서 System.Xaml 어셈블리로 형식이 전달됩니다. 이렇게 하면 WPF 및 Windows Workflow Foundation) (등 다른 프레임 워크의 어셈블리를 포함 하지 않고 XAML 확장성 시나리오.  
  
 마이그레이션된 형식의 경우 대부분의 형식이 <xref:System.Windows.Markup> 네임스페이스에 계속 유지됩니다. 이는 부분적으로 기존 구현의 CLR 네임스페이스 매핑이 파일별로 분할되지 않도록 하기 위한 것이었습니다. 결과적으로, <xref:System.Windows.Markup> 의 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 네임스페이스에 System.Xaml 어셈블리의 일반 XAML 언어 지원 형식과 WindowsBase 및 기타 WPF 어셈블리의 WPF XAML 구현과 관련된 형식이 혼합되어 포함됩니다. System.Xaml로 마이그레이션되었지만 이전에 WPF 어셈블리에 있었던 형식은 WPF 어셈블리의 버전 4에서 형식 전달을 지원합니다.  
  
### <a name="workflow-xaml-support-types"></a>워크플로 XAML 지원 형식  
 Windows Workflow Foundation XAML 지원 형식을 제공 하 고 대부분의 경우에 해당 하는 WPF 항목과 동일한 짧은 이름을 가졌습니다. 다음은 Windows Workflow Foundation XAML 지원 형식의 목록입니다.  
  
-   <xref:System.Workflow.ComponentModel.Serialization.ContentPropertyAttribute>  
  
-   <xref:System.Workflow.ComponentModel.Serialization.RuntimeNamePropertyAttribute>  
  
-   <xref:System.Workflow.ComponentModel.Serialization.XmlnsPrefixAttribute>  
  
 이러한 지원 형식에 대 한 Windows Workflow Foundation 어셈블리에 여전히 존재 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 특정 Windows Workflow Foundation 응용 프로그램에 계속 사용할 수 있습니다; 그러나 해야 참조 됩니다 응용 프로그램 또는 사용 하지 않는 프레임 워크에서 Windows Workflow Foundation 합니다.  
  
<a name="markupextension"></a>   
## <a name="markupextension"></a>MarkupExtension  
 [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] 및 [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)]에서는 WPF용 <xref:System.Windows.Markup.MarkupExtension> 클래스가 WindowsBase 어셈블리에 있었습니다. Windows Workflow Foundation에 대 한 병렬 클래스 <xref:System.Workflow.ComponentModel.Serialization.MarkupExtension>System.Workflow.ComponentModel 어셈블리에 있었습니다. [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]에서는 <xref:System.Windows.Markup.MarkupExtension> 클래스가 System.Xaml 어셈블리로 마이그레이션되었습니다. [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]에서는 <xref:System.Windows.Markup.MarkupExtension> 이 특정 프레임워크에서 빌드된 시나리오가 아니라 .NET Framework XAML 서비스를 사용하는 모든 XAML 확장성 시나리오에 사용됩니다. 가능한 경우 특정 프레임워크 또는 프레임워크의 사용자 코드도 XAML 확장에 대한 <xref:System.Windows.Markup.MarkupExtension> 클래스에서 빌드되어야 합니다.  
  
<a name="markupextension_supporting_service_classes"></a>   
## <a name="markupextension-supporting-service-classes"></a>MarkupExtension 지원 서비스 클래스  
 WPF용[!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] 및 [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)] 에서는 <xref:System.Windows.Markup.MarkupExtension> implementers 및 <xref:System.ComponentModel.TypeConverter> 구현에서 XAML의 형식/속성 사용을 지원하기 위해 사용할 수 있었던 여러 서비스를 제공했습니다. 이러한 서비스는 다음과 같습니다.  
  
-   <xref:System.Windows.Markup.IProvideValueTarget>  
  
-   <xref:System.Windows.Markup.IUriContext>  
  
-   <xref:System.Windows.Markup.IXamlTypeResolver>  
  
> [!NOTE]
>  태그 확장과 관련된 [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] 의 또 다른 서비스는 <xref:System.Windows.Markup.IReceiveMarkupExtension> 인터페이스입니다. <xref:System.Windows.Markup.IReceiveMarkupExtension> 이 마이그레이션되지 않았으며 `[Obsolete]` 에 대해 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]로 표시됩니다. 이전에 <xref:System.Windows.Markup.IReceiveMarkupExtension> 을 사용한 시나리오에서는 대신 <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute> 특성 콜백을 사용해야 합니다. <xref:System.Windows.Markup.AcceptedMarkupExtensionExpressionTypeAttribute> 도 `[Obsolete]`로 표시됩니다.  
  
<a name="xaml_language_features"></a>   
## <a name="xaml-language-features"></a>XAML 언어 기능  
 WPF용 여러 XAML 언어 기능과 구성 요소는 이전에 PresentationFramework 어셈블리에 있었습니다. 이러한 항목은 XAML 태그로 태그 확장 사용을 노출하는 <xref:System.Windows.Markup.MarkupExtension> 서브클래스로 구현되었습니다. [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]에서는 WPF 어셈블리를 포함하지 않는 프로젝트가 이러한 XAML 언어 수준 기능을 사용할 수 있도록 System.Xaml 어셈블리에 있습니다. WPF는 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 응용 프로그램에 대해서도 동일한 구현을 사용합니다. 이 항목에 나열된 다른 경우와 마찬가지로, 지원 형식은 이전 참조가 손상되지 않도록 계속 <xref:System.Windows.Markup> 네임스페이스에 있습니다.  
  
 다음 표에는 System.Xaml에서 정의되는 XAML 기능 지원 클래스 목록이 포함되어 있습니다.  
  
|XAML 언어 기능|사용량|  
|---------------------------|-----------|  
|<xref:System.Windows.Markup.ArrayExtension>|`<x:Array ...>`|  
|<xref:System.Windows.Markup.NullExtension>|`{x:Null}`|  
|<xref:System.Windows.Markup.StaticExtension>|`{x:Static ...}`|  
|<xref:System.Windows.Markup.TypeExtension>|`{x:Type ...}`|  
  
 System.Xaml에 특정 지원 클래스가 없을 수도 있지만 이제 XAML 언어의 언어 기능 처리를 위한 일반적인 논리가 System.Xaml과 구현된 XAML 판독기 및 XAML 작성기에 상주합니다. 예를 들어 `x:TypeArguments` 는 System.Xaml 구현의 XAML 판독기 및 XAML 작성기에서 처리되는 특성입니다. XAML 노드 스트림에 기록될 수 있고, 기본(CLR 기반) XAML 스키마 컨텍스트 처리가 있으며, XAML 형식 시스템 표현을 포함합니다. 결과적으로, 모든 XAML 언어 수준 기능에 대한 참조 설명서는 3.5 설명서 집합에서와 같이 [고급(Windows Presentation Foundation)](../../../docs/framework/xaml-services/index.md) 의 하위 항목으로 WPF 설명서에 포함되는 대신 [XAML Services](../../../docs/framework/wpf/advanced/index.md) 의 하위 항목 및 .NET Framework 설명서 집합의 일반 영역입니다.  
  
<a name="valueserializer_and_supporting_classes"></a>   
## <a name="valueserializer-and-supporting-classes"></a>ValueSerializer 및 지원 클래스  
 <xref:System.Windows.Markup.ValueSerializer> 클래스는 특히 직렬화 시 출력에 여러 모드 또는 노드가 필요할 수 있는 XAML 직렬화 사례를 위해 문자열로의 형식 변환을 지원합니다. [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] 및 [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)]에서는 WPF용 <xref:System.Windows.Markup.ValueSerializer> 가 WindowsBase 어셈블리에 있었습니다. [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]에서는, <xref:System.Windows.Markup.ValueSerializer> 클래스가 System.Xaml에 있으며 WPF에서 빌드된 시나리오뿐 아니라 모든 XAML 확장성 시나리오에 사용됩니다. <xref:System.Windows.Markup.IValueSerializerContext> (지원 서비스) 및 <xref:System.Windows.Markup.DateTimeValueSerializer> (특정 서브클래스)도 System.Xaml로 마이그레이션됩니다.  
  
<a name="xamlrelated_attributes"></a>   
## <a name="xaml-related-attributes"></a>XAML 관련 특성  
 WPF XAML은 XAML 동작에 대한 특징을 나타내기 위해 CLR 형식에 적용할 수 있는 여러 특성을 포함했습니다. 다음은 [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] 및 [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)]에서 WPF 어셈블리에 있었던 특성 목록입니다. 이러한 특성은 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]에서 System.Xaml로 마이그레이션되었습니다.  
  
-   <xref:System.Windows.Markup.AmbientAttribute>  
  
-   <xref:System.Windows.Markup.ContentPropertyAttribute>  
  
-   <xref:System.Windows.Markup.ContentWrapperAttribute>  
  
-   <xref:System.Windows.Markup.DependsOnAttribute>  
  
-   <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>  
  
-   <xref:System.Windows.Markup.NameScopePropertyAttribute>  
  
-   <xref:System.Windows.Markup.RootNamespaceAttribute>  
  
-   <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>  
  
-   <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>  
  
-   <xref:System.Windows.Markup.ValueSerializerAttribute>  
  
-   <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>  
  
-   <xref:System.Windows.Markup.XmlLangPropertyAttribute>  
  
-   <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>  
  
-   <xref:System.Windows.Markup.XmlnsDefinitionAttribute>  
  
-   <xref:System.Windows.Markup.XmlnsPrefixAttribute>  
  
<a name="miscellaneous_classes"></a>   
## <a name="miscellaneous-classes"></a>기타 클래스  
 <xref:System.Windows.Markup.IComponentConnector> 인터페이스는 [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] 및 [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)]에서는 WindowsBase에 있었지만 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]에서는 System.Xaml에 있습니다. <xref:System.Windows.Markup.IComponentConnector> 는 주로 도구 지원 및 XAML 태그 컴파일러에 사용됩니다.  
  
 <xref:System.Windows.Markup.INameScope> 인터페이스는 [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] 및 [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)]에서는 WindowsBase에 있었지만 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]에서는 System.Xaml에 있습니다. <xref:System.Windows.Markup.INameScope> 는 XAML 네임스페이스에 대한 기본 작업을 정의합니다.  
  
<a name="xamlrelated_classes_with_shared_names_that_exist_in_wpf_and_systemxaml"></a>   
## <a name="xaml-related-classes-with-shared-names-that-exist-in-wpf-and-systemxaml"></a>WPF 및 System.Xaml에 있는 공유 이름의 XAML 관련 클래스  
 다음 클래스는 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]에서 WPF 어셈블리와 System.Xaml 어셈블리 둘 다에 있습니다.  
  
 `XamlReader`  
  
 `XamlWriter`  
  
 `XamlParseException`  
  
 WPF 구현은 <xref:System.Windows.Markup> 네임스페이스 및 PresentationFramework 어셈블리에 있습니다. System.Xaml 구현은 <xref:System.Xaml> 네임스페이스에 있습니다. WPF 형식을 사용하거나 WPF 형식에서 파생하는 경우 일반적으로 System.Xaml 구현 대신 <xref:System.Windows.Markup.XamlReader> 및 <xref:System.Windows.Markup.XamlWriter> 의 WPF 구현을 사용해야 합니다. 자세한 내용은 <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> 및 <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>의 설명을 참조하세요.  
  
 WPF 어셈블리 및 System.Xaml에 대한 참조를 둘 다 포함하고 `include` 및 <xref:System.Windows.Markup> 네임스페이스에 모두 <xref:System.Xaml> 문을 사용하는 경우 형식을 명확하게 확인하기 위해 이러한 API에 대한 호출을 정규화해야 할 수도 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [XAML 서비스](../../../docs/framework/xaml-services/index.md)
