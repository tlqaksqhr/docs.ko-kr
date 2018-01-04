---
title: "방법: 글꼴 메트릭 얻기"
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
helpviewer_keywords:
- fonts [Windows Forms], obtaining metrics
- font metrics [Windows Forms], obtaining
ms.assetid: ff7c0616-67f7-4fa2-84ee-b8d642f2b09b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 16f1126cc75b75ae98298f5d1c58c78ff30edbb6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-obtain-font-metrics"></a>방법: 글꼴 메트릭 얻기
<xref:System.Drawing.FontFamily> 클래스는 특정 제품군/스타일 조합에 대 한 다양 한 메트릭을 검색 하는 다음 메서드를 제공 합니다.  
  
-   <xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)  
  
-   <xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)  
  
-   <xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)  
  
-   <xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)  
  
 크기 및 특정 단위에 종속 되므로 이러한 메서드에 의해 반환 된 숫자는 글꼴 디자인 단위로 <xref:System.Drawing.Font> 개체입니다.  
  
 다음 그림에서는 다양 한 메트릭을 보여 줍니다.  
  
 ![글꼴 텍스트](../../../../docs/framework/winforms/advanced/media/fontstext7a.png "fontstext7A")  
  
## <a name="example"></a>예  
 다음 예제에서는 Arial 글꼴 패밀리의 일반 스타일에 대 한 메트릭을 표시합니다. 코드는 또한 만듭니다는 <xref:System.Drawing.Font> 16 픽셀 크기 및 표시 해당 특정 픽셀 단위로 메트릭 포함 된 개체 (Arial 제품군에 기반) <xref:System.Drawing.Font> 개체입니다.  
  
 다음 그림에서는 예제 코드의 출력을 보여 줍니다.  
  
 ![글꼴 텍스트](../../../../docs/framework/winforms/advanced/media/csfontstext8.png "csFontsText8")  
  
 앞의 그림에는 출력의 처음 두 줄 note 합니다. <xref:System.Drawing.Font> 16의 크기를 반환 하는 개체 및 <xref:System.Drawing.FontFamily> 2, 048는 em 높이 반환 하는 개체입니다. 이러한 두 값 (16과 2, 048)은 글꼴 디자인 단위로 단위 (이 예제의 경우 픽셀)의 간에 변환 하는 <xref:System.Drawing.Font> 개체입니다.  
  
 예를 들어 변환할 수 있습니다 경사가 디자인 단위에서 픽셀 다음과 같습니다.  
  
 ![글꼴 텍스트](../../../../docs/framework/winforms/advanced/media/fontstext9.png "FontsText9")  
  
 다음 코드 텍스트를 세로로 배치 설정 하 여는 <xref:System.Drawing.PointF.Y%2A> 의 데이터 멤버는 <xref:System.Drawing.PointF> 개체입니다. 에 대 한 y-좌표 만큼 증가 `font.Height` 텍스트의 각 새 줄에 대 한 합니다. <xref:System.Drawing.Font.Height%2A> 속성은 <xref:System.Drawing.Font> 해당 특정의 줄 간격 (픽셀 단위)를 반환 하는 개체 <xref:System.Drawing.Font> 개체입니다. 이 예제에서 반환 된 수 <xref:System.Drawing.Font.Height%2A> 은 19입니다. 줄 간격 메트릭을를 픽셀로 변환 하 여 얻은 (정수로 반올림) क 이것이 note 합니다.  
  
 Em 높이 (크기 또는 em 크기 라고도 함)는 기준선 위와 총 아닌지 note 합니다. 위와 경사가 합계 셀 높이 라고 합니다. 내부 여백 뺀 셀 높이 em 높이 같습니다. 셀 높이 및 외부 앞에 오는 줄 간격 같습니다.  
  
 [!code-csharp[System.Drawing.FontsAndText#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [글꼴 및 텍스트 사용](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
