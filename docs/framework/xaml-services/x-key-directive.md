---
title: x:Key 지시문
ms.date: 03/30/2017
f1_keywords:
- xKey
- Key
- x:Key
helpviewer_keywords:
- x:Key attribute [XAML Services]
- Key attribute in XAML [XAML Services]
- XAML [XAML Services], x:Key attribute
ms.assetid: 1985cd45-f197-42d5-b75e-886add64b248
ms.openlocfilehash: 53e89b664b3885bea7d2da8633505488438a1af5
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207549"
---
# <a name="xkey-directive"></a>x:Key 지시문
고유 하 게 생성 되 고 XAML 정의 사전에서 참조 하는 요소를 식별 합니다. 추가 `x:Key` XAML 개체 요소 값은 예를 들어 WPF에에서 리소스 사전에 리소스를 식별 하는 가장 일반적인 방법은 <xref:System.Windows.ResourceDictionary>합니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```  
<object x:Key="stringKeyValue".../>  
-or-  
<object x:Key="{markupExtensionUsage}".../>  
```  
  
## <a name="xaml-attribute-usage-wpf-specific"></a>XAML 특성 사용 (WPF에 따라 다름)  
  
```  
<object.Resources>  
  <object x:Key="stringKeyValue".../>  
</object.Resources>  
-or-  
<object.Resources>  
  <object x:Key="{markupExtensionUsage}".../>  
</object.Resources>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`stringKeyValue`|키로 사용 하는 텍스트 문자열입니다. 텍스트 문자열을 준수 해야는 [XamlName 문법](../../../docs/framework/xaml-services/xamlname-grammar.md)합니다.|  
|`markupExtensionUsage`|태그 확장 구분 기호 내에서 {}, 키로 사용할 개체를 제공 하는 태그 확장 사용 합니다. 설명 부분을 참조하세요.|  
  
## <a name="remarks"></a>설명  
 `x:Key` XAML 리소스 사전 개념을 지원합니다. XAML에 특정 UI 프레임 워크에 남아 있는 리소스 사전 구현을 정의 하지 않습니다. WPF에서 XAML 리소스 사전을 구현 되는 방식에 대 한 자세한 참조 [XAML 리소스](../../../docs/framework/wpf/advanced/xaml-resources.md)합니다.  
  
 WPF 및 XAML 2006 `x:Key` 특성으로 제공 되어야 합니다. 문자열이 아닌 키를 사용할 수 있습니다 있지만 특성 형식에서 문자열이 아닌 값을 제공 하기 위해 태그 확장 사용이 경우 필요 합니다. XAML 2009를 사용 하는 경우 `x:Key` 아닌 다른 개체 형식에 의해 입력 되는 사전을 명시적으로 지원 하기 위해 태그 확장 중간 필요 없이 문자열 요소를 지정할 수 있습니다. 이 항목의 "XAML 2009" 섹션을 참조 하십시오. 주의 섹션의 나머지 부분에서는 XAML 2006 구현에 특별히 적용 됩니다.  
  
 특성 값 `x:Key` 모든 문자열에 정의할 수는 [XamlName 문법](../../../docs/framework/xaml-services/xamlname-grammar.md) 또는 태그 확장을 통해 평가 되는 개체가 있을 수 있습니다. WPF에서 예제를 보려면 "WPF 사용 정보"를 참조 하십시오.  
  
 부모 요소의 자식 요소는 <xref:System.Collections.IDictionary> 구현 일반적으로 포함 되어야 합니다는 `x:Key` 해당 사전 내에서 고유 키 값을 지정 하는 특성입니다. 프레임 워크에 별칭이 지정 된 키 속성에 대 한을 구현할 수 있습니다 `x:Key` 특정 종류의; 등의 속성을 정의 하는 형식 특성을 지정 해야와 <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>합니다.  
  
 지정의 코드에 해당 하는 `x:Key` 내부에 사용 되는 키 <xref:System.Collections.IDictionary>합니다. 예를 들어는 `x:Key` wpf에서 리소스의 값에 해당 하는 태그에 적용 되는 `key` 의 매개 변수 <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> 를 WPF 리소스를 추가 하면 <xref:System.Windows.ResourceDictionary> 코드에서.  
  
## <a name="wpf-usage-notes"></a>WPF 사용 정보  
 부모의 자식 개체가 되는 개체는 <xref:System.Collections.IDictionary> WPF와 같은 구현 <xref:System.Windows.ResourceDictionary>, 일반적으로 포함 해야 합니다는 `x:Key` 특성과 키 값 해당 사전 내에서 고유 해야 합니다. 두 가지 주목할 만한 예외가 있습니다.  
  
-   일부 WPF 형식 사전 사용에 대 한 암시적 키를 선언합니다. 예를 들어 한 <xref:System.Windows.Style> 와 <xref:System.Windows.Style.TargetType%2A>, 또는 <xref:System.Windows.DataTemplate> 와 <xref:System.Windows.DataTemplate.DataType%2A>에 있을 수 있습니다는 <xref:System.Windows.ResourceDictionary> 암시적 키를 사용 합니다.  
  
-   WPF는 병합 된 리소스 사전 개념을 지원합니다. 키 병합된 된 사전 간에 공유할 수 있으며를 사용 하 여 공유 키 동작에 액세스할 수 있습니다 <xref:System.Windows.FrameworkContentElement.FindResource%2A>합니다. 자세한 내용은 [병합된 리소스 사전](../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md)을 참조하세요.  
  
 전체 WPF XAML 구현과 응용 프로그램 모델에서 키 고유성 XAML 태그 컴파일러에 의해 확인 하지 않습니다. 대신, 누락 되었거나 고유 하지 않은 `x:Key` 값 로드할 때 XAML 파서 오류가 발생 합니다. 그러나 WPF에 대 한 사전 Visual Studio 처리 설계 단계에서 그러한 오류가 메모 종종 수 있습니다.  
  
 표시 된 구문을는 <xref:System.Windows.ResourceDictionary> 개체는 암시적 WPF XAML 프로세서에서 채우는 데 컬렉션을 생성 하는 방법에 <xref:System.Windows.FrameworkElement.Resources%2A> 컬렉션입니다. A <xref:System.Windows.ResourceDictionary> 제공 하지 않으면 일반적으로 명시적으로 태그의 요소로 쉽게 구별할 수 있도록 원하는 경우에 따라 사용할 수 있지만 (간의 컬렉션 object 요소는 것은 <xref:System.Windows.FrameworkElement.Resources%2A> 채울 속성 요소 및 해당 항목 내에 사전)입니다. 이유는 컬렉션 개체는 거의 항상 암시적 태그 요소에에서 대 한 정보를 참조 하십시오. [XAML 구문에서 세부](../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)합니다.  
  
 리소스 사전 키에 대 한 처리 정의한 WPF XAML 구현에는 <xref:System.Windows.ResourceKey> 추상 클래스입니다. 그러나 WPF XAML 프로세서는 용도에 따라 키에 대 한 서로 다른 기본 확장 형식을 생성 합니다. 예를 들어에 대 한 키를 <xref:System.Windows.DataTemplate> 파생된 클래스 개별적으로 처리 되 고 고유한 생성 또는 <xref:System.Windows.DataTemplateKey> 개체입니다.  
  
 키 및 이름을 사용 하 여 다른 지시문 및 언어 요소 (`x:Key` 비교 `x:Name`)의 기본 XAML 정의 합니다. 키와 이름 WPF 정의와 이러한 개념 중 응용 프로그램에서 다양 한 상황에 사용도 됩니다. 자세한 내용은 참조 [WPF XAML 이름 범위](../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)합니다.  
  
 앞서 설명한 것 처럼 키의 값 태그 확장을 통해 제공 될 수 있습니다 및 문자열 값이 아닌 일 수 있습니다. 값은 예제 WPF 시나리오 `x:Key` 될 수 있습니다는 [ComponentResourceKey](../../../docs/framework/wpf/advanced/componentresourcekey-markup-extension.md)합니다. 특정 컨트롤의 스타일을 완전히 바꾸지 않고 모양과 및 해당 컨트롤의 동작에 영향을 주는 사용자 지정 스타일 리소스에 대 한 해당 유형의 스타일 키를 노출 합니다. 이러한 키의 예로 <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>합니다.  
  
 WPF 병합 된 사전 기능 키 고유성 및 키 조회 동작에 대 한 추가 고려 사항을 소개합니다. 자세한 내용은 [병합된 리소스 사전](../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md)을 참조하세요.  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009는 제한을 완화 하는 `x:Key` 항상 특성 형태로 제공 합니다.  
  
 WPF에서 XAML 2009 기능을 있지만 태그 컴파일되지 않은 XAML에만 사용할 수 있습니다. WPF에 대한 태그로 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 키워드 및 기능을 지원하지 않습니다.  
  
 XAML 2009에서 지정할 수 있습니다 `x:Key` 요소는 다음을 사용 하 여:  
  
### <a name="xaml-element-usage-xaml-2009-only"></a>XAML 요소 사용 (XAML 2009에만 해당)  
  
```  
<object>  
  <x:Key>  
