---
title: PropertyPath XAML 구문
ms.date: 03/30/2017
helpviewer_keywords:
- PropertyPath object [WPF]
- XAML [WPF], PropertyPath object
ms.assetid: 0e3cdf07-abe6-460a-a9af-3764b4fd707f
ms.openlocfilehash: 547c7d009d2fecf863284324c7ea45006d20d20c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548989"
---
# <a name="propertypath-xaml-syntax"></a>PropertyPath XAML 구문
<xref:System.Windows.PropertyPath> 개체가 지원 복잡 한 인라인 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 구문을 사용 하는 다양 한 속성을 설정 하기 위한는 <xref:System.Windows.PropertyPath> 형식을 값으로. 이 항목 문서는 <xref:System.Windows.PropertyPath> 구문 되는 바인딩 및 애니메이션 구문에 적용 합니다.  
    
  
<a name="where"></a>   
## <a name="where-propertypath-is-used"></a>PropertyPath를 사용하는 경우  
 <xref:System.Windows.PropertyPath> 몇 개에 사용 되는 공통 개체 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 기능입니다. 일반을 사용 했는데도 <xref:System.Windows.PropertyPath> 속성 경로 정보를 전달 하기 위해 각 사용 기능 영역 여기서 <xref:System.Windows.PropertyPath> 다를 형식으로 사용 됩니다. 따라서 구문은 기능별로 설명하는 것이 좋습니다.  
  
 기본적으로, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 사용 하 여 <xref:System.Windows.PropertyPath> 개체 데이터 원본의 속성을 탐색 하는 데 개체 모델 경로 설명 하 고 대상된 애니메이션에 대 한 대상 경로 설명 하기 위해 합니다.  
  
 와 같은 일부 스타일 및 템플릿 속성 <xref:System.Windows.Setter.Property%2A?displayProperty=nameWithType> 유사한 외견상으로 정규화 된 속성 이름을 인수로 <xref:System.Windows.PropertyPath>합니다. 있지만이 실제 <xref:System.Windows.PropertyPath>; 정규화 된 만으로도 *owner.property* WPF에서 사용 하도록 설정 하는 형식 사용 문자열 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에 대 한 형식 변환기와 함께에서 <xref:System.Windows.DependencyProperty>합니다.  
  
