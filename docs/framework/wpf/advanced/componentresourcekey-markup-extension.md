---
title: "ComponentResourceKey 태그 확장 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ComponentResourceKey"
  - "ComponentResourceKeyExtension"
helpviewer_keywords: 
  - "ComponentResourceKey 태그 확장"
  - "XAML, ComponentResourceKey 태그 확장"
ms.assetid: d6bcdbe6-61b3-40a7-b381-4e02185b5a85
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# ComponentResourceKey 태그 확장
외부 어셈블리에서 로드되는 리소스의 키를 정의하고 참조합니다.  리소스 조회 시 어셈블리 또는 클래스에서 명시적 리소스 사전 대신 대상 형식을 지정할 수 있습니다.  
  
## XAML 특성 사용\(키 설정, 간단한 구문\)  
  
```  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## XAML 특성 사용\(키 설정, 자세한 구문\)  
  
```  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## XAML 특성 사용\(리소스 요청, 간단한 구문\)  
  
```  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## XAML 특성 사용\(리소스 요청, 자세한 구문\)  
  
```  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## XAML 값  
  
|||  
|-|-|  
|`targetTypeName`|리소스 어셈블리에 정의된 공용 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 형식의 이름입니다.|  
|`targetID`|리소스의 키입니다.  리소스를 조회할 때는 `targetID`가 리소스의 [x:Key 지시문](../../../../docs/framework/xaml-services/x-key-directive.md)과 비슷합니다.|  
  
## 설명  
 위의 용도에서 볼 수 있듯이 {`ComponentResourceKey`} 태그 확장 사용은 두 위치에서 발견됩니다.  
  
-   컨트롤 작성자가 제공한 경우 테마 리소스 사전 내의 키 정의입니다.  
  
-   제어의 템플릿을 다시 지정하되 제어의 테마에서 제공하는 리소스에서 받는 속성 값을 사용하고 싶을 때 어셈블리의 테마 리소스에 액세스합니다.  
  
 테마에서 제공되는 구성 요소에서 리소스를 참조할 경우 일반적으로 `{StaticResource}` 대신 `{DynamicResource}`를 사용하는 것이 좋습니다.  용도는 볼 수 있습니다.  사용자가 해당 테마를 변경할 수 있으므로 `{DynamicResource}`를 사용하는 것이 좋습니다.  테마를 지원하기 위해 컨트롤 작성자의 의도와 가장 일치하는 구성 요소 리소스를 원하는 경우 구성 요소 리소스 참조를 동적으로 사용할 수 있도록 해야 합니다.  
  
 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>는 리소스가 실제로 정의된 대상 어셈블리에 포함된 형식을 식별합니다.  `ComponentResourceKey`는 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>가 정의된 위치를 모르는 경우에도 독립적으로 정의하고 사용할 수 있지만 궁극적으로는 참조된 어셈블리를 통해 형식을 확인해야 합니다.  
  
 <xref:System.Windows.ComponentResourceKey>의 일반적인 용도는 클래스의 멤버로 노출되는 키를 정의하는 데 있습니다.  이러한 용도로 사용하는 경우 태그 확장이 아니라 <xref:System.Windows.ComponentResourceKey> 클래스 생성자를 사용합니다.  자세한 내용은 <xref:System.Windows.ComponentResourceKey> 또는 항목 [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md)의 "테마 리소스의 키 정의 및 참조"를 참조하십시오.  
  
 키를 설정하고 입력된 리소스 참조를 위해 특성 구문은 `ComponentResourceKey` 태그 확장에 주로 사용됩니다.  
  
 앞에 나온 간단한 구문에서는 <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=fullName> 생성자 시그니처와 태그 확장의 위치 매개 변수를 사용합니다.  `targetTypeName` 및 `targetID`를 제공하는 순서는 중요합니다.  자세한 구문에서는 <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=fullName> 기본 생성자를 사용하고 개체 요소의 실제 특성 구문과 비슷한 방법으로 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> 및 <xref:System.Windows.ComponentResourceKey.ResourceId%2A>를 설정합니다.  자세한 구문에서는 속성을 설정하는 순서가 중요하지 않습니다.  간단한 구문과 자세한 구문의 관계 및 메커니즘에 대해서는 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md) 항목에 보다 자세히 설명되어 있습니다.  
  
 기술적으로 `targetID`의 값은 모든 개체가 될 수 있으며 문자열일 필요가 없습니다.  그러나 WPF의 가장 일반적인 사용은 `targetID` 값을 문자열인 폼에 정렬하는 것이며 이러한 문자열은 [XamlName 문법](../../../../docs/framework/xaml-services/xamlname-grammar.md)에서 유효합니다.  
  
 `ComponentResourceKey`는 개체 요소 구문에서 사용할 수 있습니다.  이 경우 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> 및 <xref:System.Windows.ComponentResourceKey.ResourceId%2A> 속성 값을 모두 지정해야만 확장을 적절히 초기화할 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 판독기 구현에서 이 태그 확장에 대한 처리는 <xref:System.Windows.ComponentResourceKey> 클래스를 통해 정의됩니다.  
  
 `ComponentResourceKey`은 태그 확장입니다.  태그 확장은 특성 값을 리터럴 값 또는 처리기 이름이 아닌 다른 값이 되도록 이스케이프해야 하는 요구 사항이 있는 경우 일반적으로 구현되며 이러한 요구 사항은 특정 형식 또는 속성에 형식 변환기를 배치하는 것보다 더 포괄적입니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 모든 태그는 태그의 특성 구문에 { 및 } 문자를 사용하며 여기서 특성 구문은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에 태그 확장이 특성을 처리해야 한다는 것을 인식하는 규칙입니다.  자세한 내용은 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.ComponentResourceKey>   
 <xref:System.Windows.Controls.ControlTemplate>   
 [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md)   
 [XAML 개요\(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)