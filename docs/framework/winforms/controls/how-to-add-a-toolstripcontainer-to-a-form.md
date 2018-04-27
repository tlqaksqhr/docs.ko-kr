---
title: '방법: 폼에 ToolStripContainer 추가'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStrip control [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], adding to Windows Forms
ms.assetid: d0f55095-a833-453e-be5a-644906d75d54
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d0da8f1363a4dd1bfaa3dec9dd2a1db6e22191b3
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-add-a-toolstripcontainer-to-a-form"></a>방법: 폼에 ToolStripContainer 추가
프로그래밍 방식으로 <xref:System.Windows.Forms.ToolStripContainer>를 Windows Form에 추가하고 컨트롤로 채울 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 <xref:System.Windows.Forms.ToolStripContainer> 및 <xref:System.Windows.Forms.ToolStrip>을 Windows Forms에 추가하는 방법, 항목을 <xref:System.Windows.Forms.ToolStrip>에 추가하는 방법, <xref:System.Windows.Forms.ToolStrip>을 <xref:System.Windows.Forms.ToolStripContainer>의 <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A>에 추가하는 방법을 보여 줍니다.  
  
 [!code-csharp[System.Windows.Forms.ToolStripContainer2#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/cs/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStripContainer2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/vb/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 코드 예제에는 다음이 필요합니다.  
  
-   System.Drawing, System.Text 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다. [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.  또한 [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)) 또는 [ToolStripContainer 태스크 대화 상자](http://msdn.microsoft.com/library/ms233647\(v=vs.110\))를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ToolStripContainer>  
 [ToolStripContainer 컨트롤](../../../../docs/framework/winforms/controls/toolstripcontainer-control.md)  
 [ToolStrip 컨트롤](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
