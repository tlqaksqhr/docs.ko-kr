---
title: "TypeConverter 및 XAML | Microsoft Docs"
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
  - "클래스, TypeConverter"
  - "TypeConverter 클래스"
  - "XAML, TypeConverter 클래스"
ms.assetid: f6313e4d-e89d-497d-ac87-b43511a1ae4b
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# TypeConverter 및 XAML
이 항목에서는 일반적인 XAML 언어 기능인 문자열 형식 변환의 목적에 대해 소개합니다.  .NET Framework에서 <xref:System.ComponentModel.TypeConverter> 클래스에는 관리되는 사용자 지정 클래스에 대한 구현에서 XAML 특성 구문의 속성 값으로 사용할 수 있는 특수한 기능이 있습니다.  사용자 지정 클래스를 작성한 다음 클래스의 인스턴스를 XAML에서 설정할 수 있는 특성 값으로 사용하려면 클래스에 <xref:System.ComponentModel.TypeConverterAttribute>를 적용하거나, 사용자 지정 <xref:System.ComponentModel.TypeConverter> 클래스를 작성하거나, 둘 다 수행해야 합니다.  
  
   
  
## 형식 변환 개념  
  
### XAML 및 문자열 값  
 XAML 파일에서 특성 값을 설정할 때 값의 초기 형식은 일반 텍스트인 문자열입니다.  <xref:System.Double>과 같은 다른 기본 형식도 처음에는 XAML 프로세서에 대해 텍스트 문자열입니다.  
  
 XAML 프로세서가 특성 값을 처리하려면 두 가지 정보가 있어야 합니다.  그 중 하나는 설정할 속성의 값 형식입니다.  특성 값을 정의하며 XAML에서 처리되는 모든 문자열은 궁극적으로 이 형식의 값으로 변환되거나 확인되어야 합니다.  값이 XAML 파서가 이해하는 기본 형식\(예: 숫자 값\)이면 문자열을 직접 변환하려고 합니다.  값이 열거형이면 이 문자열을 사용하여 해당 열거형에서 일치하는 명명된 상수가 있는지 확인합니다.  값이 파서가 이해하는 기본 형식도 아니고 열거형도 아닌 경우 해당 형식은 변환되는 문자열에 따라 형식의 인스턴스 또는 값을 제공할 수 있어야 합니다.  이 작업은 형식 변환기 클래스를 지정하여 수행됩니다.  형식 변환기는 XAML 시나리오와 .NET 코드에서 코드 호출을 위해 또 다른 클래스의 값을 제공하는 데 사용할 수 있는 도우미 클래스입니다.  
  
### XAML에서 기존 형식 변환 동작 사용  
 기본 XAML 개념에 얼마나 익숙한지에 따라 자신도 모르는 사이에 기본 응용 프로그램 XAML에서 형식 변환 동작을 이미 사용했을 수 있습니다.  예를 들어 WPF는 <xref:System.Windows.Point> 형식의 값을 사용하는 수백 개의 속성을 정의합니다.  <xref:System.Windows.Point>는 2차원 좌표 공간에서 좌표를 설명하는 값이며 두 가지 중요한 속성인 <xref:System.Windows.Point.X%2A> 및 <xref:System.Windows.Point.Y%2A>만 갖고 있습니다.  XAML에서 점을 지정하는 경우 제공하는 <xref:System.Windows.Point.X%2A> 및 <xref:System.Windows.Point.Y%2A> 값 사이에 구분 기호\(대개 쉼표\)를 사용하여 문자열로 점을 지정합니다.  예를 들어 `<LinearGradientBrush StartPoint="0,0" EndPoint="1,1">`과 같이 지정합니다.  
  
 이렇게 간단한 <xref:System.Windows.Point> 형식과 XAML에서 이 형식의 간단한 사용에도 형식 변환기가 필요합니다.  이 경우에 형식 변환기는 <xref:System.Windows.PointConverter> 클래스입니다.  
  
 클래스 수준에서 정의된 <xref:System.Windows.Point>의 형식 변환기는 <xref:System.Windows.Point>를 사용하는 모든 속성의 태그 사용을 간소화합니다.  여기에서 형식 변환기가 없으면 앞의 예제에 다음과 같이 훨씬 자세한 태그가 필요합니다.  
  
 `<LinearGradientBrush>`  
  
 `<LinearGradientBrush.StartPoint>`  
  
 `<Point X="0" Y="0"/>`  
  
 `</LinearGradientBrush.StartPoint>`  
  
 `<LinearGradientBrush.EndPoint>`  
  
 `<Point X="1" Y="1"/>`  
  
 `</LinearGradientBrush.EndPoint>`  
  
 `<LinearGradientBrush>`  
  
 형식 변환 문자열을 사용할지, 아니면 더 자세한 동등한 구문을 사용할지는 일반적으로 코딩 스타일에 따라 선택합니다.  XAML 도구 워크플로는 값이 설정되는 방식에도 영향을 미칠 수 있습니다.  일부 XAML 도구는 디자이너 뷰 또는 자체 serialization 메커니즘으로의 라운드트립에 더 쉽기 때문에 가장 자세한 형태의 태그를 내보내는 경향이 있습니다.  
  
 적용된 <xref:System.ComponentModel.TypeConverterAttribute>가 있는지 클래스나 속성에서 확인하여 WPF 및 .NET Framework 형식에 대한 기존 형식 변환기를 찾을 수 있습니다.  이 특성은 XAML 용도나 다른 용도로 해당 형식의 값에 대한 지원 형식 변환기인 클래스의 이름을 지정합니다.  
  
