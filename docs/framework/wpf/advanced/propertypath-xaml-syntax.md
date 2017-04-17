---
title: "PropertyPath XAML 구문 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "PropertyPath 개체"
  - "XAML, PropertyPath 개체"
ms.assetid: 0e3cdf07-abe6-460a-a9af-3764b4fd707f
caps.latest.revision: 24
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# PropertyPath XAML 구문
<xref:System.Windows.PropertyPath> 개체는 <xref:System.Windows.PropertyPath> 형식을 값으로 사용하는 다양한 속성을 설정하기 위한 복잡한 인라인 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 구문을 지원합니다.  이 항목에서는 바인딩 및 애니메이션 구문에 적용되는 <xref:System.Windows.PropertyPath> 구문에 대해 설명합니다.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="where"></a>   
## PropertyPath 사용 대상  
 <xref:System.Windows.PropertyPath>는 여러 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 기능에 사용되는 공통 개체입니다.  그러나 공통 <xref:System.Windows.PropertyPath>를 사용하여 속성 경로 정보를 제공하더라도 이 개체의 사용 방법은 <xref:System.Windows.PropertyPath>를 형식으로 사용하는 기능 영역마다 다르기 때문에  여기에서는 보다 유용하도록 기능별로 구문을 설명합니다.  
  
 기본적으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 개체 데이터 소스의 속성을 이동하기 위한 개체 모델 경로 및 대상으로 지정된 애니메이션의 경로를 설명하는 데 <xref:System.Windows.PropertyPath>를 사용합니다.  
  
 <xref:System.Windows.Setter.Property%2A?displayProperty=fullName> 같은 일부 스타일 및 템플릿 속성도 겉보기에는 <xref:System.Windows.PropertyPath>와 비슷한 정규화된 속성 이름을 사용합니다.  그러나 이는 <xref:System.Windows.PropertyPath>가 아니며 WPF [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에서 <xref:System.Windows.DependencyProperty>의 형식 변환기와 함께 사용하는 정규화된 *owner.property* 문자열 형식입니다.  
  
<a name="databinding_s"></a>   
## 데이터 바인딩 시 개체의 PropertyPath  
 데이터 바인딩은 원하는 [종속성 속성](GTMT)의 대상 값에 바인딩할 수 있는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기능입니다.  그러나 이러한 데이터 바인딩의 소스는 [종속성 속성](GTMT)뿐 아니라 해당 데이터 공급자가 인식할 수 있는 모든 속성 형식일 수 있습니다.  속성 경로는 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 개체와 해당 속성에서 바인딩 소스를 가져오는 데 사용되는 <xref:System.Windows.Data.ObjectDataProvider>에 주로 사용됩니다.  
  
 참고로 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]에 대한 데이터 바인딩에서는 <xref:System.Windows.Data.Binding>에 <xref:System.Windows.Data.Binding.Path%2A>를 사용하지 않기 때문에 <xref:System.Windows.PropertyPath>를 사용하지 않습니다.  대신, <xref:System.Windows.Data.Binding.XPath%2A>를 사용하고 데이터의 [!INCLUDE[TLA#tla_xmldom](../../../../includes/tlasharptla-xmldom-md.md)]에 올바른 XPath 구문을 지정합니다.  <xref:System.Windows.Data.Binding.XPath%2A>는 문자열로도 지정되지만 여기에 문서화되지 않았습니다. [XMLData Provider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md) 를 참조하십시오.  
  
 데이터 바인딩에서 속성 경로를 사용할 때는 개별 속성 값을 바인딩 대상으로 지정하거나 목록 또는 컬렉션을 사용하는 속성을 바인딩 대상으로 지정할 수 있다는 점을 알아야 합니다.  컬렉션을 바인딩하는 경우, 예를 들어 컬렉션에 있는 데이터 항목 수에 따라 확장되는 <xref:System.Windows.Controls.ListBox>를 바인딩하는 경우에는 속성 경로에서 개별 컬렉션 항목이 아니라 컬렉션 개체를 참조해야 합니다.  데이터 바인딩 엔진은 데이터 소스로 사용된 컬렉션을 바인딩 대상의 형식에 자동으로 일치시켜 <xref:System.Windows.Controls.ListBox>에 항목 배열 채우기 등의 동작을 수행합니다.  
  
<a name="singlecurrent"></a>   
### 직접 연결된 개체에서 데이터 컨텍스트를 나타내는 단일 속성  
  
```  
<Binding Path="propertyName" .../>  
```  
  
 <xref:System.Windows.Data.Binding.Path%2A>를 사용할 때 *propertyName*은 현재 <xref:System.Windows.FrameworkElement.DataContext%2A>에 포함된 속성의 이름이어야 합니다.  바인딩을 통해 소스를 업데이트할 경우 해당 속성이 읽기\/쓰기 가능해야 하며 소스 개체가 변경 가능해야 합니다.  
  
<a name="singleindex"></a>   
### 직접 연결된 개체에서 데이터 컨텍스트를 나타내는 단일 인덱서  
  
```  
<Binding Path="[key]" .../>  
```  
  
 `key`는 사전이나 해시 테이블에 대한 형식화된 인덱스이거나, 배열의 정수 인덱스여야 합니다.  또한 키 값은 해당 키가 적용되는 속성에 직접 바인딩될 수 있는 형식이어야 합니다.  예를 들어 이 방법을 사용하여 문자열 키와 문자열 값을 포함하는 해시 테이블을 <xref:System.Windows.Controls.TextBox>의 Text에 바인딩할 수 있습니다.  또는 키가 컬렉션이나 하위 인덱스를 가리키는 경우 이 구문을 사용하여 대상 컬렉션 속성에 바인딩할 수 있습니다.  이런 경우 이외에는 `<Binding Path="[``key``].``propertyName``" .../>` 같은 구문을 통해 특정 속성을 참조해야 합니다.  
  
 필요한 경우 인덱스 형식을 지정할 수 있습니다.  인덱싱된 속성 경로에 대해 이와 관련된 자세한 내용은 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName>를 참조하십시오.  
  
<a name="multipleindirect"></a>   
### 여러 속성\(간접 속성 대상 지정\)  
  
```  
<Binding Path="propertyName.propertyName2" .../>  
```  
  
 `propertyName`은 현재 <xref:System.Windows.FrameworkElement.DataContext%2A>에 포함된 속성의 이름이어야 합니다.  경로 속성 `propertyName` 및 `propertyName2`는 서로 관련된 모든 속성이 될 수 있으며 여기서 `propertyName2`는 `propertyName` 값의 형식에 포함된 속성이어야 합니다.  
  
<a name="singleattached"></a>   
### 연결되거나 형식이 정규화된 단일 속성  
  
```  
<object property="(ownerType.propertyName)" .../>  
```  
  
 여기서 괄호는 <xref:System.Windows.PropertyPath>의 이 속성을 부분 정규화를 통해 생성해야 함을 나타냅니다.  XML 네임스페이스를 사용하여 적합한 매핑을 포함한 형식을 찾을 수 있습니다.  `ownerType`은 각 어셈블리의 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 선언을 통해 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에서 액세스할 수 있는 형식을 검색합니다.  대부분의 응용 프로그램에는 [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)] 네임스페이스에 기본 XML 네임스페이스가 매핑되기 때문에 일반적으로 사용자 지정 형식이나 XML 네임스페이스의 범위에 포함되지 않는 형식에 대해서만 접두사가 필요합니다.  `propertyName`은 `ownerType`에 있는 속성의 이름이어야 합니다.  일반적으로 이 구문은 다음과 같은 경우 중 하나에 사용됩니다.  
  
-   대상 형식이 지정되지 않은 스타일 또는 템플릿에 포함된 경로를 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]로 지정한 경우.  스타일 또는 템플릿을 사용하지 않는 경우 속성은 형식이 아니라 인스턴스에 존재하기 때문에 정규화된 방식은 일반적으로 이와 같은 경우에만 유효합니다.  
  
