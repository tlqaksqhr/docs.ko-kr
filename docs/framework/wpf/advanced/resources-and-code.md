---
title: "리소스 및 코드 | Microsoft Docs"
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
  - "keys, 개체 사용"
  - "프로시저 코드, 리소스 액세스"
  - "프로시저 코드, 리소스 만들기"
  - "리소스, 프로시저 코드에서 액세스"
  - "리소스, 프로시저 코드로 만들기"
ms.assetid: c1cfcddb-e39c-41c8-a7f3-60984914dfae
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 리소스 및 코드
이 개요에서는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 구문이 아니라 코드를 사용하여 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 리소스를 액세스하거나 만드는 방법을 주로 다룹니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 구문의 측면에서 일반적인 리소스 사용과 리소스에 대한 자세한 내용은 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)를 참조하십시오.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="accessing"></a>   
## 코드에서 리소스 액세스  
 리소스를 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 통해 정의하는 경우 리소스를 식별하는 키는 코드에서 리소스를 요청하는 경우 특정 리소스를 검색하는 데에도 사용됩니다.  코드에서 리소스를 검색하는 가장 간단한 방법은 응용 프로그램의 프레임워크 수준 개체에서 <xref:System.Windows.FrameworkElement.FindResource%2A> 또는 <xref:System.Windows.FrameworkElement.TryFindResource%2A> 메서드를 사용하는 것입니다.  이러한 메서드의 동작은 요청한 키가 없을 경우에 차이가 납니다.  이 경우 <xref:System.Windows.FrameworkElement.FindResource%2A>는 예외를 발생시키는 반면 <xref:System.Windows.FrameworkElement.TryFindResource%2A>는 예외를 발생시키지 않지만 `null`을 반환합니다.  각 메서드에서는 리소스 키를 입력 매개 변수로 사용하고 자유로운 형식의 개체를 반환합니다.  일반적으로 리소스 키는 문자열이자만 문자열이 아닌 키를 사용하는 경우도 가끔 있습니다. 자세한 내용은 [개체를 키로 사용](#objectaskey) 단원을 참조하십시오.  일반적으로 반환된 개체를 리소스를 요청할 때 설정하는 속성에 필요한 형식으로 캐스팅합니다.  코드 리소스 확인의 조회 논리는 동적 리소스 참조 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 경우와 동일합니다.  리소스 검색은 호출 요소에서 시작되어 [논리적 트리](GTMT)의 후속 부모 요소로 이어집니다.  그 다음 조회는 필요한 경우 응용 프로그램 리소스, 테마 및 시스템 리소스로 계속 이어집니다.  리소스에 대한 코드 요청에서는 리소스 사전이 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 로드된 후 수행된 해당 리소스 사전에 대한 런타임 변경 사항뿐 아니라 실시간 시스템 리소스 변경 사항도 적절히 고려합니다.  
  
 다음은 리소스를 키별로 찾고 반환된 값을 사용하여 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트 처리기로 구현된 속성을 설정하는 간단한 코드 예제입니다.  
  
 [!code-csharp[PropertiesOvwSupport#ResourceProceduralGet](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml.cs#resourceproceduralget)]
 [!code-vb[PropertiesOvwSupport#ResourceProceduralGet](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page3.xaml.vb#resourceproceduralget)]  
  
 리소스 참조를 할당하는 다은 메서드는 <xref:System.Windows.FrameworkElement.SetResourceReference%2A>입니다.  이 메서드는 두 개의 매개 변수를 사용합니다. 하나는 리소스 키이고 다른 하나는 리소스 값을 할당할 요소 인스턴스에 있는 특정 종속성 속성에 대한 식별자입니다.  이 메서드는 다른 메서드와 기능이 동일하며 반환 값의 캐스팅이 필요하지 않다는 이점이 있습니다.  
  
 또한 리소스를 프로그래밍 방식으로 액세스하는 다른 방식은 <xref:System.Windows.FrameworkElement.Resources%2A> 속성의 콘텐츠를 사전으로 액세스하는 것입니다.  이 속성에 포함된 사전에 액세스하면 기존 컬렉션에 새 리소스를 추가하고 지정한 키 이름이 컬렉션 및 다른 사전\/컬렉션 작업에서 이미 사용되고 있는지 확인할 수도 있습니다.  또한 전체 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 코드로 작성하는 경우 전체 컬렉션을 코드로 만들고 이 컬렉션에 키를 할당한 다음 완료한 컬렉션을 설정된 요소의 <xref:System.Windows.FrameworkElement.Resources%2A> 속성에 할당할 수 있습니다.  이에 대해서는 다음 단원에서 설명합니다.  
  
 지정한 <xref:System.Windows.FrameworkElement.Resources%2A> 컬렉션 내에서 특정 키를 인덱스로 사용하여 인덱싱할 수 있지만 이와 같은 방법으로 리소스에 액세스하면 리소스 확인의 일반적인 런타임 규칙을 따르지 않습니다.  이 경우 해당하는 특정 컬렉션에만 액세스합니다.  리소스 조회에서는 요청된 키에서 유효한 개체를 찾지 못하는 경우 범위를 루트나 응용 프로그램으로 이동하지 않습니다.  그러나 이 방법은 키의 검색 범위가 더 제한적이기 때문에 일부 경우 성능상 이점이 있을 수 있습니다.  리소스 사전을 직접 사용하는 방법에 대한 자세한 내용은 <xref:System.Windows.ResourceDictionary> 클래스를 참조하십시오.  
  
<a name="creating"></a>   
## 코드로 리소스 만들기  
 전체 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 코드에서 만들려는 경우 해당 응용 프로그램의 리소스도 코드에서 만들 수 있습니다.  이렇게 하려면 새 <xref:System.Windows.ResourceDictionary> 인스턴스를 만든 다음 이후에 <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=fullName>를 호출하여 사전에 모든 리소스를 추가합니다.  그런 다음 생성된 <xref:System.Windows.ResourceDictionary>를 사용하여 페이지 범위나 <xref:System.Windows.Application.Resources%2A?displayProperty=fullName>에 있는 요소의 <xref:System.Windows.FrameworkElement.Resources%2A> 속성을 설정합니다.  또한 <xref:System.Windows.ResourceDictionary>를 요소에 추가하지 않고 독립 실행형 개체로 유지할 수도 있습니다.  그러나 이렇게 하는 경우 이 개체 내의 리소스를 일반 사전처럼 항목 키를 사용하여 액세스해야 합니다.  `Resources` 속성에 연결하지 않은 <xref:System.Windows.ResourceDictionary>는 요소 트리의 일부로 존재하지 않으며 <xref:System.Windows.FrameworkElement.FindResource%2A> 및 관련 메서드에서 사용할 수 있는 조회 시퀀스의 범위가 없습니다.  
  
<a name="objectaskey"></a>   
## 개체를 키로 사용  
 대부분의 리소스 사용에서는 리소스 키를 문자열로 설정합니다.  그러나 여러 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기능에서는 의도적으로 문자열 형식을 사용하여 키를 지정하지 않고 대신 개체를 매개 변수로 사용합니다.  리소스 키를 개체로 지정하는 기능은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 스타일 및 테마 지원에서 사용됩니다.  스타일이 지정되지 않은 컨트롤의 기본 스타일이 되는 테마의 스타일에는 해당 스타일을 적용할 컨트롤의 <xref:System.Type>에 따라 각각의 키가 지정됩니다.  형식별로 키를 지정하면 각 컨트롤 형식의 기본 인스턴스에서 작동하는 신뢰할 수 있는 조회 메커니즘을 제공할 수 있으며 형식을 리플렉션으로 검색할 수 있고 파생된 형식에 기본 스타일이 없더라도 파생된 클래스의 스타일을 지정하는 데 사용할 수 있습니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 정의한 리소스의 <xref:System.Type> 키는 [x:Type 태그 확장](../../../../docs/framework/xaml-services/x-type-markup-extension.md)을 사용하여 지정할 수 있습니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기능을 지원하는 문자열이 아닌 다른 키 사용을 위한 [ComponentResourceKey 태그 확장](../../../../docs/framework/wpf/advanced/componentresourcekey-markup-extension.md)과 같은 유사한 확장이 있습니다.  
  
## 참고 항목  
 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)