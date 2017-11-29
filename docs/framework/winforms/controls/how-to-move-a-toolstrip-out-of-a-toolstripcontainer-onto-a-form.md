---
title: "방법: ToolStripContainer의 ToolStrip을 폼으로 이동"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStrip control [Windows Forms], parenting to forms
- Windows Forms, parenting ToolStrip controls
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 02d1e4b105329f3d346168123debbbf73e17b9eb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>방법: ToolStripContainer의 ToolStrip을 폼으로 이동
이동 하려면 다음 절차를 사용 하 여 한 <xref:System.Windows.Forms.ToolStrip> 부재 중는 <xref:System.Windows.Forms.ToolStripContainer> 폼으로 합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>ToolStrip을 폼으로 ToolStripContainer 외부로 이동 하려면  
  
1.  <xref:System.Windows.Forms.ToolStrip>를 선택합니다.  
  
2.  잘라내기는 <xref:System.Windows.Forms.ToolStrip> 에서 CTRL + X 키를 누르거나 마우스 오른쪽 단추로 클릭는 <xref:System.Windows.Forms.ToolStrip> 선택 **잘라내기** 상황에 맞는 메뉴입니다.  
  
3.  폼을 선택 합니다.  
  
4.  붙여넣기는 <xref:System.Windows.Forms.ToolStrip> 에서 CTRL + V를 누르거나 선택 **붙여넣기** 에서 **편집** 메뉴.  
  
5.  설정의 <xref:System.Windows.Forms.ToolStrip.Dock%2A> 속성은 <xref:System.Windows.Forms.ToolStrip> 를 **Top**합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripContainer>  
 [ToolStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