keyObject  
  </x:Key>  
...  
</object>  
```  
  
### <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`keyObject`|에 대 한 키로 사용 되는 개체에 대 한 object 요소는 주어진 `object` 특수 사전에서 합니다.|  
  
-   이러한 종류의 사용에 대 한 부모 컨테이너/여기 표시 되지 않습니다. `object` 특수 사전 구현을 나타내는 object 요소 자식이 될 예정입니다. `keyObject` 개체 인스턴스 (또는 값 형식의 값)으로 예상 되는 특정 특수 사전 구현 위한 키로 적합 합니다.  
  
-   WPF에는이 사용법을 필요로 하는 사전을 구현 하지 않습니다. 개체 키는 XAML 언어 XAML의 사전을 만드는 바람직한 특정 사용자 지정 사전 시나리오에 대 한 가능한 유용한의 일반 기능 더입니다. 문자열이 아닌 키를 사용 하 여 리소스에 대 한 암시적 스타일과 같은 WPF 기능에 대 한 설정 하거나 키를 지정 하는 다른 기술을 존재 하므로 개체 키를 사용 하 여 필요 하지 않습니다.  
  
-   *keyObject* 직접 개체 인스턴스가 아닌 개체 요소 형태에서 태그 확장 사용이 발생할 수도 있습니다.  
  
## <a name="silverlight-usage-notes"></a>Silverlight 사용 정보  
 `x:Key` Silverlight 용은 별도로 설명 되어 있습니다. 자세한 내용은 참조 [XAML Namespace (x:) 언어 기능 (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=199081)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [XAML 리소스](../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [리소스 및 코드](../../../docs/framework/wpf/advanced/resources-and-code.md)  
 [StaticResource 태그 확장](../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)