<a name="databinding_s"></a>   
## <a name="propertypath-for-objects-in-data-binding"></a>데이터 바인딩의 개체에 대한 PropertyPath  
 데이터 바인딩은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기능으로 이를 통해 종속성 속성의 대상 값에 바인딩할 수 있습니다. 하지만 해당 데이터 바인딩의 소스는 종속성 속성이어야 하며 적용 가능한 데이터 공급자가 인식하는 모든 속성 형식일 수 있습니다. 속성 경로 특히 사용 된 <xref:System.Windows.Data.ObjectDataProvider>에서 바인딩 소스를 가져오는 데 사용 되는 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 개체 및 개체 속성입니다.  
  
 데이터 바인딩을 지를 확인 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 사용 하지 않는 <xref:System.Windows.PropertyPath>사용 하지 않으므로, <xref:System.Windows.Data.Binding.Path%2A> 에 <xref:System.Windows.Data.Binding>합니다. 대신를 사용 하 여 <xref:System.Windows.Data.Binding.XPath%2A> 에 유효한 XPath 구문을 지정 하 고는 [!INCLUDE[TLA#tla_xmldom](../../../../includes/tlasharptla-xmldom-md.md)] 데이터입니다. <xref:System.Windows.Data.Binding.XPath%2A> 또한를 문자열로 지정 되었지만; 여기에 설명 되어 있지 않습니다. 참조 [XMLDataProvider 및 XPath 쿼리가 사용 하 여 XML 데이터에 바인딩할](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)합니다.  
  
 데이터 바인딩의 속성 경로를 이해하는 열쇠는 개별 속성 값에 대한 바인딩을 대상으로 지정할 수 있거나 목록이나 컬렉션을 사용하는 대상 속성에 바인딩할 수 있다는 점입니다. 예를 들어 바인딩 컬렉션에 바인딩하는 경우는 <xref:System.Windows.Controls.ListBox> 컬렉션에 있는 데이터 항목의 수에 따라 확장 되는 속성 경로 컬렉션 개체, 개별이 아닌 컬렉션 항목을 참조 해야 합니다. 데이터 바인딩 엔진은 데이터 원본 바인딩 대상의 형식에 자동으로 채우기 등의 동작으로 인해 발생 하는 대로 사용 되는 컬렉션을 찾습니다는 <xref:System.Windows.Controls.ListBox> 항목 배열을 사용 하 여 합니다.  
  
<a name="singlecurrent"></a>   
### <a name="single-property-on-the-immediate-object-as-data-context"></a>데이터 컨텍스트로서 직접 실행 개체에 대한 단일 속성  
  
```xml  
<Binding Path="propertyName" .../>  
```  
  
 *propertyName* 현재에 있는 속성의 이름 이어야 <xref:System.Windows.FrameworkElement.DataContext%2A> 에 대 한는 <xref:System.Windows.Data.Binding.Path%2A> 사용 합니다. 바인딩이 소스를 업데이트하면 해당 속성은 읽기/쓰기여야 하고 소스 개체는 변경 가능해야 합니다.  
  
<a name="singleindex"></a>   
### <a name="single-indexer-on-the-immediate-object-as-data-context"></a>데이터 컨텍스트로서 직접 실행 개체에 대한 단일 인덱서  
  
```xml  
<Binding Path="[key]" .../>  
```  
  
 `key`는 사전 및 해시 테이블에 대한 형식화된 인덱스이거나 배열의 정수 인덱스여야 합니다. 또한 키 값은 키 값이 적용되는 속성에 직접 바인딩할 수 있는 형식이어야 합니다. 예를 들어, 문자열 키와 문자열 값을 포함 하는 해시 테이블 데 사용할 수 있습니다 이러한 방식으로 텍스트에 바인딩하는 <xref:System.Windows.Controls.TextBox>합니다. 또는 키가 컬렉션이나 하위 인덱스를 가리키는 경우 이 구문을 사용하여 대상 컬렉션 속성에 바인딩할 수 있습니다. 이외의 경우에는 `<Binding Path="[``key``].``propertyName``" .../>`과 같은 구문을 통해 특정 속성을 참조해야 합니다.  
  
 필요한 경우 인덱스의 형식을 지정할 수 있습니다. 인덱싱된 속성 경로이 측면이 대 한 세부 정보를 참조 하십시오. <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>합니다.  
  
<a name="multipleindirect"></a>   
### <a name="multiple-property-indirect-property-targeting"></a>다중 속성(간접 속성 대상 지정)  
  
```xml  
<Binding Path="propertyName.propertyName2" .../>  
```  
  
 `propertyName` 현재 속성의 이름 이어야 <xref:System.Windows.FrameworkElement.DataContext%2A>합니다. 경로 속성 `propertyName` 및 `propertyName2`는 관계에 있는 속성일 수 있습니다. 여기서 `propertyName2`는 `propertyName` 값인 형식에 있는 속성입니다.  
  
<a name="singleattached"></a>   
### <a name="single-property-attached-or-otherwise-type-qualified"></a>연결된 또는 정규화된 형식의 단일 속성  
  
```xml  
<object property="(ownerType.propertyName)" .../>  
```  
  
 괄호를 표시 하는이 속성에는 <xref:System.Windows.PropertyPath> 부분 정규화를 사용 하 여 생성 해야 합니다. XML 네임스페이스를 사용하여 적절한 매핑이 있는 형식을 찾을 수 있습니다. `ownerType` 있는 형식을 검색은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에 통해에 대 한 액세스는 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 각 어셈블리의 선언입니다. 대부분 응용 프로그램에서는 기본 XML 네임스페이스가 [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)] 네임스페이스에 매핑되므로 접두사는 대개 사용자 지정 형식 또는 해당 네임스페이스 외부의 형식에만 필요합니다.  `propertyName`은 `ownerType`에 있는 속성의 이름으로 확인되어야 합니다. 일반적으로 이 구문은 다음 경우 중 하나에 사용됩니다.  
  
-   경로는 지정된 대상 형식이 없는 스타일 또는 템플릿인 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 지정됩니다. 스타일이 아니고 템플릿이 아닌 경우에 속성은 형식이 아닌 인스턴스에 있으므로 일반적으로 이를 제외한 다른 경우에는 정규화된 사용이 적절하지 않습니다.  
  
-   속성은 연결된 속성입니다.  
  
-   정적 속성이 바인딩 중입니다.  
  
 스토리 보드 대상으로 사용에 대 한 속성으로 지정 `propertyName` 이어야 합니다는 <xref:System.Windows.DependencyProperty>합니다.  
  
<a name="sourcetraversal"></a>   
### <a name="source-traversal-binding-to-hierarchies-of-collections"></a>소스 순회(컬렉션 계층 구조에 바인딩)  
  
```xml  
<object Path="propertyName/propertyNameX" .../>  
```  
  
 이 구문의 /는 계층적 데이터 소스 개체 내에서 탐색하는 데 사용되고 연속 / 문자가 있는 계층 구조에 대한 여러 단계는 지원되지 않습니다. 소스 순회는 데이터를 뷰의 UI와 동기화할 때 결정되는 현재 레코드 포인터 위치를 처리합니다. 계층적 데이터 소스 개체를 사용한 바인딩 및 데이터 바인딩의 현재 레코드 포인터 개념에 대한 자세한 내용은 [계층적 데이터에 마스터-세부 패턴 사용](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md) 또는 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하세요.  
  
> [!NOTE]
>  표면적으로 이 구문은 [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)]와 비슷합니다. 진정한 [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)] 식에 대 한 바인딩에 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터 원본으로 사용 되지 않는 한 <xref:System.Windows.Data.Binding.Path%2A> 값과 함께 사용할 수 없는에 대신 사용할 <xref:System.Windows.Data.Binding.XPath%2A> 속성입니다.  
  
