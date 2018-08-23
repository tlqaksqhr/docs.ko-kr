---
title: XAML 구문 정보
ms.date: 03/30/2017
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
ms.openlocfilehash: f2c3aab20dc5bcf9b0f9f7053323ccd7a04443cc
ms.sourcegitcommit: bd4fa78f5a46133efdead1bc692a9aa2811d7868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/23/2018
ms.locfileid: "42755053"
---
# <a name="xaml-syntax-in-detail"></a>XAML 구문 정보
이 항목에서는 XAML 구문 요소에 설명 하는 데 사용 되는 용어를 정의 합니다. 이러한 용어는 특히 및 XAML 또는 System.Xaml 수준에서 XAML 언어 지원을 사용 하도록 설정 하는 기본 XAML 개념을 사용 하는 다른 프레임 워크에 대 한 WPF 설명서에 대 한 모두이 문서의 나머지 부분에서 자주 사용 됩니다. 이 항목에서는 확장 항목에 도입 하는 기본 용어 [XAML 개요 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)합니다.  
  

  
<a name="the_xaml_language_specification"></a>   
## <a name="the-xaml-language-specification"></a>XAML 언어 사양  
 또한 여기에 정의 된 XAML 구문 용어 정의 되었거나 XAML 언어 사양 내에서 참조 합니다. XAML은 XML 기반 언어 및 또는 XML 구조적 규칙에 따라 확장 합니다. 일부의 용어를 공유 하거나 XML 언어 또는 XML 문서 개체 모델을 설명 하는 경우 일반적으로 사용 되는 용어를 기반으로 합니다.  
  
 XAML 언어 사양에 대 한 자세한 내용은 다운로드 [ \[MS XAML\] ](http://go.microsoft.com/fwlink/?LinkId=114525) Microsoft 다운로드 센터에서.  
  
<a name="xaml_and_clr"></a>   
## <a name="xaml-and-clr"></a>XAML 및 CLR  
 XAML은 태그 언어입니다. [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]런타임 실행 하면 해당 이름으로 암시 한 대로, 합니다. XAML 아닙니다 자체적으로 직접 CLR 런타임에서 사용 되는 일반적인 언어 중 하나입니다. 대신, 고유한 형식 시스템을 지 원하는 것으로 XAML의 생각할 수 있습니다. WPF에서 사용 되는 특정 XAML 구문 분석 시스템은 CLR 및 CLR 형식 시스템을 기반으로 합니다. XAML 형식은 wpf XAML을 구문 분석할 때 런타임 표현을 인스턴스화하기 위해 CLR 형식에 매핑됩니다. 이 따라서 구문 설명에이 문서의 나머지 XAML 언어 사양에 해당 구문 설명 하지 않습니다 하는 경우에 CLR 형식 시스템에 대 한 참조가 포함 됩니다. (XAML 언어 사양 수준별로 XAML 형식에 매핑될 수 있는 CLR 수 없지만 생성 및 다른 XAML 파서를 사용 해야 하는 모든 다른 형식 시스템,.)  
  
#### <a name="members-of-types-and-class-inheritance"></a>형식 및 클래스 상속의 멤버  
 속성 및의 XAML 멤버로 표시 하므로 이벤트는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 종류는 종종 기본 형식에서 상속 됩니다. 예를 들어이 예제에서는: `<Button Background="Blue" .../>`합니다. 합니다 <xref:System.Windows.Controls.Control.Background%2A> 속성을 즉시 선언 된 속성에 없는 <xref:System.Windows.Controls.Button> 클래스를 클래스 정의 리플렉션 결과 또는 설명서에서 확인 하려는 경우. 대신 <xref:System.Windows.Controls.Control.Background%2A> 기본에서 상속 된 <xref:System.Windows.Controls.Control> 클래스입니다.  
  
 클래스 상속 동작은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML 요소는 XML 태그의 해석 스키마 적용 하는 상당한 차이가 있습니다. 클래스 상속 하거나 인터페이스와 관련 된 중간 기본 클래스는 추상적 하는 경우에 특히 복잡 한 될 수 있습니다. 이 일반적으로 사용 되는 XAML 요소 및 해당 허용 가능한 특성의 집합은 정확 하 고 완전히 스키마 유형을 사용 하 게 표현 하기 어렵게 하는 한 가지 이유 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] DTD 나 XSD 형식과 같은 프로그래밍 합니다. 또 다른 이유는 확장성 및 자체 XAML 언어의 형식 매핑 기능이 허용 되는 형식 및 멤버의 모든 고정 표현의 불완전 합니다.  
  
<a name="object_element_syntax"></a>   
## <a name="object-element-syntax"></a>개체 요소 구문  
 *개체 요소 구문을* XML 요소를 선언 하 여 CLR 클래스 또는 구조체를 인스턴스화하는 XAML 태그 구문입니다. 이 구문 요소에 대 한 구문의 HTML과 같은 다른 태그 언어와 유사합니다. 개체 요소 구문은 왼쪽된 꺾쇠 괄호 (\<) 클래스 또는 구조체를 인스턴스화할 액션이의 형식 이름 바로 뒤, 합니다. 0 개 이상의 공간 형식 이름, 따르면 및 0 개 이상의 특성 선언할 수도 개체 요소의 각 특성 이름을 구분 하는 하나 이상의 공백으로 = "value" 쌍입니다. 마지막으로 다음 중 하나를 참 이어야 합니다.  
  
-   요소 및 태그를 슬래시 (/)는 오른쪽 꺾쇠 괄호 (>) 바로 뒤에 여 닫아야 합니다.  
  
