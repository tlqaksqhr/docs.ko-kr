---
title: '방법: 그린 텍스트에 탭 정지 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
ms.openlocfilehash: e7f3fe9757db26bcc9dc9735f3d3d854edb7c099
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523639"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a>방법: 그린 텍스트에 탭 정지 설정
호출 하 여 텍스트에 대 한 탭 정지를 설정할 수 있습니다는 <xref:System.Drawing.StringFormat.SetTabStops%2A> 메서드는 <xref:System.Drawing.StringFormat> 개체와 전달 하는 <xref:System.Drawing.StringFormat> 개체는 <xref:System.Drawing.Graphics.DrawString%2A> 의 메서드는 <xref:System.Drawing.Graphics> 클래스.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> 기존 탭을 확장할 수 있지만 그린된 텍스트에 탭 정지를 추가 하는 지원 하지 정지를 사용 하는 <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> 플래그입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 150, 250 및 350 탭 정지 설정 합니다. 그런 다음 코드는 이름과 테스트 점수의 탭된 목록을 표시합니다.  
  
 다음은 탭으로 이동한 텍스트입니다.  
  
 ![글꼴 텍스트](../../../../docs/framework/winforms/advanced/media/fontstext4.png "fontstext4")  
  
 다음 코드는 두 개의 인수를 전달 된 <xref:System.Drawing.StringFormat.SetTabStops%2A> 메서드. 두 번째 인수가 탭 오프셋을 포함 하는 배열입니다. 첫 번째 인수에 전달 된 <xref:System.Drawing.StringFormat.SetTabStops%2A> 은 0이 배열의 첫 번째 오프셋 위치 0는 경계 사각형의 왼쪽된 가장자리에서에서 측정 됩니다 나타냅니다.  
  
 [!code-csharp[System.Drawing.FontsAndText#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
  
-   앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.  
  
## <a name="see-also"></a>참고 항목  
 [글꼴 및 텍스트 사용](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [방법: GDI를 사용하여 텍스트 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
