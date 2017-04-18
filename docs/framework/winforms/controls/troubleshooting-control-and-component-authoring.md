---
title: "컨트롤 및 구성 요소 제작 문제 해결 | Microsoft Docs"
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
  - "구성 요소[Windows Forms], 문제 해결"
  - "컨트롤[Windows Forms], 문제 해결"
  - "구성 요소 문제 해결"
  - "컨트롤 문제 해결"
  - "Windows Forms 컨트롤, 디버깅"
ms.assetid: e9c8c099-2271-4737-882f-50f336c7a55e
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# 컨트롤 및 구성 요소 제작 문제 해결
이 항목에서는 다음과 같이 구성 요소와 컨트롤을 개발할 때 발생하는 일반적인 문제에 대해 설명합니다.  자세한 내용은 [구성 요소를 사용한 프로그래밍](../Topic/Programming%20with%20Components.md)을 참조하십시오.  
  
-   도구 상자에 컨트롤을 추가할 수 없습니다.  
  
-   Windows Forms 사용자 정의 컨트롤 또는 구성 요소를 디버깅할 수 없습니다.  
  
-   상속된 컨트롤 또는 구성 요소에서 이벤트가 두 번 발생합니다.  
  
-   디자인 타임 오류: "'*구성 요소 이름*' 구성 요소를 만들지 못했습니다."  
  
-   STAThreadAttribute  
  
-   구성 요소 아이콘이 도구 상자에 표시되지 않음  
  
## 도구 상자에 컨트롤을 추가할 수 없습니다.  
 다른 프로젝트에서 만든 사용자 지정 컨트롤이나 타사 컨트롤은 **도구 상자**에 수동으로 추가해야 합니다.  현재 프로젝트에 컨트롤이나 구성 요소가 있는 경우 **도구 상자**에 자동으로 나타납니다.  자세한 내용은 [연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)를 참조하십시오.  
  
#### 도구 상자에 컨트롤을 추가하려면  
  
1.  **도구 상자**를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **항목 선택**을 선택합니다.  
  
2.  **도구 상자 항목 선택** 대화 상자에서 구성 요소를 추가합니다.  
  
    -   .NET Framework 구성 요소 또는 컨트롤을 추가하려면 **.NET Framework 구성 요소** 탭을 클릭합니다.  
  
         \-또는\-  
  
    -   COM 구성 요소 또는 ActiveX 컨트롤을 추가하려면 **COM 구성 요소** 탭을 클릭합니다.  
  
3.  컨트롤이 대화 상자에 표시되어 있으면 해당 컨트롤을 선택한 다음 **확인**을 클릭합니다.  
  
     컨트롤이 **도구 상자**에 추가됩니다.  
  
4.  추가할 컨트롤이 대화 상자에 표시되어 있지 않은 경우 다음을 수행합니다.  
  
    1.  **찾아보기** 단추를 클릭합니다.  
  
    2.  해당 컨트롤이 포함된 .dll 파일이 있는 폴더를 찾습니다.  
  
    3.  .dll 파일을 선택하고 **열기**를 클릭합니다.  
  
         컨트롤이 대화 상자에 표시됩니다.  
  
    4.  컨트롤이 선택되었는지 확인한 다음 **확인**을 클릭합니다.  
  
         컨트롤이 **도구 상자**에 추가됩니다.  
  
## Windows Forms 사용자 정의 컨트롤 또는 구성 요소를 디버깅할 수 없습니다.  
 컨트롤이 <xref:System.Windows.Forms.UserControl> 클래스에서 파생된 경우 테스트 컨테이너를 사용하여 런타임 동작을 디버깅할 수 있습니다.  자세한 내용은 [방법: UserControl의 런타임 동작 테스트](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)를 참조하십시오.  
  
 그 외 사용자 지정 컨트롤 및 구성 요소는 독립 실행형 프로젝트가 아닙니다.  이러한 컨트롤과 구성 요소는 Windows Forms 프로젝트 등의 응용 프로그램에서 호스팅해야 합니다.  컨트롤이나 구성 요소를 디버깅하려면 Windows Forms 프로젝트에 추가해야 합니다.  
  
#### 컨트롤이나 구성 요소를 디버깅하려면  
  
1.  **빌드** 메뉴에서 **솔루션 빌드**를 클릭하여 솔루션을 빌드합니다.  
  
