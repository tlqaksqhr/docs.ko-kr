---
title: "방법: 자동 레이아웃을 사용하여 단추 만들기 | Microsoft Docs"
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
  - "자동 레이아웃, 단추 만들기"
  - "Button 컨트롤, 자동 레이아웃으로 만들기"
  - "만들기, 자동 레이아웃으로 단추"
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 자동 레이아웃을 사용하여 단추 만들기
이 예제에서는 자동 레이아웃 방법을 사용하여 지역화할 수 있는 응용 프로그램에서 단추를 만드는 방법을 설명합니다.  
  
 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 지역화에는 많은 시간이 소요될 수 있습니다.  지역화 담당자는 텍스트를 번역하는 작업 외에도 요소의 크기를 조정하고 위치를 변경해야 하는 경우가 많습니다.  과거에는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 조정에 사용한 각 언어에 조정 작업이 필요했습니다.  이제는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 기능을 사용하여 조정 작업의 필요성이 낮은 요소를 디자인할 수 있습니다.  크기 조정 및 변경 작업이 보다 쉽도록 응용 프로그램을 작성하는 방법을 `automatic layout`이라고 합니다.  
  
 다음 두 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 예제에서는 단추를 인스턴스화하는 응용 프로그램을 만듭니다. 한 예제에서는 영어 텍스트를 사용하고 다른 예제에서는 스페인어 텍스트를 사용합니다.  코드는 텍스트를 제외하고 같습니다. 단추는 텍스트에 맞게 조정됩니다.  
  
## 예제  
 [!code-xml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 [!code-xml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 다음 그래픽에서는 코드 샘플의 출력을 보여 줍니다.  
  
 ![텍스트가 여러 언어로 표시되는 동일한 단추](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")  
자동으로 크기를 조정할 수 있는 단추  
  
## 참고 항목  
 [자동 레이아웃 사용 개요](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)   
 [자동 레이아웃에 Grid 사용](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)