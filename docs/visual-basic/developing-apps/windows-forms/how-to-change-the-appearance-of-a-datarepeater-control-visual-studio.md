---
title: "방법: DataRepeater 컨트롤의 모양 변경(Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, customizing
- DataRepeater, changing run time appearance
ms.assetid: 2af6dfce-760b-489e-b863-8da967f315c3
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 585ff4c942185f3199fe6e9e47a4ebd9f1f0a478
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-appearance-of-a-datarepeater-control-visual-studio"></a>방법: DataRepeater 컨트롤의 모양 변경(Visual Studio)
모양을 변경할 수 있습니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 속성을 설정 하 여 디자인 타임 또는 런타임에 처리 하 여 컨트롤의 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> 이벤트입니다.  
  
 컨트롤의 항목 템플릿 섹션을 선택한 경우 디자인 타임에 설정 된 속성 각각에 대해 반복 됩니다 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> 런타임 시. 모양 관련 속성의는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 런타임 시 컨테이너의 일부 경우에만 남아 처리 되지 않는 컨트롤 자체는 표시 됩니다 (경우에 예를 들어는 <xref:System.Windows.Forms.Control.Padding%2A> 속성은 큰 값으로).  
  
 런타임 시 모양 관련 속성 수 수 조건에 따라 설정할 합니다. 예를 들어 예약 응용 프로그램에서 사용자에 게 경고할 항목 지연 되는 항목의 배경색을 변경할 수 있습니다. 에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> 이벤트 처리기와 같은 조건문에서 속성을 설정 하는 경우 `If…Then`도 사용 해야는 `Else` 절 조건에 맞지 않을 때 모양을 지정할 수 있습니다.  
  
### <a name="to-change-the-appearance-at-design-time"></a>디자인 타임에 모양을 변경 하려면  
  
1.  Windows Forms 디자이너에서의 항목 템플릿 (위쪽) 영역을 선택는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다.  
  
2.  속성 창에서 속성을 선택 하 고 값을 변경 합니다. 모양에 영향을 주는 공용 속성 포함 <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Panel.BorderStyle%2A>, 및 <xref:System.Windows.Forms.Control.ForeColor%2A>합니다.  
  
### <a name="to-change-the-appearance-at-run-time"></a>런타임 시 모양을 변경 하려면  
  
1.  코드 편집기의 이벤트 드롭다운 목록에서 **DrawItem**을 클릭합니다.  
  
2.  에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> 이벤트 처리기 속성을 설정 하는 코드를 추가 합니다.  
  
     [!code-csharp[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.vb)]  
  
## <a name="example"></a>예제  
 에 대 한 몇 가지 일반적인 사용자 지정의 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 다른 색 및 조건에 따라 필드의 색 변경 행을 표시 하는 컨트롤 포함 합니다. 다음 예제에서는 이러한 사용자 지정을 수행 하는 방법을 보여 줍니다. 이 예에서는 있다고 가정는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Northwind 데이터베이스의 Products 테이블에 바인딩되는 컨트롤입니다.  
  
 [!code-vb[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.vb)]
 [!code-csharp[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.cs)]  
  
 참고 모두 이러한 사용자 지정에 대 한 조건의 양쪽 모두에 대 한 속성을 설정 하는 코드를 제공 해야 합니다. 지정 하지 않는 경우는 `Else` 조건, 실행 시 예기치 않은 결과가 표시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>  
 [DataRepeater 컨트롤 소개](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [DataRepeater 컨트롤 문제 해결](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [방법: DataRepeater 컨트롤의 바인딩된 데이터 표시](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [방법: DataRepeater 컨트롤의 바인딩되지 않은 컨트롤 표시](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [방법: DataRepeater 컨트롤의 항목 머리글 표시](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)
