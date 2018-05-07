---
title: '방법: Windows Forms ColorDialog 구성 요소의 모양 변경'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ColorDialog component [Windows Forms], examples
- ColorDialog component [Windows Forms], formatting appearance
- color dialog box [Windows Forms], configuring appearance
ms.assetid: bba4e262-1cd7-4f63-89cf-330a36f7b539
ms.openlocfilehash: 816850fa61de97b5f4c251571a74da7e0a70cba8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a>방법: Windows Forms ColorDialog 구성 요소의 모양 변경
Windows Forms의 모양을 구성할 수 있습니다 <xref:System.Windows.Forms.ColorDialog> 다양 한 속성이 해당 구성 요소입니다. 대화 상자에 다음 두 섹션이-기본 색을 사용자 지정 색을 정의할 수 있도록 표시 하는 합니다.  
  
 대부분의 속성 대화 상자에서 선택할 수 있는 색을 제한 합니다. 경우는 <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> 속성이로 설정 되어 `true`, 사용자가 사용자 지정 색을 정의할 수 있습니다. <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> 속성은 `true` ; 사용자 지정 색을 정의 하 여 대화 상자 확장 되 면 그렇지 않은 경우 사용자를 클릭 해야 "사용자 지정 색 만들기" 단추입니다. 경우는 <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> 속성이로 설정 되어 `true`, 대화 상자 기본 색 집합에서 사용 가능한 모든 색을 표시 합니다. 경우는 <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> 속성이 `true`, 사용자 디더링된 색을 선택할 수 없으므로 단색만 선택할 사용할 수 있습니다.  
  
 경우는 <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> 속성이 `true`, 대화 상자에 도움말 단추가 나타납니다. 사용자가 도움말 단추를 클릭 하면는 <xref:System.Windows.Forms.ColorDialog> 구성 요소의 <xref:System.Windows.Forms.CommonDialog.HelpRequest> 이벤트가 발생 합니다.  
  
### <a name="to-configure-the-appearance-of-the-color-dialog-box"></a>색 대화 상자의 모양을 구성 하려면  
  
1.  설정의 <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>, 및 <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> 속성을 원하는 값입니다.  
  
    ```vb  
    ColorDialog1.AllowFullOpen = True  
    ColorDialog1.AnyColor = True  
    ColorDialog1.SolidColorOnly = False  
    ColorDialog1.ShowHelp = True  
    ```  
  
    ```csharp  
    colorDialog1.AllowFullOpen = true;  
    colorDialog1.AnyColor = true;  
    colorDialog1.SolidColorOnly = false;  
    colorDialog1.ShowHelp = true;  
    ```  
  
    ```cpp  
    colorDialog1->AllowFullOpen = true;  
    colorDialog1->AnyColor = true;  
    colorDialog1->SolidColorOnly = false;  
    colorDialog1->ShowHelp = true;  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ColorDialog>  
 [ColorDialog 구성 요소](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)  
 [ColorDialog 구성 요소 개요](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md)
