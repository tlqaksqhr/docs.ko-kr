---
title: ".NET Framework XAML 서비스에서 사용할 사용자 지정 형식 정의"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: defining custom types [XAML Services]
ms.assetid: c2667cbd-2f46-4a7f-9dfc-53696e35e8e4
caps.latest.revision: "11"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 0b35c35be7351fdf45157153ce6ca55fc763c3ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="defining-custom-types-for-use-with-net-framework-xaml-services"></a>.NET Framework XAML 서비스에서 사용할 사용자 지정 형식 정의
비즈니스 개체는 사용자 지정 형식을 정의 하거나 특정 프레임 워크에 대 한 종속성이 없는 유형이 때 참고할 수 XAML에 대 한 유용한 특정 있습니다. 이러한 사례를 따르는 경우.NET Framework XAML 서비스 XAML 판독기 및 XAML 작성기 수 형식의 XAML 특징을 검색 하 고 XAML 형식 시스템을 사용 하 여 XAML 노드 스트림의 적절 한 표현 합니다. 이 항목 형식 정의 멤버의 정의 및 CLR 형식 또는 멤버의 특성 설정에 대 한 모범 사례를 설명 합니다.  
  
## <a name="constructor-patterns-and-type-definitions-for-xaml"></a>생성자 패턴 및 XAML에 대 한 형식 정의  
 Xaml에서 개체 요소 인스턴스화할 수는 사용자 지정 클래스는 다음 요구 사항을 충족 해야 합니다.  
  
-   사용자 지정 클래스는 공용 이어야 하며 기본 (매개 변수가 없는) 공용 생성자를 노출 해야 합니다. 구조체에 대한 자세한 내용은 다음 섹션을 참조하세요.  
  
-   사용자 지정 클래스는 중첩 된 클래스 수 없습니다. 추가 전체 이름 경로에서 "점" 클래스 네임 스페이스 나누기 모호 만들고 연결 된 속성 등의 기타 XAML 기능을 방해 합니다.  
  
 개체 요소를 개체를 인스턴스화할 수 만든된 개체 내부 형식으로 개체를 사용 하는 모든 속성의 속성 요소 형식을 작성할 수 있습니다.  
  
 여전히 값 변환기를 사용 하도록 설정 하면 이러한 조건을 충족 하지 않는 형식에 대 한 개체 값을 제공할 수 있습니다. 자세한 내용은 참조 [형식 변환기 및 XAML 태그 확장명](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md)합니다.  
  
### <a name="structures"></a>구조체  
 구조체는 항상 CLR 정의 하 여 XAML에서 생성 될 수 있습니다. 즉, CLR 컴파일러는 구조에 대 한 기본 생성자를 암시적으로 만듭니다. 이 생성자는 모든 속성 값을 기본값으로 초기화합니다.  
  
 일부 경우에는 구조에 대 한 기본 생성 동작 바람직하지 않습니다. 구조 개념적으로 공용 구조체의 값을 채우고를 채우기 위한 것은 때문일 수 있습니다. 공용 구조체의 경우 포함된 된 값 상호 배타적인 해석을 하며 따라서 해당 속성은 설정할 수 있습니다. WPF 어휘에 이러한 구조체의 예로 <xref:System.Windows.GridLength>합니다. 문자열을 만드는 규칙을 서로 다른 해석을 또는 구조 값의 모드를 사용 하 여 특성 형식으로 값을 표현할 수 수 있도록 이러한 구조체는 형식 변환기를 구현 해야 합니다. 이러한 구조체는 기본값이 아닌 생성자를 통해 코드를 생성하는 경우에도 이와 유사한 동작을 노출해야 합니다.  
  
### <a name="interfaces"></a>인터페이스  
 인터페이스 멤버의 기본 형식으로 사용할 수 있습니다. XAML 형식 시스템 할당 가능한 목록을 확인 하 고 값으로 제공 되는 개체는 인터페이스에 할당 될 수 예상 합니다. 어떻게 인터페이스 표시 되어야 하는 XAML 형식으로 관련 할당 가능한 형식이 XAML 생성 요구 사항을 지 원하는 한 개념이 없습니다.  
  
### <a name="factory-methods"></a>팩터리 메서드  
 팩터리 메서드는 XAML 2009 기능입니다. 개체에 기본 생성자가 있어야 하는 XAML 원칙을 수정 합니다. 팩터리 메서드는이 항목에서 설명 하지 않습니다. 참조 [X:factorymethod 지시문](../../../docs/framework/xaml-services/x-factorymethod-directive.md)합니다.  
  
