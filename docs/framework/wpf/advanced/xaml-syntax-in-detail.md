---
title: "XAML 구문 정보"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML [WPF], namespaces
- XAML [WPF], parsing of attributes
- parsing of attributes [WPF]
- XAML [WPF], markup extensions
- attached properties [WPF]
- tag syntax [XAML]
- markup extensions [WPF]
- XAML [WPF], object element syntax
- XAML [WPF], syntax terminology
- attached events [WPF]
- lookup semantics [WPF]
- XAML [WPF], attached events
- XAML [WPF], content syntax
- XAML [WPF], lookup semantics
- content syntax [WPF]
- object element syntax [WPF]
- syntax terminology [XAML]
- XAML [WPF], attached properties
- attributes [XAML], parsing
- XAML [WPF], tag syntax
- XAML [WPF], attribute syntax
- property element syntax [WPF]
- terminology [XAML]
- namespaces [WPF], XML
- attribute syntax [XAML]
- XAML [WPF], property element syntax
ms.assetid: 67cce290-ca26-4c41-a797-b68aabc45479
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0aa85c9ec6e6b911444b07a4169dc769ac4df816
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="xaml-syntax-in-detail"></a>XAML 구문 정보
이 항목에서는 XAML 구문 요소에 설명 하는 데 사용 되는 용어를 정의 합니다. 이러한 용어는 특히 및 XAML 또는으로 System.Xaml 수준에서 XAML 언어 지원을 사용 하도록 설정 하는 기본 XAML 개념을 사용 하는 다른 프레임 워크에 대 한 WPF 설명서에 대 한이 설명서의 나머지 부분 전체에서 자주 사용 됩니다. 이 항목을 확장 항목에 도입 된 기본 용어 [XAML 개요 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)합니다.  
  

  
<a name="the_xaml_language_specification"></a>   
## <a name="the-xaml-language-specification"></a>XAML 언어 사양  
 또한 여기에 정의 된 XAML 구문 용어 정의 되었거나 XAML 언어 사양 내에서 참조 합니다. XAML은 XML 기반 언어 및 뒤에 오는 또는 XML 구조 규칙에 따라 확장 합니다. 용어 중 일부를 공유 하거나 XML 언어 XML 문서 개체 모델을 설명 하는 경우에 주로 사용 되는 용어를 기반으로 합니다.  
  
 XAML 언어 사양에 대 한 자세한 내용은 다운로드 [ \[MS-XAML\] ](http://go.microsoft.com/fwlink/?LinkId=114525) Microsoft 다운로드 센터에서.  
  
<a name="xaml_and_clr"></a>   
## <a name="xaml-and-clr"></a>XAML 및 CLR  
 XAML은 태그 언어입니다. [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]하듯이 이름을 기준으로 사용 하면 런타임 실행 합니다. XAML은 하지 단독으로 직접 CLR 런타임에서 사용 되는 일반적인 언어 중 하나입니다. 대신, 지원 형식 시스템 자체의 XAML 생각할 수 있습니다. WPF에서 사용 되는 특정 XAML 구문 분석 시스템 CLR 및 CLR 형식 시스템에 작성 됩니다. XAML 형식은 WPF에 대 한 XAML 구문 분석 하는 실행된 시간 표시를 인스턴스화하는 CLR 형식에 매핑됩니다. 이러한 이유로이 문서에 대 한 구문 설명의 나머지 부분에서는 XAML 언어 사양에 해당 구문 설명에는 없는 경우에 CLR 형식 시스템에 대 한 참조가 포함 됩니다. (XAML 언어 사양 수준 당 XAML 형식에 매핑될 수 생성 및 다른 XAML 파서에서 사용 해야 하지만 CLR 수 없는 있는 모든 다른 형식 시스템을 합니다.)  
  
#### <a name="members-of-types-and-class-inheritance"></a>형식 및 클래스 상속의 멤버  
 속성 및 XAML 멤버로 표시 되었을 때 이벤트는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 형식을 기본 형식에서 종종 상속 됩니다. 예를 들어이 예에서는: `<Button Background="Blue" .../>`합니다. <xref:System.Windows.Controls.Control.Background%2A> 속성은 즉시 선언 된 속성이 아닙니다에 <xref:System.Windows.Controls.Button> 클래스를 클래스 정의 리플렉션 결과 또는 설명서를 확인 하는 경우. 대신, <xref:System.Windows.Controls.Control.Background%2A> 기본에서 상속 <xref:System.Windows.Controls.Control> 클래스입니다.  
  
 클래스 상속의 동작의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML 요소는 XML 태그 해석 스키마 적용 하는에서 중요 한 시작 되었습니다. 클래스 상속 인터페이스가 포함 된 경우 또는 중간 기본 클래스는 추상적 하는 경우에 특히, 복잡 한 될 수 있습니다. 이 XAML 요소 및 해당 허용 가능한 특성의 집합은 정확 하 고 완전히 스키마 형식을 사용 하 여 표현 하기 어렵게에 일반적으로 사용 되는 한 가지 이유는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] DTD 또는 XSD 형식 등 프로그래밍 합니다. 또 다른 이유는 확장성 및 허용 되는 형식 및 멤버에 대 한 모든 고정 표현의 XAML 언어 자체의 형식 매핑이 기능 불완전 합니다.  
  
<a name="object_element_syntax"></a>   
## <a name="object-element-syntax"></a>개체 요소 구문  
 *요소 구문 개체* XML 요소를 선언 하 여 CLR 클래스 또는 구조체를 인스턴스화하는 XAML 태그 구문입니다. 이 구문은 HTML과 같은 다른 태그 언어의 요소 구문과 유사합니다. 개체 요소 구문은 왼쪽된 꺾쇠 괄호 (\<) 인스턴스화 중인 구조체 또는 클래스의 형식 이름에 즉시 이어집니다. 0 개 이상의 공간 형식 이름에 따라 수 및 0 개 이상의 특성이 선언할 수도 개체 요소에서 하나 이상의 공백 구분 특성 = "value" 쌍입니다. 마지막으로, 다음 중 하나가 적용 되어야 합니다.  
  
-   슬래시 (/)는 오른쪽 꺾쇠 괄호 (>) 바로 뒤에 요소 및 태그 닫혀 있어야 합니다.  
  