### 형식 변환기 및 태그 확장  
 태그 확장과 형식 변환기는 XAML 프로세서 동작과 적용되는 시나리오의 측면에서 서로 교차하는 역할을 합니다.  태그 확장 사용에 컨텍스트를 사용할 수 있지만 태그 확장이 값을 제공하는 속성의 형식 변환 동작은 일반적으로 태그 확장 구현에서 확인되지 않습니다.  즉, 태그 확장이 `ProvideValue` 출력으로 텍스트 문자열을 반환하는 경우에도 특정 속성이나 속성 값 형식에 적용될 때 해당 문자열에서 형식 변환 동작이 호출되지 않습니다. 일반적으로 태그 확장의 목적은 형식 변환기 없이 문자열을 처리하고 개체를 반환하는 것입니다.  
  
 일반적으로 형식 변환기 대신 태그 확장이 필요한 경우는 이미 있는 개체를 참조하는 경우입니다.  상태 비저장 형식 변환기는 새 인스턴스만 생성할 수 있으며 이는 바람직하지 않을 수도 있습니다.  태그 확장에 대한 자세한 내용은 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)을 참조하십시오.  
  
### 네이티브 형식 변환기:  
 XAML 파서의 WPF 및 .NET Framework 구현에는 네이티브 형식 변환 처리가 있지만 일반적으로 기본 형식으로 간주될 수 있는 형식이 아닌 특정 형식이 있습니다.  이러한 형식의 예로는 <xref:System.DateTime>이 있습니다.  이에 대한 이유는 .NET Framework 아키텍처의 작동 방식을 바탕으로 합니다. <xref:System.DateTime> 형식은 .NET의 가장 기본적인 라이브러리인 mscorlib에서 정의됩니다.  <xref:System.DateTime>의 경우 특성 지정에 의한 일반적인 형식 변환기 검색 메커니즘을 지원할 수 없도록 하기 위해 종속성\(<xref:System.ComponentModel.TypeConverterAttribute>는 System에서 제공됨\)을 도입하는 다른 어셈블리에서 제공하는 특성이 지정될 수 없습니다.  대신 XAML 파서는 이러한 기본 처리가 필요한 형식의 목록을 갖고 있으며 실제 기본 형식이 처리되는 방식과 유사하게 이러한 형식을 처리합니다.  <xref:System.DateTime>의 경우 여기에는 <xref:System.DateTime.Parse%2A> 호출이 포함됩니다.  
  
<a name="Implementing_a_Type_Converter"></a>   
## 형식 변환기 구현  
  
### TypeConverter  
 앞의 <xref:System.Windows.Point> 예제에는 <xref:System.Windows.PointConverter> 클래스가 나와 있습니다.  XAML의 .NET 구현의 경우 XAML 용도로 사용되는 모든 형식 변환기는 기본 클래스인 <xref:System.ComponentModel.TypeConverter>에서 파생되는 클래스입니다.  <xref:System.ComponentModel.TypeConverter> 클래스는 XAML이 도입되기 전의 .NET Framework 버전에도 있습니다. 이 클래스의 원래 용도 중 하나는 비주얼 디자이너에서 속성 대화 상자에 문자열 변환을 제공하는 것입니다.  XAML을 위해 <xref:System.ComponentModel.TypeConverter>는 문자열 특성 값을 구문 분석할 수 있도록 하는 문자열 변환을 위한 기본 클래스이며 특정 개체 속성의 런타임 값을 특성으로 serialization을 위해 문자열로 다시 처리하는 역할까지 수행합니다.  
  
 <xref:System.ComponentModel.TypeConverter>는 XAML 처리를 위한 문자열 변환에 관련된 네 개의 멤버를 정의합니다.  
  
-   <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A>  
  
-   <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A>  
  
-   <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>  
  
