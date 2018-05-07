---
title: '방법: TextBox에서 텍스트가 변경되는 시점 감지'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
ms.openlocfilehash: 1befd18220488334319a55bce2ce602aef20d3d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a>방법: TextBox에서 텍스트가 변경되는 시점 감지
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 메서드를 실행 하는 이벤트 때마다의 텍스트는 <xref:System.Windows.Controls.TextBox> 컨트롤이 변경 합니다.  
  
 에 대 한 코드 숨김 클래스에는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 를 포함 하는 <xref:System.Windows.Controls.TextBox> 변경 내용을 모니터링 하려면 컨트롤 삽입 메서드를 호출할 때마다는 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 이벤트 발생 합니다.  이 메서드에 의해 실행 되는 것을 일치 하는 서명이 있어야 합니다.는 <xref:System.Windows.Controls.TextChangedEventHandler> 위임 합니다.  
  
 이벤트 처리기가 호출 될 때마다 내용의 <xref:System.Windows.Controls.TextBox> 컨트롤 사용자가 또는 프로그래밍 방식으로 변경 됩니다.  
  
 **참고:** 이 이벤트가 발생할 때의 <xref:System.Windows.Controls.TextBox> 컨트롤이 만들어지고 처음 텍스트가 채워집니다.  
  
## <a name="example"></a>예제  
 에 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 정의 하는 프로그램 <xref:System.Windows.Controls.TextBox> 을 제어는 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 이벤트 처리기 메서드 이름과 일치 하는 값을 가진 특성입니다.  
  
 [!code-xaml[TextBox_MiscCode#_TextChangedXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]  
  
## <a name="example"></a>예제  
 에 대 한 코드 숨김 클래스에는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 를 포함 하는 <xref:System.Windows.Controls.TextBox> 변경 내용을 모니터링 하려면 컨트롤 삽입 메서드를 호출할 때마다는 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 이벤트 발생 합니다.  이 메서드에 의해 실행 되는 것을 일치 하는 서명이 있어야 합니다.는 <xref:System.Windows.Controls.TextChangedEventHandler> 위임 합니다.  
  
 [!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
 [!code-vb[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]  
  
 이벤트 처리기가 호출 될 때마다 내용의 <xref:System.Windows.Controls.TextBox> 컨트롤 사용자가 또는 프로그래밍 방식으로 변경 됩니다.  
  
 **참고:** 이 이벤트가 발생할 때의 <xref:System.Windows.Controls.TextBox> 컨트롤이 만들어지고 처음 텍스트가 채워집니다.  
  
 설명  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.TextChangedEventArgs>  
 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
