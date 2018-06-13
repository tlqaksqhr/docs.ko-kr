---
title: '방법: TextBox 컨트롤에서 탭 문자 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], enabling tab characters
- tab characters [WPF], enabling
ms.assetid: 14b1b064-61f7-4958-be63-88d85b868d03
ms.openlocfilehash: 9203a09408b4f88f3fbe8c0d87e365c1d05a1462
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33550188"
---
# <a name="how-to-enable-tab-characters-in-a-textbox-control"></a>방법: TextBox 컨트롤에서 탭 문자 사용
탭 문자에 대 한 동의에서 일반 입력으로 사용 하도록 설정 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.TextBox> 제어 합니다.  
  
## <a name="example"></a>예제  
 입력으로 수락이 탭 문자를 사용 하도록 설정 하려면 한 <xref:System.Windows.Controls.TextBox> 제어, 설정는 <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsTab%2A> 특성을 **true**합니다.  
  
 [!code-xaml[TextBox_EnablingTab#_AcceptsTab](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_EnablingTab/CS/Window1.xaml#_acceptstab)]  
  
## <a name="see-also"></a>참고 항목  
 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
