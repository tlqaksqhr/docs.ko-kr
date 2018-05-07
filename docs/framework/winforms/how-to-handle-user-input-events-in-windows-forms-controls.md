---
title: '방법: Windows Forms 컨트롤에서 사용자 입력 이벤트 처리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, user input
- user input [Windows Forms], Windows Forms controls
ms.assetid: 3de74dcf-fae3-42d0-92b5-bc04a61a6888
ms.openlocfilehash: 1faff6112f7857c2b1d6e4ac70c87f1a2adb62a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-handle-user-input-events-in-windows-forms-controls"></a>방법: Windows Forms 컨트롤에서 사용자 입력 이벤트 처리
이 예제에서는 Windows Forms 컨트롤에서 발생할 수 있는 대부분의 키보드, 마우스, 포커스 및 유효성 검사 이벤트를 처리하는 방법을 보여 줍니다. 포커스가 있을 경우 `TextBoxInput`이라는 텍스트 상자가 이벤트를 수신하며, 각 이벤트에 대한 정보가 이벤트 발생 순서대로 `TextBoxOutput`이라는 텍스트 상자에 기록됩니다. 응용 프로그램에는 보고할 이벤트를 필터링하는 데 사용할 수 있는 확인란 집합도 포함되어 있습니다.  
  
## <a name="example"></a>예제  
 [!code-cpp[System.Windows.Forms.UserInputWalkthrough#0](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.UserInputWalkthrough#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.UserInputWalkthrough#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다. 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.  [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms에 사용자 입력](../../../docs/framework/winforms/user-input-in-windows-forms.md)