### <a name="collection-views"></a>컬렉션 뷰  
 명명된 컬렉션 뷰를 참조하려면 해시 문자(`#`)를 컬렉션 뷰 이름에 접두사로 추가합니다.  
  
### <a name="current-record-pointer"></a>현재 레코드 포인터  
 컬렉션 뷰 또는 마스터 세부 데이터 바인딩 시나리오에 대한 현재 레코드 포인터를 참조하려면 경로 문자열을 슬래시(`/`)로 시작합니다. 슬래시를 통과하는 모든 경로는 현재 레코드 포인터부터 이동합니다.  
  
### <a name="multiple-indexers"></a>여러 인덱서  
  
```  
<object Path="[index1,index2...]" .../>  
or  
<object Path="propertyName[index,index2...]" .../>  
```  
  
 특정 개체가 여러 인덱서를 지원할 경우 이러한 인덱서는 배열 참조 구문처럼 순서대로 지정될 수 있습니다. 해당 개체는 현재 컨텍스트이거나 여러 인덱스 개체를 포함하는 속성의 값일 수 있습니다.  
  
 기본적으로 인덱서 값은 기본 개체의 특징을 사용해서 형식화됩니다. 필요한 경우 인덱스의 형식을 지정할 수 있습니다. 인덱서 입력에 대 한 세부 정보를 참조 하십시오. <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>합니다.  
  
<a name="mixing"></a>   
### <a name="mixing-syntaxes"></a>구문 혼합  
 위에 표시되는 각 구문은 섞여 있을 수 있습니다. 예를 들어, 다음은 특정 x, y에 색에 대 한 속성 경로 만드는 예제를 한 `ColorGrid` 의 픽셀 모눈 배열이 포함 된 속성 <xref:System.Windows.Media.SolidColorBrush> 개체:  
  
```xml  
<Rectangle Fill="{Binding ColorGrid[20,30].SolidColorBrushResult}" .../>  
```  
  
### <a name="escapes-for-property-path-strings"></a>속성 경로 문자열에 대한 이스케이프  
 특정 비즈니스 개체의 경우 제대로 구문 분석되려면 속성 경로 문자열에 이스케이프 시퀀스가 있어야 하는 경우가 있습니다. 이스케이프해야 하는 경우는 드뭅니다. 대부분의 이러한 문자에는 일반적으로 비즈니스 개체를 정의하는 데 사용되는 언어에 비슷한 명명 상호 작용 문제가 있기 때문입니다.  
  
-   인덱서([ ]) 안의 캐럿 문자(^)는 다음 문자를 이스케이프합니다.  
  
-   XML 언어 정의와 관련된 특정 문자를 이스케이프(XML 엔터티 사용)해야 합니다. "&" 문자를 이스케이프하려면 `&`를 사용합니다. ">" 끝 태그를 이스케이프하려면 `>`를 사용합니다.  
  
