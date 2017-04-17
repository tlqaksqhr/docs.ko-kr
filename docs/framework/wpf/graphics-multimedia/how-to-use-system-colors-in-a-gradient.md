---
title: "방법: 그라데이션에 시스템 색 사용 | Microsoft Docs"
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
  - "그라데이션, 시스템 색"
  - "그라데이션이 적용된 시스템 색"
ms.assetid: 11942e7e-6300-4b50-8ed1-f50e8d20e7d2
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: 그라데이션에 시스템 색 사용
그라데이션에 시스템 색을 사용하려면 <xref:System.Windows.SystemColors> 클래스의 *\<SystemColor\>*Color 및 *\<SystemColor\>*ColorKey 정적 속성을 사용하여 색에 대한 참조를 가져옵니다. 여기서 *\<SystemColor\>*는 사용할 시스템 색의 이름입니다.  시스템 테마가 변경되면 자동으로 업데이트되는 동적 참조를 만들려면 *\<SystemColor\>*ColorKey 속성을 사용하고,  그렇지 않으면 *\<SystemColor\>*Color 속성을 사용합니다.  
  
## 예제  
 다음 예제에서는 동적 시스템 색 리소스를 사용하여 그라데이션을 만듭니다.  
  
 [!code-xml[brushsamples_snip#GraphicsMMDynamicSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemColorExample.xaml#graphicsmmdynamicsystemcolorgradientexamplewholepage)]  
  
 다음 예제에서는 정적 시스템 색 리소스를 사용하여 그라데이션을 만듭니다.  
  
 [!code-xml[brushsamples_snip#GraphicsMMStaticSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemColorExample.xaml#graphicsmmstaticsystemcolorgradientexamplewholepage)]  
  
## 참고 항목  
 <xref:System.Windows.SystemColors>   
 [시스템 브러시로 영역 그리기](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)   
 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)