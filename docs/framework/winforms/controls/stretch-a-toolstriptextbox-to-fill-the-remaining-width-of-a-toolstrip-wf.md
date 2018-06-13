---
title: '방법: ToolStripTextBox를 늘려 ToolStrip의 나머지 너비 채우기(Windows Forms)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: bd58cbd109b8e3dd04c6a284dc6926e95830fb61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537722"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a>방법: ToolStripTextBox를 늘려 ToolStrip의 나머지 너비 채우기(Windows Forms)
설정 하는 경우는 <xref:System.Windows.Forms.ToolStrip.Stretch%2A> 속성의는 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 `true`, 해당 컨테이너를 끝까지 채웁니다 컨트롤과 해당 컨테이너 크기를 조정할 때의 크기를 조정 합니다. 이 구성에서는 하면 유용할 수와 같은 컨트롤에서 항목을 스트레치 하는 <xref:System.Windows.Forms.ToolStripTextBox>, 사용 가능한 공간 및 컨트롤 크기를 조정할 때의 크기를 조정 합니다. 이러한 늘이기, 예를 들어 경우 유용 모양 및 동작 Microsoft® Internet Explorer의 주소 표시줄 유사 합니다.  
  
## <a name="example"></a>예제  
 파생 된 클래스를 제공 하는 다음 코드 예제에서는 <xref:System.Windows.Forms.ToolStripTextBox> 호출 `ToolStripSpringTextBox`합니다. 이 클래스는 재정의 <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> 부모의 사용 가능한 너비를 계산 하는 메서드 <xref:System.Windows.Forms.ToolStrip> 후 다른 모든 항목의 결합 된 너비를 뺀 값을 제어 합니다. 이 코드 예제도 제공 합니다. 한 <xref:System.Windows.Forms.Form> 클래스 및 `Program` 클래스 새 동작을 보여 줍니다.  
  
 [!code-csharp[ToolStripSpringTextBox#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripTextBox>  
 <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>  
 [ToolStrip 컨트롤 아키텍처](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [방법: StatusStrip에서 대화형으로 Spring 속성 사용](../../../../docs/framework/winforms/controls/how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