-   속성이 연결된 속성인 경우  
  
-   정적 속성에 바인딩하는 경우.  
  
 Storyboard 대상으로 사용하는 경우 `propertyName`으로 지정하는 속성은 <xref:System.Windows.DependencyProperty>이어야 합니다.  
  
<a name="sourcetraversal"></a>   
### 소스 이동\(컬렉션 계층 구조에 바인딩\)  
  
```  
<object Path="propertyName/propertyNameX" .../>  
```  
  
 이 구문에서 \/는 계층적 데이터 소스 개체 내에서 탐색하는 데 사용되며, \/를 여러 개 사용하여 계층 구조 내에서 여러 단계를 이동할 수 있습니다.  소스 이동 시 현재 레코드 포인터 위치가 고려되는데, 현재 레코드 포인터 위치는 데이터와 해당 뷰의 UI를 동기화하여 결정됩니다.  계층적 데이터 소스 개체와의 바인딩 및 데이터 바인딩 시 현재 레코드 포인터의 개념에 대한 자세한 내용은 [계층적 데이터에 마스터\-세부 패턴 사용](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md) 또는 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하십시오.  
  
> [!NOTE]
>  이 구문은 겉보기에는 [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)]와 비슷합니다.  [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터 소스에 바인딩하기 위한 실제 [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)] 식은 <xref:System.Windows.Data.Binding.Path%2A> 값으로 사용하는 대신 함께 사용할 수 없는 <xref:System.Windows.Data.Binding.XPath%2A> 속성에 사용해야 합니다.  
  
