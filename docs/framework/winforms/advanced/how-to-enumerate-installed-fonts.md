---
title: '방법: 설치된 글꼴 열거'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
ms.openlocfilehash: 9f31880cbfb42c03122fc7d2730b9ca89db49226
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enumerate-installed-fonts"></a>방법: 설치된 글꼴 열거
<xref:System.Drawing.Text.InstalledFontCollection> 클래스에서 상속 된 <xref:System.Drawing.Text.FontCollection> 추상 기본 클래스입니다. 사용할 수는 <xref:System.Drawing.Text.InstalledFontCollection> 컴퓨터에 설치 된 글꼴 열거 하는 개체입니다. <xref:System.Drawing.Text.FontCollection.Families%2A> 속성은 <xref:System.Drawing.Text.InstalledFontCollection> 개체의 배열이 <xref:System.Drawing.FontFamily> 개체입니다.  
  
## <a name="example"></a>예제  
 다음 예제에는 컴퓨터에 설치 된 모든 글꼴 패밀리의 이름을 나열 합니다. 코드 검색은 <xref:System.Drawing.FontFamily.Name%2A> 각 속성 <xref:System.Drawing.FontFamily> 에서 반환 된 배열에 있는 개체는 <xref:System.Drawing.Text.FontCollection.Families%2A> 속성입니다. 패밀리 이름을 검색 하는 쉼표로 구분 된 형식 목록에 연결 합니다. 그런 다음 <xref:System.Drawing.Graphics.DrawString%2A> 의 메서드는 <xref:System.Drawing.Graphics> 클래스 사각형에 쉼표로 구분 된 목록을 그립니다.  
  
 예제 코드를 실행 하는 경우 출력 다음 그림에 표시 된 것과 비슷한 됩니다.  
  
 ![설치 된 글꼴](../../../../docs/framework/winforms/advanced/media/csfontstext6.png "csfontstext6")  
  
 [!code-csharp[System.Drawing.FontsAndText#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다. 또한 가져오는 것이 고 <xref:System.Drawing.Text> 네임 스페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [글꼴 및 텍스트 사용](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
