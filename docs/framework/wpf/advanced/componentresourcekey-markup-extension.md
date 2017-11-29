---
title: "ComponentResourceKey 태그 확장"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ComponentResourceKey
- ComponentResourceKeyExtension
helpviewer_keywords:
- ComponentResourceKey markup extension [WPF]
- XAML [WPF], ComponentResourceKey markup extension
ms.assetid: d6bcdbe6-61b3-40a7-b381-4e02185b5a85
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b7f959318c5991fea2df92ff8000e85345fb35ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="componentresourcekey-markup-extension"></a>ComponentResourceKey 태그 확장
정의 하 고 외부 어셈블리에서 로드 되는 리소스에 대 한 키를 참조 합니다. 그러면 리소스 조회는 클래스 또는 어셈블리에 명시적 리소스 사전 하지 않고 어셈블리의 대상 형식을 지정할 수 있습니다.  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a>XAML 특성 사용 (키 설정, compact)  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a>XAML 특성 사용 (키 설정, 자세한 정보)  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a>XAML 특성 사용 (리소스 요청, compact)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a>XAML 특성 사용 (리소스 요청, 자세한 정보)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`targetTypeName`|공용 이름 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 리소스 어셈블리에 정의 된 형식입니다.|  
|`targetID`|리소스에 대 한 키입니다. 리소스를 조회할 때 `targetID` 유사 됩니다는 [X:key 지시문](../../../../docs/framework/xaml-services/x-key-directive.md) 리소스의 합니다.|  
  
## <a name="remarks"></a>설명  
 위의 사용에 표시 되는 {`ComponentResourceKey`} 태그 확장 사용은 다음 두 위치에서 찾을 수:  
  
-   테마 리소스 사전 컨트롤 작성자가 제공한 내에서 키의 정의입니다.  
  
-   템플릿을 컨트롤은 있지만 컨트롤의 테마에서 제공 하는 리소스에서 제공 하는 속성 값을 사용 하려면 때 어셈블리에서 테마 리소스에 액세스 합니다.  
  
 테마에서 제공 하는 구성 요소 리소스 참조에 일반적으로 것을 사용 하는 `{DynamicResource}` 대신 `{StaticResource}`합니다. 이 용도에 표시 됩니다. `{DynamicResource}`사용자가 자체 테마를 변경할 수 있으므로 좋습니다. 구성 요소 리소스를 가장 일치 하는 테마를 지원 하기 위한 컨트롤 작성자의 의도 하려는 경우 동적 구성 요소에서는 리소스 참조를 사용 해야 합니다.  
  
 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> 리소스 실제로 정의 된 대상 어셈블리에 존재 하는 형식을 식별 합니다. A `ComponentResourceKey` 정의 하 고 정확히 알고 있으면 별도로 사용할 수 있는 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> 정의 되어 있지만 결국 참조 된 어셈블리를 통해 형식을 확인 해야 합니다.  
  
 에 대 한 일반적인 사용 <xref:System.Windows.ComponentResourceKey> 클래스의 멤버로 노출 되는 키를 정의 하는 것입니다. 사용이 사용에 대 한는 <xref:System.Windows.ComponentResourceKey> 클래스 생성자, 태그 확장 되지 않습니다. 자세한 내용은 참조 <xref:System.Windows.ComponentResourceKey>, 또는 항목의 "및 참조 키에 대 한 테마 리소스 정의" 섹션 [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md)합니다.  
  
 키를 설정 하 고 참조 표시가 리소스에 대 한 특성 구문을 일반적으로 사용 된 `ComponentResourceKey` 태그 확장 합니다.  
  
 표시 된 compact 구문에서는 <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> 생성자 시그니처 및 태그 확장의 위치 매개 변수를 사용 합니다. 되는 순서는 `targetTypeName` 및 `targetID` 제공 됩니다이 중요 합니다. 자세한 구문에서는 <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> 기본 생성자를 사용 하 고 다음 집합에서 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> 및 <xref:System.Windows.ComponentResourceKey.ResourceId%2A> 개체 요소에 실제 특성 구문과 유사 하는 방식에서입니다. 자세한 구문에서 속성을 설정 하는 데는 순서가 중요 하지 않습니다. 관계 및 메커니즘의 이러한 두 가지 대체 방법 (압축 및 자세한 정보) 항목에서 자세히 설명 되어 [태그 확장명 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)합니다.  
  
 에 대 한 값 기술적으로 `targetID` 할 수 있는 개체, 문자열이 될 필요가 없습니다. 그러나 WPF의 가장 일반적인 사용 정렬 하는 것은 `targetID` forms 문자열 있으며 이러한 문자열은에서 유효한 값의 [XamlName 문법](../../../../docs/framework/xaml-services/xamlname-grammar.md)합니다.  
  
 `ComponentResourceKey`개체 요소 구문에서 사용할 수 있습니다. 이 경우 둘 다의 값을 지정 하는 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> 및 <xref:System.Windows.ComponentResourceKey.ResourceId%2A> 속성은 제대로 확장을 초기화 해야 합니다.  
  
 에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 판독기 구현이 태그 확장에 대 한 처리가 정의한는 <xref:System.Windows.ComponentResourceKey> 클래스입니다.  
  
 `ComponentResourceKey`은 태그 확장입니다. 태그 확장은 특성 값을 리터럴 값 또는 처리기 이름이 아닌 다른 값이 되도록 이스케이프해야 하는 요구 사항이 있는 경우 일반적으로 구현되며 이러한 요구 사항은 특정 형식 또는 속성에 형식 변환기를 배치하는 것보다 더 포괄적입니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 모든 태그 확장은 특성 구문에서 { 및 } 문자를 사용합니다. 이러한 문자는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서가 태그 확장이 특성을 처리해야 함을 인식하는 데 사용되는 규칙입니다. 자세한 내용은 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.ComponentResourceKey>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md)  
 [XAML 개요(WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
