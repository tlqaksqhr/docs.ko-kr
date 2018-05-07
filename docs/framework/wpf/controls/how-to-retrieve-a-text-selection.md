---
title: '방법: 텍스트 선택 검색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], retrieving
- TextBox control [WPF], retrieving text
- retrieving text [WPF]
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
ms.openlocfilehash: 6b25c555d5e6cac93b2e1518b25e7880ab77c866
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-retrieve-a-text-selection"></a>방법: 텍스트 선택 검색
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.TextBox.SelectedText%2A> 속성에서 사용자가 선택한 텍스트를 검색할는 <xref:System.Windows.Controls.TextBox> 제어 합니다.  
  
## <a name="example"></a>예제  
 다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 의 정의 표시 하는 예제는 <xref:System.Windows.Controls.TextBox> 를 선택 하려면 몇 가지 텍스트가 포함 된 컨트롤 및 <xref:System.Windows.Controls.Button> 지정한 <xref:System.Windows.Controls.Button.OnClick%2A> 메서드.  
  
 이 예제에서는 관련 된 단추 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트 처리기는 텍스트 선택 항목을 검색 하는 데 사용 됩니다. 사용자가 단추를 클릭할 때는 <xref:System.Windows.Controls.Button.OnClick%2A> 메서드는 문자열에 텍스트 상자에 선택한 모든 텍스트를 복사 합니다. 텍스트 선택 영역이 검색 하 (단추 클릭) 뿐만 아니라 다양 한 시나리오에 맞게 쉽게 수정할 수 있습니다 (텍스트 선택 항목을 문자열로 복사)는 해당 선택으로 수행 되는 작업 하는 특별 한 상황이 합니다.  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxSelectTextXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## <a name="example"></a>예제  
 다음 C# 예제에서는 <xref:System.Windows.Controls.Button.OnClick%2A> 에 정의 된 단추에 대 한 이벤트 처리기는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 이 예제에 대 한 합니다.  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## <a name="see-also"></a>참고 항목  
 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
