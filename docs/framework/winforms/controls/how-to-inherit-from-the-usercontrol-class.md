---
title: "방법: UserControl 클래스에서 상속 | Microsoft Docs"
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
  - "복합 컨트롤, 만들기"
  - "상속, Windows Forms 사용자 지정 컨트롤"
  - "사용자 정의 컨트롤[Windows Forms], 만들기"
  - "UserControl 클래스, 상속"
ms.assetid: 67713625-e2e4-4f6a-bce7-0855ee5043d9
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: UserControl 클래스에서 상속
하나 이상의 Windows Forms 컨트롤의 기능에 사용자 지정 코드를 결합하려면 *사용자 정의 컨트롤*을 만들어야 합니다.  사용자 정의 컨트롤은 표준 Windows Forms 컨트롤 기능, 신속한 컨트롤 개발 및 사용자 지정 속성과 메서드의 다양성을 함께 제공합니다.  사용자 정의 컨트롤을 만드는 작업을 시작하면 시각적인 디자이너가 표시되고 여기에 표준 Windows Forms 컨트롤을 배치할 수 있습니다.  이러한 컨트롤은 컨트롤의 모든 고유 기능뿐만 아니라 표준 컨트롤의 모양과 동작\(모양 및 느낌\)을 유지합니다.  그러나 이러한 컨트롤이 사용자 정의 컨트롤에 빌드되면 더 이상 코드를 통해 사용할 수 없습니다.  사용자 정의 컨트롤은 고유한 칠하기를 수행할 뿐만 아니라 컨트롤과 관련된 모든 기본 기능을 처리합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 사용자 정의 컨트롤을 만들려면  
  
1.  새 **Windows 컨트롤 라이브러리** 프로젝트를 만듭니다.  
  
     빈 사용자 정의 컨트롤을 가진 새 프로젝트가 만들어집니다.  
  
2.  **도구 상자**의 **Windows Forms** 탭에 있는 컨트롤을 디자이너로 끌어 옵니다.  
  
3.  최종 사용자 정의 컨트롤에서 나타나는 것과 동일하게 컨트롤의 위치를 지정하고 디자인합니다.  개발자가 구성 요소 컨트롤에 액세스할 수 있도록 하려면 공용으로 선언하거나 구성 요소 컨트롤의 속성을 선택적으로 노출해야 합니다.  자세한 내용은 [방법: 구성 요소 컨트롤의 속성 노출](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md)을 참조하십시오.  
  
4.  컨트롤이 구체화할 모든 사용자 지정 메서드나 속성을 구현합니다.  
  
5.  F5 키를 눌러 프로젝트를 빌드하고 **UserControl Test Container**에서 컨트롤을 실행합니다.  자세한 내용은 [방법: UserControl의 런타임 동작 테스트](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)를 참조하십시오.  
  
## 참고 항목  
 [사용자 지정 컨트롤의 종류](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)   
 [방법: Control 클래스에서 상속](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)   
 [방법: 기존 Windows Forms 컨트롤에서 상속](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)   
 [방법: Windows Forms 컨트롤 제작](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)   
 [Troubleshooting Inherited Event Handlers in Visual Basic](../Topic/Troubleshooting%20Inherited%20Event%20Handlers%20in%20Visual%20Basic.md)   
 [방법: UserControl의 런타임 동작 테스트](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)