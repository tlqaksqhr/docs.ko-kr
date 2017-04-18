---
title: "방법: Windows Forms 컨트롤 제작 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "컨트롤[Windows Forms], 만들기"
  - "사용자 지정 컨트롤[Windows Forms], 만들기"
  - "UserControl 클래스, Windows Forms"
ms.assetid: 7570e982-545b-4c3a-a7c7-55581d313400
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: Windows Forms 컨트롤 제작
컨트롤은 사용자와 프로그램 사이를 그래픽으로 연결합니다.  컨트롤은 데이터를 제공하거나 처리하고, 사용자의 입력을 받고, 이벤트에 응답할 수 있을 뿐만 아니라 사용자와 응용 프로그램을 연결하는 기타 여러 가지 기능을 수행할 수 있습니다.  컨트롤은 본질적으로 그래픽 인터페이스를 가진 구성 요소이기 때문에 사용자와의 상호 작용을 제공하는 것은 물론 구성 요소가 수행하는 모든 기능을 수행할 수 있습니다.  컨트롤은 특정 목적을 수행하도록 만들어지며 컨트롤 제작은 또 다른 프로그래밍 작업의 하나입니다.  이러한 점을 고려하여 아래에서는 컨트롤 제작 프로세스의 개요를 단계별로 설명합니다.  해당 링크는 각 단계에 대한 추가 정보를 제공합니다.  
  
> [!NOTE]
>  Web Forms에서 사용할 사용자 지정 컨트롤을 제작하려면 [Developing Custom ASP.NET Server Controls](../Topic/Developing%20Custom%20ASP.NET%20Server%20Controls.md)을 참조하십시오.  
>   
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 컨트롤을 제작하려면  
  
1.  컨트롤을 통해 수행할 작업과 응용 프로그램의 어느 부분에서 컨트롤을 사용할지 결정합니다.  고려해야 할 사항은 다음과 같습니다.  
  
    -   어떤 종류의 그래픽 인터페이스가 필요합니까?  
  
    -   컨트롤이 어떤 특정 사용자 인터페이스를 처리합니까?  
  
    -   기존 컨트롤을 통해 필요한 기능이 제공됩니까?  
  
    -   여러 Windows Forms 컨트롤을 결합하여 필요한 기능을 얻을 수 있습니까?  
  
2.  컨트롤에 개체 모델이 필요한 경우 기능을 개체 모델 전체에 분산시키는 방법을 결정한 다음 컨트롤과 하위 개체 간의 기능을 분리합니다.  개체 모델은 복잡한 컨트롤을 제작하거나 여러 기능을 구체화하려는 경우에 유용합니다.  
  
3.  용도에 맞는 컨트롤 형식\(예: 사용자 정의 컨트롤, 사용자 지정 컨트롤, 상속된 Windows Forms 컨트롤\)을 결정합니다.  자세한 내용은 [컨트롤 형식 권장 사항](../../../../docs/framework/winforms/controls/control-type-recommendations.md) 및 [사용자 지정 컨트롤의 종류](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)를 참조하십시오.  
  
4.  해당 컨트롤과 그 하위 개체 또는 보조 구조의 속성, 메서드 및 이벤트를 사용하여 기능을 나타내고 적절한 액세스 수준\(예: public, protected 등\)을 할당합니다.  
  
5.  컨트롤에 사용자 지정 그리기가 필요하면 코드를 추가합니다.  자세한 내용은 [사용자 지정 컨트롤 그리기 및 렌더링](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)을 참조하십시오.  
  
6.  컨트롤이 <xref:System.Windows.Forms.UserControl>에서 상속되는 경우 컨트롤 프로젝트를 빌드하고 **UserControl Test Container**에서 실행하여 컨트롤의 런타임 동작을 테스트할 수 있습니다.  자세한 내용은 [방법: UserControl의 런타임 동작 테스트](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)를 참조하십시오.  
  
7.  또한 Windows 응용 프로그램과 같은 새 프로젝트를 만들어 컨트롤을 테스트 및 디버깅한 다음 컨테이너에 넣을 수도 있습니다.  이 과정에 대한 내용은 [연습: Visual Basic에서 합성 컨트롤 제작](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)을 참조하십시오.  
  
8.  각 기능을 추가하면서 새 기능을 연습할 수 있는 기능을 테스트 프로젝트에 추가합니다.  
  
9. 디자인을 좀 더 구체화합니다.  
  
10. 컨트롤을 패키지하여 배포합니다.  자세한 내용은 [응용 프로그램, 서비스 및 구성 요소 배포](../Topic/Deploying%20Applications,%20Services,%20and%20Components.md)를 참조하십시오.  
  
## 참고 항목  
 [연습: Visual Basic에서 합성 컨트롤 제작](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)   
 [연습: Visual Basic을 사용하여 Windows Forms 컨트롤에서 상속](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)   
 [방법: UserControl 클래스에서 상속](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)   
 [방법: Control 클래스에서 상속](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)   
 [방법: 기존 Windows Forms 컨트롤에서 상속](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)   
 [방법: UserControl의 런타임 동작 테스트](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)   
 [사용자 지정 컨트롤의 종류](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)