-   <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>  
  
 이 중에서 가장 중요한 메서드는 <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>입니다.  이 메서드는 입력 문자열을 필요한 개체 형식으로 변환합니다.  엄격하게 말하면 <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> 메서드는 훨씬 넓은 범위의 형식을 변환기의 의도한 대상 형식으로 변환하도록 구현될 수 있으므로 런타임 변환 지원과 같은 XAML을 벗어나는 기능을 수행하지만 XAML 용도를 위해 중요한 <xref:System.String> 입력을 처리할 수 있는 유일한 코드 경로입니다.  
  
 그 다음으로 중요한 메서드는 <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>입니다.  응용 프로그램을 태그 표현으로 변환하는 경우\(예: 응용 프로그램을 파일로 XAML에 저장하는 경우\) <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>는 태그 표현을 생성하는 작업을 담당합니다.  이 경우 XAML에 중요한 코드 경로는 <xref:System.String>의 `destinationType`을 전달할 때입니다.  
  
 <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A>와 <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A>은 서비스에서 <xref:System.ComponentModel.TypeConverter> 구현의 기능을 쿼리할 때 사용되는 지원 메서드입니다.  이러한 메서드는 변환기와 동등한 변환 메서드가 지원하는 형식과 관련된 경우에 `true`를 반환하도록 구현해야 합니다.  XAML 용도를 위해 이는 일반적으로 <xref:System.String> 형식을 의미합니다.  
  
