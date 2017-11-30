---
title: "방법: Windows Forms 상속"
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
- inherited forms [Windows Forms], creating at run-time
- inheritance [Windows Forms], forms
- Windows Forms, inheritance
ms.assetid: cb3e1c0f-3d2a-4cdc-b0d1-c92eae567ffb
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e986c79887ad19c77761b5ce134e4a3d68200d1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-inherit-windows-forms"></a>방법: Windows Forms 상속
기본 폼에서 상속해서 새 Windows Forms를 만드는 것은 필요할 때마다 폼을 전체적으로 다시 만드는 프로세스를 거치지 않고 최선의 노력을 되풀이하는 편리한 방법입니다.  
  
 디자인 타임에서 **상속 선택** 대화 상자를 사용하여 양식을 상속하는 방법과 상속된 컨트롤의 보안 수준을 시각적으로 구분하는 방법에 대한 자세한 내용은 [방법: 상속 선택 대화 상자를 사용하여 양식 상속](../../../../docs/framework/winforms/advanced/how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md)을 참조하세요.  
  
 **참고** 양식을 상속받으려면 해당 양식이 포함된 파일 또는 네임스페이스가 실행 파일 또는 DLL로 빌드되었어야 합니다. 프로젝트를 빌드하려면 **빌드** 메뉴에서 **빌드**를 선택합니다. 또한 네임스페이스에 대한 참조는 폼을 상속하는 클래스에 추가되어야 합니다. 표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-inherit-a-form-programmatically"></a>폼을 프로그래밍 방식으로 상속하려면 다음을 수행합니다.  
  
1.  클래스에서 상속받을 폼이 포함된 네임스페이스에 대한 참조를 추가합니다.  
  
2.  클래스 정의에서 상속받을 폼에 대한 참조를 추가합니다. 참조에는 폼이 들어 있는 네임스페이스, 마침표, 기본 폼 자체의 이름이 차례로 포함되어야 합니다.  
  
    ```vb  
    Public Class Form2  
        Inherits Namespace1.Form1  
    ```  
  
    ```csharp  
    public class Form2 : Namespace1.Form1  
    ```  
  
 폼을 상속할 때 이벤트 처리기가 기본 클래스와 상속된 클래스에서 두 번 호출되는 문제가 발생할 수 있다는 점을 염두에 두어야 합니다. 이 문제를 방지하는 방법에 대한 자세한 내용은 [Visual Basic에서 상속된 이벤트 처리기 관련 문제 해결](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [Inherits 문](~/docs/visual-basic/language-reference/statements/inherits-statement.md)  
 [Imports 문(.NET 네임스페이스 및 형식)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [using](~/docs/csharp/language-reference/keywords/using.md)  
 [기본 폼의 모양 수정 효과](../../../../docs/framework/winforms/advanced/effects-of-modifying-base-form-appearance.md)  
 [Windows Forms 시각적 개체 상속](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)
