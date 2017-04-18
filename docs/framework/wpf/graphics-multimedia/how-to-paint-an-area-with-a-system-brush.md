---
title: "방법: 시스템 브러시로 영역 그리기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "브러시, 시스템 브러시로 그리기"
  - "그리기, 시스템 브러시로"
  - "시스템 브러시, 그리기"
ms.assetid: 5141a763-9235-42cb-a6bb-afc75513eac7
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: 시스템 브러시로 영역 그리기
<xref:System.Windows.SystemColors> 클래스를 사용하면 <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A> 및 <xref:System.Windows.SystemColors.DesktopBrush%2A>와 같은 시스템 브러시 및 색에 액세스할 수 있습니다.  시스템 브러시는 지정된 시스템 색으로 영역을 그리는 <xref:System.Windows.Media.SolidColorBrush> 개체입니다.  시스템 브러시는 항상 대상을 단색으로 채우므로 그라데이션을 생성하는 데 사용할 수 없습니다.  
  
 시스템 브러시를 정적 리소스나 동적 리소스로 사용할 수 있습니다.  응용 프로그램이 실행되는 동안 사용자가 시스템 브러시를 변경할 때 자동으로 브러시가 업데이트되게 하려면 동적 리소스를 사용하고, 그렇지 않은 경우에는 정적 리소스를 사용합니다.  SystemColors 클래스에는 다음과 같은 엄격한 명명 규칙을 따르는 다양한 정적 속성이 있습니다.  
  
-   *\<SystemColor\>*Brush  
  
     지정된 시스템 색의 <xref:System.Windows.Media.SolidColorBrush>에 대한 정적 참조를 가져옵니다.  
  
-   *\<SystemColor\>*BrushKey  
  
     지정된 시스템 색의 <xref:System.Windows.Media.SolidColorBrush>에 대한 동적 참조를 가져옵니다.  
  
-   *\<SystemColor\>*Color  
  
     지정된 시스템 색의 <xref:System.Windows.Media.Color> 구조체에 대한 정적 참조를 가져옵니다.  
  
-   *\<SystemColor\>*ColorKey  
  
     지정된 시스템 색의 <xref:System.Windows.Media.Color> 구조체에 대한 동적 참조를 가져옵니다.  
  
 시스템 색은 브러시를 구성하는 데 사용할 수 있는 <xref:System.Windows.Media.Color> 구조체입니다.  예를 들어 시스템 색에 <xref:System.Windows.Media.LinearGradientBrush> 개체의 그라디언트 중지점에 대한 <xref:System.Windows.Media.GradientStop.Color%2A> 속성을 설정하면 시스템 색을 사용하는 그라데이션을 만들 수 있습니다.  예제를 보려면 [그라데이션에 시스템 색 사용](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 동적 시스템 브러시 참조를 사용하여 단추의 배경을 설정합니다.  
  
 [!code-xml[brushsamples_snip#GraphicsMMDynamicSystemColorDesktopBrushKeyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemBrushExample.xaml#graphicsmmdynamicsystemcolordesktopbrushkeyexamplewholepage)]  
  
 다음 예제에서는 정적 시스템 브러시 참조를 사용하여 단추의 배경을 설정합니다.  
  
 [!code-xml[brushsamples_snip#GraphicsMMStaticSystemColorDesktopBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemBrushExample.xaml#graphicsmmstaticsystemcolordesktopbrushexamplewholepage)]  
  
 그라데이션에서 시스템 색을 사용하는 방법을 보여 주는 예제를 보려면 [그라데이션에 시스템 색 사용](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md)을 참조하십시오.  
  
## 참고 항목  
 [그라데이션에 시스템 색 사용](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md)   
 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)