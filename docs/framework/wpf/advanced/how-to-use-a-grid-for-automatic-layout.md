---
title: "방법: 자동 레이아웃에 Grid 사용 | Microsoft Docs"
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
  - "자동 레이아웃, 모눈 사용"
  - "모눈, 자동 레이아웃"
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 자동 레이아웃에 Grid 사용
이 예제에서는 지역화할 수 있는 응용 프로그램을 만드는 자동 레이아웃 방법에서 모눈을 사용하는 방법을 설명합니다.  
  
 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 지역화에는 많은 시간이 소요될 수 있습니다.  지역화 담당자는 텍스트를 번역하는 작업 외에도 요소의 크기를 조정하고 위치를 변경해야 하는 경우가 많습니다.  과거에는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 조정에 사용한 각 언어에 조정 작업이 필요했습니다.  이제는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 기능을 사용하여 조정 작업의 필요성이 낮은 요소를 디자인할 수 있습니다.  크기 조정 및 변경 작업이 보다 쉽도록 응용 프로그램을 작성하는 방법을 `auto layout`이라고 합니다.  
  
 다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 예제에서는 모눈을 사용하여 일부 단추 및 텍스트의 위치를 지정하는 것을 보여 줍니다.  셀의 높이와 너비가 `Auto`로 설정되어 있으므로 이미지가 있는 단추가 포함된 셀이 이미지에 맞게 조정됩니다.  <xref:System.Windows.Controls.Grid> 요소는 해당 콘텐츠에 맞게 조정될 수 있으므로 지역화할 수 있는 응용 프로그램을 디자인하는 자동 레이아웃 방법을 사용할 때 유용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 모눈을 사용하는 방법을 보여 줍니다.  
  
 [!code-xml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 다음 그래픽에서는 코드 샘플의 출력을 보여 줍니다.  
  
 ![표 예제](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob\_grid")  
모눈  
  
## 참고 항목  
 [자동 레이아웃 사용 개요](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)   
 [자동 레이아웃을 사용하여 단추 만들기](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)