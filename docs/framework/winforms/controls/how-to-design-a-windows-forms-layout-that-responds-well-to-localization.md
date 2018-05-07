---
title: '방법: 지역화에 적합한 Windows Forms 레이아웃 디자인'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- application design [Windows Forms], localization
- Windows Forms, localization
- localization [Windows Forms], Windows Forms layout
ms.assetid: d13eff2d-701c-4b6e-8838-3885cbfb7223
ms.openlocfilehash: aa141319e902ff96ecfb9e9a70ca66528705418d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a>방법: 지역화에 적합한 Windows Forms 레이아웃 디자인
지역화할 준비가 된 폼을 만들면 국제 시장에서 개발 속도를 크게 높일 수 있습니다. <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 사용하여 <xref:System.Windows.Forms.Control.Text%2A> 속성 값 변경 때문에 컨트롤 크기가 조정될 때 정상적으로 응답하는 레이아웃을 구현할 수 있습니다.  
  
## <a name="example"></a>예제  
 이 폼에서는 표시된 문자열 값을 다른 언어로 번역할 때 비례하여 조정되는 레이아웃을 만드는 방법을 보여 줍니다. 이 번역 프로세스를 *지역화*라고 합니다. 자세한 내용은 [지역화](../../../../docs/standard/globalization-localization/localization.md)를 참조하세요.  
  
 Visual Studio에서는 이 작업이 광범위하게 지원됩니다.  또한 [연습: 지역화를 위해 비율을 조정하는 레이아웃 만들기](http://msdn.microsoft.com/library/7k9fa71y\(v=vs.110\))를 참조하세요.  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]  
  
1.  [방법: TableLayoutPanel 컨트롤의 컨트롤 맞춤 및 늘이기](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))  
  
2.  [연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](http://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\))  
  
3.  [방법: TableLayoutPanel 컨트롤에서 행과 열 확장](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))  
  
4.  [방법: TableLayoutPanel 컨트롤에서 열과 행 편집](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))  
  
5.  [연습: Windows Forms 컨트롤에서 스마트 태그를 사용하여 일반 작업 수행](http://msdn.microsoft.com/library/xhz359sc\(v=vs.110\))  
  
6.  [연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))  
  
7.  [연습: Padding, Margins 및 AutoSize 속성을 사용하여 Windows Forms 컨트롤 레이아웃](http://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\))  
  
8.  [방법: AutoSize 속성과 TableLayoutPanel 컨트롤을 사용하여 Windows Forms 지역화 지원](http://msdn.microsoft.com/library/1zkt8b33\(v=vs.110\))  
  
9. [연습: 데이터를 입력할 수 있는 크기 조정 가능한 Windows Form 만들기](http://msdn.microsoft.com/library/991eahec\(v=vs.110\))  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다. 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.  [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 [지역화](../../../../docs/standard/globalization-localization/localization.md)
