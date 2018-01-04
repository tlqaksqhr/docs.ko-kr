---
title: "방법: ContextMenuStrip과 컨트롤 연결"
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
- context menus [Windows Forms], relating
- ContextMenuStrips [Windows Forms], associating with controls
- context menus [Windows Forms], associating with controls
- ContextMenuStrips [Windows Forms], relating
ms.assetid: 6fc40a42-5d69-427f-aa30-0a146193226b
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7307af535dce39443b623e1fee4491dd48ffbd94
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-associate-a-contextmenustrip-with-a-control"></a>방법: ContextMenuStrip과 컨트롤 연결
컨트롤 및 바로 가기 메뉴를 만든 후 다음 절차를 따라 사용자가 컨트롤을 마우스 오른쪽 단추로 클릭할 때 지정된 바로 가기 메뉴를 표시합니다. 이러한 절차에서는 <xref:System.Windows.Forms.ContextMenuStrip>을 Windows Form 및 <xref:System.Windows.Forms.ToolStrip> 컨트롤과 연결합니다.  
  
### <a name="to-associate-a-contextmenustrip-with-a-windows-form"></a>ContextMenuStrip을 Windows Form과 연결하려면  
  
1.  <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 속성을 연결된 <xref:System.Windows.Forms.ContextMenuStrip>의 이름으로 설정합니다.  
  
### <a name="to-associate-a-contextmenustrip-with-a-toolstrip-control"></a>ContextMenuStrip을 ToolStrip 컨트롤과 연결하려면  
  
1.  컨트롤의 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 속성을 연결된 <xref:System.Windows.Forms.ContextMenuStrip>의 이름으로 설정합니다.  
  
## <a name="example"></a>예  
 다음 코드 예제에서는 Windows Form 및 <xref:System.Windows.Forms.ToolStrip>을 만들고 다른 <xref:System.Windows.Forms.ContextMenuStrip> 컨트롤을 각각에 연결합니다.  
  
 [!code-csharp[System.Windows.Forms.ContextMenuStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ContextMenuStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]의 명령줄에서 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요. [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.  [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>  
 <xref:System.Windows.Forms.ToolStrip>  
 [방법: ContextMenuStrip에 메뉴 항목 추가](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md)  
 [ContextMenuStrip 컨트롤](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)
