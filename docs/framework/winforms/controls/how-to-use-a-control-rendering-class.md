---
title: '방법: 컨트롤 렌더링 클래스 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- professional appearance [Windows Forms], rendering Windows Forms controls
- visual themes [Windows Forms], applying to Windows Forms controls
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: c0125e34-cd74-4c35-818c-3e40f462b0a3
ms.openlocfilehash: e5b82c3317d2d162fbd5a182166a9e0061fd770e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534107"
---
# <a name="how-to-use-a-control-rendering-class"></a>방법: 컨트롤 렌더링 클래스 사용
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Forms.ComboBoxRenderer> 드롭 다운 화살표는 콤보 상자 컨트롤을 렌더링 하는 클래스입니다. 이 예제에서는 이루어져는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드는 간단한 사용자 지정 컨트롤입니다. <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> 속성은 응용 프로그램 창의 클라이언트 영역에서 비주얼 스타일을 사용 하는지 여부를 결정 하는 데 사용 합니다. 비주얼 스타일은 활성 상태인 경우 하면 <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> 메서드는 비주얼 스타일; 있는 드롭다운 화살표를 렌더링 하는 그렇지 않은 경우는 <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> 메서드는 기본 Windows 스타일에 있는 드롭다운 화살표를 렌더링 합니다.  
  
## <a name="example"></a>예제  
 [!code-cpp[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/cpp/form1.cpp#10)]
 [!code-csharp[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   파생 되는 사용자 지정 컨트롤은 <xref:System.Windows.Forms.Control> 클래스입니다.  
  
-   A <xref:System.Windows.Forms.Form> 사용자 지정 컨트롤을 호스팅하는 합니다.  
  
-   에 대 한 참조는 <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, 및 <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> 네임 스페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [비주얼 스타일을 사용하여 컨트롤 렌더링](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)
