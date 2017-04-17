---
title: "DateTime XAML 구문 | Microsoft Docs"
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
  - "DateTime XAML 구문[WPF]"
  - "DateTime XAML 구문[WPF], 형식 문자열"
  - "DateTime XAML 구문[WPF], 문자열"
  - "DateTime XAML 구문[WPF], 사용된 위치"
  - "DateTime XAML 텍스트[WPF]"
  - "간단한 날짜 형식[WPF], DateTime"
ms.assetid: 5901710a-609b-40c8-9d65-f0016cd9090b
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# DateTime XAML 구문
<xref:System.Windows.Controls.Calendar>, <xref:System.Windows.Controls.DatePicker> 등의 일부 컨트롤은 <xref:System.DateTime> 형식을 사용하는 속성을 가집니다.  일반적으로 런타임에 코드 숨김에서 이러한 컨트롤에 대해 초기 날짜 또는 시간을 지정하지만 XAML에 초기 날짜 또는 시간을 지정할 수 있습니다.  WPF XAML 파서는 기본 제공 XAML 텍스트 구문을 사용하여 <xref:System.DateTime> 값의 구문 분석을 처리합니다.  이 항목에서는 <xref:System.DateTime> XAML 텍스트 구문 세부 사항을 설명합니다.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="where_datetime_xaml_syntax_is_used"></a>   
## DateTime XAML 구문 사용 시기  
 XAML에서 항상 날짜를 설정해야 하는 것은 아니며 바람직하지 않을 수도 있습니다.  예를 들어, <xref:System.DateTime.Now%2A?displayProperty=fullName> 속성을 사용하여 런타임에 날짜를 초기화하거나 사용자 입력을 기반으로 하는 코드 숨김으로 달력에 대한 모든 날짜 조정을 수행할 수 있습니다.  그러나 컨트롤 템플릿에서 날짜를 <xref:System.Windows.Controls.Calendar> 및 <xref:System.Windows.Controls.DatePicker>로 하드 코딩할 수 있는 시나리오가 있습니다.  이러한 시나리오에서는 <xref:System.DateTime> XAML 구문을 사용해야 합니다.  
  
### DateTime XAML 구문은 네이티브 동작임  
 <xref:System.DateTime>은 CLR의 기본 클래스 라이브러리에 정의된 클래스입니다.  기본 클래스 라이브러리가 CLR의 나머지 부분과 어떤 관련이 있기 때문에 클래스에 <xref:System.ComponentModel.TypeConverterAttribute>를 적용하고 형식 변환기를 사용하여 XAML에서 문자열을 처리하고 이를 런타임 개체 모델에서 <xref:System.DateTime>으로 변환하지 못할 수 있습니다.  변환 동작을 제공하는 `DateTimeConverter` 클래스가 없습니다. 이 항목에서 설명하는 변환 동작은 WPF XAML 파서의 기본 역할입니다.  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>   
## DateTime XAML 구문의 형식 문자열  
 형식 문자열을 사용하여 <xref:System.DateTime>의 형식을 지정할 수 있습니다.  값을 만드는 데 사용할 수 있는 텍스트 구문을 공식화하는 형식 문자열입니다.  기존 WPF 컨트롤에 대한 <xref:System.DateTime> 값은 일반적으로 시간 구성 요소가 아닌 <xref:System.DateTime>의 날짜 구성 요소만 사용합니다.  
  
 XAML에서 <xref:System.DateTime>을 지정하면 형식 문자열을 교대로 사용할 수 있습니다.  
  
 이 항목에서 구체적으로 표시되지 않는 형식 및 형식 문자열을 사용할 수도 있습니다.  기술적으로 WPF XAML 파서에 의해 지정되고 구문 분석된 <xref:System.DateTime> 값에 대한 XAML은 <xref:System.DateTime.Parse%2A?displayProperty=fullName>에 대해 내부 호출을 사용하므로 XAML 입력에 대해 <xref:System.DateTime.Parse%2A?displayProperty=fullName>에서 허용되는 모든 문자열을 사용할 수 있습니다.  자세한 내용은 <xref:System.DateTime.Parse%2A?displayProperty=fullName>를 참조하십시오.  
  
> [!IMPORTANT]
>  DateTime XAML 구문은 항상 네이티브 변환을 위해 `en-us`를 <xref:System.Globalization.CultureInfo>로 사용합니다.  이는 XAML 특성 수준 형식 변환이 해당 컨텍스트 없이 동작하기 때문에 XAML에 있는 <xref:System.Windows.FrameworkElement.Language%2A> 값 또는 `xml:lang` 값의 영향을 받지 않습니다.  일과 월이 나타나는 순서 같이 문화적 변형으로 인해 여기에 표시된 형식 문자열을 보간하려 하지 마십시오.  여기에 표시된 형식 문자열은 다른 문화적 설정에 관계없이 XAML을 구문 분석할 때 사용하는 정확한 형식 문자열입니다.  
  
 다음 단원에서는 일반적인 몇 가지 <xref:System.DateTime> 형식 문자열을 설명합니다.  
  
### 간단한 날짜 패턴\("d"\)  
 다음은 XAML의 <xref:System.DateTime>에 대한 간단한 날짜 형식을 보여줍니다.  
  
 `M/d/YYYY`  
  
 이는 WPF 컨트롤에 의해 일반적인 사용에 필요한 모든 정보를 지정하는 가장 간단한 양식이며 시간 구성 요소에 비해 실수로 시간대 오프셋의 영향을 받을 수는 없으므로 다른 형식보다 권장합니다.  
  
 예를 들어, 2010년 6월 1일의 날짜를 지정하려면 다음 문자열을 사용하십시오.  
  
 `3/1/2010`  
  
 자세한 내용은 <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=fullName>를 참조하십시오.  
  
### 정렬 가능한 날짜\/시간 패턴\("s"\)  
 다음은 XMAL에서 정렬 가능한 <xref:System.DateTime> 패턴을 보여 줍니다.  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 예를 들어, 2010년 6월 1일의 날짜를 지정하려면 시간 구성 요소를 모두 0으로 입력한 다음 문자열을 사용하십시오.  
  
 `2010-06-01T000:00:00`  
  
### RFC1123 패턴\("r"\)  
 RFC1123 패턴은 고정 문화권을 이유로 RFC1123 패턴도 사용하는 다른 날짜 생성기의 문자열 입력이 될 수 있으므로 유용합니다.  다음은 XMAL에서 RFC1123 <xref:System.DateTime> 패턴을 보여 줍니다.  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 예를 들어, 2010년 6월 1일의 날짜를 지정하려면 시간 구성 요소를 모두 0으로 입력한 다음 문자열을 사용하십시오.  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### 다른 형식 및 패턴  
 앞에서 언급했듯이 XAML의 <xref:System.DateTime>은 <xref:System.DateTime.Parse%2A?displayProperty=fullName>에 대한 입력으로 사용할 수 있는 문자열로 지정할 수 있습니다.  여기에는 다른 공식화된 형식\(예: <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>\)과 특정 <xref:System.Globalization.DateTimeFormatInfo> 양식으로 공식화되지 않은 형식이 포함됩니다.  예를 들어, 양식 `YYYY/mm/dd`는 <xref:System.DateTime.Parse%2A?displayProperty=fullName>에 대한 입력으로 사용할 수 있습니다.  이 항목은 작동하는 가능한 모든 형식을 설명하지는 않으며, 대신 표준 사례로 간단한 날짜 패턴을 권장합니다.  
  
## 참고 항목  
 [XAML 개요\(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)