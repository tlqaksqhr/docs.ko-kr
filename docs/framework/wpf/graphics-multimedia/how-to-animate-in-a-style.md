---
title: "방법: 스타일에 애니메이션 효과 적용 | Microsoft Docs"
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
  - "애니메이션, 속성, 스타일 내"
  - "스타일, 속성에 애니메이션 적용"
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 스타일에 애니메이션 효과 적용
이 예제에서는 스타일 내에서 속성에 애니메이션 효과를 적용하는 방법을 보여 줍니다.  스타일 내에서 애니메이션 효과를 적용할 때는 스타일이 정의된 프레임워크 요소만 직접 대상으로 사용할 수 있습니다.  Freezable 개체를 대상으로 하려면 스타일이 지정된 요소의 속성과 "점으로 구분"해야 합니다.  
  
 다음 예제에서는 몇 개의 애니메이션을 스타일 안에서 정의하고 <xref:System.Windows.Controls.Button>에 적용합니다.  사용자가 단추 위로 마우스를 옮기면 불투명했던 단추가 부분적으로 반투명해졌다가 다시 원래 상태로 돌아오는 과정이 반복됩니다.  사용자가 마우스를 단추 바깥으로 옮기면 단추가 완전히 불투명해집니다.  단추를 클릭하면 배경색이 주황색에서 흰색으로 변했다 다시 원래 색상으로 돌아옵니다.  단추를 칠하는 데 사용되는 <xref:System.Windows.Media.SolidColorBrush>는 직접 대상으로 지정할 수 없기 때문에 단추의 <xref:System.Windows.Controls.Control.Background%2A> 속성과 점으로 구분하여 액세스합니다.  
  
## 예제  
 [!code-xml[timingbehaviors_snip#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]  
  
 스타일 내에서 애니메이션 효과를 적용할 때는 존재하지 않는 개체를 대상으로 할 수도 있습니다.  예를 들어 스타일에서 <xref:System.Windows.Media.SolidColorBrush>를 사용하여 단추의 배경 속성을 설정하지만 특정 지점에서 이 스타일이 재정의되고 배경이 <xref:System.Windows.Media.LinearGradientBrush>로 설정된다고 가정해 보겠습니다.  이때 <xref:System.Windows.Media.SolidColorBrush>에 애니메이션 효과를 적용하려고 하면 예외가 throw되지 않고 애니메이션이 만들어지지 않습니다.  
  
 Storyboard 대상 지정 구문에 대한 자세한 내용은 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)를 참조하십시오.  애니메이션에 대한 자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하십시오.  스타일에 대한 자세한 내용은 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)을 참조하십시오.