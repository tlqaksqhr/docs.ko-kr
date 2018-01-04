---
title: "방법: 프로그래밍 방식으로 TextWrapping 속성 변경"
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
- documents [WPF], changing TextWrapping property programmatically
- TextWrapping property [WPF], changing programmatically
ms.assetid: 30d25554-4c82-4df9-a8d6-35683a4a13bb
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ca87d651f66edba00280a57ca1468af33657a329
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-textwrapping-property-programmatically"></a>방법: 프로그래밍 방식으로 TextWrapping 속성 변경
## <a name="example"></a>예  
 다음 코드 예제에서는의 값을 변경 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> 속성 프로그래밍 방식으로 합니다.  
  
 세 가지 <xref:System.Windows.Controls.Button> 요소 안에 배치 되는 <xref:System.Windows.Controls.StackPanel> 요소에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]합니다. 각 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 에 대 한 이벤트는 <xref:System.Windows.Controls.Button> 를 이벤트 처리기 코드에 해당 합니다. 이벤트 처리기와 같은 이름을 사용 하 여는 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> 값에 적용 됩니다 `txt2` 단추를 클릭 합니다. 또한 텍스트 `txt1` (한 <xref:System.Windows.Controls.TextBlock> 에 표시 되지는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]) 속성의 변경 내용을 반영 하도록 업데이트 됩니다.  
  
 [!code-xaml[TextWrapProperty#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml#1)]  
  
 [!code-csharp[TextWrapProperty#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextWrapProperty/CSharp/Window1.xaml.cs#2)]
 [!code-vb[TextWrapProperty#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>  
 <xref:System.Windows.TextWrapping>
