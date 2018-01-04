---
title: "방법: TextBox 컨트롤을 읽기 전용으로 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f3d3acf1e5065633f9f4c75f24780230525b01ba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-a-textbox-control-read-only"></a>방법: TextBox 컨트롤을 읽기 전용으로 설정
구성 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.TextBox> 컨트롤을 사용자 입력 또는 수정할 수 없습니다.  
  
## <a name="example"></a>예  
 내용을 수정 하지 못하게 하려면는 <xref:System.Windows.Controls.TextBox> 제어, 설정 된 <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> 특성을 **true**합니다.  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> 특성에 사용자 입력에만 영향을 줍니다;에 설정 된 텍스트에는 영향을 주지 않습니다는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 설명은 <xref:System.Windows.Controls.TextBox> 컨트롤 또는 통해 프로그래밍 방식으로 설정 된 텍스트는 <xref:System.Windows.Controls.TextBox.Text%2A> 속성입니다.  
  
 기본값 <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> 은 **false**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