-   여는 태그 오른쪽 꺾쇠 괄호 (>)가 완료 해야 합니다. 다른 개체 요소, 속성 요소 또는 내부 텍스트를 여는 태그를 따르면 됩니다. 콘텐츠를 여기 포함 될 수 있습니다 정확히 요소 개체 모델에서 일반적으로 제한 됩니다. 또한 개체 요소의 닫는 태그를 해당 하는 올바른 중첩에 존재 하 고 다른 중괄호와 닫는 태그 쌍으로 균형을 조정 해야 합니다.  
  
 .NET에 의해 구현 된 XAML 개체 요소 형식, 속성 또는 이벤트 및 CLR 네임 스페이스 및 어셈블리로 XAML 네임 스페이스에는 특성으로 매핑하는 규칙 집합이 있습니다. WPF 및.NET Framework에 대 한 XAML 개체 요소에 매핑하는 [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] 형식에 정의 된 대로 어셈블리, 참조 및 이러한 형식의 멤버에 특성이 매핑됩니다. XAML에서 CLR 형식을 참조 하는 경우 해당 형식의 상속된 된 멤버에는 액세스할을 수 있습니다.  
  
 예를 들어 다음 예제는의 새 인스턴스를 인스턴스화하는 개체 요소 구문은 <xref:System.Windows.Controls.Button> 클래스도 지정 하 고는 <xref:System.Windows.FrameworkElement.Name%2A> 특성 및 해당 특성에 대 한 값:  
  
 [!code-xaml[XAMLOvwSupport#SyntaxOE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxoe)]  
  
 다음 예제는 XAML 콘텐츠 속성인 구문이 포함 된 개체 요소 구문. 내에 포함 된 내부 텍스트를 사용 하 여 설정할 수는 <xref:System.Windows.Controls.TextBox> XAML 콘텐츠 속성인 <xref:System.Windows.Controls.TextBox.Text%2A>합니다.  
  
 [!code-xaml[XAMLOvwSupport#ThisIsATextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#thisisatextbox)]  
  
### <a name="content-models"></a>정적 콘텐츠 모델  
 클래스는 구문의 측면에서 XAML 개체 요소 사용을 지원할 수 있지만 해당 요소의 전체 콘텐츠 모델 또는 요소 트리 필요한 위치에 배치 된 경우에 응용 프로그램 또는 페이지에서 제대로 동작 합니다. 예를 들어 한 <xref:System.Windows.Controls.MenuItem> 의 자식 사이트로 배치 일반적으로 해야는 <xref:System.Windows.Controls.Primitives.MenuBase> 파생 클래스와 같은 <xref:System.Windows.Controls.Menu>합니다. 특정 요소에 대 한 모델은 컨트롤 및 기타 클래스 페이지에는 주의의 일환으로 문서화 되어 콘텐츠 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML 요소도 사용할 수 있는 클래스입니다.  
  
<a name="properties_of_object_elements"></a>   
## <a name="properties-of-object-elements"></a>개체 요소 속성  
 XAML의 속성은 다양 한 구문에 의해 설정 됩니다. 특정 속성에 사용할 수 있는 구문 설정 하는 속성의 기본 형식 시스템 특성에 따라 다릅니다.  
  
 속성의 값을 설정 하 여 기능 또는 특성에 추가 개체 런타임 개체 그래프에 있는 대로. Object 요소에서 만든된 개체의 초기 상태는 기본 생성자 동작을 기반으로 합니다. 일반적으로 응용 프로그램 지정된 된 개체의 완전히 기본 인스턴스 이외의 노드를 사용 합니다.  
  
<a name="attribute_syntax_properties"></a>   
## <a name="attribute-syntax-properties"></a>특성 구문(속성)  
 특성 구문은 기존 개체 요소에 특성을 선언 하 여 속성에 대 한 값을 설정 하는 XAML 태그 구문입니다. 특성 이름을 관련 개체 요소를 지 원하는 클래스의 속성의 CLR 멤버 이름과 일치 해야 합니다. 특성 이름 뒤에 할당 연산자 (=)가 있습니다. 특성 값에는 따옴표로 묶인 문자열 이어야 합니다.  
  
> [!NOTE]
>  특성에 리터럴 따옴표를 배치에 다른 따옴표를 사용할 수 있습니다. 예를 들어 큰따옴표 문자를 포함 하는 문자열을 선언 하는 방법으로 작은따옴표를 사용할 수 있습니다. 작은따옴표 또는 큰따옴표를 사용 하 든 열기 및 닫기 특성 값 문자열에 대 한 일치 하는 쌍을 사용 해야 합니다. 또한 이스케이프 시퀀스 또는 기타 기술을 사용 가능한 있습니다 특정 XAML 구문에서 부과 하는 문자 제한 사항 해결 하기 위한. 참조 [XML 문자 엔터티 및 XAML](../../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)합니다.  
  
 특성 구문을 통해 설정 하려면 속성 공용 이어야 하며 쓸 수 있어야 합니다. 지원 형식 시스템에 있는 속성의 값을 값 형식 이어야 합니다 또는 해야 인스턴스화하거나 관련에 액세스할 때 XAML 프로세서에서 참조할 수 있는 참조 형식을 백업 유형입니다.  
  
 WPF XAML 이벤트에 대 한 특성 이름으로 참조 되는 이벤트는 public 이어야 하 고 공용 대리자는 해야 합니다.  
  
 속성 또는 이벤트 클래스 또는 구조체를 포함 하는 개체 요소에 의해 인스턴스화될의 구성원 이어야 합니다.  
  
### <a name="processing-of-attribute-values"></a>특성 값 처리  
 여는 태그와 닫는 따옴표 내에 포함 된 문자열 값은 XAML 프로세서에서 처리 됩니다. 속성에 대 한 기본 처리 동작은 형식 기본 CLR 속성에 따라 결정 됩니다.  
  
 특성 값은 다음 중 하나에 의해 채워집니다이 처리 순서를 사용 하 여:  
  
1.  XAML 프로세서는 중괄호로 또는 object 요소에서 파생 되는 발생 한 경우 <xref:System.Windows.Markup.MarkupExtension>인 다음 참조 된 태그 확장 값을 문자열로 처리 하는 대신 먼저 평가 되 고으로 태그 확장에서 반환 된 개체가 사용 되는 값입니다. 대부분의 경우에서 태그 확장에서 반환 되는 개체는 런타임까지 평가 지연 있으며는 새로 인스턴스화된 개체는 식 또는 기존 개체에 대 한 참조 됩니다.  
  
2.  속성 선언 되 면 특성이 사용 된 <xref:System.ComponentModel.TypeConverter>, 해당 속성의 값 형식에 선언 된 특성이 사용 된 <xref:System.ComponentModel.TypeConverter>, 특성의 문자열 값으로 변환 입력 형식 변환기에 전송 된 및 변환기를 반환 합니다는 새 개체 인스턴스입니다.  
  
3.  없는 경우 없는 <xref:System.ComponentModel.TypeConverter>, 속성 형식으로 직접 변환이 시도 됩니다. 이 최종 수준은 XAML 언어 기본 형식 또는 이름 (파서가 액세스 하는 일치 하는 값)는 열거형에서 명명 된 상수에 대 한 검사 사이 있는 파서 네이티브 값에서 직접 변환 합니다.  
  
#### <a name="enumeration-attribute-values"></a>열거 속성 값  
 열거형의 명명 된 상수 중 하나의 문자열 이름을 지정 하 여 열거형의 멤버를 지정 해야 및 XAML의 열거형으로 XAML 파서가 기본적으로 처리 됩니다.  
  
 Nonflag 열거형 값에 대 한 기본 동작은 특성 값의 문자열을 처리 하는 열거형 값 중 하나로 확인 합니다. 형식에 열거형을 지정 하지 않으면 *열거형*. *값*코드에서와 마찬가지로, 합니다. 만 지정 하는 대신, *값*, 및 *열거형* 설정 하는 속성의 형식에 의해 유추 됩니다. 특성을 지정 하는 경우는 *열거형*. *값* 폼을 확인 하지 것입니다 올바르게 합니다.  
  
 플래그 열거형에 대 한 동작에 따라이 <xref:System.Enum.Parse%2A?displayProperty=nameWithType> 메서드. 각 값을 쉼표로 구분 하 여 플래그 열거형에 대 한 여러 값을 지정할 수 있습니다. 그러나 플래그 되는 열거형 값을 결합할 수 없습니다. 예를 들어,를 만드는 쉼표 구문을 사용할 수 없습니다는 <xref:System.Windows.Trigger> nonflag 열거형의 여러 조건에 역할을 합니다.  
  
```  
<!--This will not compile, because Visibility is not a flagwise enumeration.-->  
...  
<Trigger Property="Visibility" Value="Collapsed,Hidden">  
  <Setter ... />  
</Trigger>  
...  
```  
  
 XAML에서 설정할 수 있는 특성을 원하는 플래그 열거형 wpf에서 드문 경우입니다. 그러나 이러한 열거가 두 개는 <xref:System.Windows.Media.StyleSimulations>합니다. 예를 들어, 쉼표로 구분 된 플래그 특성 구문을 사용 하 여 대 한 설명에서 제공 되는 예제를 수정할 수는 <xref:System.Windows.Documents.Glyphs> 클래스입니다. `StyleSimulations = "BoldSimulation"` 가 될 수 있습니다 `StyleSimulations = "BoldSimulation,ItalicSimulation"`합니다. <xref:System.Windows.Input.KeyBinding.Modifiers%2A?displayProperty=nameWithType>속성이 다른 둘 이상의 열거형 값을 지정할 수 있습니다. 하지만 때문에이 속성 특별 한 경우에 발생는 <xref:System.Windows.Input.ModifierKeys> 열거형 자체 형식 변환기를 지원 합니다. 한정자에 대 한 형식 변환기를 쉼표 (,)가 아닌 구분 기호는 더하기 기호 (+)를 사용합니다. 이 변환에는 "Ctrl + Alt"와 같은 Microsoft Windows 프로그래밍에서 키 조합을 나타내기 위해 더 많은 기존 구문을 지원 합니다.  
  
### <a name="properties-and-event-member-name-references"></a>속성 및 이벤트 멤버 이름 참조  
 특성을 지정할 때 모든 속성이 나 이벤트를 포함 하는 개체 요소에 대해 인스턴스화된 CLR 형식의 멤버를 참조할 수 있습니다.  
  
 또는 연결된 된 속성을 참조할 수 있습니다 또는 연결 된 이벤트를 포함 하는 개체 요소와 무관 합니다. (연결 된 속성은 이후 섹션에서 설명 함).  
  
 사용 하 여 기본 네임 스페이스를 통해 액세스할 수 있는 모든 개체에서 모든 이벤트 이름을 지정할 수도 있습니다는 *typeName*. *이벤트* 부분적으로 정규화 된 이름; 처리기 라우트된 이벤트에 대 한 연결을 지원 합니다. 자식 요소 하지만 부모 요소에서 경로 이벤트를 처리 하는 처리기 용도가 여기서도 없는 해당 이벤트 멤버 테이블에 맞게이 구문입니다. 이 구문은 연결 된 이벤트 구문을 비슷하지만 행사 실제 연결 된 이벤트가 없는 합니다. 대신,은 정규화 된 이름 사용 하 여 이벤트를 참조 합니다. 자세한 내용은 참조 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)합니다.  
  
 일부 시나리오에 대 한 특성 이름이 아닌 특성의 값으로 속성 이름은 제공 되기도 합니다. 이 속성 이름 예: 폼에 지정 된 속성의 한정자를 포함할 수도 *ownerType*. *dependencyPropertyName*합니다. 이 시나리오는 XAML에서 스타일이 나 템플릿을 작성할 때 일반적입니다. 특성 값에 제공 된 속성 이름에 대 한 처리 규칙은 서로 다르며 설정 되는 속성 유형 또는 특정 WPF 하위 시스템의 동작을 제어 됩니다. 자세한 내용은 참조 [스타일 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)합니다.  
  
 속성 이름에 대 한 다른 사용 때 특성 값 속성 간 관계를 설명 합니다. 이 기능은 데이터 바인딩에 사용 되 고으로 활성화 되어는 <xref:System.Windows.PropertyPath> 클래스 및 해당 형식 변환기입니다. 참조에 대 한 조회 의미 체계 설명은 보다 완전 [PropertyPath XAML 구문](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md)합니다.  
  
<a name="property_element_syntax"></a>   
## <a name="property-element-syntax"></a>속성 요소 구문  
 *속성 요소 구문을* 는 구문 요소에 대 한 기본 XML 구문 규칙에서 다소 모델과입니다. Xml에서 특성의 값은 사실상 문자열, 사용 되는 문자열 인코딩 형식만 되 고 가능한 유일한 변형 합니다. Xaml에서는 다른 개체 요소 속성의 값이 되도록 지정할 수 있습니다. 속성 요소 구문을 사용 하 여이 기능을 사용 합니다. 요소 태그에서 특성으로 지정 되 고 속성을 대신 해당 속성이 시작 요소를 사용 하 여 지정 된 태그 *elementTypeName*. *propertyName* 폼 속성의 값을 지정한 하 고 다음 속성 요소를 닫습니다.  
  
 특히 구문은 왼쪽된 꺾쇠 괄호 (\<) 속성 요소 구문 내에 포함 된 구조체 또는 클래스의 형식 이름에 즉시 이어집니다. 이 바로 뒤 단일 점 (.), 다음 속성의 이름으로 다음 괄호가 오른쪽 꺾쇠 괄호 (>). 특성 구문에서와 마찬가지로 해당 속성이 지정 된 형식의 선언 된 공용 멤버 내에 있어야 합니다. 속성에 할당할 값 속성 요소가 포함 되어 있습니다. 일반적으로 해당 값이 하나 이상의 개체 요소를 지정 하는, 해당 속성 요소 구문을 주소로 용도가 이므로 값으로 개체를 지정 하는 시나리오입니다. 동일한를 지정 하는 해당 하는 닫는 태그가 마지막으로, *elementTypeName*. *propertyName* 조합이 제공 해야 합니다를 적절 한 중첩을 요소 태그로 다른 분산 합니다.  
  
 예를 들어 다음은에 대 한 속성 요소 구문을 <xref:System.Windows.FrameworkElement.ContextMenu%2A> 속성은 <xref:System.Windows.Controls.Button>합니다.  
  
 [!code-xaml[XAMLOvwSupport#ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#contextmenu)]  
  
 속성 요소 내의 값 지정할 수도 있습니다 되는 경우에 지정 하는 속성 형식이 기본 값 형식 내부 텍스트로 같은 <xref:System.String>, 또는 이름이 지정 되는 열거형입니다. 각각의이 경우 단순한 특성 구문을 사용할 수도 있으므로이 두 가지 사용 방법이 많이있지 않습니다. 속성에는 XAML 콘텐츠 속성인 있지만 여전히 UI 텍스트 표현에 사용 되는 문자열로 속성 요소를 채우기 위한 한 가지 시나리오 및 줄 바꿈과 같은 특정 공백 요소 UI 텍스트에 표시 하는 데 필요한 합니다. 특성 구문은 바꿈을 유지할 수 없지만 유효한 공백 유지를 활성화할 경우 활성 속성 요소 구문을 수 (세부 정보를 참조 하십시오. [XAML의 공백 처리](../../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)). 다른 시나리오는 있도록 [X:uid 지시문](../../../../docs/framework/xaml-services/x-uid-directive.md) property 요소에 적용 될 수 있으며 따라서 WPF에서 지역화 해야 하는 값을 출력 BAML로 또는 다른 방법으로 내에서 값을 표시 합니다.  
  
 속성 요소는 WPF 논리적 트리에서 표시 되지 않습니다. 속성 요소 속성을 설정 하기 위한 특정 구문을 뿐 이며는 인스턴스 또는 지원 되는 개체를 가진 요소가 아닙니다. (논리적 트리 개념에 대 한 세부 정보를 참조 하십시오. [In WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).)  
  
 속성의 특성과 속성 요소 구문을 사용할 수 있는 경우 두 구문 일반적으로 동일한 결과 있지만 있는 공백 처리와 같은 세세 구문 약간 달라질 수 있습니다.  
  
<a name="collection_syntax"></a>   
## <a name="collection-syntax"></a>컬렉션 구문  
 XAML 사양 값 형식이 컬렉션이 속성을 식별 하는 XAML 프로세서 구현이 필요 합니다. .NET의 일반 XAML 프로세서 구현 관리 코드와 CLR을 기반으로 하며 다음 중 하나를 통해 컬렉션 형식을 식별 합니다.  
  
-   구현 입력 <xref:System.Collections.IList>합니다.  
  
-   구현 입력 <xref:System.Collections.IDictionary>합니다.  
  
-   파생 되 <xref:System.Array> (XAML에서 배열에 대 한 자세한 내용은 참조 [X:array 태그 확장](../../../../docs/framework/xaml-services/x-array-markup-extension.md).)  
  
 속성 형식이 컬렉션이 유추 된 컬렉션 형식을 개체 요소로 태그에 지정 필요 하지 않습니다. 대신, 요소를 컬렉션의 항목 될 속성 요소의 자식 요소를 하나 이상으로 지정 됩니다. 이러한 각 요소를 로드 하는 동안 개체에 계산 되 고 호출 하 여 컬렉션에 추가 된 `Add` 묵시적된 컬렉션 메서드. 예를 들어는 <xref:System.Windows.Style.Triggers%2A> 속성 <xref:System.Windows.Style> 특수 컬렉션 형식을 사용 <xref:System.Windows.TriggerCollection>를 구현 하는 <xref:System.Collections.IList>합니다. 인스턴스화할 필요는 없습니다는 <xref:System.Windows.TriggerCollection> object 태그에는 요소입니다. 하나 이상 지정 하는 대신, <xref:System.Windows.Trigger> 항목 내의 요소로 `Style.Triggers` 속성 요소 위치 <xref:System.Windows.Trigger> (또는 파생된 클래스)는 강력한 형식의 및 암시적 항목 형식으로 예상 형식 <xref:System.Windows.TriggerCollection>합니다.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxPECollection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxpecollection)]  
  
 속성은 컬렉션 형식 및 해당 형식에 대 한 XAML 콘텐츠 속성인 수 있으며이 항목의 다음 섹션에 설명 된 대로 파생 된 형식이 있습니다.  
  
 암시적 컬렉션 요소 태그는 요소로 표시 되지 않는 경우에 논리적 트리 표현에서 멤버를 만듭니다. 부모 형식의 생성자는 해당 속성 중 하나는 컬렉션에 대 한 인스턴스화를 수행 하는 일반적으로 되 고 처음 빈 컬렉션 개체 트리의 일부가 됩니다.  
  
> [!NOTE]
>  제네릭 목록 및 사전 인터페이스 (<xref:System.Collections.Generic.IList%601> 및 <xref:System.Collections.Generic.IDictionary%602>) 컬렉션 검색에 지원 되지 않습니다. 사용할 수 있습니다는 <xref:System.Collections.Generic.List%601> 클래스를 구현 하기 때문에 기본 클래스도 <xref:System.Collections.IList> 를 직접 또는 <xref:System.Collections.Generic.Dictionary%602> 기본 클래스로 구현 하기 때문에 <xref:System.Collections.IDictionary> 직접 합니다.  
  
 컬렉션 형식에 대 한.NET 참조 페이지의 컬렉션에 대 한 개체 요소의 의도적으로 생략 된이 구문은 때때로 XAML 구문 섹션에 암시적인 컬렉션 구문으로 표시 됩니다.  
  
 루트 요소를 제외 하 고 다른 요소의 자식 요소로 중첩 된 XAML 파일의 모든 개체 요소는 실제로 요소는 다음과 같은 경우 중 하나 또는 모두를: 해당 부모 요소의 암시적 컬렉션 속성의 구성원 또는 부모 요소 (XAML 콘텐츠 속성은 이후 섹션에 설명)에 대 한 XAML 콘텐츠 속성의 값을 지정 하는 요소입니다. 즉, 부모 요소와 자식 요소의 태그 페이지에서 관계는 단일 개체의 루트를 실제로 하 고 루트 아래의 모든 개체 요소는 부모의 속성 값을 제공 하는 단일 인스턴스 또는 한 열 내에 있는 항목 중 하나 lection 부모 컬렉션 형식 속성 값 이기도 합니다. 이 단일 루트 개념 xml을 사용 하면 일반적 이며 같은 XAML을 로드 하는 Api의 동작에서 자주 적용 <xref:System.Windows.Markup.XamlReader.Load%2A>합니다.  
  
 다음 예제는 컬렉션에 대 한 개체 요소와 구문 (<xref:System.Windows.Media.GradientStopCollection>) 명시적으로 지정 합니다.  
  
```xaml  
<LinearGradientBrush>  
  <LinearGradientBrush.GradientStops>  
    <GradientStopCollection>  
      <GradientStop Offset="0.0" Color="Red" />  
      <GradientStop Offset="1.0" Color="Blue" />  
    </GradientStopCollection>  
  </LinearGradientBrush.GradientStops>  
</LinearGradientBrush>  
```  
  
 참고는 항상 수 없으면를 명시적으로 컬렉션을 선언 합니다. 예를 들어, 선언 하려고 <xref:System.Windows.TriggerCollection> 앞에 나온에 명시적으로 <xref:System.Windows.Style.Triggers%2A> 예에서는 실패 합니다. 컬렉션 클래스는 기본 생성자를 지원 해야 한다는 요구 컬렉션을 명시적으로 선언 및 <xref:System.Windows.TriggerCollection> 기본 생성자가 없습니다.  
  
<a name="xaml_content_properties"></a>   
## <a name="xaml-content-properties"></a>XAML 콘텐츠 속성  
 XAML 콘텐츠 구문은 지정 하는 클래스에만 사용할 수 있는 구문에서 <xref:System.Windows.Markup.ContentPropertyAttribute> 클래스 선언의 일부로 합니다. <xref:System.Windows.Markup.ContentPropertyAttribute> 요소 (파생된 클래스 포함)의 해당 형식에 대 한 콘텐츠 속성은 속성 이름을 참조 합니다. XAML 프로세서에서 처리 될 때 모든 자식 요소 또는 내부 텍스트는 태그와 개체 요소의 닫는 태그 사이 있는 해당 개체에 대 한 XAML 콘텐츠 속성의 값으로 할당 됩니다. 콘텐츠 속성에 대 한 명시적 속성 요소를 지정할 수는 있지만이 사용법 일반적으로.NET 참조의 XAML 구문 섹션에 표시 되지 않습니다. 자세한 정보 표시 명시적 기술은 태그 스타일 문제 또는 태그 명확성에 대 한 필요에 따른 값을 갖지만 콘텐츠 속성의 의도 부모-자식으로 있는 요소를 직접 중첩 될 수 있도록 태그를 간소화 하는 일반적으로. 속성 요소 태그 요소에 다른 속성에 대 한 엄격한 XAML 언어 정의; 당 "콘텐츠"로 할당 되지 않습니다. XAML 파서가 처리 순서에서 이전에 처리 되 고 "콘텐츠"로 간주 되지 않습니다.  
  
### <a name="xaml-content-property-values-must-be-contiguous"></a>XAML 콘텐츠 속성 값이 연속적 이어야 합니다.  
 XAML 콘텐츠 속성의 값 해당 개체 요소에서 맨 앞 또는 다른 속성 요소의 맨 뒤 제공 수 해야 합니다. 이 XAML 콘텐츠 속성의 값을 문자열로 또는 개체를 하나 이상으로 지정 됩니다 든에 적용 합니다. 예를 들어 다음 태그를 구문 분석 하지 않습니다.  
  
```  
<Button>I am a   
  <Button.Background>Blue</Button.Background>  
  blue button</Button>  
```  
  
 이 동작은 잘못 기본적으로 시도 하면이 구문은 된 명시적 콘텐츠 속성에 대 한 속성 요소 구문을 사용 하 여 콘텐츠 속성 두 번 설정 되기 때문에:  
  
```xml  
<Button>  
  <Button.Content>I am a </Button.Content>  
  <Button.Background>Blue</Button.Background>  
  <Button.Content> blue button</Button.Content>  
</Button>  
```  
  
 콘텐츠 속성은 컬렉션 및 자식 요소에 속성 요소와 함께 섞여 경우은 잘못 되었습니다. 마찬가지로 예제가입니다.  
  
```xml  
<StackPanel>  
  <Button>This example</Button>  
  <StackPanel.Resources>  
    <SolidColorBrush x:Key="BlueBrush" Color="Blue"/>  
  </StackPanel.Resources>  
  <Button>... is illegal XAML</Button>  
</StackPanel>  
```  
  
<a name="content_properties_and_collection_syntax_combined"></a>   
## <a name="content-properties-and-collection-syntax-combined"></a>콘텐츠 속성 및 컬렉션 구문 조합  
 허용 하려면 두 개 이상의 단일 개체 요소 내용으로 콘텐츠 속성의 유형을 구체적으로 컬렉션 형식 이어야 합니다. 컬렉션 형식에 대 한 속성 요소 구문을 처럼 XAML 프로세서는 형식인 컬렉션 형식을 식별 해야 합니다. XAML 콘텐츠 속성 형식이 컬렉션이 요소에는 XAML 콘텐츠 속성을 다음 암시적된 컬렉션 형식을 개체 요소로 태그에 지정 하지 않아도 고 XAML 콘텐츠 속성인 속성 el로 지정할 필요가 없습니다. ement 합니다. 따라서 태그에서 콘텐츠 모델의 내용으로 할당 된 둘 이상의 자식 요소가 생깁니다 수 있습니다. 다음은 콘텐츠 구문에 대 한는 <xref:System.Windows.Controls.Panel> 클래스를 파생 합니다. 모든 <xref:System.Windows.Controls.Panel> 되도록 XAML 콘텐츠 속성을 설정 하는 파생된 클래스 <xref:System.Windows.Controls.Panel.Children%2A>, 형식의 값이 필요한 <xref:System.Windows.Controls.UIElementCollection>합니다.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxContent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page5.xaml#syntaxcontent)]  
  
 두는 속성 요소에 대 한 <xref:System.Windows.Controls.Panel.Children%2A> 의 요소가 <xref:System.Windows.Controls.UIElementCollection> 태그에 필요 합니다. 재귀적으로 정의 하는 요소를 포함 되도록이 xaml 디자인 기능은 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 은 인접 부모-자식 요소 관계 없이 중간 속성 요소 태그 중첩 된 요소가 트리로 표현 보다 직관적으로 또는 컬렉션 개체입니다. 사실, <xref:System.Windows.Controls.UIElementCollection> 지정할 수 없습니다 명시적으로 태그에서 개체 요소로 설계 합니다. 원래 용도 암시적 컬렉션이 이므로 <xref:System.Windows.Controls.UIElementCollection> 공용 기본 생성자를 노출 하지 않으며 따라서 개체 요소로 인스턴스화할 수 없습니다.  
  
### <a name="mixing-property-elements-and-object-elements-in-an-object-with-a-content-property"></a>속성 요소와 콘텐츠 속성을 갖는 개체의 개체 요소  
 XAML 사양 XAML 프로세서는 object 요소 내에서 XAML 콘텐츠 속성을 채우는 데 사용 되는 개체 요소 연속적 이어야 하 고 혼합 하지 시행할 수를 선언 합니다. 속성 요소와 콘텐츠가 혼합에 대 한이 제한에 의해 적용 된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML 프로세서.  
  
 Object 요소 내에서 즉시 첫 번째 태그로 자식 개체 요소를 사용할 수 있습니다. 속성 요소 도입할 수 있습니다. 또는 하나 이상의 속성 요소 콘텐츠를 차례로 더 많은 속성 요소를 지정할 수 있습니다. 하지만 속성 요소 콘텐츠 뒤 되 면 더 이상 콘텐츠를 지정할 수 없으며, 속성 요소에만 추가할 수 있습니다.  
  
 이 콘텐츠 / 내용으로 사용 되는 내부 텍스트에 속성 요소 순서 요구 사항은 적용 되지 않습니다. 그러나 이것이 여전히 유효한 공백 속성 요소에 내부 텍스트가 있는 섞여 하는 경우 태그에서 시각적으로 감지 하기가 어려울 것 때문에 내부 텍스트가 연속을 유지 하는 좋은 태그 스타일입니다.  
  
<a name="xaml_namespaces"></a>   
## <a name="xaml-namespaces"></a>XAML 네임스페이스  
 이전 구문 예제에서는 기본 XAML 네임 스페이스 이외의 XAML 네임 스페이스를 지정 합니다. 일반적인 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 되도록 지정 된 응용 프로그램을 기본 XAML 네임 스페이스는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 네임 스페이스입니다. 기본 XAML 네임 스페이스 이외의 모든 XAML 네임 스페이스를 지정 하 고 계속과 유사한 구문을 사용 하 여 수 있습니다. 하지만 그런 다음 원하는 위치 여기서는 클래스 이름이 기본 XAML 네임 스페이스 내에서 액세스할 수 없는 해당 클래스 이름 앞에 XAML 네임 스페이스 접두사와 함께 해당 CLR 네임 스페이스에 매핑된 대로 합니다. 예를 들어 `<custom:Example/>` 는 개체 요소 구문의 인스턴스를 인스턴스화하는 `Example` 해당 클래스 (및 가능한 지원 형식이 포함 된 외부 어셈블리 정보)를 포함 하는 CLR 네임 스페이스에 이전에 매핑된 클래스는 `custom` 접두사입니다.  
  
 XAML 네임 스페이스에 대 한 자세한 내용은 참조 [XAML 네임 스페이스 및 WPF XAML에 대 한 매핑 Namespace](../../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)합니다.  
  
<a name="markup_extensions"></a>   
## <a name="markup-extensions"></a>태그 확장  
 XAML 개체 요소 또는 특성 값 문자열의 일반 XAML 프로세서 처리에서 수 있도록 하 고 처리 지원 클래스를 통해 엔터티를 프로그래밍 하는 태그 확장을 정의 합니다. 여는 중괄호 ({})에 닫는 중괄호 (}) 이외의 모든 문자는 특성 구문을 사용 하는 경우에 XAML 프로세서는 태그 확장을 식별 하는 문자입니다. 첫 번째 문자열에서 여는 중괄호 뒤 해당 부분 문자열 true 클래스 이름의 일부인 경우 참조 부분 문자열을 생략할 수 있는 특정 확장 동작을 "Extension"을 제공 하는 클래스를 참조 해야 합니다. 그런 다음에 단일 공백이 나타날 수 있습니다 하 고 각 후속 문자 입력으로 사용 됩니다 확장 구현에서 닫는 중괄호 발견 될 때까지 합니다.  
  
 .NET XAML 구현에서 사용 된 <xref:System.Windows.Markup.MarkupExtension> 추상 클래스에서 지원 되는 태그 확장의 모든 작업에 대 한 기준으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 뿐만 아니라 다른 프레임 워크 또는 기술 합니다. 태그 확장 하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 구체적으로 구현 하는 다른 기존 개체를 참조 하거나 런타임에 평가 하는 개체에 대 한 지연 된 참조를 확인 하는 방법 제공 하려는 경우가 많습니다. 지정 하 여 간단한 WPF 데이터 바인딩을 수행할 예를 들어는 `{Binding}` 특정 속성 일반적으로 수행 되는 값 대신 태그 확장 합니다. WPF 태그 확장은 대부분 여기서 특성 구문을 가능 하지 않은 속성에 대 한 특성 구문을 사용 합니다. 예를 들어 한 <xref:System.Windows.Style> 개체는 중첩 된 일련의 개체 및 속성을 포함 하는 상대적으로 복잡 한 형식입니다. WPF의 스타일은에 리소스로 정의 일반적으로 <xref:System.Windows.ResourceDictionary>, 다음 리소스를 요청 하는 두 개의 WPF 태그 확장 중 하나를 통해 참조 합니다. 태그 확장을 리소스 조회 속성 값의 평가 지연 및의 값을 제공할 수 있도록는 <xref:System.Windows.FrameworkElement.Style%2A> 형식 라인 속성 <xref:System.Windows.Style>에 특성 다음 예제와 같이 구문:  
  
 `<Button Style="{StaticResource MyStyle}">My button</Button>`  
  
 여기에서 `StaticResource` 식별 된 <xref:System.Windows.StaticResourceExtension> 태그 확장 구현에 제공 하는 클래스입니다. 다음 문자열 `MyStyle` 기본값이 아닌에 대 한 입력으로 사용 <xref:System.Windows.StaticResourceExtension> 확장명 문자열에서 가져온 대로 매개 변수 선언에서 요청 된 생성자 <xref:System.Windows.ResourceKey>합니다. `MyStyle`이어야 하는데는 [X:key](../../../../docs/framework/xaml-services/x-key-directive.md) 값은 <xref:System.Windows.Style> 원본으로 정의 합니다. [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) 사용 요청 리소스 사용을 제공할 수는 <xref:System.Windows.Style> 로드할 때 정적 리소스 조회 논리를 통해 속성 값입니다.  
  
 태그 확장에 대한 자세한 내용은 [XAML 태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)을 참조하세요. 태그 확장 및 다른 XAML 일반.NET XAML 구현에서 사용 하는 기능을 프로그래밍에 대 한 참조를 참조 하십시오. [XAML Namespace (x:) 언어 기능](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md)합니다. WPF 관련 태그 확장에 대 한 참조 [WPF XAML 확장](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md)합니다.  
  
<a name="attached_properties"></a>   
## <a name="attached-properties"></a>연결된 속성  
 연결 된 속성에는 그에 따라 속성 소유 하 고 특정 형식으로 정의 된 XAML에서 도입 된 프로그래밍 개념은 모든 요소에 속성 요소 또는 특성으로 하지만 설정 합니다. 주로 모든 요소에서 광범위 하 게 공유 개체 모델을 요구 하지 않고 자식 요소는 부모 요소에 정보를 보고할 태그 구조에 사용할 수 있도록은 연결 된 속성은 위한 것입니다. 반대로, 자식 요소에 정보를 보고할 부모 요소에 의해 연결 된 속성을 사용할 수 있습니다. 연결 된 속성 및 나만의 사이트 생성 하는 방법의 목적에 대 한 자세한 내용은 연결 된 속성을 참조 [연결 된 속성 개요](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)합니다.  
  
 연결 된 속성도 지정 한다는 점에서 속성 요소 구문을 외견상으로 유사한 구문을 사용 하 여 한 *typeName*. *propertyName* 조합 합니다. 다음과 같은 두 가지 중요한 차이점이 있습니다.  
  
-   사용할 수는 *typeName*. *propertyName* 특성 구문을 통해 연결된 된 속성을 설정 하는 경우에 조합 합니다. 연결 된 속성은 유일한 경우 속성 이름 정규화는 특성 구문에 대 한 요구 사항입니다.  
  
-   또한 연결 된 속성의 속성 요소 구문을 사용할 수 있습니다. 그러나 일반적인 속성 요소 구문에 대 한는 *typeName* 속성 요소를 포함 하는 개체 요소를 지정 합니다. 연결된 된 속성을 참조 하는 경우 다음의 *typeName* 개체 요소가 포함 하는 것이 아니라 연결된 된 속성을 정의 하는 클래스입니다.  
  
<a name="attached_events"></a>   
## <a name="attached-events"></a>연결된 이벤트  
 연결 된 이벤트는 모든 개체 요소에서 처리기를 연결할 수 있지만 여기서는 특정 형식으로 이벤트를 정의할 수는 XAML에서 도입 된 또 다른 프로그래밍 개념입니다. WOF 구현에서 종종 연결된 된 이벤트를 정의 하는 형식이 서비스를 정의 하는 정적 형식이 고 이러한 연결 된 이벤트는 서비스를 노출 하는 형식의 별칭을 라우트된 이벤트에 의해 노출 되는 경우에 따라 합니다. 연결 된 이벤트에 대 한 처리기 특성 구문을 통해 지정 됩니다. 수 있도록 연결 된 이벤트에 대 한 확장 특성 구문 되 연결 된 이벤트와 같이 한 *typeName*. *eventName* 사용, 여기서 *typeName* 제공 하는 클래스 `Add` 및 `Remove` 연결 된 이벤트 인프라에 대 한 이벤트 처리기 접근자 및 *eventName* 이벤트 이름입니다.  
  
<a name="anatomy_of_a_xaml_page_root_element"></a>   
## <a name="anatomy-of-a-xaml-root-element"></a>XAML 루트 요소 분석  
 다음 표에서 일반적인 XAML 루트 요소를, 중단 된 표시 루트 요소의 특정 특성을 보여 줍니다.  
  
|||  
|-|-|  
|`<Page`|루트 요소의 여는 object 요소|  
|`xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`|기본값 ([!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]) XAML 네임 스페이스|  
|`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`|XAML 언어 XAML 네임 스페이스|  
|`x:Class="ExampleNamespace.ExampleCode"`|Partial 클래스에 대해 정의 된 모든 코드 숨김에 태그를 연결 하는 partial 클래스 선언|  
|`>`|Object 요소는 루트의 끝입니다. 요소가 자식 요소를 포함 하기 때문에 개체 아직 닫혀 있지 않습니다.|  
  
<a name="optional_and_nonrecommended_xaml_usages"></a>   
## <a name="optional-and-nonrecommended-xaml-usages"></a>선택적 사용  
 다음 섹션에서는 XAML 사용 XAML 프로세서에서 지 원하는 기술적으로 되지만 자세한 정도 또는 기타 미적인 문제 XAML 파일 읽을 때 방해를 생성 하 여 XAML 소스를 포함 하는 응용 프로그램 개발 .  
  
### <a name="optional-property-element-usages"></a>선택적 속성 요소 사용  
 선택적 속성 요소 사용을 구체적으로 지정 요소 콘텐츠 속성 XAML 프로세서에서는 암시적 포함 됩니다. 콘텐츠를 선언할 때 예를 들어는 <xref:System.Windows.Controls.Menu>, 명시적으로 선언 하도록 선택할 수 있습니다는 <xref:System.Windows.Controls.ItemsControl.Items%2A> 의 컬렉션은 <xref:System.Windows.Controls.Menu> 으로 `<Menu.Items>` 속성 요소 태그 및 위치는 각 <xref:System.Windows.Controls.MenuItem> 내에서 `<Menu.Items>`, 대신 암시적 XAML 프로세서의 동작을 사용 하 여 보다 하의 모든 자식 요소는 <xref:System.Windows.Controls.Menu> 이어야 합니다는 <xref:System.Windows.Controls.MenuItem> 에 배치 하 고는 <xref:System.Windows.Controls.ItemsControl.Items%2A> 컬렉션입니다. 경우에 따라 선택적 사용법 태그에 표시 된 대로 개체 구조를 시각적으로 명확 하 게 데 도움이 됩니다. 또는 경우에 따라 명시적 속성 요소 사용 기술적으로 작동 하지만 중첩 된 태그 확장 특성 값 내에서 같은 시각적으로 혼동 하는 태그를 방지할 수 있습니다.  
  
### <a name="full-typenamemembername-qualified-attributes"></a>한정 된 전체 typeName.memberName 특성  
 *typeName*. *memberName* 특성 실제로 라우트된 이벤트 사례만 보다 더 광범위 하 게 작동에 대 한를 형성 합니다. 하지만 다른 경우에 해당 형식이 불필요 하며 이유로 태그 스타일 및 가독성을 하지 않아야 합니다. 다음 예제에서는 세 개의 각에 대 한 참조는 <xref:System.Windows.Controls.Control.Background%2A> 특성은 완전히 동일 합니다.  
  
 [!code-xaml[XAMLOvwSupport#TypeNameProp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenameprop)]  
  
 `Button.Background`사용 하기 때문에 해당 속성에 대 한 정규화 된 조회 <xref:System.Windows.Controls.Button> 성공 (<xref:System.Windows.Controls.Control.Background%2A> 컨트롤에서 상속 된) 및 <xref:System.Windows.Controls.Button> 개체 요소의 클래스 또는 기본 클래스입니다. `Control.Background`때문에 작동는 <xref:System.Windows.Controls.Control> 클래스 정의 <xref:System.Windows.Controls.Control.Background%2A> 및 <xref:System.Windows.Controls.Control> 는 <xref:System.Windows.Controls.Button> 기본 클래스입니다.  
  
 그러나 다음 *typeName*. *memberName* 양식 예제는 작동 하지 않으며 따라서 주석이 표시 됩니다.  
  
 [!code-xaml[XAMLOvwSupport#TypeNameBadProp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenamebadprop)]  
  
 <xref:System.Windows.Controls.Label>다른 파생된 클래스의 <xref:System.Windows.Controls.Control>, 및를 지정한 경우 `Label.Background` 내에서 한 <xref:System.Windows.Controls.Label> object 요소가이 사용법은 동작 합니다. 그러나 때문에 <xref:System.Windows.Controls.Label> 클래스 또는 기본 클래스의 <xref:System.Windows.Controls.Button>, 지정한 XAML 프로세서 동작을 처리 하는 것 `Label.Background` 연결된 된 속성으로. `Label.Background`사용 가능한 연결 된 속성을 아니며이 사용법은 실패 합니다.  
  
### <a name="basetypenamemembername-property-elements"></a>baseTypeName.memberName 속성 요소  
 방법을 유사한 방식으로 *typeName*. *memberName* 특성 구문에 대해 작동 하는 폼은 *baseTypeName*. *memberName* 구문에 속성 요소 구문에 대 한 작동 합니다. 예를 들어, 다음 구문은 작동합니다.  
  
 [!code-xaml[XAMLOvwSupport#GoofyPE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofype)]  
  
 속성 요소도 지정 된 여기서 `Control.Background` 속성 요소에 포함 된 경우에 `Button`합니다.  
  
 마찬가지로 하지만 *typeName*. *memberName* 특성에 대 한 폼 *baseTypeName*. *memberName* 태그에서 저하 스타일 이며 하지 않아야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [XAML 개요(WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [XAML 네임스페이스(x:) 언어 기능](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md)  
 [WPF XAML 확장](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md)  
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [TypeConverter 및 XAML](../../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md)  
 [WPF에 대한 XAML 및 사용자 지정 클래스](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
