---
title: "바인딩 선언 개요 | Microsoft Docs"
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
  - "데이터 바인딩, 선언"
  - "바인딩 선언"
  - "데이터 바인딩(data binding), 선언"
  - "태그 확장"
  - "개체 요소 구문"
  - "구문, 개체 요소"
ms.assetid: b97fd626-4c0d-4761-872a-2bca5820da2c
caps.latest.revision: 34
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 33
---
# 바인딩 선언 개요
이 항목에서는 바인딩을 선언하는 여러 가지 방법을 설명합니다.  
  
   
  
<a name="Prereq"></a>   
## 사전 요구 사항  
 이 항목을 읽기 전에 먼저 태그 확장의 개념과 사용 방법을 잘 알고 있어야 합니다.  태그 확장에 대한 자세한 내용은 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)을 참조하십시오.  
  
 이 항목에서는 데이터 바인딩 개념은 다루지 않습니다.  데이터 바인딩 개념에 대한 자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하십시오.  
  
<a name="BindinginXAML"></a>   
## XAML에서 바인딩 선언  
 이 단원에서는 XAML에서 바인딩을 선언하는 방법을 설명합니다.  
  
<a name="MarkupExtensionSyntax"></a>   
### 태그 확장 사용  
 <xref:System.Windows.Data.Binding>은 태그 확장입니다.  바인딩 확장을 사용하여 바인딩을 선언하는 경우 선언은 `Binding` 키워드 뒤에 오며 쉼표\(,\)로 구분된 일련의 절로 구성됩니다.  바인딩 선언의 절은 원하는 순서에 관계없이 지정할 수 있으며 다양하게 조합할 수 있습니다.  사용할 수 있는 절은 *Name*\=*Value* 쌍이며 여기서 *Name*은 <xref:System.Windows.Data.Binding> 속성의 이름이고 *Value*는 속성에 설정할 값입니다.  
  
 바인딩 선언 문자열을 태그로 만들 때는 대상 개체의 특정 [종속성 속성](GTMT)에 문자열을 연결해야 합니다.  다음 예제에서는 <xref:System.Windows.Data.Binding.Source%2A> 및 <xref:System.Windows.Data.Binding.Path%2A> 속성을 지정하여 바인딩 확장을 통해 <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=fullName> 속성을 바인딩하는 방법을 보여 줍니다.  
  
 [!code-xml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 <xref:System.Windows.Data.Binding> 클래스의 속성 대부분은 이 방법으로 지정할 수 있습니다.  바인딩 확장에 대한 자세한 내용 및 바인딩 확장을 사용하여 설정할 수 없는 <xref:System.Windows.Data.Binding> 속성의 목록을 보려면 [Binding 태그 확장](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) 개요를 참조하십시오.  
  
<a name="ObjectElementSyntax"></a>   
### 개체 요소 구문  
 개체 요소 구문은 바인딩 선언을 작성하는 대신 사용할 수 있는 방법입니다.  대부분의 경우에는 태그 확장을 사용하든 개체 요소 구문을 사용하든 큰 차이가 없습니다.  그러나 속성 값이 문자열 형식이 아니고 해당 형식에 대한 형식 변환기가 지원되지 않는 경우와 같이 태그 확장을 사용할 수 없을 때는 개체 요소 구문을 대신 사용해야 합니다.  
  
 다음 예제에서는 개체 요소 구문과 태그 확장 둘 모두 사용합니다.  
  
 [!code-xml[BindConversionMarkup#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindConversionMarkup/CSharp/Page1.xaml#1)]  
  
 이 예제에서는 확장 구문을 통해 바인딩을 선언하여 <xref:System.Windows.Controls.TextBlock.Foreground%2A> 속성을 바인딩하고,  개체 요소 구문을 사용하여 <xref:System.Windows.Controls.TextBlock.Text%2A> 속성의 바인딩을 선언합니다.  
  
 용어에 대한 자세한 내용은 [XAML 구문 정보](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)를 참조하십시오.  
  
<a name="MBandPB"></a>   
### MultiBinding 및 PriorityBinding  
 <xref:System.Windows.Data.MultiBinding> 및 <xref:System.Windows.Data.PriorityBinding>에는 XAML 확장 구문을 사용할 수 없습니다.  따라서 XAML에서 <xref:System.Windows.Data.MultiBinding> 또는 <xref:System.Windows.Data.PriorityBinding>을 선언할 때는 개체 요소 구문을 사용해야 합니다.  
  
<a name="BindinginCode"></a>   
## 코드에서 바인딩 만들기  
 코드에서 <xref:System.Windows.Data.Binding> 개체에 속성을 직접 설정하여 바인딩을 지정할 수도 있습니다.  다음 예제에서는 코드에서 <xref:System.Windows.Data.Binding> 개체를 만들고 속성을 지정하는 방법을 보여 줍니다.  이 예제에서 `TheConverter`는 <xref:System.Windows.Data.IValueConverter> 인터페이스를 구현하는 개체입니다.  
  
 [!code-csharp[BindConversion#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindConversion/CSharp/Window1.xaml.cs#1)]
 [!code-vb[BindConversion#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindConversion/visualbasic/window1.xaml.vb#1)]  
[!code-csharp[BindConversion#end1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindConversion/CSharp/Window1.xaml.cs#end1)]
[!code-vb[BindConversion#end1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindConversion/visualbasic/window1.xaml.vb#end1)]  
  
 바인딩하는 개체가 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>인 경우에는 <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=fullName>을 사용하는 대신 개체에서 `SetBinding` 메서드를 직접 호출할 수 있습니다.  예제를 보려면 [코드에서 바인딩 만들기](../../../../docs/framework/wpf/data/how-to-create-a-binding-in-code.md)를 참조하십시오.  
  
<a name="Path_Syntax"></a>   
## 바인딩 경로 구문  
 <xref:System.Windows.Data.Binding.Path%2A> 속성을 사용하여 다음과 같이 바인딩할 소스 값을 지정합니다.  
  
-   가장 간단한 경우에는 <xref:System.Windows.Data.Binding.Path%2A> 속성 값이 바인딩에 사용할 소스 개체의 속성 이름\(예: `Path=PropertyName`\)입니다.  
  
-   [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)]에서 사용하는 것과 유사한 구문을 사용하여 속성의 하위 속성을 지정할 수 있습니다.  예를 들어 `Path=ShoppingCart.Order` 절은 `ShoppingCart`라는 개체 또는 속성의 `Order` 하위 속성에 대한 바인딩을 설정합니다.  
  
-   [연결된 속성](GTMT)에 바인딩하려면 [연결된 속성](GTMT)을 괄호로 묶습니다.  예를 들어 [연결된 속성](GTMT) <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName>에 바인딩하려면 `Path=(DockPanel.Dock)` 구문을 사용합니다.  
  
-   속성의 인덱서는 인덱서가 적용된 속성의 이름 다음에 대괄호로 묶어서 지정할 수 있습니다.  예를 들어 `Path=ShoppingCart[0]` 절은 속성의 내부 인덱싱에서 리터럴 문자열 "0"을 처리하는 방법에 해당하는 인덱스에 대한 바인딩을 설정합니다.  중첩 인덱서도 지원됩니다.  
  
-   `Path=ShoppingCart.ShippingInfo[MailingAddress,Street]`와 같이 인덱서와 하위 속성을 `Path` 절에 혼합하여 사용할 수 있습니다.  
  
-   인덱서 안에는 여러 인덱서 매개 변수를 쉼표\(,\)로 구분하여 지정할 수 있습니다.  이때 각 매개 변수의 형식은 괄호 안에 지정할 수 있습니다.  예를 들면 `Path="[(sys:Int32)42,(sys:Int32)24]"`와 같이 지정하고, 여기서 `sys`는 `System` 네임스페이스에 매핑됩니다.  
  
-   소스가 컬렉션 뷰이면 슬래시\(\/\)를 사용하여 현재 항목을 지정할 수 있습니다.  예를 들어 `Path=/` 절은 바인딩을 뷰의 현재 항목으로 설정합니다.  소스가 컬렉션인 경우 이 구문은 기본 컬렉션 뷰의 현재 항목을 지정합니다.  
  
-   속성 이름과 슬래시를 결합하여 컬렉션 속성을 이동할 수 있습니다.  예를 들어 `Path=/Offices/ManagerName`은 소스 컬렉션의 현재 항목을 지정합니다. 소스 컬렉션에는 `Offices` 속성이 포함되어 있으며 이 속성 또한 컬렉션입니다.  소스 컬렉션의 현재 항목은 `ManagerName` 속성이 있는 개체입니다.  
  
-   경우에 따라 마침표\(.\) 경로를 사용하여 현재 소스에 바인딩할 수도 있습니다.  예를 들어, `Text="{Binding}"`은 `Text="{Binding Path=.}"`와 같습니다.  
  
### 이스케이프 메커니즘  
  
-   인덱서\(\[ \]\) 안에서 캐럿 문자\(^\)는 다음 문자를 이스케이프합니다.  
  
-   XAML에서 <xref:System.Windows.Data.Binding.Path%2A>를 설정할 경우에도 XML 엔터티를 사용하여 XML 언어 정의에 특별한 의미를 갖는 특수 문자를 이스케이프해야 합니다.  
  
    -   "&" 문자는 `&`을 사용하여 이스케이프합니다.  
  
    -   닫는 태그 "\>"는 `>`을 사용하여 이스케이프합니다.  
  
-   태그 확장 구문을 사용하여 특성에 바인딩 전체를 지정하는 경우에도 백슬래시\(\\\)를 사용하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 태그 확장 파서에서 특수한 의미를 갖는 특수 문자를 이스케이프해야 합니다.  
  
    -   백슬래시\(\\\)는 이스케이프 문자 자체입니다.  
  
    -   등호\(\=\)는 속성 이름과 속성 값을 구분합니다.  
  
    -   쉼표\(,\)는 속성을 구분합니다.  
  
    -   닫는 중괄호\(}\)는 태그 확장의 끝을 나타냅니다.  
  
<a name="Default"></a>   
## 기본 동작  
 선언에 별도로 지정하지 않을 경우 기본 동작은 다음과 같습니다.  
  
-   [바인딩 소스](GTMT) 값과 [바인딩 대상](GTMT) 값 사이의 형식 변환을 시도하는 기본 변환기가 만들어집니다.  변환을 수행할 수 없으면 기본 변환기가 `null`을 반환합니다.  
  
-   <xref:System.Windows.Data.Binding.ConverterCulture%2A>를 설정하지 않으면 바인딩 엔진은 [바인딩 대상](GTMT) 개체의 `Language` 속성을 사용합니다.  XAML에서는 기본값으로 "en\-US"를 사용하거나, 속성을 명시적으로 설정한 경우, 페이지의 루트 요소나 기타 요소에서 값이 상속됩니다.  
  
-   바인딩에 데이터 컨텍스트\(예: 부모 요소에서 상속된 데이터 컨텍스트\)가 이미 있고 해당 컨텍스트에서 반환되는 항목이나 컬렉션을 별도의 경로 수정 없이 그대로 바인딩할 수 있는 경우에는 `{Binding}`과 같이 바인딩 선언에 절을 사용하지 않아도 됩니다. 데이터 스타일을 지정하는 경우와 같이 컬렉션에 대해 바인딩을 수행할 때는 주로 이 방법으로 바인딩을 지정합니다.  자세한 내용은 [바인딩 소스 개요](../../../../docs/framework/wpf/data/binding-sources-overview.md)에서 "바인딩 소스로 사용되는 전체 개체" 단원을 참조하십시오.  
  
-   기본 <xref:System.Windows.Data.Binding.Mode%2A>는 바인딩하는 [종속성 속성](GTMT)에 따라 양방향 또는 단방향으로 설정됩니다.  그러나 바인딩 모드는 원하는 방법으로 바인딩되도록 언제든지 명시적으로 선언할 수 있습니다.  대개 <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=fullName> 및 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A?displayProperty=fullName>와 같이 사용자가 편집할 수 있는 컨트롤 속성에는 양방향 바인딩이 기본적으로 사용되고, 대부분의 다른 속성에는 단방향 바인딩이 기본적으로 사용됩니다.  
  
-   기본 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값도 바인딩되는 [종속성 속성](GTMT)에 따라 <xref:System.Windows.Data.UpdateSourceTrigger> 또는 <xref:System.Windows.Data.UpdateSourceTrigger>로 설정됩니다.  대부분의 [종속성 속성](GTMT)은 기본값이 <xref:System.Windows.Data.UpdateSourceTrigger>이지만 <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=fullName> 속성의 기본값은 <xref:System.Windows.Data.UpdateSourceTrigger>입니다.  
  
## 참고 항목  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)   
 [데이터 바인딩](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [PropertyPath XAML 구문](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md)