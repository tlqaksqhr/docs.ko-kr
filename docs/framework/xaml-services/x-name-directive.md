---
title: x:Name 지시문
ms.date: 03/30/2017
f1_keywords:
- x:Name
- xName
- Name
helpviewer_keywords:
- x:Name attribute [XAML Services]
- XAML [XAML Services], x:Name attribute
- Name attribute in XAML [XAML Services]
ms.assetid: b7e61222-e8cf-48d2-acd0-6df3b7685d48
ms.openlocfilehash: 7fcb7fe767e892109e48c5e56db26b5943b6ef13
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565852"
---
# <a name="xname-directive"></a>x:Name 지시문
XAML 네임 스페이스의 XAML 정의 요소를 고유 하 게 식별 합니다. XAML 이름 범위 및 해당 고유성 모델 프레임 워크 Api를 제공 하거나 런타임에 XAML에서 생성 된 개체 그래프에 액세스 하는 동작을 구현 하는 경우 인스턴스화된 개체에 적용할 수 있습니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```xaml  
<object x:Name="XAMLNameValue".../>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`XAMLNameValue`|제한 사항을 준수 하는 문자열은 [XamlName 문법](../../../docs/framework/xaml-services/xamlname-grammar.md)합니다.|  
  
## <a name="remarks"></a>설명  
 후 `x:Name` 에 적용 되는 프레임 워크의 백업 프로그래밍 모델, 생성자에서 반환 된 인스턴스 또는 개체 참조를 보유 하는 변수의 이름이 같습니다.  
  
 값은 `x:Name` 지시문 사용 XAML 이름 범위 내에서 고유 해야 합니다. 기본적으로.NET Framework XAML 서비스 API에서 사용 하는 기본 XAML 이름 범위 단일 XAML 프로덕션의 XAML 루트 요소에서 정의 및 해당 XAML 프로덕션에 포함 된 요소를 포함 합니다. 특정 시나리오를 해결 하기 위해 프레임 워크에 의해 XAML 프로덕션 단일 내에서 발생할 수 있는 추가 불연속 XAML 이름 범위를 정의할 수 있습니다. 예를 들어 WPF에서 새로운 XAML 네임 스페이스 정의 되 고 해당 XAML 프로덕션에 정의 된 모든 템플릿으로 생성 합니다. 으로 작성 된 WPF 용 여러 XAML 이름 범위 개념에 대 한 관련 되지만 XAML 이름 범위에 대 한 자세한 내용은 참조 하십시오. [WPF XAML 이름 범위](../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)합니다.  
  
 일반적으로 `x:Name` 를 사용 하는 경우에는 적용 되지 않도록 `x:Key`합니다. 특정 기존 프레임 워크에서 XAML 구현 간의 대체 개념을 도입 `x:Key` 및 `x:Name`는 없지만 것이 좋습니다. .NET framework XAML 서비스와 같은 이름/키 정보를 처리 하는 경우 등의 대체 개념을 지원 하지 않습니다 <xref:System.Windows.Markup.INameScope> 또는 <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>합니다.  
  
 허용 규칙 `x:Name` 이름 고유성이 적용 뿐만 아니라가 잠재적으로 정의한 특정 구현 프레임 워크입니다. 그러나.NET Framework XAML 서비스를 사용 하려면 XAML 네임 스페이스 고유성의 프레임 워크 정의와 일치 해야 정의 <xref:System.Windows.Markup.INameScope> 이 설명서의 내용은 위치에 대 한 동일한 규칙을 사용 해야 하 고는 정보가 적용 됩니다. 예를 들어는 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 구현 별도 다양 한 태그 요소 나눕니다 <xref:System.Windows.NameScope> 리소스 사전과 같은 콘텐츠, 페이지 수준 XAML, 서식 파일 및 기타 지연 하 여 만든 논리 트리 범위 하 고 다음 XAML을 적용 각 해당 XAML 이름 범위 내에서 이름의 고유성이 보장 합니다.  
  
 .NET Framework XAML 서비스 XAML 개체 작성기를 사용 하는 사용자 지정 형식에 대 한 속성에 매핑되는 `x:Name` 에 형식을 설정 하거나 변경할 수 있습니다. 사용 하 여 매핑할 속성의 이름을 참조 하 여이 동작을 정의 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> 형식 정의 코드에서.  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> 형식 수준 특성이입니다.  
  
 Using.NET Framework XAML 서비스 XAML 이름 범위 지원에 대 한 백업 논리를 구현 하 여 프레임 워크 중립 방식으로 정의할 수 있습니다는 <xref:System.Windows.Markup.INameScope> 인터페이스입니다.  
  
## <a name="wpf-usage-notes"></a>WPF 사용 정보  
 에 대 한 표준 빌드 구성에서는 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML, partial 클래스 및 코드 숨김, 지정된 된 사용 하는 응용 프로그램 `x:Name` 내부에서 생성 된 필드의 이름이 됩니다 때 코드 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 는 태그에서 처리 컴파일 빌드 작업을 하 고 해당 필드는 개체에 대 한 참조를 보유 합니다. 기본적으로 생성된 된 필드는 내부입니다. 지정 하 여 필드 액세스를 변경할 수는 [X:fieldmodifier 특성](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md)합니다. WPF 및 Silverlight에 순서가 정의 태그 컴파일 및 이름 부분 클래스 하지만 값의 필드는 처음에 비어 있습니다. 그런 다음 생성 된 메서드가 `InitializeComponent` 클래스 생성자 내에서 호출 됩니다. `InitializeComponent` 이루어져 `FindName` 각 사용 하 여 호출 하는 `x:Name` 으로 partial 클래스의 XAML 정의 부분에 있는 값 문자열을 입력 합니다. 반환 값을 구문 분석에 XAML에서 생성 된 개체를 사용 하 여 필드 값을 채우는 같은 이름의 필드 참조로 다음 할당 됩니다. 실행 `InitializeComponent` 참조를 사용 하 여 런타임에 개체 그래프를 가능 하 게는 `x:Name` 필드 이름 시작를 직접 호출 하는 것이 아니라 / `FindName` 언제 든 지 명시적으로 해야 하는 XAML 정의 개체에 대 한 참조입니다.  
  
 WPF에 대 한 Microsoft Visual Basic을 사용 하는 응용 프로그램을 대상으로 하 고 인 XAML 파일을 포함 `Page` 빌드 작업을 별도 참조 속성을 추가 하는 컴파일하는 동안 만들어집니다는 `WithEvents` 키워드는 있는모든요소를`x:Name`지원 하기 위해 `Handles` 이벤트 처리기 대리자에 대 한 구문입니다. 이 속성은 항상 공개 합니다. 자세한 내용은 [Visual Basic 및 WPF 이벤트 처리](../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md)를 참조하세요.  
  
 `x:Name` 페이지가 없는 경우 빌드 작업 (예를 들어 리소스 사전의 느슨한 XAML)에 의해 태그 컴파일된에 대해서도 로드할 때 XAML 이름 범위에 이름을 등록 하려면 WPF XAML 프로세서에서 사용 됩니다. 이 동작에 대 한 한 가지 이유 때문에는 `x:Name` 필요 <xref:System.Windows.Data.Binding.ElementName%2A> 바인딩. 자세한 내용은 참조 [데이터 바인딩 개요](../../../docs/framework/wpf/data/data-binding-overview.md)합니다.  
  
 앞에서 설명한 대로 `x:Name` (또는 `Name`)를 사용 하는 경우에는 적용 되지 않도록 `x:Key`합니다. [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.ResourceDictionary> XAML 이름 범위로 정의 자체를 구현 하지 않았거나에 null 값을 반환 하지만 특별 한 동작이 <xref:System.Windows.Markup.INameScope> 이 동작을 적용 하는 방법으로는 Api입니다. WPF XAML 파서가 발견할 경우 `Name` 또는 `x:Name` XAML 정의의 <xref:System.Windows.ResourceDictionary>, 이름을 XAML 이름 범위에 추가 되지 않습니다. 모든 XAML 이름 범위에서 해당 이름을 찾으려고 시도 하 고 `FindName` 메서드는 올바른 결과 반환 하지 것입니다.  
  
### <a name="xname-and-name"></a>x: 이름 및 이름  
 대부분의 WPF 응용 프로그램 시나리오의 사용을 방지할 수는 `x:Name` 특성 때문에 `Name` 종속성 속성에에서 지정 된 기본 XAML 네임 스페이스 몇 가지 중요 한 기본 클래스와 같은 <xref:System.Windows.FrameworkElement> 및 <xref:System.Windows.FrameworkContentElement> 이 동일한 목적을 충족합니다. 몇 가지 일반적인 XAML을 WPF 시나리오는 계속 액세스 하지 않은 요소에 대 한 코드 `Name` 프레임 워크 수준 속성은 중요 합니다. 예를 들어 특정 애니메이션 및 스토리 보드 지원 클래스 지원 하지 않는 한 `Name` 속성이 있지만 주로 애니메이션을 제어 하려면 코드에서 참조 되도록 해야 합니다. 지정 해야 `x:Name` 타임 라인 및 나중에 코드에서 참조 하려는 경우, XAML에서 생성 하는 변환에 대 한 특성으로 합니다.  
  
 경우 <xref:System.Windows.FrameworkElement.Name%2A> 클래스에 대 한 속성으로 사용할 수는 <xref:System.Windows.FrameworkElement.Name%2A> 및 `x:Name` 특성으로, 같은 의미로 사용 될 수 있지만 둘 다 같은 요소에 지정 되는 구문 분석 예외가 발생 합니다. 이 태그 컴파일된 XAML 예외 로드가 발생 하지 않으면 태그 컴파일에 발생 합니다.  
  
 <xref:System.Windows.FrameworkElement.Name%2A> XAML 특성 구문을 사용 하 여 설정할 수 있습니다 및 사용 하 여 코드 <xref:System.Windows.DependencyObject.SetValue%2A>; 그러나 해당 설정의 <xref:System.Windows.FrameworkElement.Name%2A> 코드에서 속성 XAML 이미은 대부분의 경우 XAML 이름 범위 내에서 필드 참조를 발생 하지 않는 로드 합니다. 설정 하는 대신 <xref:System.Windows.FrameworkElement.Name%2A> 코드를 사용 하 여 <xref:System.Windows.NameScope> 적절 한 이름 범위에 대 한 코드에서 메서드.  
  
 <xref:System.Windows.FrameworkElement.Name%2A> 내부 텍스트가 있는 속성 요소 구문을 사용 하 여 설정할 수도 있습니다 하지만이 일반적입니다. 반면, `x:Name` XAML 속성 요소 구문 또는 사용 하 여 코드에서 설정할 수 없습니다 <xref:System.Windows.DependencyObject.SetValue%2A>;만 설정할 수 있습니다는 지시문 때문에 개체에 특성 구문을 사용 합니다.  
  
## <a name="silverlight-usage-notes"></a>Silverlight 사용 정보  
 `x:Name` Silverlight 용은 별도로 설명 되어 있습니다. 자세한 내용은 참조 [XAML Namespace (x:) 언어 기능 (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=199081)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>  
 <xref:System.Windows.FrameworkContentElement.Name%2A?displayProperty=nameWithType>  
 [WPF의 트리](../../../docs/framework/wpf/advanced/trees-in-wpf.md)