-   태그 확장을 처리하기 위해 WPF XAML 구문 분석기 동작과 관련된 특정 문자를 이스케이프해야 합니다(백슬래시 `\` 사용).  
  
    -   백슬래시(`\`)는 그 자체로 이스케이프 문자입니다.  
  
    -   등호(`=`)는 속성 값에서 속성 이름을 구분합니다.  
  
    -   쉼표(`,`)는 속성을 구분합니다.  
  
    -   오른쪽 중괄호(`}`)는 태그 확장의 끝입니다.  
  
> [!NOTE]
>  기술적으로 이러한 이스케이프는 스토리보드 속성 경로에도 적용되지만 대개 기존 WPF 개체에 대한 개체 모델을 통과하므로 이스케이프가 필요하지 않습니다.  
  
<a name="databinding_sa"></a>   
## <a name="propertypath-for-animation-targets"></a>애니메이션 대상에 대한 PropertyPath  
 애니메이션의 대상 속성 중 하나를 사용 하는 종속성 속성 이어야 합니다는 <xref:System.Windows.Freezable> 또는 기본 형식입니다. 하지만 형식의 대상 속성 및 최종 애니메이션 효과가 적용된 속성은 서로 다른 개체에 있을 수 있습니다. 애니메이션에 대한 속성 경로는 속성 값에서 개체 속성 관계를 통과하는 방식으로 명명된 애니메이션 대상 개체의 속성과 의도한 대상 애니메이션 속성 간 연결을 정의하는 데 사용됩니다.  
  
<a name="general"></a>   
### <a name="general-object-property-considerations-for-animations"></a>애니메이션에 대한 일반 개체 속성 고려 사항  
 일반적인 애니메이션 개념에 대한 자세한 내용은 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md) 및 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하세요.  
  
 값 형식 또는 되는 속성 중 하나 여야 합니다는 <xref:System.Windows.Freezable> 또는 기본 형식입니다. 경로 시작 하는 속성에 지정 된 종속성 속성의 이름으로 해결 해야 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 유형입니다.  
  
 애니메이션을 적용 하는 것에 대 한 복제를 지원 하기 위해는 <xref:System.Windows.Freezable> 는 이미 중지 하 여 지정 된 개체가 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 이어야 합니다는 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement> 클래스를 파생 합니다.  
  
<a name="singlestepanim"></a>   
### <a name="single-property-on-the-target-object"></a>대상 개체에 대한 단일 속성  
  
```xml  
<animation Storyboard.TargetProperty="propertyName" .../>  
```  
  
 `propertyName` 지정 된 존재 하는 종속성 속성의 이름 이어야 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 유형입니다.  
  
<a name="indirectanim"></a>   
### <a name="indirect-property-targeting"></a>간접 속성 대상 지정  
  
```xml  
<animation Storyboard.TargetProperty="propertyName.propertyName2" .../>  
```  
  
 `propertyName` 속성 이어야 합니다는 <xref:System.Windows.Freezable> 값 형식 또는 지정 된 존재 하는 기본 형식 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 유형입니다.  
  
 `propertyName2`는 `propertyName` 값인 개체에 있는 종속성 속성의 이름이어야 합니다. 즉, `propertyName2` 되는 형식에서 종속성 속성으로 존재 해야 합니다는 `propertyName` <xref:System.Windows.DependencyProperty.PropertyType%2A>합니다.  
  
 적용된 스타일 및 템플릿 때문에 애니메이션의 간접 대상 지정이 필요합니다. 애니메이션을 대상으로 해야는 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 대상 개체에 이름으로 설정 됩니다 [X:name](../../../../docs/framework/xaml-services/x-name-directive.md) 또는 <xref:System.Windows.FrameworkElement.Name%2A>합니다. 템플릿 및 스타일 요소에 이름이 있을 수 있지만 해당 이름은 스타일 및 템플릿의 네임스페이스 내에서만 유효합니다. 템플릿 및 스타일이 네임스페이스를 응용 프로그램 태그와 공유한 경우 이름이 고유하지 않습니다. 스타일 및 템플릿은 문자 그대로 인스턴스 간에 공유되고 중복 이름을 영구화합니다. 따라서 애니메이션 효과를 줄 요소의 개별 속성이 스타일이나 템플릿을 기반으로 한 경우 스타일 템플릿을 기반으로 하지 않은 명명된 요소 인스턴스로 시작한 다음 애니메이션 효과를 줄 속성에 도착할 스타일 또는 템플릿 시각적 트리를 대상으로 지정해야 합니다.  
  
 예를 들어,는 <xref:System.Windows.Controls.Panel.Background%2A> 속성은 <xref:System.Windows.Controls.Panel> 된 완전 <xref:System.Windows.Media.Brush> (실제로 <xref:System.Windows.Media.SolidColorBrush>) 테마 템플릿에서 생성 하는 합니다. 애니메이션 효과를 주는 <xref:System.Windows.Media.Brush> 완전히 있습니다이 될 필요가 BrushAnimation (것에 대 한 모든 <xref:System.Windows.Media.Brush> 형식) 형식이 없습니다. 브러시를 애니메이션 효과를 줄 대신 애니메이션 효과 줄 속성의 특정 <xref:System.Windows.Media.Brush> 유형입니다. 가져와야 할 <xref:System.Windows.Media.SolidColorBrush> 를 해당 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 적용 하는 <xref:System.Windows.Media.Animation.ColorAnimation> 있습니다. 이 예제의 속성 경로는 `Background.Color`입니다.  
  
<a name="attachedanim"></a>   
### <a name="attached-properties"></a>연결된 속성  
  
```xml  
<animation Storyboard.TargetProperty="(ownerType.propertyName)" .../>  
```  
  
 괄호를 표시 하는이 속성에는 <xref:System.Windows.PropertyPath> 부분 정규화를 사용 하 여 생성 해야 합니다. XML 네임스페이스를 사용하여 형식을 찾을 수 있습니다. `ownerType` 있는 형식을 검색은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에 통해에 대 한 액세스는 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 각 어셈블리의 선언입니다. 대부분 응용 프로그램에서는 기본 XML 네임스페이스가 [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)] 네임스페이스에 매핑되므로 접두사는 대개 사용자 지정 형식 또는 해당 네임스페이스 외부의 형식에만 필요합니다. `propertyName`은 `ownerType`에 있는 속성의 이름으로 확인되어야 합니다. 로 지정 된 속성이 `propertyName` 이어야 합니다는 <xref:System.Windows.DependencyProperty>합니다. 모든 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 연결된 속성은 종속성 속성으로 구현되므로 이 문제는 사용자 지정 연결된 속성에만 관련됩니다.  
  
<a name="indexanim"></a>   
### <a name="indexers"></a>인덱서  
  
```xml  
<animation Storyboard.TargetProperty="propertyName.propertyName2[index].propertyName3" .../>  
```  
  
 대부분의 종속성 속성 또는 <xref:System.Windows.Freezable> 유형은 인덱서를 지원 하지 않습니다. 따라서 애니메이션 경로에서 인덱서는 명명된 대상에서 체인을 시작하는 속성과 최종 애니메이션 효과가 적용된 속성 사이의 중간 위치에만 사용됩니다. 제공된 구문에서 인덱서는 `propertyName2`입니다. 예를 들어, 인덱서가 경우 필요할 수 있습니다와 같은 중간 속성은 컬렉션 <xref:System.Windows.Media.TransformGroup>와 같은 속성 경로에서 `RenderTransform.Children[1].Angle`합니다.  
  
<a name="ppincode"></a>   
## <a name="propertypath-in-code"></a>코드의 PropertyPath  
 코드에 대 한 사용법 <xref:System.Windows.PropertyPath>를 생성 하는 방법을 포함 하는 <xref:System.Windows.PropertyPath>에 대 한 참조 항목에 설명 되어 <xref:System.Windows.PropertyPath>합니다.  
  
 일반적으로 <xref:System.Windows.PropertyPath> 바인딩 사용 및 가장 간단한 애니메이션 사용에 대 한 클래스 생성자와 복잡 한 애니메이션 사용에 대 한 두 명의 서로 다른 생성자 생성자를 사용 하도록 구성 되었습니다. 사용 하 여는 <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> 바인딩 사용, 여기서 개체는 문자열에 대 한 서명입니다. 사용 하 여는 <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> 단계 애니메이션 경로에서 개체에 대 한 시그니처는 <xref:System.Windows.DependencyProperty>합니다. 사용 하 여 <xref:System.Windows.PropertyPath.%23ctor%28System.String%2CSystem.Object%5B%5D%29> 복잡 한 애니메이션에 대 한 서명 합니다. 후자의 생성자는 첫 번째 매개 변수에 토큰 문자열을 사용하고 속성 경로 관계를 정의하기 위해 토큰 문자열의 위치를 채우는 개체 배열을 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.PropertyPath>  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
