---
title: "방법: 안쪽 여백을 사용하여 Windows Forms 컨트롤 주위에 테두리 만들기"
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
- margins
- controls [Windows Forms], Margin property
- padding [Windows Forms], Windows Forms
- controls [Windows Forms], Padding property
- controls [Windows Forms], outlining
- Padding property [Windows Forms]
- margins [Windows Forms], Windows Forms
- Margin property [Windows Forms]
ms.assetid: bac7ed4d-a163-4259-98bd-155a36345890
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 573a27343a15ef12ad955295c3beb3fef9130023
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-border-around-a-windows-forms-control-using-padding"></a>방법: 안쪽 여백을 사용하여 Windows Forms 컨트롤 주위에 테두리 만들기
다음 코드 예제에 테두리를 만들거나 주위에 대해 간략하게 설명 하는 방법을 보여 줍니다는 <xref:System.Windows.Forms.RichTextBox> 제어 합니다. 값을 설정 하는 예제는 <xref:System.Windows.Forms.Panel> 컨트롤의 <xref:System.Windows.Forms.Padding> 속성을 5로 설정은 <xref:System.Windows.Forms.Control.Dock%2A> 자식 속성 <xref:System.Windows.Forms.RichTextBox> 컨트롤을 <xref:System.Windows.Forms.DockStyle.Fill>합니다. <xref:System.Windows.Forms.Control.BackColor%2A> 의 <xref:System.Windows.Forms.Panel> 로 설정 되어 <xref:System.Drawing.Color.Blue%2A>, 주위에 파란색 테두리가 만듦는 <xref:System.Windows.Forms.RichTextBox> 제어 합니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[System.Windows.Forms.Padding#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Padding>  
 [Windows Forms 컨트롤의 여백 및 안쪽 여백](../../../../docs/framework/winforms/controls/margin-and-padding-in-windows-forms-controls.md)
