---
title: "방법: 윤곽선이 있는 텍스트 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], linear gradient brush
- outlined text [WPF]
- gradient brush [WPF]
- linear gradient brush [WPF]
- typography [WPF], outline effects
ms.assetid: 4aa3cf6e-1953-4f26-8230-7c1409e5f28d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 76d0dcf63f9d8a66106f4bcdc52a2bf98c75cdc4
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-outlined-text"></a>방법: 윤곽선이 있는 텍스트 만들기
대부분의 경우 장식을의 텍스트 문자열에 추가할 때 프로그램 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 불연속 문자 또는 문자 모양의 컬렉션과 관련 된 텍스트를 사용 하는 응용 프로그램입니다. 예를 들어 만들고 하는 선형 그라데이션 브러시에 적용 된 <xref:System.Windows.Controls.Control.Foreground%2A> 속성은 <xref:System.Windows.Controls.TextBox> 개체입니다. 을 표시 하거나 텍스트 상자를 편집할 때 선형 그라데이션 브러시 현재 텍스트 문자열의 문자 집합에 자동으로 적용 됩니다.  
  
 ![선형 그라데이션 브러시로 표시 되는 텍스트](../../../../docs/framework/wpf/advanced/media/outlinedtext01.jpg "OutlinedText01")  
텍스트 상자에 적용 하는 선형 그라데이션 브러시의 예  
  
 그러나 텍스트를 또한 변환할 수 <xref:System.Windows.Media.Geometry> 개체를 다른 유형의 시각적 서식 있는 텍스트를 만들 수 있습니다. 예를 들어, 만들 수는 <xref:System.Windows.Media.Geometry> 텍스트 문자열의 윤곽선을 기반으로 하는 개체입니다.  
  
 ![선형 그라데이션 브러시를 사용 하 여 텍스트 윤곽선](../../../../docs/framework/wpf/advanced/media/outlinedtext02.jpg "OutlinedText02")  
텍스트의 개요 기 하 도형에 적용 된 선형 그라데이션 브러시의 예  
  
 에 변환 된 텍스트는 <xref:System.Windows.Media.Geometry> 문자의 컬렉션은 더 이상 개체-텍스트 문자열의에서 문자를 수정할 수 없습니다. 그러나 스트로크와 채우기 속성을 수정하여 변환된 텍스트의 모양에 영향을 줄 수 있습니다. 스트로크는 변환된 텍스트의 윤곽선을 나타내고, 채우기는 변환된 텍스트의 윤곽선 내부에 있는 영역을 나타냅니다.  
  
 다음 예제에는 변환 된 텍스트의 흑백 수정 하 여 시각적 효과 만드는 여러 가지 방법을 보여 줍니다.  
  
 ![채우기와 스트로크에 다른 색으로 텍스트](../../../../docs/framework/wpf/advanced/media/outlinedtext03.jpg "OutlinedText03")  
스트로크와 채우기를 다른 색상으로 설정하는 예  
  
 ![스트로크에 이미지 브러시가 적용 된 텍스트](../../../../docs/framework/wpf/advanced/media/outlinedtext04.jpg "OutlinedText04")  
스트로크에 적용한 이미지 브러시의 예  
  
 경계 상자 사각형 또는 변환된 된 텍스트의 강조 표시를 수정 하는 것도 가능 합니다. 다음 예제에서는 스트로크 및 변환 된 텍스트의 강조 표시를 수정 하 여 시각 효과를 만드는 방법을 보여 줍니다.  
  
 ![스트로크에 이미지 브러시가 적용 된 텍스트](../../../../docs/framework/wpf/advanced/media/outlinedtext05.jpg "OutlinedText05")  
스트로크와 강조 표시에 적용된 이미지 브러시의 예  
  
## <a name="example"></a>예제  
 텍스트를 변환 하는 <xref:System.Windows.Media.Geometry> 는 사용 하 여 <xref:System.Windows.Media.FormattedText> 개체입니다. 이 개체를 만든 후 사용할 수 있습니다는 <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> 및 <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> 텍스트를 변환 하는 메서드 <xref:System.Windows.Media.Geometry> 개체입니다. 첫 번째 메서드는 서식 있는 텍스트;의 기 하 도형을 반환합니다. 두 번째 방법은 경계 상자의 서식 있는 텍스트의 기 하 도형을 반환 합니다. 다음 코드 예제에서는 만드는 방법을 보여 줍니다.는 <xref:System.Windows.Media.FormattedText> 개체 서식 있는 텍스트와 해당 경계 상자의의 기 하 도형이 검색할 수 있습니다.  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 검색을 표시 하기 위해는 <xref:System.Windows.Media.Geometry> 개체에 액세스 해야는 <xref:System.Windows.Media.DrawingContext> 변환된 된 텍스트를 표시 하는 개체입니다. 이 코드 예제에서이 사용자 지정 렌더링을 지원 되는 클래스에서 파생 된 사용자 지정 컨트롤 개체를 만들어 이루어집니다.  
  
 표시 하려면 <xref:System.Windows.Media.Geometry> 에 대 한 재정의 제공 하는 사용자 지정 컨트롤의 개체는 <xref:System.Windows.UIElement.OnRender%2A> 메서드. 재정의 된 메서드를 사용할지는 <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> 를 그리는 메서드는 <xref:System.Windows.Media.Geometry> 개체입니다.  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
## <a name="see-also"></a>참고 항목  
 [서식 있는 텍스트 그리기](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
