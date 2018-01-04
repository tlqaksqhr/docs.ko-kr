---
title: "WPF에 대한 XAML 및 사용자 지정 클래스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom classes in XAML [WPF]
- XAML [WPF], custom classes
- classes [WPF], custom classes in XAML
ms.assetid: e7313137-581e-4a64-8453-d44e15a6164a
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: da599afc94fba617d4df17c57679d8ee4bb05c61
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="xaml-and-custom-classes-for-wpf"></a>WPF에 대한 XAML 및 사용자 지정 클래스
[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 프레임워크에서 구현된 XAML은 모든 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 언어로 사용자 지정 클래스 또는 구조체를 정의한 다음 XAML 태그를 사용하여 해당 클래스에 액세스하는 기능을 지원합니다. 일반적으로 사용자 지정 형식을 XAML 네임스페이스 접두사에 매핑하여 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 정의 형식과 사용자 지정 형식의 혼합을 동일한 태그 파일에서 함께 사용할 수 있습니다. 이 항목에서는 사용자 지정 클래스를 XAML 요소로 사용 가능하기 위해 만족해야 하는 요구 사항을 설명합니다.  
  
 
  
<a name="Custom_Classes_in_Applications_vs__in_Assemblies"></a>   
## <a name="custom-classes-in-applications-or-assemblies"></a>응용 프로그램 또는 어셈블리의 사용자 지정 클래스  
 XAML에서 사용되는 사용자 지정 클래스는 두 가지 방법으로 정의할 수 있습니다. 즉, 기본 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램을 생성하는 다른 코드 또는 코드 숨김 파일에서 정의하거나, 클래스 라이브러리로 사용되는 DLL 또는 실행 파일과 같은 별도 어셈블리의 클래스로 정의합니다. 각 방법에는 고유한 장점과 단점이 있습니다.  
  
-   클래스 라이브러리를 만드는 경우 사용자 지정 클래스를 서로 다른 여러 응용 프로그램에서 공유할 수 있다는 장점이 있습니다. 또한 별도 라이브러리 응용 프로그램의 버전 관리 문제를 더 쉽게 컨트롤하고 클래스를 XAML 페이지의 루트 요소로 사용하는 클래스를 간단하게 만들 수 있습니다.  
  
-   사용자 지정 클래스를 응용 프로그램에 정의하는 방법은 비교적 간단하며 기본 응용 프로그램 실행 파일이 아닌 별도의 어셈블리를 사용할 때 발생하는 배포 및 테스트 문제를 최소화할 수 있다는 장점이 있습니다.  
  
-   동일한 어셈블리에 정의되어 있는지 다른 어셈블리에 정의되어 있는지에 상관없이, 사용자 지정 클래스를 XAML에서 요소로 사용하려면 CLR 네임스페이스와 XML 네임스페이스 간에 매핑해야 합니다. [WPF XAML을 위한 XAML 네임스페이스 및 네임스페이스 매핑](../../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)을 참조하세요.  
  
<a name="Requirements_for_a_Custom_Class_as_a_XAML_Element"></a>   
## <a name="requirements-for-a-custom-class-as-a-xaml-element"></a>사용자 지정 클래스를 XAML 요소로 사용하기 위한 요구 사항  
 클래스를 개체 요소로 인스턴스화하려면 클래스가 다음 요구 사항을 충족해야 합니다.  
  
-   사용자 지정 클래스가 공용 클래스여야 하고 매개 변수가 없는 기본 공용 생성자를 지원해야 합니다. 구조체에 대한 자세한 내용은 다음 섹션을 참조하세요.  
  
-   사용자 지정 클래스가 중첩 클래스가 아니어야 합니다. 중첩 클래스 및 일반 CLR 사용 구문의 "점"은 연결된 속성과 같은 다른 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및/또는 XAML의 기능을 방해합니다.  
  
 개체 요소 구문을 사용하는 것 외에도 개체 정의에서 해당 개체를 값 형식으로 사용하는 다른 공용 속성에 대해서는 속성 요소 구문을 사용해야 합니다. 그 이유는 이제 개체가 개체 요소로 인스턴스화되어 이러한 속성의 속성 요소 값을 채울 수 있기 때문입니다.  
  
### <a name="structures"></a>구조체  
 사용자 지정 형식으로 정의하는 구조체는 항상 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 XAML로 생성될 수 있어야 합니다. [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 컴파일러에서는 모드 속성 값을 기본값으로 초기화하는 구조체의 기본 생성자를 내재적으로 만들기 때문입니다. 경우에 따라서는 구조체의 기본 생성 동작 및/또는 개체 요소를 사용하는 것이 바람직하지 않습니다. 구조체가 값을 채우고 개념적으로 공용 구조체로 작동하기 때문일 수 있습니다. 이 경우 포함된 값의 해석이 서로 달라서 어느 속성도 설정할 수 없습니다. A [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이러한 구조체의 예는 <xref:System.Windows.GridLength>합니다. 일반적으로 이러한 구조체는 구조체의 값에 대해 서로 다른 해석이나 모드를 만드는 문자열 규칙을 사용하여 값을 특성 형식으로 표현할 수 있도록 형식 변환기를 구현합니다. 이러한 구조체는 기본값이 아닌 생성자를 통해 코드를 생성하는 경우에도 이와 유사한 동작을 노출해야 합니다.  
  
<a name="Requirements_for_Properties_of_a_Custom_Class_as_XAML"></a>   
## <a name="requirements-for-properties-of-a-custom-class-as-xaml-attributes"></a>사용자 지정 클래스의 속성을 XAML 특성으로 사용하기 위한 요구 사항  
 속성이 값 기준 형식(예: 기본 형식)을 참조하거나 XAML 프로세서에서 액세스할 수 있는 기본 생성자나 전용 형식 변환기를 가지고 있는 형식에 대한 클래스를 사용해야 합니다. CLR XAML 구현에서 XAML 프로세서 이러한 변환기를 찾습니다 또는 응용 프로그램의 언어 기본 형식에 대 한 기본 지원을 통해 <xref:System.ComponentModel.TypeConverterAttribute> 유형 또는 멤버에 지원 형식 정의  
  
 또는 속성이 추상 클래스 형식 또는 인터페이스를 참조할 수도 있습니다. 추상 클래스나 인터페이스의 경우에는 XAML 구문 분석 시 해당 인터페이스를 구현하는 실제 클래스 인스턴스로 또는 추상 클래스에서 파생되는 형식의 인스턴스로 속성 값을 채워야 합니다.  
  
 속성을 추상 클래스에서 선언할 수 있지만 해당 속성은 추상 클래스에서 파생되는 실제 클래스에서만 설정될 수 있습니다. 클래스에 대한 개체 요소를 만들려면 클래스에 공용 기본 생성자가 필요하기 때문입니다.  
  
### <a name="typeconverter-enabled-attribute-syntax"></a>TypeConverter 사용 특성 구문  
 클래스 수준에서 전용 특성 사용 형식 변환기를 제공한 경우 적용된 형식 변환을 사용하면 해당 형식을 인스턴스화해야 하는 모든 속성에 특성 구문을 사용할 수 있습니다. 형식 변환기는 해당 형식의 개체 요소를 사용하지 않습니다. 해당 형식에 대한 기본 생성자가 있는 경우에만 개체 요소를 사용할 수 있습니다. 따라서 형식 변환기가 사용하는 속성은 일반적으로 속성 구문에서 사용할 수 없습니다. 단, 형식 자체가 개체 요소 구문도 지원하는 경우는 예외입니다. 한 가지 예외적인 경우로 속성 요소에 문자열을 포함하여 속성 요소 구문을 지정할 수 있습니다. 이는 기본적으로 특성 구문을 사용하는 것과 같지만, 특성 값에 대한 보다 강력한 공백 처리가 필요한 경우가 아니면 일반적이지 않은 방법입니다. 예를 들어 다음은 문자열을 사용하는 속성 요소를 사용하는 방법을 보여 주며 이는 특성을 사용하는 것과 같습니다.  
  
 [!code-xaml[XamlOvwSupport#GoofyTCPE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofytcpe)]  
  
 [!code-xaml[XamlOvwSupport#GoofyTCPE2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofytcpe2)]  
  
 여기서 특성 구문을 사용할 수 있지만 xaml 속성 요소 구문을 개체 요소를 포함 하는 허용 되지 않습니다. 속성의 예로 사용 하는 다양 한 속성의 <xref:System.Windows.Input.Cursor> 유형입니다. <xref:System.Windows.Input.Cursor> 클래스에는 전용된 형식 변환기 <xref:System.Windows.Input.CursorConverter>, 하지만 기본 생성자를 노출 하지 않습니다 하므로 <xref:System.Windows.FrameworkElement.Cursor%2A> 만 속성 특성 구문을 통해도 실제 <xref:System.Windows.Input.Cursor> 형식은 참조 형식입니다.  
  
### <a name="per-property-type-converters"></a>속성별 형식 변환기  
 또는 속성 자체가 속성 수준에서 형식 변환기를 선언할 수도 있습니다. 이렇게 하면 "미니 language"에 대 한 입력으로 특성의 들어오는 문자열 값을 처리 하 여 속성 인라인 유형의 개체를 인스턴스화하는 <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> 적절 한 형식에 따라 작업입니다. 일반적으로 이 작업은 XAML에서 속성을 설정할 수 있는 유일한 방법이 아니라 편리한 접근자를 제공하기 위해 수행합니다. 그러나 기본 생성자나 특성 사용 형식 변환기를 제공하지 않는 기존 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 형식을 사용하려는 특성에 대해서도 형식 변환기를 사용할 수도 있습니다. 예제는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] API를 사용 하는 특정 속성은는 <xref:System.Globalization.CultureInfo> 유형입니다. 이 경우 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기존 사용 [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] <xref:System.Globalization.CultureInfo> 이전 버전의 프레임 워크에서 사용 되었던 호환성 및 마이그레이션 시나리오를 해결 하기 위해 형식 이지만 <xref:System.Globalization.CultureInfo> 형식은 필요한 생성자를 지원 하지 않습니다 또는 형식 수준의 직접 XAML 속성 값으로 사용할 수 있도록 하려면 형식 변환 합니다.  
  
 따라서 컨트롤 작성자는 XAML을 사용하는 속성을 노출할 때마다 해당 속성에 종속성 속성을 지원하는 방법을 고려해야 합니다. 기존 사용 하는 경우에 특히 그렇습니다 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] XAML 프로세서의 구현을 사용 하 여 성능을 향상 시킬 수 있습니다 때문에 <xref:System.Windows.DependencyProperty> 백업 합니다. 종속성 속성은 XAML 액세스 가능 속성이 제공할 것으로 예상되는 속성 시스템의 기능을 노출합니다. 이러한 기능에는 애니메이션, 데이터 바인딩 및 스타일 지원 등이 포함됩니다. 자세한 내용은 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md) 및 [XAML 로드 및 종속성 속성](../../../../docs/framework/wpf/advanced/xaml-loading-and-dependency-properties.md)을 참조하세요.  
  
### <a name="writing-and-attributing-a-type-converter"></a>형식 변환기 작성 및 특성 설정  
 경우에 따라 사용자 지정 작성 해야 합니다 <xref:System.ComponentModel.TypeConverter> 파생 클래스 속성 형식에 대 한 형식 변환을 제공 합니다. 파생 하 고 XAML 사용을 지원할 수 있는 형식 변환기를 만드는 방법 및 적용 하는 방법에 대 한 지침은 <xref:System.ComponentModel.TypeConverterAttribute>, 참조 [TypeConverters 및 XAML](../../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md)합니다.  
  
<a name="Requirements_for_Events_of_a_Custom_Class_as_XAML"></a>   
## <a name="requirements-for-xaml-event-handler-attribute-syntax-on-events-of-a-custom-class"></a>사용자 지정 클래스의 이벤트에 XAML 이벤트 처리기 특성 구문을 사용하기 위한 요구 사항  
 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 이벤트로 사용할 이벤트는 파생 클래스에서 이벤트 액세스가 가능한 추상 클래스 또는 기본 생성자를 지원하는 클래스에 공용 이벤트로 노출되어야 합니다. 라우트된 이벤트로 편리 하 게 사용 하려면 프로그램 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 이벤트 명시적 구현 해야 `add` 및 `remove` 추가 하 고에 대 한 처리기를 제거 하는 메서드는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 이벤트 서명의 이러한 처리기는 를앞뒤로<xref:System.Windows.UIElement.AddHandler%2A>및 <xref:System.Windows.UIElement.RemoveHandler%2A> 메서드. 이 두 메서드는 이벤트가 연결된 인스턴스의 라우트된 이벤트 처리기 저장소에 처리기를 추가하거나 제거합니다.  
  
> [!NOTE]
>  직접 사용 하 여 라우트된 이벤트에 대 한 처리기를 등록 하는 것이 불가능 <xref:System.Windows.UIElement.AddHandler%2A>를 의도적으로 정의 하는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 라우트된 이벤트를 노출 하는 이벤트입니다. 이벤트에서 연결 처리기에 대해 XAML 특성 구문을 사용하지 않으며 결과 클래스에서 해당 형식의 기능에 대해 투명도가 떨어지는 XAML 보기를 제공하므로, 이 방법은 일반적으로 권장되지 않습니다.  
  
<a name="Collection_Properties"></a>   
## <a name="writing-collection-properties"></a>컬렉션 속성 작성  
 컬렉션 형식을 사용하는 속성에는 컬렉션에 추가할 개체를 지정하는 데 사용할 수 있는 XAML 구문이 있습니다. 이 구문은 다음과 같은 두 가지 중요한 기능을 제공합니다.  
  
-   컬렉션 개체인 개체를 개체 요소 구문에 지정할 필요가 없습니다. 컬렉션 형식을 사용하는 XAML에 속성을 지정할 때마다 컬렉션 형식이 항상 암시적으로 존재합니다.  
  
-   태그에서 컬렉션 속성의 자식 요소는 컬렉션의 멤버로 처리됩니다. 일반적으로 컬렉션 멤버에 대한 코드 액세스는 `Add`와 같은 목록/사전 메서드를 통해 또는 인덱서를 통해 수행됩니다. 하지만 XAML 구문은 메서드나 인덱서를 지원하지 않습니다(예외: XAML 2009는 메서드를 지원할 수 있지만, XAML 2009를 사용하여 가능한 WPF 사용을 제한합니다. [XAML 2009 언어 기능](../../../../docs/framework/xaml-services/xaml-2009-language-features.md) 참조). 컬렉션은 요소 트리를 구성하는 데 있어 공통된 요구 사항이므로 선언적 XAML에서 이러한 컬렉션을 채우는 데 사용할 몇 가지 방법이 필요합니다. 따라서 컬렉션 속성의 자식 요소는 컬렉션 속성 형식 값인 컬렉션에 추가하여 처리됩니다.  
  
 .NET Framework XAML 서비스 구현과 WPF XAML 프로세서에서 컬렉션 속성을 구성하는 사항에 대한 다음 정의를 사용합니다. 속성의 형식은 다음 중 하나를 구현해야 합니다.  
  
-   구현 <xref:System.Collections.IList>합니다.  
  
-   구현 <xref:System.Collections.IDictionary> 또는 해당 제네릭 (<xref:System.Collections.Generic.IDictionary%602>).  
  
-   파생 <xref:System.Array> (XAML에서 배열에 대 한 자세한 내용은 참조 [X:array 태그 확장](../../../../docs/framework/xaml-services/x-array-markup-extension.md).)  
  
-   구현 <xref:System.Windows.Markup.IAddChild> (정의한 인터페이스 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]).  
  
 CLR의 각 형식에는 개체 그래프를 만들 때 XAML 프로세서에서 기본 컬렉션에 항목을 추가하는 데 사용하는 `Add` 메서드가 있습니다.  
  
> [!NOTE]
>  제네릭 `List` 및 `Dictionary` 인터페이스 (<xref:System.Collections.Generic.IList%601> 및 <xref:System.Collections.Generic.IDictionary%602>) 하 여 컬렉션 검색에 지원 되지 않습니다는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML 프로세서. 사용할 수 있습니다는 <xref:System.Collections.Generic.List%601> 클래스를 구현 하기 때문에 기본 클래스도 <xref:System.Collections.IList> 를 직접 또는 <xref:System.Collections.Generic.Dictionary%602> 기본 클래스로 구현 하기 때문에 <xref:System.Collections.IDictionary> 직접 합니다.  
  
 컬렉션을 사용하는 속성을 선언하는 경우 해당 형식의 새 인스턴스에서 속성 값이 초기화되는 방법에 유의하세요. 속성을 종속성 속성으로 구현하지 않는 경우에는 속성이 컬렉션 형식 생성자를 호출하는 지원 필드를 사용하도록 설정하는 것이 좋습니다. 속성이 종속성 속성인 경우에는 기본 형식 생성자의 일부로 컬렉션 속성을 초기화해야 할 수 있습니다. 그 이유는 종속성 속성이 속성의 기본값을 메타데이터에서 가져오는데, 개발자는 일반적으로 컬렉션 속성의 초기 값을 정적 공유 컬렉션에 사용하지 않으려고 하기 때문입니다. 형식 인스턴스를 포함하는 경우마다 컬렉션 인스턴스가 있어야 합니다. 자세한 내용은 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)을 참조하세요.  
  
 컬렉션 속성에 대해 사용자 지정 컬렉션 형식을 구현할 수 있습니다. 암시적 컬렉션 속성 처리로 인해 사용자 지정 컬렉션 형식은 기본 생성자를 제공하지 않아도 XAML에서 암시적으로 사용할 수 있습니다. 하지만 필요한 경우 컬렉션 형식에 대한 기본 생성자를 제공할 수도 있습니다. 이 방법은 유용한 방법입니다. 기본 생성자를 제공하지 않으면 컬렉션을 개체 요소로 명시적으로 선언할 수 없습니다. 명시적 컬렉션을 태그 스타일의 문제로 보는 태그 작성자도 있습니다. 기본 생성자를 사용하면 컬렉션 형식을 속성 값으로 사용하는 새 개체를 만들 때 초기화 요구 사항을 줄일 수도 있습니다.  
  
<a name="XAMLCONtent"></a>   
## <a name="declaring-xaml-content-properties"></a>XAML 콘텐츠 속성 선언  
 XAML 언어를 통해 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 콘텐츠 속성의 개념을 정의합니다. 개체 구문에서 사용할 수 있는 각 클래스에는 정확히 하나의 XAML 콘텐츠 속성만 포함될 수 있습니다. 클래스에 대 한 XAML 콘텐츠 속성을 속성을 선언 하려면 적용 된 <xref:System.Windows.Markup.ContentPropertyAttribute> 클래스 정의의 일부로 합니다. 으로 의도 된 XAML 콘텐츠 속성의 이름을 지정는 <xref:System.Windows.Markup.ContentPropertyAttribute.Name%2A> 특성에 있습니다. 속성은 문자열로 지정 된 이름으로는 리플렉션 구문 아니라와 같은 <xref:System.Reflection.PropertyInfo>합니다.  
  
 컬렉션 속성을 XAML 콘텐츠 속성으로 지정할 수 있습니다. 이 경우 중간의 컬렉션 개체 요소나 속성 요소 태그 없이도 개체 요소가 하나 이상의 자식 요소를 가질 수 있는 상황에서 해당 속성이 사용됩니다. 그러면 이러한 요소가 XAML 콘텐츠 속성에 대한 값으로 처리되어 지원 컬렉션 인스턴스에 추가됩니다.  
  
 기존 XAML 콘텐츠 속성 중 일부에서는 `Object`의 속성 형식을 사용합니다. 이렇게 하면 XAML와 같은 기본을 사용할 수 있는 속성 값이 콘텐츠는 <xref:System.String> 단일 참조 개체 값 뿐만 아니라 합니다. 이 모델을 따르는 경우 사용자의 형식을 통해 형식을 결정하고 가능한 형식을 처리합니다. 에 대 한 일반적인 이유는 <xref:System.Object> 하는 문자열로 (기본 표현 처리를 받습니다.), 개체 콘텐츠를 추가 하는 두 단순한 방법과 지원 하기 위해 형식이 나 개체 기본이 아닌 표현을 지정 하는 콘텐츠를 추가 하는 고급 방법을 콘텐츠 또는 추가 데이터입니다.  
  
<a name="Serializing"></a>   
## <a name="serializing-xaml"></a>XAML Serialize  
 예를 들어 컨트롤 작성자인 경우 XAML에서 인스턴스화할 수 있는 개체 표현도 해당 XAML 태그로 다시 serialize할 수 있도록 하려는 경우가 있습니다. Serialization 요구 사항은 이 항목에서 설명하지 않습니다. [컨트롤 작성 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md) 및 [요소 트리 및 Serialization](../../../../docs/framework/wpf/advanced/element-tree-and-serialization.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [XAML 개요(WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md)  
 [기본 요소 개요](../../../../docs/framework/wpf/advanced/base-elements-overview.md)  
 [XAML 로드 및 종속성 속성](../../../../docs/framework/wpf/advanced/xaml-loading-and-dependency-properties.md)
