---
title: "방법: Windows Forms DataGridView 셀에서 컨트롤 호스팅"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], hosting in cells
- DataGridView control [Windows Forms], hosting controls in cells
- cells [Windows Forms], hosting controls
ms.assetid: e79a9d4e-64ec-41f5-93ec-f5492633cbb2
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dbd315b5980c0aed222c9576632064ea9f7b2ce1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-host-controls-in-windows-forms-datagridview-cells"></a>방법: Windows Forms DataGridView 셀에서 컨트롤 호스팅
<xref:System.Windows.Forms.DataGridView> 컨트롤은 사용자가 다양한 방법으로 값을 입력하고 편집할 수 있도록 하는 여러 가지 열 형식을 제공합니다. 그러나 이들 열 형식이 데이터 입력 요구 사항에 맞지 않으면 선택한 컨트롤을 호스트하는 셀을 사용하여 고유한 열 형식을 만들 수 있습니다. 이 작업을 하려면 <xref:System.Windows.Forms.DataGridViewColumn> 및 <xref:System.Windows.Forms.DataGridViewCell>에서 파생된 클래스를 정의해야 합니다. <xref:System.Windows.Forms.Control>에서 파생되고 <xref:System.Windows.Forms.IDataGridViewEditingControl> 인터페이스를 구현하는 클래스도 정의해야 합니다.  
  
 다음 코드 예제에서는 달력 열을 만드는 방법을 보여 줍니다. 이 열의 셀에는 날짜가 일반 텍스트 상자 셀로 표시되지만 사용자가 셀을 편집할 때 <xref:System.Windows.Forms.DateTimePicker> 컨트롤이 표시됩니다. 텍스트 상자 표시 기능을 다시 구현하지 않아도 되도록, <xref:System.Windows.Forms.DataGridViewCell> 클래스를 직접 상속하는 것이 아니라 `CalendarCell` 클래스가 <xref:System.Windows.Forms.DataGridViewTextBoxCell> 클래스에서 파생됩니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridViewCell> 또는 <xref:System.Windows.Forms.DataGridViewColumn>에서 파생시키고 파생 클래스에 새 속성을 추가하는 경우 복제 작업 중 새 속성을 복사하도록 `Clone` 메서드를 재정의해야 합니다. 또한 기본 클래스의 속성이 새로운 셀 또는 열에 복사되도록 기본 클래스의 `Clone` 메서드를 호출해야 합니다.  
  
## <a name="example"></a>예  
 [!code-csharp[System.Windows.Forms.DataGridViewCalendarColumn#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/CS/datagridviewcalendarcolumn.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewCalendarColumn#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/VB/datagridviewcalendarcolumn.vb#000)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 다음 예제에는 다음이 필요합니다.  
  
-   System 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]의 명령줄에서 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요. [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.  [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <xref:System.Windows.Forms.DateTimePicker>  
 [Windows Forms DataGridView 컨트롤 사용자 지정](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 [DataGridView 컨트롤 아키텍처](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 [Windows Forms DataGridView 컨트롤의 열 형식](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
