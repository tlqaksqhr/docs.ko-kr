---
title: '방법: Windows Forms BindingSource를 사용하여 항목 추가 사용자 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], creating new items
- BindingSource component [Windows Forms], customizing item addition with
- examples [Windows Forms], BindingSource component
- BindingSource component [Windows Forms], examples
ms.assetid: 1aae11fc-6fb2-4cb9-b3d0-e0638fe77ef0
ms.openlocfilehash: 299b24eb42c576535389f53982581bf4a776ee3d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-customize-item-addition-with-the-windows-forms-bindingsource"></a>방법: Windows Forms BindingSource를 사용하여 항목 추가 사용자 지정
<xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 Windows Forms 컨트롤을 데이터 소스에 바인딩하는 경우 새 항목의 생성을 사용자 지정해야 할 수도 있습니다. <xref:System.Windows.Forms.BindingSource> 구성 요소는 일반적으로 바인딩된 컨트롤이 새 항목을 만들어야 할 때 발생하는 <xref:System.Windows.Forms.BindingSource.AddingNew> 이벤트를 제공하여 이 작업을 간소화합니다. 이벤트 처리기에서 필요한 사용자 지정 동작(예: 웹 서비스에 대해 메서드 호출 또는 클래스 팩터리에서 새 개체 가져오기)을 제공할 수 있습니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.BindingSource.AddingNew> 이벤트를 처리하여 항목을 추가하는 경우 추가 작업을 취소할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Forms.DataGridView> 구성 요소를 사용하여 <xref:System.Windows.Forms.BindingSource> 컨트롤을 클래스 팩터리에 바인딩하는 방법을 보여 줍니다. 사용자가 <xref:System.Windows.Forms.DataGridView> 컨트롤의 새 행을 클릭하면 <xref:System.Windows.Forms.BindingSource.AddingNew> 이벤트가 발생합니다. 이벤트 처리기에서 `DemoCustomer` 개체를 새로 만들고 <xref:System.ComponentModel.AddingNewEventArgs.NewObject%2A?displayProperty=nameWithType> 속성에 개체가 할당됩니다. 그러면 새 `DemoCustomer` 개체가 <xref:System.Windows.Forms.BindingSource> 구성 요소의 목록에 추가되고 <xref:System.Windows.Forms.DataGridView> 컨트롤의 새 행에 표시됩니다.  
  
 [!code-cpp[System.Windows.Forms.DataConnector.AddingNew#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.AddingNew#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.AddingNew#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다. 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.  [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [BindingSource 구성 요소](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [방법: 형식에 Windows Forms 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
