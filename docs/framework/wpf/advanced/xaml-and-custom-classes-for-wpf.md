---
title: "WPF에 대한 XAML 및 사용자 지정 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "클래스, XAML의 사용자 지정 클래스"
  - "XAML의 사용자 지정 클래스"
  - "XAML, 사용자 지정 클래스"
ms.assetid: e7313137-581e-4a64-8453-d44e15a6164a
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# WPF에 대한 XAML 및 사용자 지정 클래스
XAML에서 구현 될 때 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 프레임 워크는 사용자 정의 클래스 또는 구조체에서 정의 하는 기능 지원 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 언어 및 다음 액세스는 클래스 XAML 태그를 사용 합니다.  일반적으로 사용자 지정 형식을 XAML 네임스페이스 접두사에 매핑하여 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 정의 형식과 사용자 지정 형식을 동일한 태그 파일에서 함께 사용할 수 있습니다.  이 항목에서는 사용자 지정 클래스를 XAML 요소로 사용 만족 시켜야 하는 요구 사항을 설명 합니다.  
  
   
  
<a name="Custom_Classes_in_Applications_vs__in_Assemblies"></a>   
## 응용 프로그램 또는 어셈블리의 사용자 지정 클래스  
 사용자 지정 클래스를 XAML에서 사용 되는 두 가지 방법으로 정의할 수 있습니다: 코드 숨김 파일 또는 주 생성 기타 코드 내에서 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램 또는 실행 파일 등을 별도 어셈블리에 있는 클래스 또는 클래스 라이브러리를 사용 하는 DLL입니다.  각 방법마다 고유의 장단점이 있습니다.  
  
-   클래스 라이브러리를 만드는 경우 사용자 지정 클래스를 서로 다른 여러 응용 프로그램에서 공유할 수 있다는 장점이 있습니다.  또한 별도 라이브러리 응용 프로그램의 버전 관리 문제를 더 쉽게 컨트롤 하 고 쉽게 의도 클래스 사용으로 XAML 페이지의 루트 요소로 있는 클래스를 만들 수 있습니다.  
  
-   사용자 지정 클래스를 응용 프로그램에 정의하는 방법은 비교적 간단하며 기본 응용 프로그램 실행 파일이 아닌 별도의 어셈블리를 사용할 때 발생하는 배포 및 테스트 문제를 최소화할 수 있다는 장점이 있습니다.  
  
-   동일 하거나 서로 다른 어셈블리에 정의 되어 있는지 사용자 지정 클래스를 XAML에서 요소로 사용 하려면 CLR 네임 스페이스와 XML 네임 스페이스 간에 매핑할 수 해야 합니다.  [WPF XAML을 위한 XAML 네임스페이스 및 네임스페이스 매핑](../../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)를 참조하십시오.  
  
<a name="Requirements_for_a_Custom_Class_as_a_XAML_Element"></a>   
## 사용자 지정 클래스를 XAML 요소로 사용하기 위한 요구 사항  
 클래스를 개체 요소로 인스턴스화하려면 클래스가 다음 요구 사항을 충족해야 합니다.  
  
-   사용자 지정 클래스가 공용 클래스여야 하고 매개 변수가 없는 기본 공용 생성자를 지원해야 합니다.  구조체에 대한 자세한 내용은 다음 단원을 참조하십시오.  
  
-   사용자 지정 클래스가 중첩 클래스가 아니어야 합니다.  중첩 클래스 및 일반 CLR 사용 구문의 "점"은 연결된 속성과 같은 다른 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및\/또는 XAML의 기능을 방해합니다.  
  
 개체 요소 구문을 사용하는 것 외에도 개체 정의에서 해당 개체를 값 형식으로 사용하는 다른 공용 속성에 대해서는 속성 요소 구문을 사용해야 합니다.  그 이유는 이제 개체가 개체 요소로 인스턴스화되어 이러한 속성의 속성 요소 값을 채울 수 있기 때문입니다.  
  
