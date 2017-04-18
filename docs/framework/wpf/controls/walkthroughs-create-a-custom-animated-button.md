---
title: "연습: 사용자 지정 애니메이션 단추 만들기 | Microsoft Docs"
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
  - "애니메이션, 단추"
  - "단추"
  - "사용자 지정 애니메이션 단추"
ms.assetid: e9532c72-460f-4898-9332-613fa21d746a
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 연습: 사용자 지정 애니메이션 단추 만들기
이름에서 알 수 있듯이 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]는 고객을 위한 풍부한 표시 경험을 만들어 주는 데 유용합니다.  이 연습에서는 단추의 모양과 동작\(애니메이션 포함\)을 사용자 지정하는 방법을 보여 줍니다.  이 사용자 지정 단추를 쉽게 응용 프로그램의 단추에 적용할 수 있도록 이러한 사용자 지정은 스타일과 템플릿을 사용하여 수행됩니다.  다음 그림에서는 사용자가 만들 사용자 지정 단추를 보여 줍니다.  
  
 ![만들게 될 사용자 지정된 단추](../../../../docs/framework/wpf/controls/media/custom-button-blend-intro.png "custom\_button\_blend\_Intro")  
  
 단추의 모양을 구성하는 벡터 그래픽은 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]을 사용하여 만들어집니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]은 좀 더 강력하고 확장 가능하다는 점을 제외하면 HTML과 유사합니다.  Microsoft Visual Studio나 메모장을 사용하여 직접 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]을 입력할 수 있거나 Microsoft Expression Blend와 같은 시각적 디자인 도구를 사용할 수 있습니다.  Expression Blend는 기본 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 코드를 만들어 작동하므로 두 방법 모두 같은 그래픽을 만듭니다.  
  
## 단원 내용  
 [Microsoft Expression Blend를 사용하여 단추 만들기](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md)  
 Expression Blend의 디자이너 기능을 사용하여 사용자 지정 동작이 있는 단추를 만드는 방법을 보여 줍니다.  
  
 [XAML을 사용하여 단추 만들기](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-xaml.md)  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 및 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]를 사용하여 사용자 지정 동작이 있는 단추를 만드는 방법을 보여 줍니다.  
  
## 관련 단원  
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 스타일 및 템플릿을 사용하여 컨트롤의 모양과 동작을 결정하는 방법을 설명합니다.  
  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 애니메이션 및 타이밍 시스템을 사용하여 개체에 애니메이션 효과를 줄 수 있는 방법을 설명합니다.  
  
 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 브러시 개체를 사용하여 단색, 선형 그라데이션 및 방사형 그라데이션으로 그리는 방법을 설명합니다.  
  
 [비트맵 효과 개요](../../../../docs/framework/wpf/graphics-multimedia/bitmap-effects-overview.md)  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 지원하는 비트맵 효과 및 이 효과를 적용하는 방법을 설명합니다.