## <a name="enumerations"></a>열거형  
 열거형에는 XAML 네이티브 형식 변환 작동 합니다. XAML에 지정 된 열거형 상수 이름을 기본 열거형 형식에 대해 확인 되며 및 XAML 개체 작성기에 열거 값을 반환 합니다.  
  
 열거형에 대 한 스타일 플래그 사용을 지원 하는 XAML <xref:System.FlagsAttribute> 적용 합니다. 자세한 내용은 참조 [XAML 구문에서 세부](../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)합니다. ([XAML 구문에서 세부](../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md) WPF audience 용으로 작성 된 대부분의 해당 항목의 정보는 특정 구현 프레임 워크 관련 된 XAML 적합 하지만.)  
  
## <a name="member-definitions"></a>멤버 정의  
 형식은은 XAML 사용에 대 한 멤버를 정의할 수 있습니다. XAML에서 사용할 수 없는 형식이 해당 하는 경우에 XAML에서 사용할 수 있는 멤버를 정의 하는 형식에 대 한 것 같습니다. 이 CLR 상속 때문에 가능 합니다. 멤버를 상속 하는 일부 형식을 지원 형식으로 XAML 사용 구성원 내부 형식에 대 한 XAML 사용을 지원 하거나 사용할 수 있는 기본 XAML 구문에 있으며, 해당 멤버는 XAML에서 사용할 수 있습니다.  
  
### <a name="properties"></a>속성  
 일반적인 CLR을 사용 하 여 공용 CLR 속성으로 속성을 정의 하는 경우 `get` 및 `set` XAML 형식 시스템에 대 한 속성을 적절 한 정보와 함께 멤버로 제공 보고할 수 접근자 패턴 및 언어에 적합 한 키워드 <xref:System.Xaml.XamlMember> 속성을 같은 <xref:System.Xaml.XamlMember.IsReadPublic%2A> 및 <xref:System.Xaml.XamlMember.IsWritePublic%2A>합니다.  
  
 특정 속성을 적용 하 여 텍스트 구문 사용 하도록 설정할 수 <xref:System.ComponentModel.TypeConverterAttribute>합니다. 자세한 내용은 참조 [형식 변환기 및 XAML 태그 확장명](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md)합니다.  
  
 텍스트 구문 또는 네이티브 XAML 변환이 없는 경우 및 속성의 형식은 태그 확장 사용 같은 간접 더 이상 없는 경우에서 (<xref:System.Xaml.XamlMember.TargetType%2A> xaml에서 형식 시스템) XAML 개체 작성기에는 t를 처리 하 여 인스턴스를 반환할 수 여야 합니다 CLR 형식으로 대상 형식입니다.  
  
 하지만 XAML 2009를 사용 하는 경우 [X:reference 태그 확장](../../../docs/framework/xaml-services/x-reference-markup-extension.md) 이전 고려 사항에 맞지 않으면 값을 제공 하는 데 사용 될; 형식 정의 문제를 보다 사용량 문제 즉 합니다.  
  
### <a name="events"></a>이벤트  
 XAML 형식 시스템으로 구성원으로 이벤트를 보고할 수 공용 CLR 이벤트로 이벤트를 정의 하는 경우 <xref:System.Xaml.XamlMember.IsEvent%2A> 으로 `true`합니다. .NET Framework XAML 서비스 기능;의 범위 내에 있지 않습니다 배선 이벤트 처리기 이 특정 프레임 워크 및 구현에 남아 있습니다.  
  
### <a name="methods"></a>메서드  
 메서드에 대 한 인라인 코드는 기본 XAML 기능이 않습니다. 대부분의 경우에서 참조 하지 않도록 직접 메서드 멤버 XAML에서 없으며 XAML에서 메서드의 역할 하기 위해 특정 XAML 패턴에 대 한 지원을 제공 합니다. [X:factorymethod 지시문](../../../docs/framework/xaml-services/x-factorymethod-directive.md) 는 예외입니다.  
  
### <a name="fields"></a>필드  
 CLR 디자인 지침 비정적 필드를 억제 합니다. 정적 필드에 대 한 정적 필드 값에 액세스할 수 있습니다 통해서만 [X:static 태그 확장](../../../docs/framework/xaml-services/x-static-markup-extension.md);이 경우에 수행 하지 않습니다에 대 한 필드를 노출 하기 위해 CLR 정의에서 특별 한 [X:static](../../../docs/framework/xaml-services/x-static-markup-extension.md) 사용 합니다.  
  
