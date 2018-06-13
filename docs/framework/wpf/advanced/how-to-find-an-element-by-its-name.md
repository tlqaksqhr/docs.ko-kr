---
title: '방법: 이름에 따라 요소 찾기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements [WPF], finding by name
ms.assetid: cfa7cf35-8aa2-4060-9454-872ed4af3f0e
ms.openlocfilehash: e2d176c9334c0a1d4c10819e0dc9f2c408e41d5d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543578"
---
# <a name="how-to-find-an-element-by-its-name"></a>방법: 이름에 따라 요소 찾기
이 예제에서는 사용 하는 방법을 설명는 <xref:System.Windows.FrameworkElement.FindName%2A> 메서드 여 요소를 해당 <xref:System.Windows.FrameworkElement.Name%2A> 값입니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 메서드 이름을 사용 하 여 특정 요소를 찾을 수 있는 단추의 이벤트 처리기로 기록 됩니다. `stackPanel` 이 <xref:System.Windows.FrameworkElement.Name%2A> 루트의 <xref:System.Windows.FrameworkElement> 검색 중인 문서를 나타내고 메서드 예제 다음 시각적으로 찾은 요소의 캐스팅 하 여 <xref:System.Windows.Controls.TextBlock> 중 하나를 변경 하 고는 <xref:System.Windows.Controls.TextBlock> 표시 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 속성.  
  
 [!code-csharp[FEFindName#Find](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFindName/CSharp/default.xaml.cs#find)]
 [!code-vb[FEFindName#Find](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FEFindName/VisualBasic/default.xaml.vb#find)]
