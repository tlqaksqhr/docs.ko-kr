---
title: "방법: Windows Forms에서 개체 계층화"
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
- cpp
helpviewer_keywords:
- Windows Forms controls, layering
- controls [Windows Forms], layering
- z order
- controls [Windows Forms], positioning
- z-order
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d956ae8fb643d616bc0e5dc514f21ca95fa50a48
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-layer-objects-on-windows-forms"></a>방법: Windows Forms에서 개체 계층화
복잡 한 사용자 인터페이스를 만들거나 여러 문서 MDI (인터페이스) 폼을 사용할 때 컨트롤과 보다 복잡 한 UI (사용자 인터페이스) 자식 폼 계층화 하려는 경우가 많습니다. 이동 하 고 컨트롤 및 windows 그룹의 컨텍스트 내에서 한 추적을 z 순서를 조작 합니다. *Z 순서* 폼의 z 축 (깊이)와 함께 폼에 컨트롤의 시각적 계층은 합니다. Z 순서 맨 아래에 있는 창에는 다른 모든 창과 겹칩니다. 다른 모든 창과 z 순서 맨 아래에 있는 창을 위에 표시 합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-layer-controls-at-design-time"></a>디자인 타임에 레이어 컨트롤에  
  
1.  레이어를 하는 컨트롤을 선택 합니다.  
  
2.  에 **형식** 메뉴에서 **순서**, 클릭 하 고 **앞으로 가져오기** 또는 **맨 뒤로 보내기**합니다.  
  
### <a name="to-layer-controls-programmatically"></a>컨트롤을 프로그래밍 방식으로 계층화  
  
-   사용 하 여 <xref:System.Windows.Forms.Control.BringToFront%2A> 및 <xref:System.Windows.Forms.Control.SendToBack%2A> 컨트롤의 z 순서를 조작 하는 메서드.  
  
     예를 들어 경우는 <xref:System.Windows.Forms.TextBox> 컨트롤 `txtFirstName`은 아래 다른 제어 및 중지할 위쪽에, 다음 코드를 사용 합니다.  
  
    ```vb  
    txtFirstName.BringToFront()  
    ```  
  
    ```csharp  
    txtFirstName.BringToFront();  
    ```  
  
    ```cpp  
    txtFirstName->BringToFront();  
    ```  
  
> [!NOTE]
>  Windows Forms에서는 *컨트롤 포함*합니다. 컨트롤 포함에서는 다양 한의 번호를 비롯 한 포함 하는 컨트롤 내에서 컨트롤 배치 <xref:System.Windows.Forms.RadioButton> 컨트롤 내는 <xref:System.Windows.Forms.GroupBox> 제어 합니다. 그런 다음 포함 하는 컨트롤 내에서 컨트롤 계층 수 있습니다. 그룹 상자를 이동 그 안에 포함 되기 때문에 컨트롤을도 이동 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/index.md)  
 [Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [기능별 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
