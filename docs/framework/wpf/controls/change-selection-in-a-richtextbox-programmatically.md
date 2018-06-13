---
title: 프로그래밍 방식으로 RichTextBox의 선택 변경
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- changing selections in a text box [WPF]
- changing selections in a RichTextBox [WPF]
ms.assetid: f1213205-1ad7-4cd2-b115-460173cc5aa3
ms.openlocfilehash: e8ad33956f1a9fdddc728457e6c302635115b709
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551005"
---
# <a name="change-selection-in-a-richtextbox-programmatically"></a>프로그래밍 방식으로 RichTextBox의 선택 변경
프로그래밍 방식으로의 현재 선택 영역을 변경 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.RichTextBox>합니다. 사용자가 사용자 인터페이스를 사용 하 여 콘텐츠를 선택 하는 경우이 옵션을이 선택은 같습니다.  
  
## <a name="example"></a>예제  
 다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 코드 설명 명명 된 <xref:System.Windows.Controls.RichTextBox> 단순 콘텐츠는 컨트롤입니다.  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml#changeselectionprogrammaticalyexamplewholepage)]  
  
## <a name="example"></a>예제  
 다음 코드는 프로그래밍 방식으로 몇 가지 임의의 텍스트를 선택 내부를 클릭할 때는 <xref:System.Windows.Controls.RichTextBox>합니다.  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml.cs#changeselectionprogrammaticalycodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/ChangeSelectionProgrammaticaly.xaml.vb#changeselectionprogrammaticalycodeexamplewholepage)]  
  
## <a name="see-also"></a>참고 항목  
 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)