### 구조체  
 사용자 지정 형식을 항상 xaml에서 생성 될 수 있으므로 사용자 정의 구조 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] .이것은 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 컴파일러는 모든 속성 값을 기본값 초기화 된 구조체에 대 한 기본 생성자를 암시적으로 만듭니다.  그러나 경우에 따라서는 구조체의 기본 생성 동작 및\/또는 개체 요소를 사용하지 않는 것이 바람직할 수 있습니다.  포함된 값의 해석이 서로 달라서 어느 속성도 설정할 수 없는 경우에 구조체가 값을 채우고 개념적으로 공용 구조체로 사용되어야 하는 경우가 여기에 해당합니다.  이러한 구조체의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 예로 <xref:System.Windows.GridLength>를 들 수 있습니다.  일반적으로 이러한 구조체는 값을 특성 형식으로 표현할 수 있도록 형식 변환기를 구현해야 하며 구조체의 값에 대해 서로 다른 해석이나 모드를 만드는 문자열 규칙을 사용해야 합니다.  이러한 구조체는 기본값이 아닌 생성자를 통해 코드를 생성하는 경우에도 이와 유사한 동작을 노출해야 합니다.  
  
<a name="Requirements_for_Properties_of_a_Custom_Class_as_XAML"></a>   
## 사용자 지정 클래스의 속성을 XAML 특성으로 사용하기 위한 요구 사항  
 속성이 값 기준 형식\(예: 기본 형식\)을 참조하거나 XAML 프로세서에서 액세스할 수 있는 기본 생성자나 전용 형식 변환기를 가지고 있는 형식에 대한 클래스를 사용해야 합니다.  CLR XAML 구현에서 XAML 프로세서는 언어 기본 형식에 대한 네이티브 지원 또는 <xref:System.ComponentModel.TypeConverterAttribute> 응용 프로그램을 통해 지원 형식 정의에서 형식 또는 멤버에 대한 이러한 변환기를 찾습니다.  
  
 또는 속성이 추상 클래스 형식 또는 인터페이스를 참조할 수도 있습니다.  추상 클래스나 인터페이스의 경우 XAML 구문 분석에 대해 해당 인터페이스를 구현하는 실제 클래스 인스턴스로 또는 추상 클래스에서 파생되는 형식의 인스턴스로 속성 값이 채워집니다.  
  
 속성을 추상 클래스에서 선언할 수 있지만 해당 속성은 추상 클래스에서 파생되는 실제 클래스에서만 설정될 수 있습니다.  클래스에 대한 개체 요소를 만들려면 클래스에 공용 기본 생성자가 필요하기 때문입니다.  
  