### XAML의 문화권 정보 및 형식 변환기  
 각 <xref:System.ComponentModel.TypeConverter> 구현은 변환할 수 있는 문자열을 구성하는 요소를 고유한 방식으로 해석할 수 있습니다. 또한 매개 변수로 전달된 형식 설명을 사용하거나 무시할 수 있습니다.  문화권 및 XAML 형식 변환과 관련하여 고려할 중요한 사항이 있습니다.  지역화할 수 있는 문자열을 특성 값으로 사용하는 것은 XAML에서 완전히 지원됩니다.  그러나 XAML 특성 값의 형식 변환기가 `en-US` 문화권을 사용하여 반드시 수정된 언어 구문 분석 동작을 수행하기 때문에 지역화할 수 있는 문자열을 특정한 문화권 요구 사항이 있는 형식 변환기 입력으로 사용하는 것은 지원되지 않습니다.  이러한 제한의 디자인 이유에 대한 자세한 내용은 XAML 언어 사양\([\[MS\-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525)\)을 참조하십시오.  
  
 문화권이 문제가 될 수 있는 예로 쉼표를 숫자의 소수점 구분 기호로 사용하는 일부 문화권을 들 수 있습니다.  이는 일반적인 X,Y 형태 또는 쉼표로 구분된 목록과 같은 선례에 따라 쉼표를 구분 기호로 사용하는 많은 WPF XAML 형식 변환기의 동작과 충돌합니다.  XAML로 묶어 문화권을 전달하는 방법\(이런 식으로 십진수에 쉼표를 사용하는 문화권의 예인 `sl-SI` 문화권으로 `Language` 또는 `xml:lang`를 설정\)으로도 문제가 해결되지 않습니다.  
  
### ConvertFrom 구현  
 XAML을 지원하는 <xref:System.ComponentModel.TypeConverter> 구현으로 사용할 수 있으려면 해당 변환기의 <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> 메서드가 문자열을 `value` 매개 변수로 받아들여야 합니다.  문자열의 형식이 올바르고 <xref:System.ComponentModel.TypeConverter> 구현을 통해 변환할 수 있으면 반환된 개체를 속성에 필요한 형식으로 캐스팅할 수 있어야 합니다.  그렇지 않으면 <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> 구현이 `null`을 반환해야 합니다.  
  
 각 <xref:System.ComponentModel.TypeConverter> 구현은 변환할 수 있는 문자열을 구성하는 요소를 고유한 방식으로 해석할 수 있습니다. 또한 매개 변수로 전달된 형식 설명이나 문화권 컨텍스트를 사용하거나 무시할 수 있습니다.  하지만 어떤 경우에 해당하든 WPF XAML 처리에서 형식 설명 컨텍스트에 값을 전달하지 않거나 `xml:lang`를 기반으로 문화권을 전달하지 않을 수도 있습니다.  
  
> [!NOTE]
>  문자열 형식의 요소로 중괄호, 특히 {는 사용하지 마십시오.  이러한 문자는 태그 확장 시퀀스의 시작과 끝에 사용하도록 예약되어 있습니다.  
  
### ConvertTo 구현  
 <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>는 serialization을 지원하기 위해 사용됩니다.  사용자 지정 형식과 해당 형식 변환기에 대한 <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>를 통한 serialization 지원은 필수 요구 사항이 아닙니다.  하지만 컨트롤을 구현하거나 클래스의 기능 또는 디자인의 일부로 serialization을 사용하는 경우에는 <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>를 구현해야 합니다.  
  
 XAML을 지원하는 <xref:System.ComponentModel.TypeConverter> 구현으로 사용할 수 있으려면 해당 변환기의 <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> 메서드가 지원되는 형식 또는 값의 인스턴스를 `value` 매개 변수로 받아들여야 합니다.  `destinationType` 매개 변수가 <xref:System.String> 형식이면 반환된 개체를 <xref:System.String>으로 캐스팅할 수 있어야 합니다.  반환된 문자열은 `value`의 serialize된 값을 나타내야 합니다.  serialization 형식을 선택할 때, 동일한 변환기의 <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A> 구현에 문자열이 전달되는 경우 중요한 정보를 손실하지 않고 동일한 값을 생성할 수 있는 형식을 선택하는 것이 가장 좋습니다.  
  
 값을 serialize할 수 없거나 변환기가 serialization을 지원하지 않으면 <xref:System.ComponentModel.TypeConverter.ConvertTo%2A> 구현이 `null`을 반환해야 하고, 이 경우 예외를 throw할 수 있어야 합니다.  그러나 예외를 throw하는 경우 <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> 구현의 일부로 변환을 사용할 수 없음을 보고하여 예외를 방지하기 위해 먼저 <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A>를 사용하여 확인하는 최선의 방법이 지원되도록 해야 합니다.  
  
 `destinationType` 매개 변수가 <xref:System.String> 형식이 아니면 고유 변환기 처리를 선택할 수 있습니다.  일반적으로 기본 구현 처리로 되돌리게 되는데 기본 구현 처리에서는 <xref:System.ComponentModel.TypeConverter.ConvertTo%2A>가 특정 예외를 발생시킵니다.  
  
### CanConvertTo 구현  
 <xref:System.ComponentModel.TypeConverter.CanConvertTo%2A> 구현은 `destinationType` 형식이 <xref:System.String>이면 `true`를 반환하고, 그렇지 않으면 기본 구현을 따라야 합니다.  
  
### CanConvertFrom 구현  
 <xref:System.ComponentModel.TypeConverter.CanConvertFrom%2A> 구현은 `sourceType` 형식이 <xref:System.String>이면 `true`를 반환하고, 그렇지 않으면 기본 구현을 따라야 합니다.  
  
<a name="Applying_the_TypeConverterAttribute"></a>   
## TypeConverterAttribute 적용  
 XAML 처리기가 사용자 지정 형식 변환기를 사용자 지정 클래스의 형식 변환기로 사용하도록 하려면 클래스 정의에 [!INCLUDE[TLA#tla_netframewkattr](../../../../includes/tlasharptla-netframewkattr-md.md)] <xref:System.ComponentModel.TypeConverterAttribute>를 적용해야 합니다.  특성을 통해 지정하는 <xref:System.ComponentModel.TypeConverterAttribute.ConverterTypeName%2A>은 사용자 지정 형식 변환기의 형식 이름이어야 합니다.  이 특성을 적용하면 속성 형식에 사용자 지정 클래스 형식이 사용되는 경우 XAML 프로세서가 값을 처리할 때 문자열을 입력하고 개체 인스턴스를 반환할 수 있습니다.  
  
 속성별로 형식 변환기를 제공할 수도 있습니다.  이 경우 [!INCLUDE[TLA#tla_netframewkattr](../../../../includes/tlasharptla-netframewkattr-md.md)] <xref:System.ComponentModel.TypeConverterAttribute>를 클래스 정의에 적용하는 대신 속성 정의\(기본 정의 내의 `get`\/`set` 구현이 아닌 기본 정의 내\)에 적용합니다.  속성 형식은 사용자 지정 형식 변환기를 통해 처리되는 형식과 일치해야 합니다.  이 특성을 적용하면 XAML 프로세서가 속성 값을 처리할 때 입력 문자열을 처리하고 개체 인스턴스를 반환할 수 있습니다.  속성별로 형식 변환기를 제공하는 방법은 특히 클래스 정의를 제어할 수 없거나 클래스 정의에 <xref:System.ComponentModel.TypeConverterAttribute>를 적용할 수 없는 일부 다른 라이브러리 또는 [!INCLUDE[TLA#tla_netframewk](../../../../includes/tlasharptla-netframewk-md.md)]의 속성 형식을 사용하는 경우 유용합니다.  
  
## 참고 항목  
 <xref:System.ComponentModel.TypeConverter>   
 [XAML 개요\(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [XAML 구문 정보](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)