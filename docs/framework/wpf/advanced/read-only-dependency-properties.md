---
title: "읽기 전용 종속성 속성 | Microsoft Docs"
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
  - "종속성 속성, 읽기 전용"
  - "읽기 전용 종속성 속성"
ms.assetid: f23d6ec9-3780-4c09-a2ff-b2f0a2deddf1
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 읽기 전용 종속성 속성
이 항목에서는 기존의 읽기 전용 종속성 속성 및 사용자 지정 읽기 전용 종속성 속성을 만드는 시나리오와 방법을 비롯하여 읽기 전용 속성에 대해 설명합니다.  
  
   
  
<a name="prerequisites"></a>   
## 사전 요구 사항  
 이 항목에서는 사용자가 종속성 속성을 구현하는 기본 시나리오와 사용자 지정 종속성 속성에 메타데이터를 적용하는 방법에 대해 잘 알고 있다고 가정합니다.  자세한 내용은 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md) 및 [종속성 속성 메타데이터](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)를 참조하십시오.  
  
<a name="existing"></a>   
## 기존 읽기 전용 종속성 속성  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 프레임워크에 정의된 일부 종속성 속성은 읽기 전용입니다.  종속성 속성을 읽기 전용으로 지정하는 이유는 대개 이러한 속성이 상태 확인에 사용되기 때문입니다. 하지만 상태는 여러 가지 요인에 의해 영향을 받으므로 속성을 특정 상태로 설정하는 것은 사용자 인터페이스 디자인 측면에서는 바람직하지 않습니다.  예를 들어 <xref:System.Windows.UIElement.IsMouseOver%2A> 속성은 실제로는 마우스 입력으로 확인되는 표면적인 상태일 뿐입니다.  실제 마우스 입력을 무시하고 이 값을 프로그래밍 방식으로 설정하려고 하면 예측할 수 없으며 일관되지 않은 결과가 발생합니다.  
  
 읽기 전용 속성은 설정할 수 없다는 점 때문에 데이터 바인딩, 값에 직접 스타일 지정, 유효성 검사, 애니메이션, 상속 등 종속성 속성이 일반적으로 제공하는 솔루션을 이용하려는 대부분의 시나리오에 적합하지 않습니다.  설정할 수 없다는 점에도 불구하고 읽기 전용 속성은 속성 시스템의 종속성 속성이 지원하는 추가 기능 중 몇 가지를 제공합니다.  이 중에서 가장 중요한 기능은 스타일에서 읽기 전용 종속성 속성을 여전히 속성 트리거로 사용할 수 있다는 것입니다.  일반 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 속성을 사용해서는 트리거를 사용할 수 없습니다. 트리거를 사용하려면 속성이 종속성 속성이어야 합니다.  앞에서 언급한 <xref:System.Windows.UIElement.IsMouseOver%2A> 속성은 사용자가 컨트롤의 정의된 영역 위로 마우스를 이동할 때 컨트롤 내 합성 요소의 배경, 전경 등의 일부 시각적 속성이 변경되는 컨트롤의 스타일을 정의할 때 유용하게 사용할 수 있는 속성의 대표적인 예입니다.  읽기 전용 속성의 변경은 속성 시스템 고유의 무효화 프로세스를 통해서도 검색 및 보고될 수 있으며 이는 속성 트리거 기능을 내부적으로 지원합니다.  
  
<a name="new"></a>   
## 사용자 지정 읽기 전용 종속성 속성 만들기  
 많은 수의 일반적인 종속성 속성 시나리오에서 읽기 전용 종속성 속성이 적합하지 않은 이유에 대해 설명하는 앞 단원을 읽었을 것입니다.  적합한 시나리오가 있는 경우에는 자체 읽기 전용 종속성 속성을 만들 수 있습니다.  
  
 읽기 전용 종속성 속성을 만드는 과정의 대부분은 다음과 같은 세 가지 큰 차이점을 제외하고는 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md) 및 [종속성 속성 구현](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md) 항목에서  설명하는 것과 같습니다.  
  
-   속성을 등록할 때 속성 등록에 일반적으로 사용하는 <xref:System.Windows.DependencyProperty.Register%2A> 메서드 대신 <xref:System.Windows.DependencyProperty.RegisterReadOnly%2A> 메서드를 호출합니다.  
  
-   [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] "래퍼" 속성을 구현하는 경우 이 래퍼에도 설정된 구현이 없어야 합니다. 그래야만 노출하는 공용 래퍼의 읽기 전용 상태가 일관되게 유지됩니다.  
  
-   읽기 전용 등록으로 반환되는 개체는 <xref:System.Windows.DependencyProperty>가 아니라 <xref:System.Windows.DependencyPropertyKey>입니다.  이 필드도 멤버로 저장해야 하지만 일반적으로 형식의 공용 멤버로는 설정하지 않습니다.  
  
 사용자가 지원하는 전용 필드나 값이 무엇이든 사용자가 선택한 논리를 사용하여 완벽하게 읽기 전용 종속성 속성을 작성할 수 있습니다.  하지만 속성 시스템을 무시하고 전용 지원 필드를 직접 설정하는 것보다는 속성 시스템의 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]를 사용하여 속성을 초기에 또는 런타임 논리의 일부로 설정하는 것이 가장 쉽습니다.  특히 <xref:System.Windows.DependencyPropertyKey> 형식의 매개 변수를 허용하는 <xref:System.Windows.DependencyObject.SetValue%2A> 시그니처가 있습니다.  응용 프로그램 논리 내에서 이 값을 프로그래밍 방식으로 설정하는 방법 및 설정하는 위치는 종속성 속성을 처음 등록할 때 만들어진 <xref:System.Windows.DependencyPropertyKey>에 대한 액세스를 설정하는 방법에 영향을 줍니다.  이 논리를 전용 클래스로 설정할 수 있는 클래스 내에서 모두 처리하거나 어셈블리의 다른 부분에서 별도로 처리하려는 경우 이 값을 내부 값으로 설정할 수도 있습니다.  이 작업을 수행하는 한 가지 방법은 저장된 속성 값을 변경해야 함을 클래스 인스턴스에 알려 주는 관련 이벤트의 클래스 이벤트 처리기 내에서 <xref:System.Windows.DependencyObject.SetValue%2A>를 호출하는 것입니다.  또 다른 방법은 등록하는 동안 쌍으로 된 <xref:System.Windows.PropertyChangedCallback> 및 <xref:System.Windows.CoerceValueCallback> 콜백을 해당 속성 메타데이터의 일부로 사용하여 종속성 속성을 모두 연결하는 것입니다.  
  
 <xref:System.Windows.DependencyPropertyKey>는 전용이고 속성 시스템을 통해 코드 외부로 전파되지 않으므로 읽기 전용 종속성 속성의 보안 설정이 읽기\/쓰기 종속성 속성보다 우수합니다.  읽기\/쓰기 종속성 속성의 경우 식별하는 필드는 명시적 또는 암시적으로 공용이므로 다양하게 속성을 설정할 수 있습니다.  자세한 내용은 [종속성 속성 보안](../../../../docs/framework/wpf/advanced/dependency-property-security.md)을 참조하십시오.  
  
## 참고 항목  
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)