2.  **파일** 메뉴에서 **추가**를 선택한 다음 **새 프로젝트**를 선택하여 응용 프로그램에 테스트 프로젝트를 추가합니다.  
  
3.  **새 프로젝트 추가** 대화 상자에서 프로젝트 형식으로 **Windows 응용 프로그램**을 선택합니다.  
  
4.  **솔루션 탐색기**에서 테스트 프로젝트에 대한 **참조** 노드를 마우스 오른쪽 단추로 클릭합니다.  바로 가기 메뉴에서 **참조 추가**를 클릭하여 해당 컨트롤이나 구성 요소가 포함된 프로젝트에 대한 참조를 추가합니다.  
  
5.  테스트 프로젝트에서 컨트롤이나 구성 요소의 인스턴스를 만듭니다.  구성 요소가 **도구 상자**에 들어 있는 경우 해당 구성 요소를 디자이너 화면으로 끌어 놓거나 다음 코드 예제에서처럼 프로그래밍 방식으로 인스턴스를 만듭니다.  
  
    ```vb  
    Dim Component1 As New MyNeatComponent()  
    ```  
  
    ```csharp  
    MyNeatComponent Component1 = new MyNeatComponent();  
    ```  
  
     이제 컨트롤이나 구성 요소를 정상적으로 디버깅할 수 있습니다.  
  
 디버깅에 대한 자세한 내용은 [Visual Studio의 디버깅](../Topic/Debugging%20in%20Visual%20Studio.md) 및 [연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버깅](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)를 참조하십시오.  
  
## 상속된 컨트롤 또는 구성 요소에서 이벤트가 두 번 발생합니다.  
 이 문제는 `Handles` 절이 중복된 경우에 발생합니다.  자세한 내용은 [Troubleshooting Inherited Event Handlers in Visual Basic](../Topic/Troubleshooting%20Inherited%20Event%20Handlers%20in%20Visual%20Basic.md)을 참조하십시오.  
  
## "'Component Name' 구성 요소를 만들지 못했습니다."라는 디자인 타임 오류가 발생합니다.  
 구성 요소 또는 컨트롤은 매개 변수가 없는 기본 생성자를 제공해야 합니다.  디자인 환경에서 구성 요소 또는 컨트롤의 인스턴스를 만드는 경우 매개 변수를 사용하는 생성자 오버로드에 대한 매개 변수를 제공하려고 하지 않습니다.  
  
## STAThreadAttribute  
 <xref:System.STAThreadAttribute>는 Windows Forms에서 단일 스레드 아파트 모델을 사용하고 있음을 CLR\(공용 언어 런타임\)에 알립니다.  이 특성을 Windows Forms 응용 프로그램의 `Main` 메서드에 적용하지 않을 경우 예상치 못한 동작이 발생할 수도 있습니다.  예를 들어, <xref:System.Windows.Forms.ListView> 같은 컨트롤에 대해 배경 이미지가 나타나지 않을 수 있습니다.  또한 일부 컨트롤에서는 올바른 자동 완성 및 끌어서 놓기 동작을 위해 이 특성이 필요할 수도 있습니다.  
  
## 구성 요소 아이콘이 도구 상자에 표시되지 않음  
 <xref:System.Drawing.ToolboxBitmapAttribute>를 사용하여 아이콘을 사용자 지정 구성 요소에 연결할 경우 비트맵은 자동 생성된 구성 요소의 도구 상자에 나타나지 않습니다.  비트맵을 보려면 **도구 상자 항목 선택** 대화 상자를 사용하여 컨트롤을 다시 로드합니다.  자세한 내용은 [방법: 컨트롤에 대한 도구 상자 비트맵 제공](../../../../docs/framework/winforms/controls/how-to-provide-a-toolbox-bitmap-for-a-control.md)을 참조하십시오.  
  
## 참고 항목  
 [디자인할 때 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)   
 [연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)   
 [방법: UserControl의 런타임 동작 테스트](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)   
 [연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버깅](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)   
 [구성 요소 제작](../Topic/Component%20Authoring.md)   
 [Troubleshooting Design\-Time Development](../Topic/Troubleshooting%20Design-Time%20Development.md)   
 [구성 요소를 사용한 프로그래밍](../Topic/Programming%20with%20Components.md)