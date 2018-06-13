---
title: DateTime XAML 구문
ms.date: 03/30/2017
helpviewer_keywords:
- DateTime XAML syntax [WPF], strings for
- DateTime XAML syntax [WPF], where used
- short date format [WPF], DateTime
- DateTime XAML syntax [WPF]
- DateTime XAML text [WPF]
- DateTime XAML syntax [WPF], format strings for
ms.assetid: 5901710a-609b-40c8-9d65-f0016cd9090b
ms.openlocfilehash: 286117cc0cce9fb54ea2c372360b13865fba77ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540565"
---
# <a name="datetime-xaml-syntax"></a>DateTime XAML 구문
와 같은 일부 컨트롤 <xref:System.Windows.Controls.Calendar> 및 <xref:System.Windows.Controls.DatePicker>를 사용 하는 속성이 <xref:System.DateTime> 유형입니다. 일반적으로 런타임에 코드 숨김으로 이러한 컨트롤에 대해 초기 날짜 또는 시간을 지정하지만 XAML로 초기 날짜 또는 시간을 지정할 수 있습니다. WPF XAML 파서에 처리의 구문 분석 <xref:System.DateTime> 기본 제공 XAML 텍스트 구문을 사용 하 여 값입니다. 이 항목의 세부 사항을 설명는 <xref:System.DateTime> XAML 텍스트 구문입니다.  
  
  
<a name="where_datetime_xaml_syntax_is_used"></a>   
## <a name="when-to-use-datetime-xaml-syntax"></a>DateTime XAML 구문을 사용하는 경우  
 날짜를 항상 XAML로 설정할 필요가 없으며 이 방법이 바람직하지 않을 수도 있습니다. 예를 들어, 사용할 수는 <xref:System.DateTime.Now%2A?displayProperty=nameWithType> 속성을 런타임에, 또는 있습니다 날짜 초기화 코드 숨김에서 사용자 입력에 따라 일정에 대 한 모든 날짜 조정을 수행할 수 있습니다. 그러나 여러 가지로 하드 코딩 날짜를 사용할 수 있는 시나리오는 <xref:System.Windows.Controls.Calendar> 및 <xref:System.Windows.Controls.DatePicker> 제어 템플릿에서 합니다. <xref:System.DateTime> 이러한 시나리오에 대 한 XAML 구문을 사용 해야 합니다.  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a>DateTime XAML 구문이 기본 동작임  
 <xref:System.DateTime> CLR의 기본 클래스 라이브러리에 정의 된 클래스입니다. 기본 클래스 라이브러리의 관계는 CLR의 나머지 부분을 때문에 불가능 적용할 <xref:System.ComponentModel.TypeConverterAttribute> 클래스와 사용으로 변환 하 고 XAML에서 문자열을 처리 하는 형식 변환기를 <xref:System.DateTime> 런타임 개체 모델에서. 변환 동작을 제공하는 `DateTimeConverter` 클래스가 없습니다. 이 항목에서 설명하는 변환 동작은 WPF XAML 파서의 기본 동작입니다.  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>   
## <a name="format-strings-for-datetime-xaml-syntax"></a>DateTime XAML 구문의 형식 문자열  
 형식을 지정할 수 있습니다는 <xref:System.DateTime> 형식 문자열을 사용 합니다. 형식 문자열은 값을 생성하는 데 사용할 수 있는 텍스트 구문을 공식화합니다. <xref:System.DateTime> 기존 WPF 컨트롤만 일반적으로 사용 하 여의 날짜 구성 요소에 대해 값 <xref:System.DateTime> 및 시간 구성 요소가 없습니다.  
  
 지정 하는 경우는 <xref:System.DateTime> XAML에서 교대로 사용할 수 있습니다는 형식 문자열 중 하나입니다.  
  
 이 항목에 구체적으로 표시되지 않은 형식 및 형식 문자열을 사용할 수도 있습니다. 에 대 한 XAML 기술적으로 <xref:System.DateTime> 지정 되 고 WPF XAML 파서에서 구문 분석 된 값에 대 한 내부 호출을 사용 하 여 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>에 허용 되는 모든 문자열을 사용할 수 있습니다 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> XAML에 대 한 입력 합니다. 자세한 내용은 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>을 참조하세요.  
  
> [!IMPORTANT]
>  날짜/시간 XAML 구문을 사용 하 여 항상 `en-us` 로 <xref:System.Globalization.CultureInfo> 해당 기본 변환에 대 한 합니다. 이 영향을 받지 않는 <xref:System.Windows.FrameworkElement.Language%2A> 값 또는 `xml:lang` 해당 컨텍스트 없이 XAML 수준 특성 형식 변환 동작 때문에 xaml에서 값입니다. 일과 월이 표시되는 순서와 같은 문화적 차이로 인해 여기에 표시된 형식 문자열을 보간하지 마세요. 여기에 표시된 형식 문자열은 다른 문화권 설정에 관계없이 XAML을 구문 분석할 때 사용되는 정확한 형식 문자열입니다.  
  
 다음 섹션에서는 일반적인 일부의 <xref:System.DateTime> 형식 문자열입니다.  
  
### <a name="short-date-pattern-d"></a>간단한 날짜 패턴("d")  
 다음은 간단한 날짜 형식에 대 한 한 <xref:System.DateTime> XAML에서:  
  
 `M/d/YYYY`  
  
 WPF 컨트롤에서 일반적으로 사용하는 데 필요한 모든 정보를 지정하는 가장 간단한 형식이며 실수에 의한 표준 시간대 오프셋 및 시간 구성 요소의 영향을 받지 않으므로 다른 형식에 비해 권장됩니다.  
  
 예를 들어 2010년 6월 1일 날짜를 지정하려면 다음 문자열을 사용합니다.  
  
 `3/1/2010`  
  
 자세한 내용은 <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>을 참조하세요.  
  
### <a name="sortable-datetime-pattern-s"></a>정렬 가능한 DateTime 패턴("s")  
 다음 테이블에 정렬 가능한 나와 <xref:System.DateTime> XAML에서 패턴:  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 예를 들어 2010년 6월 1일 날짜를 지정하려면 다음 문자열을 사용합니다. 시간 구성 요소는 모두 0으로 입력됩니다.  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a>RFC1123 패턴("r")  
 RFC1123 패턴은 문화권이 고정되어 있다는 이유로 RFC1123 패턴도 사용하는 다른 날짜 생성기의 문자열 입력이 될 수 있기 때문에 유용합니다. 다음은 RFC1123 <xref:System.DateTime> XAML에서 패턴:  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 예를 들어 2010년 6월 1일 날짜를 지정하려면 다음 문자열을 사용합니다. 시간 구성 요소는 모두 0으로 입력됩니다.  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a>기타 형식 및 패턴  
 이전에 설명한 것 처럼는 <xref:System.DateTime> XAML에서 문자열은 허용 가능한로 지정할 수 있습니다에 대 한 입력으로 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>합니다. 여기에 다른 공식화 된 형식 (예를 들어 <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>), 및 특정으로 공식화 되지 않은 형식 <xref:System.Globalization.DateTimeFormatInfo> 폼입니다. 예를 들어 폼 `YYYY/mm/dd` 되어도 대 한 입력으로 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>합니다. 이 항목에서는 작동 가능한 모든 형식에 대해 설명하려고 하지 않으며 대신 간단한 날짜 패턴을 표준 사례로 권장합니다.  
  
## <a name="see-also"></a>참고 항목  
 [XAML 개요(WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