## <a name="attachable-members"></a>연결 가능한 멤버  
 연결 가능한 멤버 접근자 메서드를 정의 하는 형식에서 패턴을 통해 XAML로 노출 됩니다. 자체 정의 형식이 XAML-으로 사용할 수 있는 개체 필요는 없습니다. 역할이 서비스 클래스를 선언 하는 일반적인 패턴은 실제로 연결 가능한 멤버를 소유 하 고 관련된 동작을 구현 하지만 UI 표현 등 다른 함수가 제공 합니다. 다음 섹션에서는 자리 표시자에 대 한 *PropertyName* 연결 가능한 멤버의 이름을 나타냅니다. 해당 이름의에서 유효 해야 합니다.는 [XamlName 문법](../../../docs/framework/xaml-services/xamlname-grammar.md)합니다.  
  
 이러한 패턴 및 다른 형태의 형식 간의 이름 충돌 주의 해야 합니다. 패턴 중 하 나와 일치 하는 멤버가 있는 경우 해석 될 수는 연결 가능한 멤버 사용 경로으로 XAML 프로세서에서 의도 되지 않은 경우에 합니다.  
  
#### <a name="the-getpropertyname-accessor"></a>GetPropertyName 접근자  
 `Get`*PropertyName* 접근자에 대한 서명은 다음과 같아야 합니다.  
  
 `public static object Get`*PropertyName* `(object`  `target` `)`  
  
-   구현에서 보다 구체적인 형식으로 `target` 개체를 지정할 수 있습니다. 연결 가능한 멤버;의 사용 범위는 데 사용할 수 있습니다. 원하는 범위를 벗어나는 사용량 XAML 구문 분석 오류에 의해 표시 되는 잘못 된 캐스팅 예외를 throw 합니다. 매개 변수 이름을 `target` 한 요구 사항은 아닙니다 되었지만 이름이 `target` 대부분의 구현에는 일반적으로 합니다.  
  
-   구현에서 보다 구체적인 형식으로 반환 값을 지정할 수 있습니다.  
  
 지원 하기 위해는 <xref:System.ComponentModel.TypeConverter> 연결 가능한 멤버의 특성 사용에 대 한 활성화 된 텍스트 구문이 적용 <xref:System.ComponentModel.TypeConverterAttribute> 에 `Get` *PropertyName* 접근자입니다. 하지만에 적용 된 `get` 대신는 `set` 임의의; 보일 수 있지만이 규칙의 개념을 지원할 수 있습니다 직렬화 할 수 있는 읽기 전용 연결 가능한 멤버, 하는 디자이너 시나리오에서 유용 합니다.  
  
#### <a name="the-setpropertyname-accessor"></a>SetPropertyName 접근자  
 집합에 대 한 서명을*PropertyName* 접근자 이어야 합니다.  
  
 `public static void Set` *PropertyName* `(object`  `target` `, object`  `value` `)`  
  
-   `target` 이전 섹션에 설명 된 대로 동일한 논리와 결과와 구현에서 더 구체적인 형식으로 개체를 지정할 수 있습니다.  
  
-   구현에서 보다 구체적인 형식으로 `value` 개체를 지정할 수 있습니다.  
  
 이 메서드에 대 한 값이 XAML 사용은 특성 형태로 일반적으로 입력 해야 합니다. 특성 형식에서 여야 텍스트 구문에 대 한 값 변환기 지원 하며이 특성에 `Get` *PropertyName* 접근자입니다.  
  
### <a name="attachable-member-stores"></a>연결 가능한 멤버 저장소  
 접근자 메서드는 일반적으로 하지는 개체 그래프에 연결 가능한 멤버 값을 배치에 또는 개체 그래프에서 값을 검색 하 고 제대로 serialize 할 수 있는 방법을 제공 하기에 충분 합니다. 이 기능을 제공 하는 `target` 이전 접근자 시그니처에 개체 값을 저장할 수 있어야 합니다. 저장 메커니즘은 연결 가능한 멤버가 있지 않은 멤버 목록에는 대상에 연결할 수 있는 멤버는 연결 가능한 멤버 원칙와 일치 해야 합니다. .NET framework XAML 서비스 Api를 통해 연결할 수 있는 멤버를 저장에 대 한 구현 기술을 제공 <xref:System.Xaml.IAttachedPropertyStore> 및 <xref:System.Xaml.AttachablePropertyServices>합니다. <xref:System.Xaml.IAttachedPropertyStore>XAML 작성기를 검색할 저장소 구현 하는 데 사용 되는 형식에 구현 해야 및는 `target` 접근자의 합니다. 정적 <xref:System.Xaml.AttachablePropertyServices> Api는 접근자의 본문 내에서 사용 되 고 하 여 연결할 수 있는 멤버를 참조 해당 <xref:System.Xaml.AttachableMemberIdentifier>합니다.  
  