### TypeConverter 사용 특성 구문  
 클래스 수준에서 전용 특성 사용 형식 변환기를 제공한 경우 적용된 형식 변환을 사용하면 해당 형식을 인스턴스화해야 하는 모든 속성에 특성 구문을 사용할 수 있습니다.  형식 변환기는 해당 형식의 개체 요소를 사용하지 않습니다. 해당 형식에 대한 기본 생성자가 있는 경우에만 개체 요소를 사용할 수 있습니다.  따라서 형식 변환기가 사용하는 속성은 일반적으로 속성 구문에서 사용할 수 없습니다. 단, 형식 자체가 개체 요소 구문도 지원하는 경우는 예외입니다.  한 가지 예외적인 경우로 속성 요소에 문자열을 포함하여 속성 요소 구문을 지정할 수 있습니다.  이는 기본적으로 특성 구문을 사용하는 것과 같지만, 특성 값에 대한 보다 강력한 공백 처리가 필요한 경우가 아니면 일반적이지 않은 방법입니다.  예를 들어 다음은 문자열을 사용하는 속성 요소를 사용하는 방법을 보여 주며 이는 특성을 사용하는 것과 같습니다.  
  
 [!code-xml[XamlOvwSupport#GoofyTCPE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofytcpe)]  
  
 [!code-xml[XamlOvwSupport#GoofyTCPE2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofytcpe2)]  
  
 위치 특성 구문을 사용할 수 있지만 XAML에서 개체 요소를 포함 하는 속성 요소 구문을 허용 되지 않는 속성의 예는 다양 한 속성을 <xref:System.Windows.Input.Cursor> 형식입니다.  <xref:System.Windows.Input.Cursor> 클래스에는 전용 형식 변환기인 <xref:System.Windows.Input.CursorConverter>가 있지만 기본 생성자를 노출하지 않으므로 <xref:System.Windows.FrameworkElement.Cursor%2A> 속성은 실제 <xref:System.Windows.Input.Cursor> 형식이 참조 형식인 경우에도 특성 구문을 통해서만 설정할 수 있습니다.  
  
### 속성별 형식 변환기  
 속성 자체가 속성 수준에서 형식 변환기를 선언할 수도 있습니다.  이렇게 하면 특성의 들어오는 문자열 값을 해당 형식에 따라 <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> 작업의 입력으로 처리하여, 속성 형식의 개체를 인라인으로 인스턴스화하는 "미니 언어"를 사용할 수 있습니다.  일반적으로 이것은 편리한 접근자를 제공 하기 위한 것 XAML에서 속성을 설정할 수 있도록 위한 유일한 방법이 아니라.  그러나 기본 생성자나 특성 사용 형식 변환기를 제공하지 않는 기존 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 형식을 사용하려는 특성에 대해 형식 변환기를 사용할 수도 있습니다.  예제에서의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] API는 특정 속성의 <xref:System.Globalization.CultureInfo> 형식입니다.  이 경우 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 사용 하 여 기존 [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)]<xref:System.Globalization.CultureInfo> 보다 이전 버전의 프레임 워크에 사용 된 호환성 및 마이그레이션 시나리오를 해결 하기 위해 형식 있지만 해당 <xref:System.Globalization.CultureInfo> 필요한 생성자 또는 형식 수준의 형식 변환을 직접 XAML 속성 값으로 사용 가능 하도록 형식을 지원 하지 않습니다.  
  
 따라서 컨트롤 작성자는 XAML을 사용하는 속성을 노출할 때마다 해당 속성에 종속성 속성을 지원하는 방법을 고려해야 합니다.  기존에 사용 하는 경우 특히 그렇습니다 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 는 XAML 프로세서 구현을 사용 하 여 성능을 향상 시킬 수 있기 때문에 <xref:System.Windows.DependencyProperty> 백업 합니다.  종속성 속성은 애니메이션, 데이터 바인딩, 스타일 지원 등 XAML 액세스 가능 속성이 제공할 것으로 예상되는  속성 시스템의 기능을 제공합니다.  자세한 내용은 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md) 및 [XAML 로드 및 종속성 속성](../../../../docs/framework/wpf/advanced/xaml-loading-and-dependency-properties.md)을 참조하십시오.  
  
### 형식 변환기 작성 및 특성 설정  
 속성 형식에 형식 변환을 제공하기 위해 사용자 지정 <xref:System.ComponentModel.TypeConverter> 파생 클래스를 작성해야 하는 경우가 있습니다.  형식 변환기에서 파생하여 XAML 사용을 지원하는 형식 변환기를 만드는 방법 및 <xref:System.ComponentModel.TypeConverterAttribute>를 적용하는 방법은 [TypeConverter 및 XAML](../../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md)을 참조하십시오.  
  
<a name="Requirements_for_Events_of_a_Custom_Class_as_XAML"></a>   
## 사용자 지정 클래스의 이벤트에 XAML 이벤트 처리기 특성 구문을 사용하기 위한 요구 사항  
 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 이벤트로 사용할 이벤트는 파생 클래스에서의 이벤트 액세스가 가능한 추상 클래스 또는 기본 생성자를 지원하는 클래스에 공용 이벤트로 노출되어야 합니다.  이벤트를 간편하게 [라우트된 이벤트](GTMT)로 사용하려면 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 이벤트가 명시적 `add` 및 `remove` 메서드를 구현해야 합니다. 이 두 메서드는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 이벤트 시그니처에 대한 처리기를 추가 및 제거하며 이러한 처리기를 <xref:System.Windows.UIElement.AddHandler%2A> 및 <xref:System.Windows.UIElement.RemoveHandler%2A> 메서드에 전달합니다.  이 두 메서드는 이벤트가 연결된 인스턴스의 라우트된 이벤트 처리기 저장소에 처리기를 추가하거나 제거합니다.  
  
> [!NOTE]
>  <xref:System.Windows.UIElement.AddHandler%2A>를 사용하여 라우트된 이벤트에 대한 처리기를 직접 등록할 수 있습니다. 또한 [라우트된 이벤트](GTMT)를 노출하는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 이벤트를 의도적으로 정의하지 않을 수도 있습니다.  이것은 일반적으로 이벤트 처리기를 첨부에 대 한 XAML 특성 구문을 사용 하지 않습니다 결과 클래스를 불투명 하 게 XAML 뷰에서 해당 유형의 기능을 제공 합니다 때문에 권장 되지 않습니다.  
  
<a name="Collection_Properties"></a>   
## 컬렉션 속성 작성  
 컬렉션 형식을 사용하는 속성에는 컬렉션에 추가할 개체를 지정하는 데 사용할 수 있는 XAML 구문이 있습니다.  이 구문은 다음과 같은 두 가지 중요한 기능을 제공합니다.  
  
-   개체\(컬렉션 개체\)를 개체 요소 구문에 지정할 필요가 없습니다.  컬렉션 형식을 사용하는 XAML에 속성을 지정하는 경우 컬렉션 형식이 항상 암시적으로 존재합니다.  
  
-   태그에서 컬렉션 속성의 자식 요소는 컬렉션의 멤버로 처리됩니다.  일반적으로 컬렉션 멤버에 대한 코드 액세스는 `Add`와 같은 목록\/사전 메서드를 통해 또는 인덱서를 통해 수행됩니다.  하지만 XAML 구문은 메서드나 인덱서를 지원 하지 않습니다 \(예외: XAML 2009 메서드를 지원할 수 있지만 XAML 2009를 사용 하 여 WPF의 가능한 용도. see [XAML 2009 언어 기능](../../../../docs/framework/xaml-services/xaml-2009-language-features.md)\).  컬렉션은 요소 트리를 구성하는 데 있어 공통된 요구 사항이므로 선언적 XAML에서 이러한 컬렉션을 채우는 데 사용할 몇 가지 방법이 필요합니다.  따라서 컬렉션 속성의 자식 요소는 컬렉션 속성 형식 값에 해당하는 컬렉션에 추가됩니다.  
  
 해당 합니다.NET Framework XAML 서비스 구현 및 따라서 WPF XAML 프로세서 사용 하 여 다음 정의 컬렉션 속성을 구성 하는 작업에 대 한.  속성의 속성 형식은 다음 중 하나를 구현해야 합니다.  
  
-   <xref:System.Collections.IList> 구현  
  
-   <xref:System.Collections.IDictionary> 또는 해당 제네릭\(<xref:System.Collections.Generic.IDictionary%602>\) 구현  
  
-   파생 됩니다 <xref:System.Array> \(XAML에서 배열 하는 방법에 대 한 자세한 내용은 참조 하십시오. [x:Array 태그 확장](../../../../docs/framework/xaml-services/x-array-markup-extension.md)입니다.\)  
  
-   <xref:System.Windows.Markup.IAddChild>\([!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 정의된 인터페이스\) 구현  
  
 이러한 각 형식에서 CLR가는 `Add` 은 XAML 프로세서에서 개체 그래프를 만들 때 기본 컬렉션에 항목을 추가 하는 데 사용 되는 메서드.  
  
> [!NOTE]
>  일반 `List` 및 `Dictionary` 인터페이스 \(<xref:System.Collections.Generic.IList%601> 및 <xref:System.Collections.Generic.IDictionary%602>\) 컬렉션 검색에서 지원 되지 않습니다을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML 프로세서.  하지만 <xref:System.Collections.Generic.List%601> 클래스는 <xref:System.Collections.IList>를 직접 구현하므로 이를 기본 클래스로 사용할 수 있습니다. 또는 <xref:System.Collections.Generic.Dictionary%602> 클래스는 <xref:System.Collections.IDictionary>를 직접 구현하므로 이를 기본 클래스로 사용할 수도 있습니다.  
  
 컬렉션을 사용하는 속성을 선언하는 경우 해당 형식의 새 인스턴스에서 속성 값이 초기화되는 방법에 유의하십시오.  속성을 종속성 속성으로 구현하지 않는 경우에는 속성이 컬렉션 형식 생성자를 호출하는 지원 필드를 사용하도록 설정하는 것이 좋습니다.  속성이 종속성 속성인 경우에는 기본 형식 생성자의 일부로 컬렉션 속성을 초기화해야 할 수 있습니다.  그 이유는 종속성 속성이 속성의 기본값을 메타데이터에서 가져오는데, 개발자는 일반적으로 컬렉션 속성의 초기 값을 정적 공유 컬렉션에 사용하지 않으려고 하기 때문입니다.  각각의 포함하는 인스턴스마다 컬렉션 인스턴스가 있어야 합니다.  자세한 내용은 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)을 참조하십시오.  
  
 컬렉션 속성에 대해 사용자 지정 컬렉션 형식을 구현할 수 있습니다.  암시적 컬렉션 속성 처리로 인해 사용자 지정 컬렉션 형식은 기본 생성자를 제공하지 않아도 XAML에서 암시적으로 사용할 수 있습니다.  하지만 필요한 경우 컬렉션 형식에 대한 기본 생성자를 제공할 수도 있습니다.  이 방법은 유용한 방법입니다.  기본 생성자를 제공하지 않으면 컬렉션을 개체 요소로 명시적으로 선언할 수 없습니다.  명시적 컬렉션을 태그 스타일의 문제로 보는 태그 작성자도 있습니다.  기본 생성자를 사용하면 컬렉션 형식을 속성 값으로 사용하는 새 개체를 만들 때 초기화 요구 사항을 줄일 수도 있습니다.  
  
<a name="XAMLCONtent"></a>   
## XAML 콘텐츠 속성 선언  
 XAML 언어 개념 정의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 속성 내용입니다.  개체 구문에서 사용할 수 있는 각 클래스는 정확히 하나의 XAML 콘텐츠 속성을 포함할 수 있습니다.  속성을 클래스의 XAML 콘텐츠 속성으로 선언하려면 클래스 정의의 일부로 <xref:System.Windows.Markup.ContentPropertyAttribute>를 적용합니다.  특성에서 <xref:System.Windows.Markup.ContentPropertyAttribute.Name%2A>으로 선언할 XAML 콘텐츠 속성의 이름을 지정합니다.  속성 문자열을 이름으로 반사 구문을 않습니다 같은 지정 된<xref:System.Reflection.PropertyInfo>.  
  
 컬렉션 속성을 XAML 콘텐츠 속성으로 지정할 수 있습니다.  이 경우 중간의 컬렉션 개체 요소나 속성 요소 태그 없이도 개체 요소가 하나 이상의 자식 요소를 가질 수 있는 상황에서 해당 속성이 사용됩니다.  그러면 이러한 요소가 XAML 콘텐츠 속성에 대한 값으로 처리되어 지원 컬렉션 인스턴스에 추가됩니다.  
  
 일부 기존 XAML 콘텐츠 속성의 속성 형식 사용 하 여  `개체`.  이 때문에 XAML 콘텐츠 속성은 <xref:System.String>과 같은 기본 값뿐만 아니라 단일 참조 개체 값을 사용할 수 있습니다.  이 모델을 따르는 경우 사용자의 형식을 통해 형식을 결정하고 가능한 형식을 처리합니다.  <xref:System.Object> 콘텐츠 형식에서 이와 같이 하는 이유는 개체 콘텐츠를 문자열\(기본 표현 처리를 수신\)로 추가하는 단순한 방법과 기본이 아닌 표현 또는 추가 데이터를 지정하는 개체 콘텐츠를 추가하는 고급 방법을 모두 지원하기 위해서입니다.  
  
<a name="Serializing"></a>   
## XAML Serialize  
 If 같은 특정 시나리오를 컨트롤 작성자가, XAML에서 인스턴스화할 수 있는 개체 표현을 다시 해당 하는 XAML 태그에도 serialize 될 수 확인을 할 수도 있습니다.  이 항목에서는 serialization 요구 사항에 대해서는 설명하지 않습니다.  [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md) 및 [요소 트리 및 serialization](../../../../docs/framework/wpf/advanced/element-tree-and-serialization.md)을 참조하십시오.  
  
## 참고 항목  
 [XAML 개요\(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md)   
 [기본 요소 개요](../../../../docs/framework/wpf/advanced/base-elements-overview.md)   
 [XAML 로드 및 종속성 속성](../../../../docs/framework/wpf/advanced/xaml-loading-and-dependency-properties.md)