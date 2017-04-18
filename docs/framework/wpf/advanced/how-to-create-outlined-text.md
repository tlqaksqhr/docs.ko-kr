---
title: "방법: 윤곽선이 있는 텍스트 만들기 | Microsoft Docs"
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
  - "그라데이션 브러시"
  - "선형 그라데이션 브러시"
  - "윤곽선이 그려진 텍스트"
  - "입력 체계, 선형 그라데이션 브러시"
  - "입력 체계, 윤곽선 효과"
ms.assetid: 4aa3cf6e-1953-4f26-8230-7c1409e5f28d
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: 윤곽선이 있는 텍스트 만들기
대부분의 경우 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램의 텍스트 문자열에 장식을 추가할 때 개별 문자나 문자 모양의 컬렉션과 관련된 텍스트를 사용하게 됩니다.  예를 들어 선형 그라데이션 브러시를 만들어 <xref:System.Windows.Controls.TextBox> 개체의 <xref:System.Windows.Controls.Control.Foreground%2A> 속성에 적용할 수 있습니다.  텍스트 상자를 표시하거나 편집할 때 선형 그라데이션 브러시가 텍스트 문자열의 현재 문자 집합에 자동으로 적용됩니다.  
  
 ![선형 그라데이션 브러시로 표시된 텍스트](../../../../docs/framework/wpf/advanced/media/outlinedtext01.png "OutlinedText01")  
텍스트 상자에 적용된 선형 그라데이션 브러시의 예  
  
 하지만 텍스트를 <xref:System.Windows.Media.Geometry> 개체로 변환하여 다른 형식의 시각적 서식이 있는 텍스트를 만들 수도 있습니다.  예를 들어 텍스트 문자열의 윤곽선을 사용하여 <xref:System.Windows.Media.Geometry> 개체를 만들 수 있습니다.  
  
 ![선형 그라데이션 브러시를 사용하여 표시한 텍스트 윤곽선](../../../../docs/framework/wpf/advanced/media/outlinedtext02.png "OutlinedText02")  
텍스트의 윤곽선 기하 도형에 적용된 선형 그라데이션 브러시의 예  
  
 <xref:System.Windows.Media.Geometry> 개체로 변환된 텍스트는 더 이상 문자 컬렉션이 아니므로 텍스트 문자열의 문자를 수정할 수 없습니다.  그러나 스트로크 및 채우기 속성을 수정하여 변환된 텍스트의 모양을 변경할 수 있습니다.  스트로크는 변환된 텍스트의 윤곽선을 참조하고 채우기는 변환된 텍스트의 윤곽선 내의 영역을 참조합니다.  
  
 다음 예제에서는 변환된 텍스트의 스트로크 및 채우기를 수정하여 시각 효과를 만드는 여러 가지 방법을 보여 줍니다.  
  
 ![채우기와 스트로크에 다른 색을 사용하는 텍스트](../../../../docs/framework/wpf/advanced/media/outlinedtext03.png "OutlinedText03")  
다른 색으로 스트로크와 채우기를 설정하는 예  
  
 ![스트로크에 이미지 브러시가 적용된 텍스트](../../../../docs/framework/wpf/advanced/media/outlinedtext04.png "OutlinedText04")  
스트로크에 이미지 브러시가 적용된 예  
  
 또한 변환된 텍스트의 경계 상자 사각형이나 강조 표시를 수정할 수 있습니다.  다음 예제에서는 변환된 텍스트의 스트로크 및 강조 표시를 수정하여 시각 효과를 만드는 방법을 보여 줍니다.  
  
 ![스트로크에 이미지 브러시가 적용된 텍스트](../../../../docs/framework/wpf/advanced/media/outlinedtext05.png "OutlinedText05")  
스트로크 및 강조 표시에 이미지 브러시가 적용된 예  
  
## 예제  
 텍스트를 <xref:System.Windows.Media.Geometry> 개체로 변환할 때 가장 중요한 것은 <xref:System.Windows.Media.FormattedText> 개체를 사용하는 것입니다.  이 개체를 만들었으면 <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> 및 <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> 메서드를 사용하여 텍스트를 <xref:System.Windows.Media.Geometry> 개체로 변환할 수 있습니다.  첫 번째 메서드는 서식 있는 텍스트의 기하 도형을 반환하고 두 번째 메서드는 서식 있는 텍스트 경계 상자의 기하 도형을 반환합니다.  다음 코드 예제에서는 <xref:System.Windows.Media.FormattedText> 개체를 만들고 서식 있는 텍스트와 해당 경계 상자의 기하 도형을 검색하는 방법을 보여 줍니다.  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 검색된 <xref:System.Windows.Media.Geometry> 개체를 표시하려면 변환된 텍스트를 표시하는 개체의 <xref:System.Windows.Media.DrawingContext>에 액세스해야 합니다.  이 코드 예제에서의 작업은 사용자 정의 렌더링을 지원하는 클래스에서 파생된 사용자 지정 컨트롤 개체를 만들어서 수행됩니다.  
  
 사용자 지정 컨트롤에서 <xref:System.Windows.Media.Geometry> 개체를 표시하려면 <xref:System.Windows.UIElement.OnRender%2A> 메서드에 대한 재정의를 제공합니다.  재정의된 메서드는 <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> 메서드를 사용하여 <xref:System.Windows.Media.Geometry> 개체를 그려야 합니다.  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
## 참고 항목  
 [서식 있는 텍스트 그리기](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)