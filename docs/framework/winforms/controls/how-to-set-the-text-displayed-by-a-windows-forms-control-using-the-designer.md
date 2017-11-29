---
title: "방법: 디자이너를 사용하여 Windows Forms 컨트롤에 표시되는 텍스트 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], setting caption
- Windows Forms, setting the text displayed
ms.assetid: 9d18e0e0-f17f-4074-837d-e67ceeeaa89d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 59d66df2c6f18ad28ad4b912c00e35f786d773da
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms 컨트롤에 표시되는 텍스트 설정
Windows Forms 컨트롤에는 일반적으로 컨트롤의 기본 기능은 관련 된 일부 텍스트가 표시 됩니다. 예를 들어 한 <xref:System.Windows.Forms.Button> 컨트롤은 일반적으로 단추를 클릭할 때 어떤 작업을 수행할지 여부를 나타내는 캡션을 표시 합니다. 모든 컨트롤에 대해 <xref:System.Windows.Forms.Control.Text%2A> 속성을 사용하여 텍스트를 설정하거나 반환할 수 있습니다. <xref:System.Windows.Forms.Control.Font%2A> 속성을 사용하여 글꼴을 변경할 수 있습니다.  
  
### <a name="to-set-the-text-and-font-with-the-designer"></a>디자이너와 글꼴 및 텍스트를 설정 하려면  
  
1.  속성 창에서 설정 된 <xref:System.Windows.Forms.Control.Text%2A> 적절 한 문자열을 컨트롤의 속성입니다.  
  
     밑줄된 바로 가기 키를 만들려면 앰퍼샌드가 포함 (&) 문자 바로 가기 키가 될를 합니다.  
  
2.  속성 창에서 줄임표 단추를 클릭 합니다. (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 옆에 <xref:System.Windows.Forms.Control.Font%2A> 속성입니다.  
  
     표준 글꼴 대화 상자, 글꼴, 글꼴 스타일, 크기, 부작용 (예: 취소선 또는 밑줄) 및 스크립트를 선택 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [글꼴 및 텍스트 사용](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
