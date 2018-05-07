---
title: '방법: RichTextBox 컨트롤에 끌어 놓은 파일 열기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], RichTextBox
- RichTextBox [WPF], drag-and-drop
- drag-and-drop [WPF], open a dropped file
ms.assetid: 6bb8bb54-f576-41db-a9a7-24102ddeb490
ms.openlocfilehash: f3c10ae76a9afcc04578c590cc57cd43c3ab7a1e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-open-a-file-that-is-dropped-on-a-richtextbox-control"></a>방법: RichTextBox 컨트롤에 끌어 놓은 파일 열기
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, 및 <xref:System.Windows.Documents.FlowDocument> 컨트롤은 모두 기능이 기본 제공 끌어서 놓기. 기본 제공 기능 컨트롤 간의 텍스트 내에서 끌어서 놓기 사용 하도록 설정 합니다. 그러나 컨트롤에 파일을 삭제 하 여 파일을 열 수 없습니다 것. 이러한 제어는 또한 처리 된 것으로 끌어서 놓기 이벤트를 표시 합니다. 결과적으로, 기본적으로 삭제 된 파일을 여는 기능을 제공 하는 고유한 이벤트 처리기를 추가할 수 없습니다.  
  
 이러한 컨트롤에서 끌어서 놓기 이벤트에 대 한 추가 처리를 추가 하려면 사용 된 <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> 메서드를 끌어서 놓기 이벤트에 대 한 이벤트 처리기를 추가 합니다. 설정의 `handledEventsToo` 매개 변수를 `true` 지정된 된 처리기 이벤트 경로 따라 다른 요소에 의해 처리 된 것으로 이미 표시 된 라우트된 이벤트에 대해 호출할 수 있어야 합니다.  
  
> [!TIP]
>  기본 제공 끌어서 놓기 기능을 바꿀 수 <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, 및 <xref:System.Windows.Documents.FlowDocument> 미리 보기 버전의 끌어서 놓기 이벤트를 처리 하 고 처리 된 것으로 미리 보기 이벤트를 표시 함으로써 합니다. 그러나이 기본 제공 끌어서 놓기 기능을 사용할 수 없게 않으며 권장 되지 않습니다.  
  
## <a name="example"></a>예제  
 다음 예제에 대 한 처리기를 추가 하는 방법을 보여 줍니다는 <xref:System.Windows.DragDrop.DragOver> 및 <xref:System.Windows.DragDrop.Drop> 이벤트에는 <xref:System.Windows.Controls.RichTextBox>합니다. 사용 하 여이 예제는 <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> 메서드 및 집합은 `handledEventsToo` 매개 변수를 `true` 이벤트 처리기도 호출 될 수 있도록는 <xref:System.Windows.Controls.RichTextBox> 처리 된 것으로 이러한 이벤트를 표시 합니다. 이벤트 처리기의 코드에서 삭제 된 텍스트 파일을 열 기능을 추가 <xref:System.Windows.Controls.RichTextBox>합니다.  
  
 이 예제를 테스트 하려면 텍스트 파일 또는 서식 있는 텍스트 RTF (형식) 파일 탐색기에서 끌어 Windows에는 <xref:System.Windows.Controls.RichTextBox>합니다. 파일을 열면 됩니다는 <xref:System.Windows.Controls.RichTextBox>합니다. 삭제 전에 SHIFT 키를 누를 경우 파일을 일반 텍스트로 파일이 열립니다.  
  
 [!code-xaml[DragDropSnippets#RtbXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]  
  
 [!code-csharp[DragDropSnippets#RtbHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
 [!code-vb[DragDropSnippets#RtbHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]