### 컬렉션 뷰  
 명명된 컬렉션 뷰를 참조하려면 컬렉션 뷰 이름 앞에 해시 문자\(`#`\)를 추가합니다.  
  
### 현재 레코드 포인터  
 마스터 세부 데이터 바인딩 시나리오나 컬렉션 보기의 현재 레코드 포인터를 참조하려면 경로 문자열을 슬래시\(`/`\)로 시작합니다.  슬래시 다음에 나오는 경로는 현재 레코드 포인터부터 이동합니다.  
  
### 여러 인덱서  
  
```  
<object Path="[index1,index2...]" .../>  
or  
<object Path="propertyName[index,index2...]" .../>  
```  
  
 지정한 개체가 인덱서를 여러 개 지원하는 경우 배열 참조 구문과 마찬가지로 해당 인덱서를 순서대로 지정할 수 있습니다.  대상 개체는 현재 컨텍스트이거나 여러 인덱스 개체를 포함하는 속성의 값일 수 있습니다.  
  
 기본적으로 인덱서 값은 기본 개체의 특성을 사용하여 형식이 지정됩니다.  필요한 경우 인덱스 형식을 지정할 수 있습니다.  인덱서 형식 지정에 대한 자세한 내용은 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName>를 참조하십시오.  
  
<a name="mixing"></a>   
### 구문 혼합  
 위에서 설명한 각 구문은 서로 혼합하여 사용할 수 있습니다.  예를 들어 다음 예제와 같이 <xref:System.Windows.Media.SolidColorBrush> 개체의 픽셀 모눈 배열이 포함된 `ColorGrid` 속성의 특정 x, y 지점에 있는 색의 속성 경로를 만들 수 있습니다.  
  
```  
<Rectangle Fill="{Binding ColorGrid[20,30].SolidColorBrushResult}" .../>  
```  
  
### 속성 경로 문자열의 이스케이프  
 특정 비즈니스 개체의 경우, 올바르게 구문 분석하기 위해 속성 경로 문자열에 이스케이프 시퀀스가 필요한 상황이 발생할 수 있습니다.  이러한 문자의 대부분은 비즈니스 개체 정의에 일반적으로 사용되는 언어에서 비슷한 이름 지정 상호 작용 문제를 가지고 있으므로 이스케이프는 꼭 필요한 경우에만 수행해야 합니다.  
  
-   인덱서\(\[ \]\) 안에서 캐럿 문자\(^\)는 다음 문자를 이스케이프합니다.  
  
-   XML 엔터티를 사용하여 XML 언어 정의에 특별한 의미를 갖는 특수 문자를 이스케이프해야 합니다.  "&" 문자는 `&`을 사용하여 이스케이프합니다.  닫는 태그 "\>"는 `>`을 사용하여 이스케이프합니다.  
  
