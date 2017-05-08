---
title: "방법: UserControl의 런타임 동작 테스트 | Microsoft Docs"
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
  - "복합 컨트롤, 테스트"
  - "사용자 정의 컨트롤[Windows Forms], 테스트"
  - "UserControl 클래스, 런타임 동작"
  - "UserControl 클래스, 테스트"
  - "UserControl Test Container"
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: UserControl의 런타임 동작 테스트
<xref:System.Windows.Forms.UserControl>을 개발하는 경우에 해당 런타임 동작을 테스트해야 합니다.  별도의 Windows 기반 응용 프로그램 프로젝트를 만들어 컨트롤을 테스트 폼에 배치할 수 있지만 이러한 절차는 불편합니다.  Visual Studio에서 제공하는 **UserControl Test Container**를 사용하면 이러한 작업을 보다 쉽고 빠르게 수행할 수 있습니다.  이 테스트 컨테이너는 Windows 컨트롤 라이브러리 프로젝트에서 직접 시작됩니다.  
  
> [!IMPORTANT]
>  테스트 컨테이너에서 <xref:System.Windows.Forms.UserControl>을 로드하려면 컨트롤에 적어도 하나의 공용 생성자가 있어야 합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
> [!NOTE]
>  Visual C\+\+ 컨트롤은 **UserControl 테스트 컨테이너**를 사용하여 테스트할 수 없습니다.  
  
### UserControl의 런타임 동작을 테스트하려면  
  
1.  TestContainerExample이라는 Windows 컨트롤 라이브러리 프로젝트를 만듭니다.  자세한 내용은 [Windows Control Library Template](http://msdn.microsoft.com/ko-kr/722f4e2d-1310-4ed5-8f33-593337ab66b4)을 참조하십시오.  
  
2.  **Windows Forms 디자이너**에서 **도구 상자**의 <xref:System.Windows.Forms.Label> 컨트롤을 컨트롤의 디자인 화면으로 끌어 옵니다.  
  
3.  F5 키를 눌러 프로젝트를 빌드하고 **UserControl Test Container**를 실행합니다.  <xref:System.Windows.Forms.UserControl>이 포함된 테스트 컨테이너가 **미리 보기** 창에 나타납니다.  
  
4.  **미리 보기** 창의 오른쪽에 있는 <xref:System.Windows.Forms.PropertyGrid> 컨트롤에 표시된 <xref:System.Windows.Forms.Control.BackColor%2A> 속성을 선택합니다.  해당 값을 `ControlDark`로 변경합니다.  컨트롤이 어두운 색으로 바뀝니다.  다른 속성 값을 변경하고 컨트롤에 미치는 영향을 확인합니다.  
  
5.  **미리 보기** 창 아래에 있는 **사용자 정의 컨트롤 전체 도킹** 확인란을 클릭합니다.  컨트롤이 창 크기에 맞게 조정되었는지 확인합니다.  테스트 컨테이너 크기를 조정하고 컨트롤이 창에 맞게 크기가 조정되었는지 확인합니다.  
  
6.  테스트 컨테이너를 닫습니다.  
  
7.  다른 사용자 정의 컨트롤을 TestContainerExample 프로젝트에 추가합니다.  자세한 내용은 [NIB:How to: Add Existing Items to a Project](http://msdn.microsoft.com/ko-kr/15f4cfb7-78ab-457f-9f14-099a25a6a2d3)를 참조하십시오.  
  
8.  **Windows Forms 디자이너**에서 **도구 상자**의 <xref:System.Windows.Forms.Button> 컨트롤을 컨트롤의 디자인 화면으로 끌어 옵니다.  
  
9. F5 키를 눌러 프로젝트를 빌드하고 테스트 컨테이너를 실행합니다.  
  
10. **사용자 정의 컨트롤 선택** <xref:System.Windows.Forms.ComboBox>를 클릭하여 두 사용자 정의 컨트롤 간에 전환합니다.  
  
## 다른 프로젝트의 사용자 정의 컨트롤 테스트  
 현재 프로젝트의 테스트 컨테이너에서 다른 프로젝트의 사용자 정의 컨트롤을 테스트할 수 있습니다.  
  
#### 다른 프로젝트의 사용자 정의 컨트롤을 테스트하려면  
  
1.  TestContainerExample2라는 Windows 컨트롤 라이브러리 프로젝트를 만듭니다.  자세한 내용은 [Windows Control Library Template](http://msdn.microsoft.com/ko-kr/722f4e2d-1310-4ed5-8f33-593337ab66b4)을 참조하십시오.  
  
2.  **Windows Forms 디자이너**에서 **도구 상자**의 <xref:System.Windows.Forms.RadioButton> 컨트롤을 컨트롤의 디자인 화면으로 끌어 옵니다.  
  
3.  F5 키를 눌러 프로젝트를 빌드하고 테스트 컨테이너를 실행합니다.  <xref:System.Windows.Forms.UserControl>이 포함된 테스트 컨테이너가 **미리 보기** 창에 나타납니다.  
  
4.  **로드** 단추를 클릭합니다.  
  
5.  **열기** 대화 상자에서 이전 절차에서 빌드한 TestContainerExample.dll을 탐색합니다.  TestContainerExample.dll을 선택하고 **열기** 단추를 클릭하여 사용자 정의 컨트롤을 로드합니다.  
  
6.  **사용자 정의 컨트롤 선택** <xref:System.Windows.Forms.ComboBox>를 사용하여 TestContainerExample 프로젝트의 두 사용자 정의 컨트롤 간에 전환합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.UserControl>   
 [방법: 합성 컨트롤 제작](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)   
 [연습: Visual Basic에서 합성 컨트롤 제작](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)   
 [연습: Visual C\#에서 합성 컨트롤 제작](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)   
 [User Control Designer](http://msdn.microsoft.com/ko-kr/2abb9eec-ba32-45cb-b73d-8b52a8bd6bf1)