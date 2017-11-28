---
title: "방법: Windows Form 인쇄"
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
- Windows Forms, printing
- printing [Windows Forms]
- printing a form
- printing [Windows Forms], printing a form
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9149b90317036c7c62c5fca3056bb697df56e543
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-print-a-windows-form"></a>방법: Windows Form 인쇄
개발 프로세스의 일환으로, 일반적으로 할 Windows Form의 복사본을 인쇄 합니다. 다음 코드 예제를 사용 하 여 현재 폼의 복사본을 인쇄 하는 방법을 보여 줍니다는 <xref:System.Drawing.Graphics.CopyFromScreen%2A> 메서드.  
  
## <a name="example"></a>예제  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 포함 하는 전체 코드 예제는 `Main` 메서드.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 다음 조건에서 예외가 발생합니다.  
  
-   프린터에 액세스할 수 있는 권한이 없습니다.  
  
-   프린터가 설치 되어 있지 않습니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 이 코드 예제를 실행 하는 데 사용할 프린터를 사용 하 여 컴퓨터를 액세스할 수 있는 권한이 있어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Printing.PrintDocument>  
 [방법: GDI+를 사용하여 이미지 렌더링](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)  
 [방법: Windows Forms의 그래픽 인쇄](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)
