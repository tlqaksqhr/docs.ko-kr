---
title: '방법: Windows Forms DataGridView 컨트롤의 단추 열에서 단추 비활성화'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], disabling buttons
- buttons [Windows Forms], disabling in button columns
- DataGridView control [Windows Forms], disabling button cells
ms.assetid: 5c344d01-013a-4a6b-8f8d-62ec9321d81e
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4511441e3d8350cd867133a87f34fcba3087f796
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-disable-buttons-in-a-button-column-in-the-windows-forms-datagridview-control"></a>방법: Windows Forms DataGridView 컨트롤의 단추 열에서 단추 비활성화
<xref:System.Windows.Forms.DataGridView> 컨트롤에는 단추처럼 UI(사용자 인터페이스)가 있는 셀을 표시하기 위한 <xref:System.Windows.Forms.DataGridViewButtonCell> 클래스가 포함됩니다. 그러나 <xref:System.Windows.Forms.DataGridViewButtonCell>은 셀에서 표시될 수 있는 단추의 모양을 비활성화하는 방법을 제공하지 않습니다.  
  
 다음 코드 예제에서는 비활성화된 것으로 나타날 수 있는 단추를 표시하도록 <xref:System.Windows.Forms.DataGridViewButtonCell> 클래스를 사용자 지정하는 방법을 보여 줍니다. 다음 예제에서는 <xref:System.Windows.Forms.DataGridViewButtonCell>에서 파생되는 새로운 셀 형식 `DataGridViewDisableButtonCell`을 정의합니다. 이 셀 형식은 셀에 비활성화된 단추를 그리기 위해 `false`로 설정할 수 있는 새로운 `Enabled` 속성을 제공합니다. 예제에서는 `DataGridViewDisableButtonCell` 개체를 표시하는 새로운 열 형식 `DataGridViewDisableButtonColumn`도 정의합니다. 이 새로운 셀 및 열 형식을 보여 주기 위해 부모 <xref:System.Windows.Forms.DataGridView>에 있는 각 <xref:System.Windows.Forms.DataGridViewCheckBoxCell>의 현재 값에 따라 동일한 행의 `DataGridViewDisableButtonCell`에 대한 `Enabled` 속성이 `true` 또는 `false`인지가 결정됩니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridViewCell> 또는 <xref:System.Windows.Forms.DataGridViewColumn>에서 파생시키고 파생 클래스에 새 속성을 추가하는 경우 복제 작업 중 새 속성을 복사하도록 `Clone` 메서드를 재정의해야 합니다. 또한 기본 클래스의 속성이 새로운 셀 또는 열에 복사되도록 기본 클래스의 `Clone` 메서드를 호출해야 합니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[System.Windows.Forms.DataGridView.DisabledButtons#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.DisabledButtons#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System, System.Drawing, System.Windows.Forms 및 System.Windows.Forms.VisualStyles 어셈블리에 대한 참조  
  
 Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다. 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.  [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms DataGridView 컨트롤 사용자 지정](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 [DataGridView 컨트롤 아키텍처](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 [Windows Forms DataGridView 컨트롤의 열 형식](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