-   오른쪽 꺾쇠 괄호 (>)에서 여는 태그를 완료 해야 합니다. 다른 개체 요소, 속성 요소 또는 내부 텍스트를 여는 태그를 따르면 됩니다. 콘텐츠를 여기 포함 될 수 있습니다 정확 하 게 요소 개체 모델에서 일반적으로 제한 됩니다. 또한 개체 요소의 닫는 태그를 해당 하는 적절 한 중첩에 존재 하 고 다른 중괄호와 닫는 태그 쌍을 사용 하 여 분산 해야 합니다.  
  
 .NET에서 구현 된 XAML 개체 요소 형식, 속성 또는 이벤트 및 CLR 네임 스페이스와 어셈블리에 XAML 네임 스페이스에는 특성으로 매핑하는 규칙 집합이 있습니다. WPF 및.NET Framework에 대 한 XAML 개체 요소를 매핑할 [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] 형식에 정의 된 대로 참조 어셈블리 및 해당 형식의 멤버에 특성이 매핑됩니다. XAML에서 CLR 형식에서 참조 하는 경우 해당 형식의 상속된 된 멤버에 액세스할을 수 있습니다.  
  
 다음 예제는의 새 인스턴스를 인스턴스화하는 개체 요소 구문 예를 들어 합니다 <xref:System.Windows.Controls.Button> 클래스 및도 지정을 <xref:System.Windows.FrameworkElement.Name%2A> 특성 및 해당 특성에 대 한 값:  
  
 [!code-xaml[XAMLOvwSupport#SyntaxOE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxoe)]  
  
 다음 예제는 XAML 콘텐츠 속성 구문을 포함 하는 개체 요소 구문입니다. 설정에 사용할 포함 된 내부 텍스트를 <xref:System.Windows.Controls.TextBox> XAML 콘텐츠 속성 <xref:System.Windows.Controls.TextBox.Text%2A>합니다.  
  
 [!code-xaml[XAMLOvwSupport#ThisIsATextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#thisisatextbox)]  
  
### <a name="content-models"></a>콘텐츠 모델  
 클래스는 XAML 개체 요소 구문 측면에서 사용을 지원할 수 있지만 해당 요소는 전반적인 콘텐츠 모델이 나 요소 트리의 필요한 위치에 배치 되는 경우에 응용 프로그램 또는 페이지에서 제대로 작동 합니다. 예를 들어를 <xref:System.Windows.Controls.MenuItem> 일반적으로 배치할 자식으로는 <xref:System.Windows.Controls.Primitives.MenuBase> 파생 클래스와 같은 <xref:System.Windows.Controls.Menu>. 특정 요소에 대 한 모델은 컨트롤 및 기타 클래스 페이지에서 설명의 일부로 문서화 되어 콘텐츠 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML 요소로 사용 될 수 있는 클래스입니다.  
  
<a name="properties_of_object_elements"></a>   
## <a name="properties-of-object-elements"></a>개체 요소의 속성  
 XAML에서 속성은 다양 한 구문으로 설정 됩니다. 특정 속성에 사용할 수 있는 구문 설정 하는 속성의 기본 형식 시스템 특성에 따라 다릅니다.  
  
 속성의 값을 설정 하 여 추가 기능 또는 특징 개체 런타임 개체 그래프에 존재 하므로 합니다. Object 요소에서 만든된 개체의 초기 상태는 기본 생성자 동작을 기반으로 합니다. 일반적으로 응용 프로그램은 특정된 개체의 완전히 기본 인스턴스 이외의 사용 합니다.  
  
<a name="attribute_syntax_properties"></a>   
## <a name="attribute-syntax-properties"></a>특성 구문(속성)  
 특성 구문은 기존 개체 요소에 특성을 선언 하 여 속성 값을 설정 하는 XAML 태그 구문입니다. 특성 이름에는 관련 개체 요소를 지 원하는 클래스의 속성의 CLR 멤버 이름과 일치 해야 합니다. 특성 이름 뒤에 할당 연산자 (=)가 있습니다. 특성 값을 따옴표로 묶인 문자열 이어야 합니다.  
  
> [!NOTE]
>  교대로 반복 되는 따옴표 특성 내에서 리터럴 따옴표를 배치에 사용할 수 있습니다. 예를 들어 그 안에 큰따옴표 문자를 포함 하는 문자열을 선언 하는 수단으로 작은따옴표를 사용할 수 있습니다. 작은따옴표 또는 큰따옴표를 사용 하는지 여부를 열기 및 닫기 특성 값 문자열에 대 한 일치 하는 쌍을 사용 해야 합니다. 밖에도 이스케이프 시퀀스 또는 기타 기술을 모든 특정 XAML 구문을 사용 하 여 문자 제한 해결 하기 위한 사용할 수 있습니다. 참조 [XML 문자 엔터티 및 XAML](../../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)합니다.  
  
 특성 구문을 통해 설정 하려면 속성을 public 이어야 하며 쓰기 가능 해야 합니다. 지원 형식 시스템에서 속성의 값을 값 형식 이어야 합니다. 또는 지 원하는 형식을 인스턴스화하거나 관련 액세스 하는 경우 XAML 프로세서에서 참조할 수 있는 참조 형식을 수 있어야 합니다.  
  
 WPF XAML 이벤트에 대 한 특성 이름으로 참조 되는 이벤트는 public 이어야 하며 public 대리자를 있어야 합니다.  
  
 속성 또는 이벤트 클래스 또는 포함 하는 개체 요소에 의해 인스턴스화되는 구조체의 멤버 여야 합니다.  
  
### <a name="processing-of-attribute-values"></a>특성 값 처리  
 여는 태그와 닫는 따옴표 내에 포함 된 문자열 값을 XAML 프로세서에서 처리 됩니다. 속성에 대 한 기본 처리 동작 기본 CLR 속성의 형식에 의해 결정 됩니다.  
  
 특성 값을 다음 중 하나에 의해 채워집니다.이 처리 순서를 사용 하 여:  
  
1.  XAML 프로세서는 중괄호 또는에서 파생 되는 개체 요소를 발견할 경우 <xref:System.Windows.Markup.MarkupExtension>, 다음 참조 된 태그 확장의 값을 문자열로 처리 하는 대신 먼저 평가 됩니다 및 태그 확장에 의해 반환 된 개체를 사용 하 여으로 값입니다. 대부분의 경우에서 태그 확장에서 반환 되는 개체에 기존 개체 또는 런타임까지 평가 지연 하는 새로 인스턴스화된 개체가 아닌 식에 대 한 참조 됩니다.  
  
2.  속성 선언 되 면 특성이 사용 된 <xref:System.ComponentModel.TypeConverter>, 해당 속성의 값 형식 선언 또는 특성이 사용 된 <xref:System.ComponentModel.TypeConverter>특성의 문자열 값으로 변환 입력 유형 변환기에 제출 되 고 변환기가 반환 됩니다는 새 개체 인스턴스입니다.  
  
3.  없는 경우 없는 <xref:System.ComponentModel.TypeConverter>, 속성 형식으로의 직접 변환을 시도 합니다. 이 최종 단계는 XAML 언어 기본 형식 또는 명명 된 상수 (다음 파서가 일치 하는 값에 액세스) 열거형의 이름 확인 간의 파서 네이티브 값을 직접 변환입니다.  
  
#### <a name="enumeration-attribute-values"></a>열거형 특성 값  
 XAML의 열거형에서 처리 하는 본질적으로 XAML 파서 및 열거형의 명명 된 상수 중 하나의 문자열 이름을 지정 하 여 열거형의 멤버를 지정 해야 합니다.  
  
 Nonflag 열거형 값에 대 한 기본 동작 특성 값의 문자열을 처리 하 고 열거형 값 중 하나를 해결 하는 합니다. 열거형 형식으로 지정 하지 않으면 *열거형*. *값*처럼 코드에서 작업을 수행 합니다. 만 지정 하는 대신 *값*, 및 *열거형* 설정 하는 속성의 형식에서 유추 됩니다. 특성을 지정 하는 경우는 *열거형*. *값* 폼을 확인 하지 것입니다 올바르게 합니다.  
  
 플래그 열거형에 대 한 동작을 기반으로 합니다 <xref:System.Enum.Parse%2A?displayProperty=nameWithType> 메서드. 각 값을 쉼표로 구분 하 여 플래그 열거형에 대 한 여러 값을 지정할 수 있습니다. 그러나 플래그 되는 열거형 값을 결합할 수 없습니다. 예를 들어, 있습니다 수 없습니다. 구문을 사용 하 여 쉼표를 만들려고 시도 <xref:System.Windows.Trigger> nonflag 열거의 여러 조건에는 역할:  
  
```  
<!--This will not compile, because Visibility is not a flagwise enumeration.-->  
...  
<Trigger Property="Visibility" Value="Collapsed,Hidden">  
  <Setter ... />  
</Trigger>  
...  
```  
  
 XAML에서 설정할 수 있는 특성을 지원 하면 플래그 열거형은 WPF에서 드물게 나타납니다. 그러나 이러한 하나의 열거형은 <xref:System.Windows.Media.StyleSimulations>합니다. 예를 들어 쉼표로 구분 된 플래그 특성 구문을 사용 하 여에 대 한 설명에 제공 된 예제를 수정할 수 있습니다는 <xref:System.Windows.Documents.Glyphs> 클래스 `StyleSimulations = "BoldSimulation"` 될 수 있습니다 `StyleSimulations = "BoldSimulation,ItalicSimulation"`합니다. <xref:System.Windows.Input.KeyBinding.Modifiers%2A?displayProperty=nameWithType> 속성이 다른 둘 이상의 열거형 값을 지정할 수 있습니다. 하지만 때문에이 속성에 특별 한 경우 발생는 <xref:System.Windows.Input.ModifierKeys> 열거형 자체 형식 변환기를 지원 합니다. 한정자에 대 한 형식 변환기는 쉼표 (,)가 아닌 구분 기호를 더하기 기호 (+)를 사용합니다. 이 변환은 Microsoft Windows 프로그래밍에서 "Ctrl + Alt"와 같은 키 조합을 나타내는 보다 일반적인 구문을 지원 합니다.  
  
### <a name="properties-and-event-member-name-references"></a>속성 및 이벤트 멤버 이름 참조  
 특성을 지정할 때 모든 속성 또는 이벤트를 포함 하는 개체 요소에 대 한 인스턴스화 CLR 형식의 멤버를 참조할 수 있습니다.  
  
 또는 연결된 된 속성을 참조할 수 있습니다 또는 연결 된 이벤트를 포함 하는 개체 요소와 무관 합니다. (연결 된 속성은 이후 섹션에서 설명 합니다.)  
  
 모든 이벤트를 사용 하 여 기본 네임 스페이스를 통해 액세스할 수 있는 모든 개체의 이름을 지정할 수도 있습니다는 *typeName*. *이벤트* 부분적으로 정규화 된 이름,이 구문은 라우트된 이벤트에 대 한 처리기를 연결 하는 지원 처리기 라우팅 자식 요소가 부모 요소에서 이벤트를 처리 하는 것도 없는 이벤트 해당 멤버 테이블에 있습니다. 이 구문은 연결 된 이벤트 구문을 비슷하지만 여기 이벤트가 연결 된 이벤트를 true 되지 않습니다. 대신은 정규화 된 이름 사용 하는 이벤트를 참조 합니다. 자세한 내용은 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)합니다.  
  
 일부 시나리오에 대 한 속성 이름은 경우에 따라 특성 이름이 아닌 특성의 값으로 제공 됩니다. 이 속성 이름이 같은 형태로 지정 된 속성 한정자를 포함할 수도 있습니다 *ownerType*. *dependencyPropertyName*합니다. 이 시나리오는 XAML에서 스타일이 나 템플릿을 작성할 때 일반적입니다. 특성 값으로 제공 하는 속성 이름에 대 한 처리 규칙은 서로 다르며 특정 WPF 하위 시스템의 동작 또는 설정 되는 속성의 형식에 의해 제어 됩니다. 자세한 내용은 참조 하세요 [스타일 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)합니다.  
  
 속성 이름에 대 한 다른 사용 때 특성 값을 속성 간 관계를 설명 합니다. 이 기능은 데이터 바인딩 및 스토리 보드 대상에 대해 사용 되 고으로 활성화 되어를 <xref:System.Windows.PropertyPath> 클래스 및 해당 형식 변환기입니다. 에 대 한 자세한 설명은 조회 의미 체계를 참조 하세요 [PropertyPath XAML 구문](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md)합니다.  
  
<a name="property_element_syntax"></a>   
## <a name="property-element-syntax"></a>속성 요소 구문  
 *속성 요소 구문을* 요소에 대 한 기본 XML 구문 규칙에서 다소 달라 지므로 구문입니다. Xml에서 특성의 값은 사실상 문자열로만 가능한 변형을 사용 하 여 사용 되는 문자열 인코딩 형식만 되 고 있습니다. XAML에서 속성의 값으로 다른 개체 요소를 할당할 수 있습니다. 이 기능은 속성 요소 구문을 사용 하 여 사용할 수 있습니다. 속성 요소 태그에서 특성으로 지정 하는 대신 해당 속성이 여는 요소를 사용 하 여 지정 된 태그 *elementTypeName*. *propertyName* 폼 속성의 값을 지정한 및 다음 속성 요소를 닫습니다.  
  
 특히 구문은 왼쪽된 꺾쇠 괄호 (\<) 클래스 또는 속성 요소 구문에 포함 된 구조체의 형식 이름 바로 뒤, 합니다. 이 바로 뒤에 단일 점 (.), 다음 속성의 이름으로 다음 오른쪽 꺾쇠 괄호 (>). 특성 구문에서와 마찬가지로 속성 지정 된 형식의 선언 된 공용 멤버 내에 있어야 합니다. 속성에 할당할 값 속성 요소 내에 포함 되어 있습니다. 일반적으로 해당 값이 하나에 해당 하는 개체의 요소를 지정 하는, 해당 속성 요소 구문을 주소로 것 이므로 값으로 개체를 지정 하는 시나리오입니다. 마지막으로, 동일한 지정 해당 닫는 태그 *elementTypeName*. *propertyName* 조합을 제공 해야 합니다, 적절 한 중첩을 다른 요소 태그를 사용 하 여 분산 합니다.  
  
 예를 들어, 다음은 속성 요소 구문에 대 한 합니다 <xref:System.Windows.FrameworkElement.ContextMenu%2A> 의 속성을 <xref:System.Windows.Controls.Button>입니다.  
  
 [!code-xaml[XAMLOvwSupport#ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#contextmenu)]  
  
 속성 요소 내에서 값을 지정할 수도 있습니다 지정 하는 속성 형식이 기본 값 형식인 경우 내부 텍스트로 같은 <xref:System.String>, 또는 위치 이름을 지정 하는 열거형입니다. 이러한 각각의이 경우 간단한 특성 구문을 사용할 수도 있으므로 이러한 두 사용 다소 일반적이 지 않습니다. XAML 콘텐츠 속성 되지 않지만 여전히 UI 텍스트 표현에 사용 되는 속성에 대 한 문자열을 사용 하 여 속성 요소를 채우는 한 가지 시나리오는 및 줄 바꿈과 같은 특정 공백 요소는 UI 텍스트에 표시 해야 합니다. 특성 구문 바꿈을 유지할 수 없지만 중요 한 공백이 유지 된 활성 속성 요소 구문을 수 (세부 정보를 참조 하세요. [공백을 XAML 처리](../../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)). 다른 시나리오는 되도록 [X:uid 지시문](../../../../docs/framework/xaml-services/x-uid-directive.md) property 요소에 적용 될 수 있으며 따라서 WPF에서 지역화 해야 하는 값을 출력 BAML로 또는 다른 기술을 통해 내의 값을 표시 합니다.  
  
 속성 요소 WPF 논리적 트리에 표시 되지 않습니다. 속성 요소 속성을 설정 하는 것에 대 한 특정 구문일 뿐 이며 인스턴스 또는 지원 되는 개체를 가진 요소가 아닙니다. (논리적 트리 개념에 대 한 세부 정보를 참조 하세요 [WPF의 트리](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).)  
  
 특성과 속성 요소 구문을 지원 되는 속성에 대 한 두 구문을 일반적으로 동일한 결과 있지만 있는 공백 처리와 같은 미묘한 구문 간에 약간 달라질 수 있습니다.  
  
<a name="collection_syntax"></a>   
## <a name="collection-syntax"></a>컬렉션 구문  
 XAML 사양에 값 형식이 컬렉션이 속성을 식별 하는 XAML 프로세서 구현 합니다. .NET의 일반 XAML 프로세서 구현 관리 코드와 CLR 기반으로 하며 다음 중 하나를 통해 컬렉션 형식을 식별 합니다.  
  
-   구현 형식 <xref:System.Collections.IList>합니다.  
  
-   구현 형식 <xref:System.Collections.IDictionary>합니다.  
  
-   형식에서 파생 <xref:System.Array> (XAML의 배열에 대 한 자세한 내용은 참조 하세요. [X:array 태그 확장](../../../../docs/framework/xaml-services/x-array-markup-extension.md).)  
  
 속성 형식의 컬렉션인 경우 유추 된 컬렉션 형식 개체 요소 태그에 지정할 필요 하지 않습니다. 대신 컬렉션의 항목 될 하는 요소는 속성 요소의 자식 요소를 하나 이상으로 지정 됩니다. 이러한 각 항목 로드 중 개체에 계산 되 고 호출 하 여 컬렉션에 추가 된 `Add` 암시적된 컬렉션 메서드. 예를 들어를 <xref:System.Windows.Style.Triggers%2A> 의 속성 <xref:System.Windows.Style> 특수 한 컬렉션 형식을 <xref:System.Windows.TriggerCollection>를 구현 하는 <xref:System.Collections.IList>. 인스턴스화하는 데 필요한 것을 <xref:System.Windows.TriggerCollection> 태그에서 개체 요소. 하나 이상 지정 하는 대신 <xref:System.Windows.Trigger> 항목 내의 요소로 합니다 `Style.Triggers` 속성 요소 위치 <xref:System.Windows.Trigger> (또는 파생된 클래스) 강력한 형식화 및 암시적 항목 종류로 예상 형식이 <xref:System.Windows.TriggerCollection>.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxPECollection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxpecollection)]  
  
 속성은 컬렉션 형식 및 해당 형식에 대 한 XAML 콘텐츠 속성 수 있으며이 항목의 다음 섹션에 설명 된 대로 파생 된 형식이 있습니다.  
  
 암시적 컬렉션 요소는 요소 태그에 나타나지 않으면 하는 경우에 논리 트리 표현에서 멤버를 만듭니다. 부모 형식의 생성자는 해당 속성 중 하나는 컬렉션에 대 한 인스턴스화를 수행 하는 일반적으로 및 개체 트리의 일부가 처음에 빈 컬렉션입니다.  
  
> [!NOTE]
>  제네릭 목록과 사전 인터페이스 (<xref:System.Collections.Generic.IList%601> 고 <xref:System.Collections.Generic.IDictionary%602>) 컬렉션 검색에 지원 되지 않습니다. 사용할 수 있습니다는 <xref:System.Collections.Generic.List%601> 구현 하기 때문에 기본 클래스로 클래스 <xref:System.Collections.IList> 직접, 또는 <xref:System.Collections.Generic.Dictionary%602> 기본 클래스로 구현 하기 때문에 <xref:System.Collections.IDictionary> 직접.  
  
 컬렉션 형식에 대 한.NET 참조 페이지에서이 구문은 의도적으로 생략 컬렉션에 대 한 개체 요소를 사용 하 여는 경우에 따라 XAML 구문 섹션에 암시적 컬렉션 구문으로 표시 됩니다.  
  
 루트 요소를 제외 하 고 다른 요소의 자식 요소로 중첩 된 XAML 파일의 모든 개체 요소는 실제로 다음 경우 중 하나 또는 모두에 있는 요소: 부모 요소의 암시적 컬렉션 속성의 멤버 또는 부모 요소 (XAML 콘텐츠 속성은 이후 섹션에서 설명)에 대 한 XAML 콘텐츠 속성의 값을 지정 하는 요소입니다. 즉, 부모 요소와 자식 요소의 태그 페이지에서 관계는 실제로 루트에 단일 개체 이며 루트 아래의 모든 개체 요소 부모의 속성 값을 제공 하는 단일 인스턴스 또는 열 내에서 항목 중 하나 lection 부모 컬렉션 형식 속성 값 이기도 합니다. 이 단일 루트는 XML을 사용 하 여 일반적인 개념과 같은 XAML을 로드 하는 Api의 동작에서 자주 적용 <xref:System.Windows.Markup.XamlReader.Load%2A>합니다.  
  
 다음 예제에서는 컬렉션에 대 한 개체 요소와 구문은 (<xref:System.Windows.Media.GradientStopCollection>) 명시적으로 지정 합니다.  
  
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
  
 항상 수 없는 컬렉션을 명시적으로 선언 하는 참고 합니다. 예를 들어 선언 하려고 <xref:System.Windows.TriggerCollection> 앞에 나온에서 명시적으로 <xref:System.Windows.Style.Triggers%2A> 예제에서는 실패 합니다. 컬렉션을 명시적으로 선언 하는 컬렉션 클래스는 기본 생성자를 지원 해야 한다는 필요 하 고 <xref:System.Windows.TriggerCollection> 기본 생성자가 없습니다.  
  
<a name="xaml_content_properties"></a>   
## <a name="xaml-content-properties"></a>XAML 콘텐츠 속성  
 XAML 콘텐츠 구문은 지정 하는 클래스에만 사용할 수 있는 구문은 <xref:System.Windows.Markup.ContentPropertyAttribute> 클래스 선언의 일부로 합니다. <xref:System.Windows.Markup.ContentPropertyAttribute> 요소 (파생된 클래스 포함)의 해당 형식에 대 한 콘텐츠 속성인 속성 이름을 참조 합니다. XAML 프로세서에서 처리 될 때 모든 자식 요소 또는 개체 요소의 닫는 태그 사이 있는 내부 텍스트를 해당 개체에 대 한 XAML 콘텐츠 속성의 값으로 할당 됩니다. 콘텐츠 속성에 대 한 명시적 속성 요소를 지정할 수 있지만이 사용법 일반적으로.NET 참조에서 XAML 구문 섹션에 표시 되지 않습니다. 자세한 정보 표시 명시적 방법을 명확히 설명 하면 태그 또는 태그 스타일의 문제로 가끔 값 갖지만 일반적으로 콘텐츠 속성의 목적은 직관적으로 부모-자식으로 관련 된 요소를 직접 중첩 될 수 있도록 태그를 간소화 하는 것입니다. 속성 요소 태그 요소에 다른 속성에 대 한 "콘텐츠" strict XAML 언어 정의;를 기준으로 할당 되지 않습니다. 이러한 XAML 파서의 처리 순서에서 이전에 처리 되 고 "콘텐츠"로 간주 되지 않습니다.  
  
### <a name="xaml-content-property-values-must-be-contiguous"></a>XAML 콘텐츠 속성 값이 연속적 이어야 합니다.  
 XAML 콘텐츠 속성의 값을 해당 개체 요소의 맨 앞 또는 다른 속성 요소의 맨 뒤 지정 되어야 합니다. 마찬가지 XAML 콘텐츠 속성의 값은 하나 이상의 개체 또는 문자열로 지정 됩니다. 예를 들어, 다음 태그를 구문 분석 하지 않습니다.  
  
```  
<Button>I am a   
  <Button.Background>Blue</Button.Background>  
  blue button</Button>  
```  
  
 이 유효 하지 않은 기본적으로 content 속성에 대 한 속성 요소 구문을 사용 하 여이 구문은 명시적 수행 된 경우 콘텐츠 속성이 두 번 설정 되기 때문에:  
  
```xml  
<Button>  
  <Button.Content>I am a </Button.Content>  
  <Button.Background>Blue</Button.Background>  
  <Button.Content> blue button</Button.Content>  
</Button>  
```  
  
 마찬가지로 잘못 된 예로 콘텐츠 속성은 컬렉션 및 자식 요소는 속성 요소를 사용 하 여 섞어서 경우:  
  
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
 허용 하려면 콘텐츠로 사용 하는 단일 개체 요소 보다 더 콘텐츠 속성의 형식 특히는 컬렉션 형식 이어야 합니다. 컬렉션 형식에 대 한 속성 요소 구문을 마찬가지로 XAML 프로세서는 컬렉션 형식인 형식을 식별 해야 합니다. 요소가 XAML 콘텐츠 속성을 XAML 콘텐츠 속성의 형식이 컬렉션을 하는 경우 암시적된 컬렉션 형식의 개체 요소 태그를 지정할 필요가 없습니다. 하 고 XAML 콘텐츠 속성을 속성 el로 지정할 필요가 없습니다. 관리 합니다. 따라서 태그에서 콘텐츠 모델의 내용으로 할당 하는 자식 요소가 둘 이상 이제 수 있습니다. 다음 구문은 콘텐츠는 <xref:System.Windows.Controls.Panel> 클래스를 파생 합니다. 모든 <xref:System.Windows.Controls.Panel> 파생된 클래스는 XAML 콘텐츠 속성을 설정할 <xref:System.Windows.Controls.Panel.Children%2A>, 형식의 값이 필요한 <xref:System.Windows.Controls.UIElementCollection>합니다.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxContent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page5.xaml#syntaxcontent)]  
  
 모두 property 요소에 대 한 <xref:System.Windows.Controls.Panel.Children%2A> 의 요소가 <xref:System.Windows.Controls.UIElementCollection> 태그에 필요 합니다. 이 기능은 디자인 XAML의 재귀적으로 정의 하는 요소를 포함 하는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 중간 속성 요소 태그 없이 즉시 부모-자식 요소 관계를 사용 하 여 중첩 된 요소 트리를 보다 직관적으로 표현 됩니다 또는 컬렉션 개체입니다. 사실, <xref:System.Windows.Controls.UIElementCollection> 에 지정할 수 없습니다 명시적으로 태그를 개체 요소로 설계 합니다. 유일한 용도 암시적 컬렉션으로 이므로 <xref:System.Windows.Controls.UIElementCollection> 공용 기본 생성자를 노출 하지 않습니다 하 고 있으므로 개체 요소로 인스턴스화할 수 없습니다.  
  
### <a name="mixing-property-elements-and-object-elements-in-an-object-with-a-content-property"></a>속성 요소 및 콘텐츠 속성을 사용 하 여 개체의 개체 요소를 혼합합니다.  
 XAML 사양 XAML 프로세서는 개체 요소 내에서 XAML 콘텐츠 속성을 채우는 데 사용 되는 개체 요소 인접 해야 하며이 혼합할 수 있어야 하는 적용할 수 있다는 것을 선언 합니다. 속성 요소 및 콘텐츠를 혼합에 대 한이 제한에 의해 적용 됩니다는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML 프로세서.  
  
 개체 요소 내에서 즉시 첫 번째 마크업으로 자식 개체 요소를 사용할 수 있습니다. 다음 속성 요소를 도입할 수 있습니다. 또는 하나 이상의 속성 요소 콘텐츠를 차례로 자세한 속성 요소를 지정할 수 있습니다. 하지만 콘텐츠 뒤에 요소를 더 이상 콘텐츠를 지정할 수 없으며, 속성 요소에만 추가할 수 있습니다.  
  
 이 콘텐츠 / 요소 순서 요구 사항 속성 내용으로 사용 되는 내부 텍스트에 적용 되지 않습니다. 그러나 유효 공백 속성 요소의 내부 텍스트를 사용 하 여 섞어서는 경우 태그에 시각적으로 감지 하기가 어려울 수 있으므로 내부 텍스트를 인접 하 게 유지 하는 좋은 태그 스타일 이기도 합니다.  
  
<a name="xaml_namespaces"></a>   
## <a name="xaml-namespaces"></a>XAML 네임스페이스  
 이전 구문 예제 중 기본 XAML 네임 스페이스 이외의 다른 XAML 네임 스페이스를 지정 합니다. 일반적인 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 되도록 지정 된 응용 프로그램의 경우 기본 XAML 네임 스페이스는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 네임 스페이스입니다. 기본 XAML 네임 스페이스 이외의 다른 XAML 네임 스페이스를 지정할 수 있으며 비슷한 구문을 사용할 수 있습니다. 하지만 그런 다음 아무 곳 이나 여기서 클래스 라는 기본 XAML 네임 스페이스 내에서 액세스할 수 없는 해당 클래스 이름 앞에 XAML 네임 스페이스의 접두사를 사용 하 여 해당 CLR 네임 스페이스에 매핑. 예를 들어 `<custom:Example/>` 의 인스턴스를 인스턴스화하지 개체 요소 구문은 `Example` 클래스 (및 가능한 백업 형식을 포함 하는 외부 어셈블리 정보)를 포함 하는 CLR 네임 스페이스에 이전에 매핑된 클래스는 `custom` 접두사입니다.  
  
 XAML 네임 스페이스에 대 한 자세한 내용은 참조 하세요. [XAML 네임 스페이스 및 WPF XAML에 대 한 매핑 Namespace](../../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)합니다.  
  
<a name="markup_extensions"></a>   
## <a name="markup-extensions"></a>태그 확장  
 XAML은 문자열 특성 값 이나 개체 요소의 일반 XAML 프로세서 처리에서 이스케이프를 사용 하도록 설정 하 고 백업 클래스 처리를 지연 하는 엔터티를 프로그래밍 하는 태그 확장을 정의 합니다. 특성 구문을 사용 하 여는 중괄호 ({), 닫는 중괄호 (}) 이외의 다른 문자가 오는 경우 XAML 프로세서에 대 한 태그 확장을 식별 하는 문자입니다. 여는 중괄호를 따라 첫 번째 문자열 해당 부분 문자열 true 클래스 이름의 일부인 경우 "확장" 참조 부분을 생략할 수 있는 특정 확장 동작을 제공 하는 클래스를 참조 해야 합니다. 그 후, 단일 공백이 나타날 수 있습니다 하 고 각 후속 문자 입력으로 사용 됩니다 확장 구현에서 닫는 중괄호 발생할 때까지.  
  
 .NET XAML 구현에서 사용 합니다 <xref:System.Windows.Markup.MarkupExtension> 추상 클래스에서 지 원하는 태그 확장 모두를 위한 기준으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 뿐만 아니라 다른 프레임 워크 또는 기술 합니다. 태그 확장은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 특히 구현 다른 기존 개체를 참조 하거나 런타임에 평가 되는 개체에 대 한 지연 된 참조가 수단을 제공 하려는 경우가 많습니다. 예를 들어, 간단한 WPF 데이터 바인딩을 지정 하면 됩니다는 `{Binding}` 태그 확장 특정 속성을 일반적으로 수행 하는 값을 대신 합니다. WPF 태그 확장의 대부분 여기서 특성 구문은 가능 하지 않은 속성에 대 한 특성 구문을 사용 합니다. 예를 들어, 한 <xref:System.Windows.Style> 개체는 중첩 된 일련의 개체 및 속성을 포함 하는 상대적으로 복잡 한 형식입니다. 일반적으로 WPF에서 스타일은 리소스로 정의 <xref:System.Windows.ResourceDictionary>, 다음 리소스를 요청 하는 두 가지 WPF 태그 확장 중 하나를 통해 참조 합니다. 태그 확장은 리소스 조회 속성 값의 평가 지연 하 고 값을 제공할 수 있도록 합니다 <xref:System.Windows.FrameworkElement.Style%2A> 형식 속성 <xref:System.Windows.Style>의 특성은 다음 예제와 같이 구문:  
  
 `<Button Style="{StaticResource MyStyle}">My button</Button>`  
  
 이때 `StaticResource` 하 게 식별 하는 <xref:System.Windows.StaticResourceExtension> 태그 확장 구현을 제공 하는 클래스입니다. 다음 문자열 `MyStyle` 기본값이 아닌에 대 한 입력으로 사용 됩니다 <xref:System.Windows.StaticResourceExtension> 생성자에는 확장 문자열에서 가져온 대로 매개 변수 선언 요청한 <xref:System.Windows.ResourceKey>합니다. `MyStyle` 이어야 하는데 합니다 [X:key](../../../../docs/framework/xaml-services/x-key-directive.md) 의 값을 <xref:System.Windows.Style> 리소스로 정의 합니다. 합니다 [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) 사용량 요청 리소스 사용을 제공할 수는 <xref:System.Windows.Style> 로드할 때 정적 리소스 조회 논리를 통해 속성 값입니다.  
  
 태그 확장에 대한 자세한 내용은 [XAML 태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)을 참조하세요. 태그 확장 및 일반.NET XAML 구현에서 사용 하는 기능을 프로그래밍 하는 다른 XAML에 대 한 참조를 참조 하세요. [XAML Namespace (x:) 언어 기능](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md)합니다. WPF 관련 태그 확장에 대 한 참조 [WPF XAML 확장](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md)합니다.  
  
<a name="attached_properties"></a>   
## <a name="attached-properties"></a>연결된 속성  
 연결 된 속성은 프로그래밍 개념 가능해 집니다 속성 소유 하 고 특정 형식에 의해 정의 된 XAML에 도입 된 모든 요소에 특성 또는 속성 요소와 이지만 설정 합니다. 기본 시나리오는 모든 요소에서 광범위 하 게 공유 개체 모델을 요구 하지 않고 자식 요소가 부모 요소에 정보를 보고 하기 위한 태그 구조를 사용 하도록 설정 하는 것 연결 된 속성은 용도로 합니다. 반대로, 자식 요소에 정보를 보고할 부모 요소에 의해 연결 된 속성을 사용할 수 있습니다. 연결 된 속성을 직접 만드는 방법과 연결 된 속성의 용도에 대 한 자세한 내용은 참조 하세요 [연결 된 속성 개요](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)합니다.  
  
 연결 된 속성 구문을 사용 하 여 속성 요소 구문을 유사한 겉으로 또한 지정 된 *typeName*. *propertyName* 조합 합니다. 다음과 같은 두 가지 중요한 차이점이 있습니다.  
  
-   사용할 수는 *typeName*. *propertyName* 특성 구문을 통해 연결된 된 속성을 설정 하는 경우에 조합 합니다. 연결 된 속성은 유일한 경우 속성 이름을 한 정하는 여기서은 특성 구문 요구 사항입니다.  
  
-   또한 연결 된 속성에 대 한 속성 요소 구문을 사용할 수 있습니다. 그러나 일반적인 속성 요소 구문에 대 한 합니다 *typeName* property 요소를 포함 하는 개체 요소를 지정 합니다. 연결된 된 속성을 참조 하는 경우 해당 *typeName* 개체 요소가 포함 하는 것이 아니라 연결된 된 속성을 정의 하는 클래스입니다.  
  
<a name="attached_events"></a>   
## <a name="attached-events"></a>연결된 이벤트  
 연결 된 이벤트는 이벤트는 특정 형식으로 정의할 수 있습니다 하지만 모든 개체 요소에 처리기를 연결할 수 있는 XAML에 도입 된 또 다른 프로그래밍 개념입니다. WOF 구현에서 종종 연결된 된 이벤트를 정의 하는 형식을 서비스를 정의 하는 정적 형식 이며 이러한 연결 된 이벤트 서비스를 노출 하는 형식에서 라우트된 이벤트 별칭에 의해 노출 되는 경우가 있습니다. 연결 된 이벤트에 대 한 처리기 특성 구문을 통해 지정 됩니다. 연결 된 이벤트를 사용 하 여 특성 구문을 수 있도록 연결 된 이벤트에 대 한 확장은 *typeName*. *eventName* 사용, 여기서 *typeName* 제공 하는 클래스인 `Add` 및 `Remove` 연결 된 이벤트 인프라에 대 한 이벤트 처리기 접근자 및 *eventName* 의 이벤트 이름입니다.  
  
<a name="anatomy_of_a_xaml_page_root_element"></a>   
## <a name="anatomy-of-a-xaml-root-element"></a>XAML 루트 요소를 분석  
 다음 표에서 일반적인 XAML 루트 요소를 세분화는 루트 요소의 특정 특성을 표시 합니다.  
  
|||  
|-|-|  
|`<Page`|루트 요소의 시작 개체 요소|  
|`xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`|기본값 ([!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]) XAML 네임 스페이스|  
|`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`|XAML 언어 XAML 네임 스페이스|  
|`x:Class="ExampleNamespace.ExampleCode"`|Partial 클래스에 대해 정의 된 모든 코드 숨김에 태그를 연결 하는 partial 클래스 선언|  
|`>`|루트에 대 한 개체 요소의 끝입니다. 요소가 자식 요소를 포함 하기 때문에 개체는 아직 닫히지 않습니다|  
  
<a name="optional_and_nonrecommended_xaml_usages"></a>   
## <a name="optional-and-nonrecommended-xaml-usages"></a>선택 사항이 며 권장 되지 않는 XAML 사용  
 다음 섹션에서는 XAML 프로세서에서 지 원하는 기술적 세부 정보 표시 또는 경우 사람이 읽을 수 있는 남은 XAML 파일을 방해 하는 기타 미적 문제를 생성 하는 하지만 XAML 사용에 XAML 소스를 포함 하는 응용 프로그램 개발 .  
  
### <a name="optional-property-element-usages"></a>선택적 속성 요소 사용  
 선택적은 명시적으로 XAML 프로세서에서는 암시적 간주 한다는 요소 콘텐츠 속성 작성을 포함 합니다. 콘텐츠를 선언할 경우에 예를 들어,를 <xref:System.Windows.Controls.Menu>, 명시적으로 선언 하도록 선택할 수 있습니다를 <xref:System.Windows.Controls.ItemsControl.Items%2A> 의 컬렉션을 <xref:System.Windows.Controls.Menu> 으로 `<Menu.Items>` 속성 요소 태그 및 위치는 각 <xref:System.Windows.Controls.MenuItem> 내에서 `<Menu.Items>`아닌 암시적 XAML 프로세서 동작을 사용 하 여 보다는 모든 자식 요소를 <xref:System.Windows.Controls.Menu> 이어야 합니다는 <xref:System.Windows.Controls.MenuItem> 에 배치 됩니다는 <xref:System.Windows.Controls.ItemsControl.Items%2A> 컬렉션입니다. 경우에 따라 선택적 사용법 태그에 표시 된 대로 개체 구조를 시각적으로 명확 하 게 도움이 됩니다. 또는 경우에 따라 명시적 속성 요소 사용을 기술적으로 작동 하지만 특성 값 내에서 중첩된 태그 확장과 같은 시각적으로 혼동 하는 태그를 방지할 수 있습니다.  
  
### <a name="full-typenamemembername-qualified-attributes"></a>정규화 된 전체 typeName.memberName 특성  
 합니다 *typeName*. *memberName* 특성은 실제로 라우트된 이벤트 사례만 보다 더 보편적으로 작동을 형성 합니다. 해당 폼이 불필요 한 경우도 있고 태그 스타일과 가독성을 위해 동안만 경우를 피해 야 합니다. 다음 예제에서는 세 개의 각 참조에 <xref:System.Windows.Controls.Control.Background%2A> 특성 완전히 동일 합니다.  
  
 [!code-xaml[XAMLOvwSupport#TypeNameProp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenameprop)]  
  
 `Button.Background` 사용 하기 때문에 해당 속성에 대 한 정규화 된 조회 <xref:System.Windows.Controls.Button> 성공 (<xref:System.Windows.Controls.Control.Background%2A> 컨트롤에서 상속 된) 및 <xref:System.Windows.Controls.Button> 개체 요소의 클래스 또는 기본 클래스. `Control.Background` 때문에 작동 합니다 <xref:System.Windows.Controls.Control> 클래스에서 실제로 정의 <xref:System.Windows.Controls.Control.Background%2A> 및 <xref:System.Windows.Controls.Control> 은 <xref:System.Windows.Controls.Button> 기본 클래스입니다.  
  
 그러나 다음 *typeName*. *memberName* 양식 예제는 작동 하지 않으며 따라서 주석 표시 됩니다.  
  
 [!code-xaml[XAMLOvwSupport#TypeNameBadProp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenamebadprop)]  
  
 <xref:System.Windows.Controls.Label> 다른 파생 클래스인 <xref:System.Windows.Controls.Control>를 지정한 경우 및 `Label.Background` 내는 <xref:System.Windows.Controls.Label> 개체 요소를이 사용법은 동작 합니다. 그러나 때문 <xref:System.Windows.Controls.Label> 가 아니면 클래스의 기본 클래스 <xref:System.Windows.Controls.Button>, 지정 된 XAML 프로세서 동작을 처리 하는 것 `Label.Background` 연결된 된 속성으로. `Label.Background` 사용 가능한 연결 된 속성, 아니며이 사용법은 실패 합니다.  
  
### <a name="basetypenamemembername-property-elements"></a>baseTypeName.memberName 속성 요소  
 유사한 방식으로 방법에는 *typeName*. *memberName* 특성 구문을 사용할 수 있는 폼을 *baseTypeName*. *memberName* 구문 속성 요소 구문에 대 한 작동 합니다. 예를 들어 다음 구문을 작동합니다.  
  
 [!code-xaml[XAMLOvwSupport#GoofyPE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofype)]  
  
 Property 요소와 지정 된 이때 `Control.Background` property 요소에 포함 된 경우에 `Button`합니다.  
  
 마찬가지로 하지만 *typeName*. *memberName* 특성에 대 한 폼 *baseTypeName*. *memberName* 는 태그에서 잘못 된 스타일 및 사용 하지 않아야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [XAML 개요(WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [XAML 네임스페이스(x:) 언어 기능](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md)  
 [WPF XAML 확장](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md)  
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [TypeConverter 및 XAML](../../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md)  
 [WPF에 대한 XAML 및 사용자 지정 클래스](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