## <a name="xaml-related-clr-attributes"></a>XAML 관련 CLR 특성  
 올바르게 형식, 멤버 및 어셈블리 특성을 지정 하는 것이.NET Framework XAML 서비스 XAML 형식 시스템의 정보를 보고 하기 위해 중요 합니다. 이 정의 하거나 해당 XAML 판독기 및 XAML 작성기를 기반으로 하는 XAML을 사용 하 여 프레임 워크를 사용 하는 경우 또는 XAML 시스템 기반으로 하는 직접.NET Framework XAML 서비스 XAML 판독기 및 XAML 작성기와 함께 사용할 형식을 하려는 경우에 해당 됩니다.  
  
 사용자 지정 형식의 XAML 지원에 대 한 관련 된 각 XAML 관련 특성의 목록을 보려면 [사용자 지정 형식 및 라이브러리에 대 한 CLR 특성 XAML-Related](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md)합니다.  
  
## <a name="usage"></a>용도  
 사용자 지정 형식 사용 해야 태그 작성자가 사용자 지정 항목 유형이 있는 어셈블리와 CLR 네임 스페이스에 대 한 접두사를 매핑해야 합니다. 이 절차는이 항목에 문서화 되지 않습니다.  
  
## <a name="access-level"></a>액세스 수준  
 XAML 로드 하 고이 있는 형식을 인스턴스화하는 방법을 제공는 `internal` 액세스 수준입니다. 이 기능은 사용자 코드는 자체 형식 정의 업데이트 하 고 다음 동일한 사용자 코드 범위의 일부 이기도 태그에서 해당 클래스를 인스턴스화할 수 있도록 제공 됩니다.  
  
 WPF에서 예로 사용자 코드에서 정의 될 때마다 한 <xref:System.Windows.Controls.UserControl> UI 동작을 리팩터링 하는 방법으로 하지만 사용 하 여 지원 클래스를 선언 하 여 암시 수 있는 모든 가능한 확장 메커니즘의 일부가 아니라 용도가 `public` 액세스 수준입니다. 이러한는 <xref:System.Windows.Controls.UserControl> 선언할 수 있습니다 `internal` 액세스할 백업 코드 참조 XAML 형식으로는 같은 어셈블리에 컴파일됩니다.  
  
 완전 신뢰 수준에서 XAML을 로드 하 여 사용 하는 응용 프로그램에 대 한 <xref:System.Xaml.XamlObjectWriter>, 인 클래스를 로드 `internal` 액세스 수준을 항상 사용 하도록 설정 합니다.  
  
 부분 신뢰에서 XAML을 로드 하는 응용 프로그램을 사용 하 여 액세스 수준 특성을 제어할 수 있습니다는 <xref:System.Xaml.Permissions.XamlAccessLevel> API입니다. 또한 지연 메커니즘 (예: WPF 서식 파일 시스템)를 액세스 수준 권한을 전파 되 고 최종 런타임 확인; 하기 위해 유지할 수 여야 합니다. 이 값은 전달 하 여 내부적으로 처리 되는 <xref:System.Xaml.Permissions.XamlAccessLevel> 정보입니다.  
  
### <a name="wpf-implementation"></a>WPF 구현  
 WPF XAML 모델을 사용 하는 부분 신뢰 액세스를 BAML 부분 신뢰 환경에서 로드 되 면 액세스할 수 있습니다 <xref:System.Xaml.Permissions.XamlAccessLevel.AssemblyAccessTo%2A> BAML 원본인 어셈블리에 대 한 합니다. WPF 지연을 위해 사용 하 여 <xref:System.Xaml.IXamlObjectWriterFactory.GetParentSettings%2A?displayProperty=nameWithType> 액세스 수준 정보를 전달 하기 위한 메커니즘으로 합니다.  
  
 WPF XAML 용어에서는 *내부 형식* 참조 하는 XAML을 포함 하는 동일한 어셈블리에서 정의 된 형식입니다. 어셈블리를 의도적으로 생략 하는 XAML 네임 스페이스를 통해 이러한 형식을 매핑할 수 = 매핑, 예를 들어 부분 `xmlns:local="clr-namespace:WPFApplication1"`합니다.  BAML 내부 형식을 참조 하는 경우 고 해당 형식의 `internal` 액세스 수준이이 생성 한 `GeneratedInternalTypeHelper` 어셈블리에 대 한 클래스입니다. 방지 하려는 경우 `GeneratedInternalTypeHelper`를 사용 하거나 `public` 액세스 수준이 또는 해야 관련 클래스를 별도 어셈블리에 모아 놓은 해당 어셈블리가 종속 되 게 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [사용자 지정 형식 및 라이브러리에 대한 XAML 관련 CLR 특성](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md)  
 [XAML 서비스](../../../docs/framework/xaml-services/index.md)
