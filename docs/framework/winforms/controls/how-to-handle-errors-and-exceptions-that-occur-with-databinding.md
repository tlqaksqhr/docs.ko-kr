---
title: '방법: 데이터 바인딩에서 발생하는 오류 및 예외 처리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- error handling [Windows Forms], examples
- data binding [Windows Forms], examples
- examples [Windows Forms], error handling
- error handling [Windows Forms], data binding
- data binding [Windows Forms], error handling
- BindingSource component [Windows Forms], handling errors and exceptions
ms.assetid: eddc5bad-9513-47df-ab28-f02d8dff7892
ms.openlocfilehash: c7c05eb8d858c1f911e148def1c714e3caf74c95
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532264"
---
# <a name="how-to-handle-errors-and-exceptions-that-occur-with-databinding"></a>방법: 데이터 바인딩에서 발생하는 오류 및 예외 처리
기본 비즈니스 개체를 컨트롤에 바인딩할 때 종종 해당 개체에서 예외와 오류가 발생합니다. 이들 오류와 예외를 가로채고 특정 <xref:System.Windows.Forms.Binding>, <xref:System.Windows.Forms.BindingSource> 또는 <xref:System.Windows.Forms.CurrencyManager> 구성 요소에 대한 <xref:System.Windows.Forms.Binding.BindingComplete> 이벤트를 처리하여 오류 정보를 복구하거나 사용자에게 전달할 수 있습니다.  
  
## <a name="example"></a>예제  
 이 코드 예제에서는 데이터 바인딩 작업 중에 발생하는 오류와 예외를 처리하는 방법을 보여 줍니다. <xref:System.Windows.Forms.Binding> 개체의 <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> 이벤트를 처리하여 오류를 가로채는 방법을 보여 줍니다. 이 이벤트를 처리하여 오류와 예외를 가로채려면 바인딩 서식 지정을 사용하도록 설정해야 합니다. 바인딩이 생성되거나 바인딩 컬렉션에 추가될 때 서식 지정을 사용하도록 설정하거나 <xref:System.Windows.Forms.Binding.FormattingEnabled%2A> 속성을 `true`로 설정하여 사용하도록 설정합니다.  
  
 [!code-cpp[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CPP/form1.cpp#3)]
 [!code-csharp[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CS/form1.cs#3)]
 [!code-vb[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/VB/form1.vb#3)]  
  
 코드가 실행 중일 때 부분 이름으로 빈 문자열이 입력되거나 부분 숫자로 100보다 작은 값이 입력되면 메시지 상자가 표시됩니다. 이들 텍스트 상자 바인딩에 대한 <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> 이벤트를 처리한 결과로 나타나는 것입니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다. 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.  [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.BindingSource.BindingComplete?displayProperty=nameWithType>  
 [BindingSource 구성 요소](../../../../docs/framework/winforms/controls/bindingsource-component.md)