-   태그 확장 처리를 위해 백슬래시\(`\`\)를 사용하여 WPF XAML 파서 동작에서 특수한 의미를 갖는 문자를 이스케이프해야 합니다.  
  
    -   백슬래시\(`\`\)는 이스케이프 문자 자체입니다.  
  
    -   등호\(`=`\)는 속성 이름과 속성 값을 구분합니다.  
  
    -   쉼표\(`,`\)는 속성을 구분합니다.  
  
    -   닫는 중괄호\(`}`\)는 태그 확장의 끝을 나타냅니다.  
  
> [!NOTE]
>  기술적으로 이러한 이스케이프는 스토리보드 속성 경로에 대해서도 실행되지만 대개는 기존 WPF 개체의 개체 모델을 이동하고 이스케이프가 필요하지 않아야 합니다.  
  
<a name="databinding_sa"></a>   
## 애니메이션 대상의 PropertyPath  
 애니메이션의 대상 속성은 형식이 <xref:System.Windows.Freezable> 또는 기본 형식인 [종속성 속성](GTMT)이어야 합니다.  그러나 형식의 대상 속성과 최종 애니메이션 속성의 개체는 서로 다를 수 있습니다.  애니메이션의 경우 속성 경로는 속성 값에 개체\-속성 관계를 지정하여, 명명된 애니메이션 대상 개체의 속성과 의도된 대상 애니메이션 속성 사이의 연결을 정의하는 데 사용됩니다.  
  
<a name="general"></a>   
### 애니메이션을 사용할 때의 일반적인 개체\-속성 고려 사항  
 일반적인 애니메이션 개념에 대한 자세한 내용은 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md) 및 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하십시오.  
  
 애니메이션 대상의 값 형식 또는 속성은 <xref:System.Windows.Freezable> 또는 기본 형식이어야 합니다.  경로의 시작 부분에 나오는 속성은 지정된 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 형식에 포함된 [종속성 속성](GTMT)의 이름이어야 합니다.  
  
 이미 고정된 <xref:System.Windows.Freezable> 애니메이션의 복제를 지원하려면 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>에 지정된 개체가 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>에서 파생된 클래스여야 합니다.  
  
<a name="singlestepanim"></a>   
### 대상 개체의 단일 속성  
  
```  
<animation Storyboard.TargetProperty="propertyName" .../>  
```  
  
 `propertyName`은 지정한 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 형식에 포함된 [종속성 속성](GTMT)의 이름이어야 합니다.  
  
<a name="indirectanim"></a>   
### 간접 속성 대상 지정  
  
```  
<animation Storyboard.TargetProperty="propertyName.propertyName2" .../>  
```  
  
 `propertyName`은 지정한 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 형식에 포함된 <xref:System.Windows.Freezable> 값 형식 또는 기본 형식의 속성이어야 합니다.  
  
 `propertyName2`는 `propertyName`의 값인 개체에 포함된 [종속성 속성](GTMT)의 이름이어야 합니다.  즉, `propertyName2`는 형식이 `propertyName` <xref:System.Windows.DependencyProperty.PropertyType%2A>에 포함된 종속성 속성이어야 합니다.  
  
 간접 애니메이션 대상 지정은 적용되는 스타일과 템플릿에 필요합니다.  애니메이션 대상을 지정하려면 대상 개체의 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>이 필요하며, 이 이름은 [x:Name](../../../../docs/framework/xaml-services/x-name-directive.md) 또는 <xref:System.Windows.FrameworkElement.Name%2A>으로 설정해야 합니다.  템플릿과 스타일 요소도 이름을 가질 수 있지만 이러한 이름은 해당 스타일 및 템플릿의 이름 범위 내에서만 유효합니다.  템플릿 및 스타일이 응용 프로그램 태그와 이름 범위를 공유하는 경우,  스타일과 템플릿은 인스턴스 사이에 실제로 공유되어 중복 이름이 사용되므로 해당 이름이 고유할 수 없습니다. 따라서 애니메이션을 적용할 요소의 개별 속성이 스타일 또는 템플릿에 포함된 경우에는 스타일 템플릿에서 가져오지 않은 명명된 요소 인스턴스로 시작한 후 스타일 또는 템플릿의 시각적 트리에서 애니메이션을 적용할 속성으로 대상을 지정해야 합니다.  
  
 예를 들어 <xref:System.Windows.Controls.Panel>의 <xref:System.Windows.Controls.Panel.Background%2A> 속성은 테마 템플릿에 포함된 완전한 <xref:System.Windows.Media.Brush>\(실제로는 <xref:System.Windows.Media.SolidColorBrush>\)입니다.  <xref:System.Windows.Media.Brush>에 애니메이션을 적용하려면 각 <xref:System.Windows.Media.Brush> 형식에 대해 BrushAnimation이 하나씩 필요할 수 있는데, 이러한 형식은 없습니다.  따라서 이렇게 하는 대신 특정 <xref:System.Windows.Media.Brush> 형식의 속성에 애니메이션 효과를 적용합니다.  그러려면 <xref:System.Windows.Media.SolidColorBrush>에서 <xref:System.Windows.Media.SolidColorBrush.Color%2A>로 이동한 후 이 속성에 <xref:System.Windows.Media.Animation.ColorAnimation>을 적용해야 합니다.  이 예제에서 속성 경로는 `Background.Color`입니다.  
  
<a name="attachedanim"></a>   
### 연결된 속성  
  
```  
<animation Storyboard.TargetProperty="(ownerType.propertyName)" .../>  
```  
  
 여기서 괄호는 <xref:System.Windows.PropertyPath>의 이 속성을 부분 정규화를 통해 생성해야 함을 나타냅니다.  XML 네임스페이스를 사용하여 형식을 찾을 수 있습니다.  `ownerType`은 각 어셈블리의 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 선언을 통해 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에서 액세스할 수 있는 형식을 검색합니다.  대부분의 응용 프로그램에는 [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)] 네임스페이스에 기본 XML 네임스페이스가 매핑되기 때문에 일반적으로 사용자 지정 형식이나 XML 네임스페이스의 범위에 포함되지 않는 형식에 대해서만 접두사가 필요합니다.  `propertyName`은 `ownerType`에 있는 속성의 이름이어야 합니다.  `propertyName`으로 지정한 속성은 <xref:System.Windows.DependencyProperty>여야 합니다.  모든 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 연결 속성은 종속성 속성으로 구현되기 때문에 이러한 문제는 사용자 지정 연결 속성에만 해당됩니다.  
  
<a name="indexanim"></a>   
### 인덱서  
  
```  
<animation Storyboard.TargetProperty="propertyName.propertyName2[index].propertyName3" .../>  
```  
  
 대부분의 종속성 속성 또는 <xref:System.Windows.Freezable> 형식은 인덱서를 지원하지 않습니다.  따라서 애니메이션 경로를 지정할 때 인덱서는 명명된 대상과 실제 애니메이션 속성의 체인을 시작하는 속성의 중간 위치에 사용됩니다.  이 구문에서는 `propertyName2`가 이에 해당합니다.  예를 들어 `RenderTransform.Children[1].Angle` 같은 속성 경로에서 중간 속성이 <xref:System.Windows.Media.TransformGroup> 같은 컬렉션인 경우 인덱서가 필요할 수 있습니다.  
  
<a name="ppincode"></a>   
## 코드에서의 PropertyPath  
 <xref:System.Windows.PropertyPath>를 생성하는 방법을 포함하여 <xref:System.Windows.PropertyPath> 코드 사용법에 대한 자세한 내용은 <xref:System.Windows.PropertyPath>의 참조 항목에 설명되어 있습니다.  
  
 일반적으로 <xref:System.Windows.PropertyPath>는 두 가지 생성자를 사용하도록 디자인되었습니다. 하나는 바인딩 및 간단한 애니메이션에 사용할 수 있는 생성자이고 다른 하나는 복잡한 애니메이션에 사용할 수 있는 생성자입니다.  <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> 시그니처는 문자열인 개체를 바인딩할 때 사용하고,  개체가 <xref:System.Windows.DependencyProperty>인 경우 단일 단계 애니메이션 경로를 지정할 때도 <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> 시그니처를 사용합니다.  [PropertyPath\(String, Object\<xref:System.Windows.PropertyPath.%23ctor%28System.String%2CSystem.Object%5B%5D%29> 시그니처는 복잡한 애니메이션에 사용합니다.  이 두 번째 생성자는 첫 번째 매개 변수에 토큰 문자열을 사용하고, 토큰 문자열의 위치를 채우는 개체 배열을 사용하여 속성 경로 관계를 정의합니다.  
  
## 참고 항목  
 <xref:System.Windows.PropertyPath>   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)