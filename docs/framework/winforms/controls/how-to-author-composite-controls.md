---
title: "방법: 합성 컨트롤 제작"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UserControl class [Windows Forms], creating composite controls
- user controls [Windows Forms], creating
- user controls [Windows Forms], inheriting from
- composite controls [Windows Forms], creating
ms.assetid: 79c9cf05-5ab6-4a18-886d-88a64748b098
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 72c68568f0178956d6154f0b3a070e69b6ff0502
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-author-composite-controls"></a>방법: 합성 컨트롤 제작
여러 가지 방법으로 복합 컨트롤을 사용할 수 있습니다. Windows 데스크톱 응용 프로그램 프로젝트의 일부로 작성하고 프로젝트의 양식에서만 사용할 수 있습니다. 또는 Windows 컨트롤 라이브러리 프로젝트에서 작성하고 프로젝트를 어셈블리로 컴파일하고 다른 프로젝트에서 컨트롤을 사용할 수 있습니다. 상속하고 시각적 상속을 사용하여 특별한 목적을 위해 신속하게 사용자 지정할 수도 있습니다.  
  
> [!NOTE]
>  Web Forms에서 사용할 복합 컨트롤을 작성하려는 경우 [사용자 지정 ASP.NET 서버 컨트롤 개발](http://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef)을 참조하세요.  
>   
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-author-a-composite-control"></a>복합 컨트롤을 작성하려면  
  
1.  `DemoControlHost`이라는 새 **Windows 응용 프로그램** 프로젝트를 엽니다.  
  
2.  **프로젝트** 메뉴에서 **사용자 정의 컨트롤 추가**를 클릭합니다.  
  
3.  **새 항목 추가** 대화 상자에서 클래스 파일(.cs 또는 .vb 파일)에 복합 컨트롤이 원하는 이름을 지정합니다.  
  
4.  **추가** 단추를 클릭하여 복합 컨트롤의 클래스 파일을 만듭니다.  
  
5.  **도구 상자**에서 복합 컨트롤 화면에 컨트롤을 추가합니다.  
  
6.  이벤트 프로시저에 복합 컨트롤 또는 구성원 컨트롤에 의해 발생한 이벤트를 처리하는 코드를 입력합니다.  
  
7.  복합 컨트롤의 디자이너를 닫고 메시지가 나타나면 파일을 저장합니다.  
  
8.  **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
     사용자 지정 컨트롤을 **도구 상자**에 표시하기 위해 프로젝트를 빌드해야 합니다.  
  
9. **도구 상자**의 **DemoControlHost** 탭을 사용하여 컨트롤의 인스턴스를 `Form1`에 추가합니다.  
  
### <a name="to-author-a-control-class-library"></a>컨트롤 클래스 라이브러리를 작성하려면  
  
1.  새 **Windows 컨트롤 라이브러리** 프로젝트를 엽니다.  
  
     기본적으로 프로젝트는 복합 컨트롤을 포함합니다.  
  
2.  위의 절차에서 설명한 대로 컨트롤 및 코드를 추가합니다.  
  
3.  변경할 클래스를 상속하려는 컨트롤을 선택하고 이 컨트롤의 **한정자** 속성을 **개인**으로 설정합니다.  
  
4.  DLL을 빌드합니다.  
  
### <a name="to-inherit-from-a-composite-control-in-a-control-class-library"></a>컨트롤 클래스 라이브러리의 복합 컨트롤에서 상속하려면  
  
1.  **파일** 메뉴에서 **추가**를 가리키고 **새 프로젝트**를 선택하여 새 **Windows 응용 프로그램** 프로젝트를 솔루션에 추가합니다.  
  
2.  **솔루션 탐색기**에서 새 프로젝트의 **References** 폴더를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 선택하여 **참조 추가** 대화 상자를 엽니다.  
  
3.  **프로젝트** 탭을 선택하고 컨트롤 라이브러리 프로젝트를 두 번 클릭합니다.  
  
4.  **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
5.  **솔루션 탐색기**에서 컨트롤 라이브러리 프로젝트를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **새 항목 추가**를 선택합니다.  
  
6.  **새 항목 추가** 대화 상자에서 **상속된 사용자 정의 컨트롤** 템플릿을 선택합니다.  
  
7.  **상속 선택** 대화 상자에서 상속하려는 컨트롤을 두 번 클릭합니다.  
  
     새 컨트롤을 프로젝트에 추가합니다.  
  
8.  새 컨트롤에 대한 시각적 디자이너를 열고 추가 구성 요소 컨트롤을 추가합니다.  
  
     DLL의 복합 컨트롤에서 상속된 구성 요소 컨트롤을 볼 수 있으며 **한정자** 속성이 **공용**인 컨트롤의 속성을 변경할 수 있습니다. **한정자** 속성이 **개인**인 컨트롤의 속성을 변경할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습: Visual Basic에서 합성 컨트롤 작성](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 [연습: Visual C#에서 합성 컨트롤 작성](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 [연습: Visual Basic을 사용하여 Windows Forms 컨트롤에서 상속](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 [연습: Visual C#을 사용하여 Windows Forms 컨트롤에서 상속](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
 [컨트롤 형식 권장 사항](../../../../docs/framework/winforms/controls/control-type-recommendations.md)  
 [방법: Windows Forms 컨트롤 작성](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [사용자 지정 컨트롤의 종류](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
