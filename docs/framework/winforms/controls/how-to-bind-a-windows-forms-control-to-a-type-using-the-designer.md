---
title: "방법: 디자이너를 사용하여 형식에 Windows Forms 컨트롤 바인딩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a25b0dc81a6511698394eb86343f09051befc87f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a>방법: 디자이너를 사용하여 형식에 Windows Forms 컨트롤 바인딩
데이터와 상호 작용하는 컨트롤을 빌드하는 경우 때로는 개체가 아니라 형식에 컨트롤을 바인딩해야 합니다. 데이터를 사용할 수 없지만 데이터 바인딩된 컨트롤에서 형식의 공용 인터페이스에서 가져온 데이터를 표시하려는 경우 일반적으로 디자인 타임에 컨트롤을 형식에 바인딩해야 합니다. 다음 절차에는 새 하는 방법을 보여 <xref:System.Windows.Forms.BindingSource> 즉, 형식에 바인딩된 한 다음에 형식의 속성 중 하나를 바인딩하는 방법에는 <xref:System.Windows.Forms.TextBox.Text%2A> 속성은 <xref:System.Windows.Forms.TextBox>합니다.  
  
### <a name="to-bind-the-bindingsource-to-a-type"></a>BindingSource를 형식에 바인딩하려면  
  
1.  Windows Forms 프로젝트를 만듭니다.  
  
     자세한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)을 참조하세요.  
  
2.  **디자인** 보기, 끌어는 <xref:System.Windows.Forms.BindingSource> 폼 구성 요소입니다.  
  
3.  에 **속성** 창에 대 한 화살표를 클릭는 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 속성입니다.  
  
4.  **DataSource UI 형식 편집기**에서 **프로젝트 데이터 소스 추가**를 클릭합니다.  
  
5.  **데이터 소스 형식 선택** 페이지에서 **개체**를 선택하고 **다음**을 클릭합니다.  
  
6.  바인딩할 형식을 선택합니다.  
  
    -   바인딩하려는 형식이 현재 프로젝트에 있거나 형식을 포함한 어셈블리가 이미 참조로 추가된 경우 노드를 확장하여 원하는 형식을 찾은 다음 선택합니다.  
  
         또는  
  
    -   바인딩하려는 형식이 현재 참조 목록에 있지 않고 다른 어셈블리에 있는 경우 **참조 추가**를 클릭한 다음 **프로젝트** 탭을 클릭합니다. 원하는 비즈니스 개체를 포함하는 프로젝트를 선택하고 **확인**을 클릭합니다. 이 프로젝트는 어셈블리 목록에 표시됩니다. 따라서 노드를 확장하여 원하는 형식을 찾은 다음 선택할 수 있습니다.  
  
        > [!NOTE]
        >  프레임워크 또는 Microsoft 어셈블리에 있는 형식에 바인딩하려는 경우 **Microsoft 또는 시스템을 시작하는 어셈블리 숨기기** 확인란의 선택을 취소합니다.  
  
7.  **다음**을 클릭한 다음 **마침**을 클릭합니다.  
  
### <a name="to-bind-the-control-to-the-bindingsource"></a>BindingSource에 컨트롤을 바인딩하려면  
  
1.  폼에 <xref:System.Windows.Forms.TextBox>를 추가합니다.  
  
2.  **속성** 창에서 **(DataBindings)** 노드를 확장합니다.  
  
3.  옆에 있는 화살표를 클릭는 <xref:System.Windows.Forms.TextBox.Text%2A> 속성입니다.  
  
4.  에 **DataSource UI 형식 편집기**, 노드를 확장 하 고는 <xref:System.Windows.Forms.BindingSource> 에 바인딩할 바인딩된 형식의 속성을 선택 하 고 이전에 추가 <xref:System.Windows.Forms.TextBox.Text%2A> 의 속성은 <xref:System.Windows.Forms.TextBox>합니다.  
  
## <a name="see-also"></a>참고 항목  
 [BindingSource 구성 요소](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [방법: 형식에 Windows Forms 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)  
 [Visual Studio에서 데이터에 컨트롤 바인딩](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
