---
title: '방법: DBNull 데이터베이스 값에 Windows Forms 컨트롤 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BindingSource component [Windows Forms], binding to DBNull values
- examples [Windows Forms], BindingSource component
- controls [Windows Forms], binding to DBNull values
ms.assetid: 96494e6f-5f40-4f83-af97-bbd7192c2af8
ms.openlocfilehash: c8c942b872b23bc6ff0a6f254b952189f9e62dbb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530317"
---
# <a name="how-to-bind-windows-forms-controls-to-dbnull-database-values"></a>방법: DBNull 데이터베이스 값에 Windows Forms 컨트롤 바인딩
Windows Forms 컨트롤을 데이터 소스에 바인딩하고 데이터 소스가 <xref:System.DBNull> 값을 반환하는 경우 이벤트를 처리, 형식 지정 또는 구문 분석하지 않고 적절한 값을 대체할 수 있습니다. <xref:System.Windows.Forms.Binding.NullValue%2A> 속성은 데이터 소스 값을 형식 지정 또는 구문 분석할 때 <xref:System.DBNull>을 지정된 개체로 변환합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 두 가지 다른 상황에서 <xref:System.DBNull> 값을 바인딩하는 방법을 보여 줍니다. 첫 번째 예제에서는 문자열 속성에 대해 <xref:System.Windows.Forms.Binding.NullValue%2A>를 설정하는 방법을 보여 주고, 두 번째 예제에서는 이미지 속성에 대해 <xref:System.Windows.Forms.Binding.NullValue%2A>를 설정하는 방법을 보여 줍니다.  
  
 [!code-csharp[System.Windows.Forms.BindingDBNull#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingDBNull#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/VB/form1.vb#1)]  
  
 바인딩된 속성의 형식 및 <xref:System.Windows.Forms.Binding.NullValue%2A> 속성은 같아야 합니다. 그러지 않으면 오류가 발생하고 더 이상 <xref:System.Windows.Forms.Binding.NullValue%2A> 값이 처리되지 않습니다. 이 경우 예외가 발생하지 않습니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다. 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.  [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [BindingSource 구성 요소](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [방법: 데이터 바인딩에서 발생하는 오류 및 예외 처리](../../../../docs/framework/winforms/controls/how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)  
 [방법: 형식에 Windows Forms 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
