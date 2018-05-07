---
title: '방법: 합성 모드를 사용하여 알파 혼합 조절'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- alpha blending [Windows Forms], compositing
- colors [Windows Forms], blending
- colors [Windows Forms], controlling transparency
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
ms.openlocfilehash: 55c6db1029c6823652ac29fca46f6f8dc4ec40d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-compositing-mode-to-control-alpha-blending"></a>방법: 합성 모드를 사용하여 알파 혼합 조절
다음과 같은 특성을 가진 오프 스크린 비트맵을 만들려고 하는 경우가 있을 수 있습니다.  
  
-   색 한 알파 값으로 255 보다 작아야 합니다.  
  
-   색은 알파 혼합 비트맵을 만들면 됩니다.  
  
-   완성된 한 비트맵을 표시 하면 비트맵 색이 알파 혼합 디스플레이 장치에서 배경 색입니다.  
  
 이러한 비트맵을 만들려면 빈 생성 <xref:System.Drawing.Bitmap> 개체를 생성 한 다음는 <xref:System.Drawing.Graphics> 해당 비트맵을 기반으로 하는 개체입니다. 합성 모드 설정에서 <xref:System.Drawing.Graphics> 개체 <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 한 <xref:System.Drawing.Graphics> 기반 개체는 <xref:System.Drawing.Bitmap> 개체입니다. 코드를 사용 하 여는 <xref:System.Drawing.Graphics> 개체와 두 개의 반투명 브러시 (알파 160 =) 페인트 하는 비트맵을 합니다. 코드에는 빨간색 타원과 반투명 브러시를 사용 하 여 녹색 타원을 채웁니다. 녹색 타원 겹치는 빨간색 타원 하지만 때문에 녹색에서 빨간색 혼합 되지는 않습니다의 합성 모드는 <xref:System.Drawing.Graphics> 개체로 설정 되어 <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>합니다.  
  
 코드는 화면에 두 번 비트맵을 그립니다: 한 번 흰색 배경 기반 및 컬러 배경에 한 번입니다. 두 타원의 일부인 경우 비트맵의 픽셀 160, 알파 구성 요소가 없으므로 줄임표는 화면의 배경색 배경색과 혼합 됩니다.  
  
 다음 그림에서는 코드 예제의 출력을 보여 줍니다. Note 줄임표, 배경색과 혼합 됩니다 하지만 서로 혼합 된 되지 않습니다.  
  
 ![복사 원본](../../../../docs/framework/winforms/advanced/media/sourcecopy.png "sourcecopy")  
  
 코드 예제에서는이 문이 포함 되어 있습니다.  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 백그라운드 뿐 아니라 서로 혼합 타원을 하려는 경우 해당 문을 다음과 변경 됩니다.  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 다음 그림에서는 수정 된 코드의 출력을 보여 줍니다.  
  
 ![통해 소스](../../../../docs/framework/winforms/advanced/media/sourceover.png "sourceover")  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs>의 매개 변수인 `e`<xref:System.Windows.Forms.PaintEventHandler>가 필요합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Color.FromArgb%2A>  
 [선 및 채우기 알파 혼합](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)
