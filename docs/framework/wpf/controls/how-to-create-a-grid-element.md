---
title: "방법: Grid 요소 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], grid instance
ms.assetid: b2f07626-9df8-43b8-8d36-492f3cb42837
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 30fdd89a46e5d2027e9c525b0ca8cfcfb1d11ed2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-grid-element"></a>방법: Grid 요소 만들기
## <a name="example"></a>예  
 만들고의 인스턴스를 사용 하는 방법을 보여 주는 다음 예제 <xref:System.Windows.Controls.Grid> 중 하나를 사용 하 여 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 또는 코드입니다. 이 예에서는 세 개의 <xref:System.Windows.Controls.ColumnDefinition> 개체 및 3 <xref:System.Windows.Controls.RowDefinition> 를 9 개까지 포함 하는 표의 만드는 셀, 워크시트와 같이 개체입니다. 각 셀을 포함 한 <xref:System.Windows.Controls.TextBlock> 데이터 및 맨 위 행을 나타내는 요소에 포함 되어는 <xref:System.Windows.Controls.TextBlock> 와 <xref:System.Windows.Controls.Grid.ColumnSpan%2A> 적용 속성입니다. 각 셀의 경계를 표시 하는 <xref:System.Windows.Controls.Grid.ShowGridLines%2A> 속성을 사용할 수 있습니다.  
  
 [!code-csharp[Grid#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xaml[Grid#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.Grid>  
 [패널 개요](../../../../docs/framework/wpf/controls/panels-overview.md)
