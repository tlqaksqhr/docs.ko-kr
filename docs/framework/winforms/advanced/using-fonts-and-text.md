---
title: "글꼴 및 텍스트 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing in Windows Forms
- examples [Windows Forms], fonts and text
- fonts [Windows Forms], using in Windows Forms
- strings [Windows Forms], drawing in Windows Forms
ms.assetid: d43640f3-da94-4df2-a29d-a9d021a1c069
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f4febeed6aff2c18b5040020c2c1d3ee6cf59a52
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="using-fonts-and-text"></a>글꼴 및 텍스트 사용
제공 하는 몇 가지 클래스는 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 및 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] Windows Forms의 텍스트를 그리기 위한 합니다. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> 클래스에 여러 개의 <xref:System.Drawing.Graphics.DrawString%2A> 텍스트, 위치, 사각형, 글꼴 및 서식을 경계 등의 다양 한 기능을 지정할 수 있도록 하는 메서드. 그릴 텍스트를 측정 하는 또한 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 정적을 사용 하 여 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 및 <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> 방법에서 제공 되는 `TextRenderer` 클래스입니다. [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 메서드 통해서도 위치, 글꼴 및 서식을 지정할 수 있습니다. 그러나 하나를 선택할 수 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 또는 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 텍스트 렌더링에 대 한 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 제안을 향상 된 성능과 더 정확한 텍스트 측정 일반적으로 합니다. 텍스트 렌더링에 영향을 주는 다른 클래스에는 `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, 및 `TextFormatFlags`합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: 글꼴 패밀리 및 글꼴 만들기](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 만드는 방법을 보여 줍니다 `Font` 및 `FontFamily` 개체입니다.  
  
 [방법: 지정된 위치에 텍스트 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)  
 에 특정 위치를 사용 하 여 텍스트를 그리는 방법을 설명 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 및 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]합니다.  
  
 [방법: 사각형 안에 줄 바꿈된 텍스트 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)  
 사용 하 여 사각형의 텍스트를 그리는 방법을 설명 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 및 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]합니다.  
  
 [방법: GDI를 사용하여 텍스트 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 사용 하는 방법을 보여 줍니다. [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 텍스트를 그리기 위한 합니다.  
  
 [방법: 그린 텍스트 맞추기](../../../../docs/framework/winforms/advanced/how-to-align-drawn-text.md)  
 서식을 지정 하는 방법을 보여 줍니다. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 및 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 텍스트입니다.  
  
 [방법: 세로 텍스트 만들기](../../../../docs/framework/winforms/advanced/how-to-create-vertical-text.md)  
 세로로 정렬 된 텍스트를 그릴 하는 방법을 설명 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]합니다.  
  
 [방법: 그린 텍스트에 탭 정지 설정](../../../../docs/framework/winforms/advanced/how-to-set-tab-stops-in-drawn-text.md)  
 텍스트와 탭 정지를 그리는 방법을 보여 줍니다 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]합니다.  
  
 [방법: 설치된 글꼴 열거](../../../../docs/framework/winforms/advanced/how-to-enumerate-installed-fonts.md)  
 설치 된 글꼴의 이름을 나열 하는 방법에 설명 합니다.  
  
 [방법: 개인 글꼴 컬렉션 만들기](../../../../docs/framework/winforms/advanced/how-to-create-a-private-font-collection.md)  
 만드는 방법에 설명 된 <xref:System.Drawing.Text.PrivateFontCollection> 개체입니다.  
  
 [방법: 글꼴 메트릭 얻기](../../../../docs/framework/winforms/advanced/how-to-obtain-font-metrics.md)  
 셀 상승 하강 등 글꼴 메트릭 얻기 하는 방법을 보여 줍니다.  
  
 [방법: 텍스트에 앤티 앨리어싱 사용](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)  
 텍스트를 그릴 때 앤티 앨리어싱 사용 하는 방법에 설명 합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Drawing.Font>  
 이 클래스를 설명 하 고 모든 해당 멤버의 링크를 포함 합니다.  
  
 <xref:System.Drawing.FontFamily>  
 이 클래스를 설명 하 고 모든 해당 멤버의 링크를 포함 합니다.  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 이 클래스를 설명 하 고 모든 해당 멤버의 링크를 포함 합니다.  
  
 <xref:System.Windows.Forms.TextRenderer>  
 이 클래스를 설명 하 고 모든 해당 멤버의 링크를 포함 합니다.  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 이 클래스를 설명 하 고 모든 해당 멤버의 링크를 포함 합니다.
