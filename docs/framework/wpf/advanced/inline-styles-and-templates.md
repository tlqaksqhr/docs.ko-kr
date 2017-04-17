---
title: "인라인 스타일 및 템플릿 | Microsoft Docs"
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
  - "인라인 스타일"
  - "인라인 템플릿"
  - "스타일, inline"
  - "템플릿, inline"
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 인라인 스타일 및 템플릿
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서는 리소스 요소의 시각적 모양을 정의하여 여러 번 사용할 수 있게 하는 방법으로 <xref:System.Windows.Style> 개체 및 템플릿 개체\(<xref:System.Windows.FrameworkTemplate> 서브클래스\)를 제공합니다.  이러한 이유로 <xref:System.Windows.Style> 및 <xref:System.Windows.FrameworkTemplate> 형식을 사용하는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 특성은 거의 항상 스타일 및 템플릿을 인라인으로 새로 정의하는 것이 아니라 기존 스타일과 템플릿에 대한 리소스 참조를 만듭니다.  
  
## 인라인 스타일 및 템플릿의 제한  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서는 스타일과 템플릿 속성을 기술적인 측면에서 다음 두 방법 중 하나로 설정할 수 있습니다.  예를 들어 `<`*object*`Style="{StaticResource`*myResourceKey*`}" .../>`와 같이 리소스 내에서 정의된 스타일을 참조하는 데 특성 구문을 사용할 수 있습니다.  또는 다음의 예제와 같이 속성 요소 구문을 사용하여 인라인 스타일을 정의할 수 있습니다.  
  
 `<` *object* `>`  
  
 `<` *object* `.Style>`  
  
 `<` `Style`  `.../>`  
  
 `</` *object* `.Style>`  
  
 `</` *object* `>`  
  
 일반적으로 특성이 더 많이 사용됩니다.  인라인으로 정의되고 리소스에서는 정의되지 않은 스타일은 포함 요소로만 범위가 지정되며 리소스 키가 없기 때문에 쉽게 재사용할 수 없습니다.  대개의 경우 리소스에서 정의되는 스타일이 더 넓은 범위에서 유용하게 사용될 수 있으며 코드로 된 프로그램 논리를 태그로 된 디자인에서 분리하는 일반적인 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 프로그래밍 모델 원칙에 더 부합됩니다.  
  
 보통 스타일이나 템플릿을 특정 위치에만 사용하려는 경우라도 스타일이나 템플릿을 인라인으로 설정할 이유는 없습니다.  스타일이나 템플릿을 사용할 수 있는 대부분의 요소는 콘텐츠 속성과 콘텐츠 모델도 지원합니다.  스타일이나 템플릿을 통해 만드는 논리 트리를 한 번만 사용하는 경우에는 해당 콘텐츠 속성을 직접 태그의 해당 자식 요소로 채우는 것이 훨씬 쉽습니다.  이렇게 하면 스타일 및 템플릿 메커니즘을 한꺼번에 우회합니다.  
  
 개체를 반환하는 태그 확장으로 활성화되는 다른 구문은 스타일과 템플릿에도 사용할 수 있습니다.  이러한 시나리오가 가능한 확장으로는 [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) 및 <xref:System.Windows.Data.Binding>이 있습니다.  
  
## 참고 항목  
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)