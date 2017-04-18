---
title: "연습: Visual Studio의 디자인 타임 기능을 사용하는 Windows Forms 컨트롤 만들기 | Microsoft Docs"
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
  - "디자인 타임 기능, Windows Forms"
  - "DocumentDesigner 클래스[Windows Forms]"
  - "연습[Windows Forms], 컨트롤"
  - "Windows Forms 컨트롤, 만들기"
ms.assetid: 6f487c59-cb38-4afa-ad2e-95edacb1d626
caps.latest.revision: 46
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 46
---
# 연습: Visual Studio의 디자인 타임 기능을 사용하는 Windows Forms 컨트롤 만들기
연결된 사용자 지정 디자이너를 만들어 사용자 지정 컨트롤의 디자인 타임 환경을 향상시킬 수 있습니다.  
  
 이 연습에서는 사용자 지정 컨트롤의 사용자 지정 디자이너를 만드는 방법을 보여 줍니다.  `MarqueeControl` 형식과 `MarqueeControlRootDesigner`라는 연결된 디자이너 클래스를 구현합니다.  
  
 `MarqueeControl` 형식은 애니메이션 조명과 깜박이는 텍스트로 극장 홍보물과 같은 화면 표시를 구현합니다.  
  
 이 컨트롤의 디자이너는 사용자 지정 디자인 타임 환경을 제공하는 디자인 환경과 상호 작용합니다.  사용자 지정 디자이너를 사용하여 애니메이션 조명 및 깜박이는 텍스트와 함께 사용자 지정 `MarqueeControl` 구현을 여러 가지 조합으로 구성할 수 있습니다.  이렇게 구성된 컨트롤을 다른 모든 Windows Forms 컨트롤과 같이 폼에서 사용할 수 있습니다.  
  
 이 연습에서 수행할 작업은 다음과 같습니다.  
  
-   프로젝트 만들기  
  
-   컨트롤 라이브러리 프로젝트 만들기  
  
-   사용자 지정 컨트롤 프로젝트 참조  
  
-   사용자 지정 컨트롤 및 해당 사용자 지정 디자이너 정의  
  
-   사용자 지정 컨트롤의 인스턴스 만들기  
  
-   디자인 타임 디버깅을 위한 프로젝트 설정  
  
-   사용자 지정 컨트롤 구현  
  
-   사용자 지정 컨트롤의 자식 컨트롤 만들기  
  
-   MarqueeBorder 자식 컨트롤 만들기  
  
-   사용자 지정 디자이너를 만들어 속성 숨기기 및 필터링  
  
-   구성 요소의 변경 내용 처리  
  
-   사용자 지정 디자이너에 디자이너 동사 추가  
  
-   사용자 지정 UITypeEditor 만들기  
  
-   디자이너에서 사용자 지정 컨트롤 테스트  
  
 작업이 끝나면 다음과 같은 사용자 지정 컨트롤이 만들어집니다.  
  
 ![가능한 MarqueeControl 배치](../../../../docs/framework/winforms/controls/media/demomarqueecontrol.gif "DemoMarqueeControl")  
  
 전체 코드 목록은 [How to: Create a Windows Forms Control That Takes Advantage of Design\-Time Features](../Topic/How%20to:%20Create%20a%20Windows%20Forms%20Control%20That%20Takes%20Advantage%20of%20Design-Time%20Features.md)를 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음과 같은 요건이 필요합니다.  
  
-   Visual Studio가 설치된 컴퓨터에서 Windows Forms 응용 프로그램 프로젝트를 만들고 실행할 수 있는 권한  
  
## 프로젝트 만들기  
 첫 번째 단계는 응용 프로그램 프로젝트를 만드는 것입니다.  사용자 지정 컨트롤을 호스팅하는 응용 프로그램을 빌드하는 데 이 프로젝트를 사용합니다.  
  
#### 프로젝트를 만들려면  
  
-   "MarqueeControlTest"라는 Windows Forms 응용 프로그램 프로젝트를 만듭니다. 자세한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하십시오.  
  
## 컨트롤 라이브러리 프로젝트 만들기  
 다음 단계에서는 컨트롤 라이브러리 프로젝트를 만듭니다.  새 사용자 지정 컨트롤과 해당 사용자 지정 디자이너를 만듭니다.  
  
#### 컨트롤 라이브러리 프로젝트를 만들려면  
  
1.  솔루션에 Windows Forms 컨트롤 라이브러리 프로젝트를 추가합니다.  프로젝트 이름을 "MarqueeControlLibrary"로 지정합니다.  
  
2.  **솔루션 탐색기**를 사용하여 선택한 언어에 따라 이름이 "UserControl1.cs" 또는 "UserControl1.vb" 소스 파일을 삭제하여 프로젝트의 기본 컨트롤을 삭제합니다.  자세한 내용은 [NIB:How to: Remove, Delete, and Exclude Items](http://msdn.microsoft.com/ko-kr/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73)를 참조하십시오.  
  
3.  `MarqueeControlLibrary` 프로젝트에 새 <xref:System.Windows.Forms.UserControl> 항목을 추가합니다.  새 소스 파일의 기본 이름을 "MarqueeControl"로 지정합니다.  
  
4.  **솔루션 탐색기**를 사용하여 `MarqueeControlLibrary` 프로젝트에 새 폴더를 만듭니다.  자세한 내용은 [NIB:How to: Add New Project Items](http://msdn.microsoft.com/ko-kr/63d3e16b-de6e-4bb5-a0e3-ecec762201ce)를 참조하십시오.  새 폴더 이름을 "Design"으로 지정합니다.  
  
5.  **Design** 폴더를 마우스 오른쪽 단추로 클릭하고 새 클래스를 추가합니다.  소스 파일의 기본 이름을 "MarqueeControlRootDesigner"로 지정합니다.  
  
6.  System.Design 어셈블리의 형식을 사용해야 하므로 이 참조를 `MarqueeControlLibrary` 프로젝트에 추가합니다.  
  
    > [!NOTE]
    >  System.Design 어셈블리를 사용하려면 프로젝트에서 .NET Framework Client Profile이 아닌 정식 버전의 .NET Framework를 대상으로 해야 합니다.  대상 프레임워크를 변경하려면 [방법: 한 버전의 .NET Framework를 대상으로 지정](../Topic/How%20to:%20Target%20a%20Version%20of%20the%20.NET%20Framework.md)을 참조하십시오.  
  
## 사용자 지정 컨트롤 프로젝트 참조  
 `MarqueeControlTest` 프로젝트를 사용하여 사용자 지정 컨트롤을 테스트합니다.  `MarqueeControlLibrary` 어셈블리에 프로젝트 참조를 추가할 때 테스트 프로젝트에서 사용자 지정 컨트롤을 인식하게 됩니다.  
  
#### 사용자 지정 컨트롤 프로젝트를 참조하려면  
  
-   `MarqueeControlTest` 프로젝트에서 `MarqueeControlLibrary` 어셈블리에 프로젝트 참조를 추가합니다.  `MarqueeControlLibrary` 어셈블리를 직접 참조하는 대신 **참조 추가** 대화 상자에서 **프로젝트** 탭을 사용해야 합니다.  
  
## 사용자 지정 컨트롤 및 해당 사용자 지정 디자이너 정의  
 사용자 지정 컨트롤은 <xref:System.Windows.Forms.UserControl> 클래스에서 파생됩니다.  따라서 컨트롤에 다른 컨트롤이 포함될 수 있으며 여러 가지 기본 기능이 제공됩니다.  
  
 사용자 지정 컨트롤에는 사용자 지정 디자이너가 연결됩니다.  이를 통해 특별히 자신의 사용자 지정 컨트롤에 맞는 고유의 디자인 환경을 만들 수 있습니다.  
  
 <xref:System.ComponentModel.DesignerAttribute> 클래스를 사용하여 컨트롤을 해당 디자이너와 연결합니다.  사용자 지정 컨트롤의 전체 디자인 타임 동작을 개발하므로 사용자 지정 디자이너에는 <xref:System.ComponentModel.Design.IRootDesigner> 인터페이스가 구현됩니다.  
  
#### 사용자 지정 컨트롤과 해당 사용자 지정 디자이너를 정의하려면  
  
1.  **코드 편집기**에서 `MarqueeControl` 소스 파일을 엽니다.  파일의 맨 위에서 다음과 같은 네임스페이스를 가져옵니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]  
  
2.  <xref:System.ComponentModel.DesignerAttribute>를 `MarqueeControl` 클래스 선언에 추가합니다.  이렇게 하면 사용자 지정 컨트롤이 해당 디자이너에 연결됩니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]  
  
3.  **코드 편집기**에서 `MarqueeControlRootDesigner` 소스 파일을 엽니다.  파일의 맨 위에서 다음과 같은 네임스페이스를 가져옵니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]  
  
4.  <xref:System.Windows.Forms.Design.DocumentDesigner> 클래스에서 상속하도록 `MarqueeControlRootDesigner` 선언을 변경합니다.  <xref:System.ComponentModel.ToolboxItemFilterAttribute>를 적용하여 디자이너와 **도구 상자**의 상호 작용을 지정합니다.  
  
     **참고** `MarqueeControlRootDesigner` 클래스에 대한 정의는 "MarqueeControlLibrary.Design" 네임스페이스에 포함되어 있습니다. 이 선언을 통해 디자이너는 디자인 관련 형식용으로 예약된 특수 네임스페이스에 배치됩니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]  
  
5.  `MarqueeControlRootDesigner` 클래스의 생성자를 정의합니다.  <xref:System.Diagnostics.Trace.WriteLine%2A> 문을 생성자 본문에 삽입합니다.  이는 디버깅에 유용합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]  
  
## 사용자 지정 컨트롤의 인스턴스 만들기  
 컨트롤의 사용자 지정 디자인 타임 동작을 관찰하기 위해 컨트롤의 인스턴스를 `MarqueeControlTest` 프로젝트의 폼에 배치합니다.  
  
#### 사용자 지정 컨트롤의 인스턴스를 만들려면  
  
1.  `MarqueeControlTest` 프로젝트에 새 <xref:System.Windows.Forms.UserControl> 항목을 추가합니다.  새 소스 파일의 기본 이름을 "DemoMarqueeControl"로 지정합니다.  
  
2.  **코드 편집기**에서 `DemoMarqueeControl` 파일을 엽니다.  파일의 맨 위에서 `MarqueeControlLibrary` 네임스페이스를 가져옵니다.  
  
```vb  
Imports MarqueeControlLibrary  
```  
  
```csharp  
using MarqueeControlLibrary;  
```  
  
1.  `MarqueeControl` 클래스에서 상속하도록 `DemoMarqueeControl` 선언을 변경합니다.  
  
2.  프로젝트를 빌드합니다.  
  
3.  Windows Forms 디자이너에서 `Form1`을 엽니다.  
  
4.  **도구 상자**에서 **MarqueeControlTest 구성 요소** 탭을 찾아 엽니다.  **도구 상자**의 `DemoMarqueeControl`을 폼으로 끌어 옵니다.  
  
5.  프로젝트를 빌드합니다.  
  
## 디자인 타임 디버깅을 위한 프로젝트 설정  
 사용자 지정 디자인 타임 환경을 개발하는 경우 컨트롤과 구성 요소를 디버깅할 필요가 있습니다.  디자인 타임에 디버깅할 수 있도록 프로젝트를 설정할 수 있는 간단한 방법이 있습니다.  자세한 내용은 [연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버깅](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)을 참조하십시오.  
  
#### 디자인 타임 디버깅을 위해 프로젝트를 설정하려면  
  
1.  `MarqueeControlLibrary` 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.  
  
2.  "MarqueeControlLibrary 속성 페이지" 대화 상자에서 **디버그** 페이지를 선택합니다.  
  
3.  **시작 작업** 구역에서 **시작 외부 프로그램**을 선택합니다.  별도의 Visual Studio 인스턴스를 디버깅하므로 줄임표\(![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) 단추를 클릭하여 Visual Studio IDE를 찾아봅니다.  실행 파일의 이름은 devenv.exe이며, 기본 위치에 설치한 경우 경로는 %programfiles%\\Microsoft Visual Studio 9.0\\Common7\\IDE\\devenv.exe입니다.  
  
4.  확인을 클릭하여 대화 상자를 닫습니다.  
  
5.  `MarqueeControlLibrary` 프로젝트를 마우스 오른쪽 단추로 클릭하고 "시작 프로젝트로 설정"을 선택하여 이 디버깅 구성을 사용합니다.  
  
## 검사점  
 이제 사용자 지정 컨트롤의 디자인 타임 동작을 디버깅할 준비가 되었습니다.  디버깅 환경이 올바르게 설정된 것을 확인했으면 사용자 지정 컨트롤과 사용자 지정 디버거 사이의 연결을 테스트합니다.  
  
#### 디버깅 환경과 디자이너 연결을 테스트하려면  
  
1.  **코드 편집기**에서 `MarqueeControlRootDesigner` 소스 파일을 열고 <xref:System.Diagnostics.Trace.WriteLine%2A> 문에 중단점을 설정합니다.  
  
2.  F5 키를 눌러 디버깅 세션을 시작합니다.  Visual Studio의 새 인스턴스가 만들어집니다.  
  
3.  Visual Studio의 새 인스턴스에서 "MarqueeControlTest" 솔루션을 엽니다.  **파일** 메뉴에서 **최근에 사용한 프로젝트**를 선택하여 솔루션을 쉽게 찾을 수 있습니다.  "MarqueeControlTest.sln" 솔루션 파일이 최근에 사용한 파일로 나열됩니다.  
  
4.  디자이너에서 `DemoMarqueeControl`을 엽니다.  Visual Studio의 디버깅 인스턴스에 포커스가 부여되고 중단점에서 실행이 중지됩니다.  F5 키를 눌러 디버깅 세션을 계속합니다.  
  
 이제 사용자 지정 컨트롤과 연결된 해당 사용자 지정 디자이너를 개발하고 디버깅할 수 있도록 모든 준비가 되었습니다.  이 연습의 나머지 부분에서는 컨트롤과 디자이너의 기능 구현에 대한 자세한 내용을 중점적으로 살펴봅니다.  
  
## 사용자 지정 컨트롤 구현  
 `MarqueeControl`은 약간의 사용자 지정이 포함된 <xref:System.Windows.Forms.UserControl>입니다.  이 컨트롤은 움직이는 텍스트 애니메이션을 시작하는 `Start`와 애니메이션을 중지하는 `Stop` 등 두 개의 메서드를 노출합니다.  `MarqueeControl`에는 `IMarqueeWidget` 인터페이스를 구현하는 자식 컨트롤을 포함하므로 `Start`와 `Stop`은 각 자식 컨트롤을 열거하고 `IMarqueeWidget`을 구현하는 각 자식 컨트롤에서 `StartMarquee`와 `StopMarquee` 메서드를 각각 호출합니다.  
  
 `MarqueeBorder` 및 `MarqueeText` 컨트롤의 모양은 레이아웃에 따라 좌우되므로 `MarqueeControl`은 <xref:System.Windows.Forms.Control.OnLayout%2A> 메서드를 재정의하고 이 형식의 자식 컨트롤에서 <xref:System.Windows.Forms.Control.PerformLayout%2A>을 호출합니다.  
  
 이것이 `MarqueeControl` 사용자 지정의 범위입니다.  런타임 기능은 `MarqueeBorder` 및 `MarqueeText` 컨트롤에 의해 구현되며 디자인 타임 기능은 `MarqueeBorderDesigner` 및 `MarqueeControlRootDesigner` 클래스에 의해 구현됩니다.  
  
#### 사용자 지정 컨트롤을 구현하려면  
  
1.  **코드 편집기**에서 `MarqueeControl` 소스 파일을 엽니다.  `Start` 및 `Stop` 메서드를 구현합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]  
  
2.  <xref:System.Windows.Forms.Control.OnLayout%2A> 메서드를 재정의합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]  
  
## 사용자 지정 컨트롤의 자식 컨트롤 만들기  
 `MarqueeControl`은 `MarqueeBorder` 컨트롤과 `MarqueeText` 컨트롤 등 두 종류의 자식 컨트롤을 호스팅합니다.  
  
-   `MarqueeBorder`: 이 컨트롤은 "조명"의 가장자리 둘레에 테두리를 그립니다.  조명은 차례로 깜박이므로 조명이 테두리를 따라 움직이는 것처럼 보입니다.  조명이 깜박이는 속도는 `UpdatePeriod`라는 속성으로 제어됩니다.  몇 가지 다른 사용자 지정 속성에 따라 컨트롤 모양의 다른 부분이 결정됩니다.  `StartMarquee`와 `StopMarquee`라는 두 가지 메서드는 애니메이션이 시작되고 중지되는 시점을 제어합니다.  
  
-   `MarqueeText`: 이 컨트롤은 깜박이는 문자열을 그립니다.  `MarqueeBorder` 컨트롤과 마찬가지로 텍스트가 깜박이는 속도는 `UpdatePeriod` 속성으로 제어됩니다.  `MarqueeText` 컨트롤에도 `MarqueeBorder` 컨트롤과 마찬가지로 `StartMarquee` 및 `StopMarquee` 메서드가 있습니다.  
  
 디자인 타임에 `MarqueeControlRootDesigner`에서 이 두 컨트롤 형식을 원하는 조합으로 `MarqueeControl`에 추가할 수 있습니다.  
  
 두 컨트롤의 공통 기능은 `IMarqueeWidget`이라는 인터페이스로 구성됩니다.  따라서 `MarqueeControl`은 움직이는 텍스트 관련 자식 컨트롤을 모두 찾아 특별하게 처리합니다.  
  
 주기적인 애니메이션 기능을 구현하려면 <xref:System.ComponentModel?displayProperty=fullName> 네임스페이스의 <xref:System.ComponentModel.BackgroundWorker> 개체를 사용합니다.  <xref:System.Windows.Forms.Timer> 개체를 사용할 수 있지만 `IMarqueeWidget` 개체가 많을 때는 단일 UI 스레드로 애니메이션을 따라가지 못할 수도 있습니다.  
  
#### 사용자 지정 컨트롤의 자식 컨트롤을 만들려면  
  
1.  `MarqueeControlLibrary` 프로젝트에 새 클래스 항목을 추가합니다.  새 소스 파일의 기본 이름을 "IMarqueeWidget"으로 지정합니다.  
  
2.  **코드 편집기**에서 `IMarqueeWidget` 소스 파일을 열고 다음과 같이 `class`에서 `interface`로 선언을 변경합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]  
  
3.  다음 코드를 `IMarqueeWidget` 인터페이스에 추가하여 움직이는 텍스트 애니메이션을 조작하는 두 개의 메서드와 한 개의 속성을 노출합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]  
  
4.  `MarqueeControlLibrary` 프로젝트에 새 **사용자 지정 컨트롤** 항목을 추가합니다.  새 소스 파일의 기본 이름을 "MarqueeText"로 지정합니다.  
  
5.  **도구 상자**의 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 `MarqueeText` 컨트롤로 끌어 옵니다.  이 구성 요소를 통해 `MarqueeText` 컨트롤이 비동기적으로 직접 업데이트될 수 있습니다.  
  
6.  속성 창에서 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 `WorkerReportsProgess` 및 <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> 속성을 `true`로 설정합니다.  이러한 설정을 통해 <xref:System.ComponentModel.BackgroundWorker> 구성 요소는 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트를 주기적으로 발생시키고 비동기 업데이트를 취소할 수 있습니다.  자세한 내용은 [BackgroundWorker 구성 요소](../../../../docs/framework/winforms/controls/backgroundworker-component.md)를 참조하십시오.  
  
7.  **코드 편집기**에서 `MarqueeText` 소스 파일을 엽니다.  파일의 맨 위에서 다음과 같은 네임스페이스를 가져옵니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]  
  
8.  <xref:System.Windows.Forms.Label>에서 상속하고 `IMarqueeWidget` 인터페이스를 구현하도록 `MarqueeText` 선언을 다음과 같이 변경합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]  
  
9. 노출된 속성에 해당하는 인스턴스 변수를 선언하고 해당 생성자에서 초기화합니다.  `isLit` 필드는 텍스트를 `LightColor` 속성에 지정된 색으로 그릴지 여부를 결정합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]  
  
10. `IMarqueeWidget` 인터페이스를 구현합니다.  
  
     `StartMarquee` 및 `StopMarquee` 메서드는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 및 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> 메서드를 호출하여 애니메이션을 시작하고 중지합니다.  
  
     <xref:System.ComponentModel.CategoryAttribute.Category%2A> 및 <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> 특성은 `UpdatePeriod` 속성에 적용되므로 속성 창의 "움직이는 텍스트"라는 사용자 지정 구역에 나타납니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]  
  
11. 속성 접근자를 구현합니다.  `LightColor`와 `DarkColor` 등 두 가지 속성을 클라이언트에 노출합니다.  <xref:System.ComponentModel.CategoryAttribute.Category%2A> 및 <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> 특성은 이러한 속성에 적용되므로 속성 창의 "움직이는 텍스트"라는 사용자 지정 구역에 속성이 나타납니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]  
  
12. <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 <xref:System.ComponentModel.BackgroundWorker.DoWork> 및 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트에 대한 처리기를 구현합니다.  
  
     코드에서 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>를 호출하여 애니메이션을 중지할 때까지 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기는 `UpdatePeriod`에 지정된 밀리초 동안 중지한 다음 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트를 발생시킵니다.  
  
     <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트 처리기는 텍스트의 밝은 상태와 어두운 상태를 전환하여 깜박이는 모양을 나타냅니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]  
  
13. 애니메이션을 사용하도록 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]  
  
14. F6 키를 눌러 솔루션을 빌드합니다.  
  
## MarqueeBorder 자식 컨트롤 만들기  
 `MarqueeBorder` 컨트롤은 `MarqueeText` 컨트롤보다 약간 더 복잡합니다.  속성이 더 많으며 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드에 애니메이션이 더 많이 사용되지만  원칙적으로 `MarqueeText` 컨트롤과 매우 비슷합니다.  
  
 `MarqueeBorder` 컨트롤은 자식 컨트롤을 가질 수 있으므로 <xref:System.Windows.Forms.Control.Layout> 이벤트를 인식해야 합니다.  
  
#### MarqueeBorder 컨트롤을 만들려면  
  
1.  `MarqueeControlLibrary` 프로젝트에 새 **사용자 지정 컨트롤** 항목을 추가합니다.  새 소스 파일의 기본 이름을 "MarqueeBorder"로 지정합니다.  
  
2.  **도구 상자**의 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 `MarqueeBorder` 컨트롤로 끌어 옵니다.  이 구성 요소를 통해 `MarqueeBorder` 컨트롤이 비동기적으로 직접 업데이트될 수 있습니다.  
  
3.  속성 창에서 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 `WorkerReportsProgess` 및 <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> 속성을 `true`로 설정합니다.  이러한 설정을 통해 <xref:System.ComponentModel.BackgroundWorker> 구성 요소는 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트를 주기적으로 발생시키고 비동기 업데이트를 취소할 수 있습니다.  자세한 내용은 [BackgroundWorker 구성 요소](../../../../docs/framework/winforms/controls/backgroundworker-component.md)를 참조하십시오.  
  
4.  속성 창에서 이벤트 단추를 클릭합니다.  <xref:System.ComponentModel.BackgroundWorker.DoWork> 및 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트에 처리기를 연결합니다.  
  
5.  **코드 편집기**에서 `MarqueeBorder` 소스 파일을 엽니다.  파일의 맨 위에서 다음과 같은 네임스페이스를 가져옵니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]  
  
6.  <xref:System.Windows.Forms.Panel>에서 상속하고 `IMarqueeWidget` 인터페이스를 구현하도록 `MarqueeBorder` 선언을 다음과 같이 변경합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]  
  
7.  `MarqueeBorder` 컨트롤의 상태를 관리하기 위한 두 개의 열거형, 즉 테두리를 따라 조명이 "회전"되는 방향을 결정하는 `MarqueeSpinDirection`과 조명의 모양\(사각형 또는 원형\)을 결정하는 `MarqueeLightShape`를 선언합니다.  이러한 선언을 `MarqueeBorder` 클래스 선언보다 먼저 지정합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]  
  
8.  노출된 속성에 해당하는 인스턴스 변수를 선언하고 해당 생성자에서 초기화합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]  
  
9. `IMarqueeWidget` 인터페이스를 구현합니다.  
  
     `StartMarquee` 및 `StopMarquee` 메서드는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 및 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> 메서드를 호출하여 애니메이션을 시작하고 중지합니다.  
  
     `MarqueeBorder` 컨트롤에는 자식 컨트롤이 포함될 수 있으므로 `StartMarquee` 메서드는 모든 자식 컨트롤을 열거하고 `IMarqueeWidget`을 구현하는 해당 자식 컨트롤에 대해 `StartMarquee`를 호출합니다.  `StopMarquee` 메서드에도 비슷한 구현이 사용됩니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]  
  
10. 속성 접근자를 구현합니다.  `MarqueeBorder` 컨트롤에는 이 컨트롤의 모양을 제어하는 속성이 몇 가지 있습니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]  
  
11. <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 <xref:System.ComponentModel.BackgroundWorker.DoWork> 및 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트에 대한 처리기를 구현합니다.  
  
     코드에서 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>를 호출하여 애니메이션을 중지할 때까지 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기는 `UpdatePeriod`에 지정된 밀리초 동안 중지한 다음 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트를 발생시킵니다.  
  
     <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트 처리기는 다른 조명의 밝기 상태를 결정하는 기준이 되는 "기본" 조명의 위치를 증가시키고 <xref:System.Windows.Forms.Control.Refresh%2A> 메서드를 호출하여 컨트롤이 다시 그려지도록 합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]  
  
12. 도우미 메서드인 `IsLit`와 `DrawLight`를 구현합니다.  
  
     `IsLit` 메서드는 지정된 위치의 조명 색을 결정합니다.  "밝아진" 조명은 `LightColor` 속성에 지정된 색으로 그려지고 "어두워진" 조명은 `DarkColor` 속성에 지정된 색으로 그려집니다.  
  
     `DrawLight` 메서드는 적절한 색, 모양, 위치를 사용하여 밝기를 나타냅니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]  
  
13. <xref:System.Windows.Forms.Control.OnLayout%2A> 및 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의합니다.  
  
     <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드는 `MarqueeBorder` 컨트롤의 가장자리를 따라 조명을 나타냅니다.  
  
     <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드는 `MarqueeBorder` 컨트롤의 차원에 따라 좌우되므로 레이아웃이 바뀔 때마다 이 메서드를 호출해야 합니다.  이렇게 하려면 <xref:System.Windows.Forms.Control.OnLayout%2A>을 재정의하고 <xref:System.Windows.Forms.Control.Refresh%2A>를 호출합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]  
  
## 사용자 지정 디자이너를 만들어 속성 숨기기 및 필터링  
 `MarqueeControlRootDesigner` 클래스는 루트 디자이너의 구현을 제공합니다.  `MarqueeControl`에서 작동하는 이 디자이너 외에도 특별히 `MarqueeBorder` 컨트롤에 연결되는 사용자 지정 디자이너가 필요합니다.  이 디자이너는 사용자 지정 루트 디자이너의 컨텍스트에서 적합한 사용자 지정 동작을 제공합니다.  
  
 특히 `MarqueeBorderDesigner`는 `MarqueeBorder` 컨트롤의 특정 속성을 "숨기고" 필터링하여 디자인 환경과의 상호 작용을 변경합니다.  
  
 구성 요소의 속성 접근자에 대한 호출을 차단하는 것을 "숨김"이라고 합니다. 디자이너는 숨김을 통해 사용자가 설정한 값을 추적하고 필요할 경우 디자인할 구성 요소에 이 값을 전달할 수 있습니다.  
  
 예를 들어, <xref:System.Windows.Forms.Control.Visible%2A> 및 <xref:System.Windows.Forms.Control.Enabled%2A> 속성은 `MarqueeBorderDesigner`에 의해 숨겨지며, 이로써 디자인 타임 중에 사용자가 `MarqueeBorder` 컨트롤을 표시하지 않거나 비활성화할 수 없습니다.  
  
 디자이너는 속성을 추가하고 제거할 수도 있습니다.  예를 들어, `MarqueeBorder` 컨트롤은 `LightSize` 속성에 지정된 조명의 크기를 기준으로 채우기를 프로그래밍 방식으로 설정하므로 <xref:System.Windows.Forms.Control.Padding%2A> 속성은 디자인 타임에 제거됩니다.  
  
 `MarqueeBorderDesigner`의 기본 클래스는 디자인 타임에 컨트롤에 의해 노출되는 특성, 속성 및 이벤트를 변경할 수 있는 메서드가 있는 <xref:System.ComponentModel.Design.ComponentDesigner>입니다.  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>  
  
 이러한 메서드를 사용하여 구성 요소의 공용 인터페이스를 변경할 때는 다음과 같은 규칙을 따라야 합니다.  
  
-   `PreFilter` 메서드의 항목만 추가하거나 제거합니다.  
  
-   `PostFilter` 메서드의 기존 항목만 수정합니다.  
  
-   기본 구현을 항상 `PreFilter` 메서드에서 처음 호출합니다.  
  
-   기본 구현을 항상 `PostFilter` 메서드에서 마지막으로 호출합니다.  
  
 이러한 규칙을 따르면 디자인 타임 환경의 모든 디자이너에서 디자인되는 모든 구성 요소를 일관된 방식으로 볼 수 있습니다.  
  
 <xref:System.ComponentModel.Design.ComponentDesigner> 클래스는 숨겨진 속성 값을 관리하는 데 필요한 사전을 제공하므로 특정 인스턴스 변수를 만들지 않아도 됩니다.  
  
#### 사용자 지정 디자이너를 만들어 속성을 숨기고 필터링하려면  
  
1.  **Design** 폴더를 마우스 오른쪽 단추로 클릭하고 새 클래스를 추가합니다.  소스 파일의 기본 이름을 "MarqueeBorderDesigner"로 지정합니다.  
  
2.  **코드 편집기**에서 `MarqueeBorderDesigner` 소스 파일을 엽니다.  파일의 맨 위에서 다음과 같은 네임스페이스를 가져옵니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]  
  
3.  <xref:System.Windows.Forms.Design.ParentControlDesigner>에서 상속하도록 `MarqueeBorderDesigner` 선언을 변경합니다.  
  
     `MarqueeBorder` 컨트롤에는 자식 컨트롤이 포함될 수 있으므로 `MarqueeBorderDesigner`는 부모\-자식 상호 작용을 처리하는 <xref:System.Windows.Forms.Design.ParentControlDesigner>에서 상속됩니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]  
  
4.  <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>의 기본 구현을 재정의합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]  
  
5.  <xref:System.Windows.Forms.Control.Enabled%2A> 및 <xref:System.Windows.Forms.Control.Visible%2A> 속성을 구현합니다.  이러한 구현에서는 컨트롤의 속성이 숨겨집니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]  
  
## 구성 요소의 변경 내용 처리  
 `MarqueeControlRootDesigner` 클래스는 `MarqueeControl` 인스턴스에 사용자 지정 디자인 타임 환경을 제공합니다.  대부분의 디자인 타임 기능이 <xref:System.Windows.Forms.Design.DocumentDesigner> 클래스에서 상속되므로 코드에는 구성 요소의 변경 내용 처리와 디자이너 동사 추가 등 두 가지의 구체적인 사용자 지정이 구현됩니다.  
  
 사용자가 `MarqueeControl` 인스턴스를 디자인하면 루트 디자이너에서 `MarqueeControl`과 해당 자식 컨트롤의 변경 내용을 추적합니다.  디자인 타임 환경에는 구성 요소의 상태 변경을 추적할 수 있는 편리한 서비스인 <xref:System.ComponentModel.Design.IComponentChangeService>가 제공됩니다.  
  
 <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> 메서드를 사용하여 환경에 대해 쿼리하면 이 서비스에 대한 참조를 가져올 수 있습니다.  쿼리에 성공하면 디자이너가 <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> 이벤트에 대한 처리기를 연결하고 디자인 타임에 일관된 상태를 유지하는 데 필요한 모든 작업을 수행할 수 있습니다.  
  
 `MarqueeControlRootDesigner` 클래스의 경우 `MarqueeControl`에 포함된 각 `IMarqueeWidget` 개체에 대해 <xref:System.Windows.Forms.Control.Refresh%2A>를 호출합니다.  이렇게 하면 `IMarqueeWidget` 개체가 해당 부모의 <xref:System.Windows.Forms.Control.Size%2A>와 같은 속성이 변경될 경우 적절히 다시 그려집니다.  
  
#### 구성 요소의 변경 내용을 처리하려면  
  
1.  **코드 편집기**에서 `MarqueeControlRootDesigner` 소스 파일을 열고 <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> 메서드를 재정의합니다.  <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>의 기본 구현을 호출하고 <xref:System.ComponentModel.Design.IComponentChangeService>를 쿼리합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]  
  
2.  <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A> 이벤트 처리기를 구현합니다.  보내는 구성 요소의 형식을 테스트하고 `IMarqueeWidget`이면 해당 <xref:System.Windows.Forms.Control.Refresh%2A> 메서드를 호출합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]  
  
## 사용자 지정 디자이너에 디자이너 동사 추가  
 디자이너 동사는 이벤트 처리기에 연결된 메뉴 명령입니다.  디자인 타임에 구성 요소의 바로 가기 메뉴에 디자이너 동사가 추가됩니다.  자세한 내용은 <xref:System.ComponentModel.Design.DesignerVerb>를 참조하십시오.  
  
 **테스트 실행**과 **테스트 중지** 등 두 개의 디자이너 동사를 디자이너에 추가합니다.  이러한 동사를 사용하면 디자인 타임에 `MarqueeControl`의 런타임 동작을 볼 수 있습니다.  이러한 동사는 `MarqueeControlRootDesigner`에 추가됩니다.  
  
 **테스트 실행**이 호출되면 동사 이벤트 처리기가 `MarqueeControl`에서 `StartMarquee` 메서드를 호출합니다.  **테스트 중지**가 호출되면 동사 이벤트 처리기가 `MarqueeControl`에서 `StopMarquee` 메서드를 호출합니다.  `StartMarquee` 및 `StopMarquee` 메서드 구현에서는 `IMarqueeWidget`을 구현하는 포함된 컨트롤에서 이러한 메서드를 호출하므로 포함된 모든 `IMarqueeWidget` 컨트롤도 테스트에 참여합니다.  
  
#### 사용자 지정 디자이너에 디자이너 동사를 추가하려면  
  
1.  `MarqueeControlRootDesigner` 클래스에서 `OnVerbRunTest` 및 `OnVerbStopTest`라는 이벤트 처리기를 추가합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]  
  
2.  이러한 이벤트 처리기를 해당 디자이너 동사에 연결합니다.  `MarqueeControlRootDesigner`는 해당 기본 클래스에서 <xref:System.ComponentModel.Design.DesignerVerbCollection>을 상속합니다.  새 <xref:System.ComponentModel.Design.DesignerVerb> 개체를 두 개 만들어 <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> 메서드의 이 컬렉션에 추가합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]  
  
## 사용자 지정 UITypeEditor 만들기  
 사용자를 위한 사용자 지정 디자인 타임 환경을 만들 때는 속성 창과의 사용자 지정 상호 작용을 만드는 것이 좋은 경우가 많습니다.  <xref:System.Drawing.Design.UITypeEditor>를 만들어 이 작업을 수행할 수 있습니다.  자세한 내용은 [How to: Create a UI Type Editor](../Topic/How%20to:%20Create%20a%20UI%20Type%20Editor.md)를 참조하십시오.  
  
 `MarqueeBorder` 컨트롤은 몇 가지 속성을 속성 창에 노출합니다.  이러한 속성 중 `MarqueeSpinDirection`과 `MarqueeLightShape`는 열거형으로 나타냅니다.  UI 형식 편집기 사용을 보여 주기 위해 `MarqueeLightShape` 속성에 <xref:System.Drawing.Design.UITypeEditor> 클래스가 연결됩니다.  
  
#### 사용자 지정 UI 형식 편집기를 만들려면  
  
1.  **코드 편집기**에서 `MarqueeBorder` 소스 파일을 엽니다.  
  
2.  `MarqueeBorder` 클래스 정의에서 <xref:System.Drawing.Design.UITypeEditor>의 파생 클래스인 `LightShapeEditor`를 선언합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]  
  
3.  `editorService`라는 <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> 인스턴스 변수를 선언합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]  
  
4.  <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> 메서드를 재정의합니다.  이 구현에서는 `LightShapeEditor` 표시 방법을 디자인 환경에 알려 주는 <xref:System.Drawing.Design.UITypeEditorEditStyle>을 반환합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]  
  
5.  <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> 메서드를 재정의합니다.  이 구현에서는 디자인 환경의 <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> 개체를 쿼리합니다.  쿼리에 성공하면 `LightShapeSelectionControl`을 만듭니다.  `LightShapeEditor`를 시작하기 위해 <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> 메서드가 호출됩니다.  이 호출에서 반환된 값이 디자인 환경으로 반환됩니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]  
  
## 사용자 지정 UITypeEditor에 대한 뷰 컨트롤 만들기  
  
1.  `MarqueeLightShape` 속성은 두 가지 형식의 조명 모양인 `Square`와 `Circle`을 지원합니다.  속성 창에서 이러한 값을 그래픽으로 표시하는 용도로만 사용하는 사용자 지정 컨트롤을 만듭니다.  이 사용자 지정 컨트롤은 <xref:System.Drawing.Design.UITypeEditor>에서 속성 창과 상호 작용하기 위해 사용됩니다.  
  
#### UI 형식 편집기에 대한 뷰 컨트롤을 만들려면  
  
1.  `MarqueeControlLibrary` 프로젝트에 새 <xref:System.Windows.Forms.UserControl> 항목을 추가합니다.  새 소스 파일의 기본 이름을 "LightShapeSelectionControl"로 지정합니다.  
  
2.  **도구 상자**의 <xref:System.Windows.Forms.Panel> 컨트롤 두 개를 `LightShapeSelectionControl`로 끌어 옵니다.  컨트롤 이름을 각각 `squarePanel`과 `circlePanel`로 지정합니다.  그런 다음 컨트롤을 나란히 정렬하고  두 <xref:System.Windows.Forms.Panel> 컨트롤의 <xref:System.Windows.Forms.Control.Size%2A> 속성을 \(60, 60\)으로 설정합니다.  `squarePanel` 컨트롤의 <xref:System.Windows.Forms.Control.Location%2A> 속성은 \(8, 10\)으로 설정하고  `circlePanel` 컨트롤의 <xref:System.Windows.Forms.Control.Location%2A> 속성은 \(80, 10\)으로 설정합니다.  끝으로 `LightShapeSelectionControl`의 <xref:System.Windows.Forms.Control.Size%2A> 속성은 \(150, 80\)으로 설정합니다.  
  
3.  **코드 편집기**에서 `LightShapeSelectionControl` 소스 파일을 엽니다.  파일의 맨 위에서 <xref:System.Windows.Forms.Design?displayProperty=fullName> 네임스페이스를 가져옵니다.  
  
```vb  
Imports System.Windows.Forms.Design  
```  
  
```csharp  
using System.Windows.Forms.Design;  
```  
  
1.  `squarePanel` 및 `circlePanel` 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 구현합니다.  이러한 메서드는 <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A>을 호출하여 사용자 지정 <xref:System.Drawing.Design.UITypeEditor> 편집 세션을 종료합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]  
  
2.  `editorService`라는 <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> 인스턴스 변수를 선언합니다.  
  
```vb  
Private editorService As IWindowsFormsEditorService  
```  
  
```csharp  
private IWindowsFormsEditorService editorService;  
```  
  
1.  `lightShapeValue`라는 `MarqueeLightShape` 인스턴스 변수를 선언합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]  
  
2.  `LightShapeSelectionControl` 생성자에서 `squarePanel` 및 `circlePanel` 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트에 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 연결합니다.  또한 디자인 환경의 `MarqueeLightShape` 값을 `lightShapeValue` 필드에 할당하는 생성자 오버로드를 정의합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]  
  
3.  <xref:System.ComponentModel.Component.Dispose%2A> 메서드에서 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 분리합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]  
  
4.  **솔루션 탐색기**에서 **모든 파일 표시** 단추를 클릭합니다.  LightShapeSelectionControl.Designer.cs 또는 LightShapeSelectionControl.Designer.vb 파일을 열고 <xref:System.ComponentModel.Component.Dispose%2A> 메서드의 기본 정의를 제거합니다.  
  
5.  `LightShape` 속성을 구현합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]  
  
6.  <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의합니다.  이를 구현하면 안쪽을 채운 사각형과 원이 그려집니다.  또한 선택한 값을 강조 표시하기 위해 두 도형 중 하나에 테두리가 그려집니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]  
  
## 디자이너에서 사용자 지정 컨트롤 테스트  
 이 시점에서 `MarqueeControlLibrary` 프로젝트를 빌드할 수 있습니다.  `MarqueeControl` 클래스를 상속하는 컨트롤을 만들고 폼에서 사용하여 구현을 테스트합니다.  
  
#### 사용자 지정 MarqueeControl 구현을 만들려면  
  
1.  Windows Forms 디자이너에서 `DemoMarqueeControl`을 엽니다.  이렇게 하면 `DemoMarqueeControl` 형식의 인스턴스가 만들어지고 이 인스턴스가 `MarqueeControlRootDesigner` 형식의 인스턴스에 표시됩니다.  
  
2.  **도구 상자**에서 **MarqueeControlLibrary 구성 요소** 탭을 엽니다.  선택 항목에 사용할 수 있는 `MarqueeBorder` 및 `MarqueeText` 컨트롤이 표시됩니다.  
  
3.  `MarqueeBorder` 컨트롤의 인스턴스를 `DemoMarqueeControl` 디자인 화면으로 끌어 옵니다.  이 `MarqueeBorder` 컨트롤을 부모 컨트롤에 도킹합니다.  
  
4.  `MarqueeText` 컨트롤의 인스턴스를 `DemoMarqueeControl` 디자인 화면으로 끌어 옵니다.  
  
5.  솔루션을 빌드합니다.  
  
6.  `DemoMarqueeControl`을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **테스트 실행** 옵션을 클릭하여 애니메이션을 시작합니다.  **테스트 중지**를 클릭하여 애니메이션을 중지합니다.  
  
7.  디자인 뷰에서 **Form1**을 엽니다.  
  
8.  두 개의 <xref:System.Windows.Forms.Button> 컨트롤을 폼에 놓습니다.  해당 컨트롤 이름을 `startButton`과 `stopButton`으로 지정하고 <xref:System.Windows.Forms.Control.Text%2A> 속성 값을 각각 시작과 중지로 변경합니다.  
  
9. 두 <xref:System.Windows.Forms.Button> 컨트롤에 대한 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 구현합니다.  
  
10. **도구 상자**에서 **MarqueeControlTest 구성 요소** 탭을 엽니다.  선택 항목에 사용할 수 있는 `DemoMarqueeControl`이 표시됩니다.  
  
11. `DemoMarqueeControl` 인스턴스를 **Form1** 디자인 화면으로 끌어 옵니다.  
  
12. <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에서 `Start` 및 `Stop` 메서드를 `DemoMarqueeControl`에서 호출합니다.  
  
```vb  
Private Sub startButton_Click(sender As Object, e As System.EventArgs)  
    Me.demoMarqueeControl1.Start()  
End Sub 'startButton_Click  
  
Private Sub stopButton_Click(sender As Object, e As System.EventArgs)  
Me.demoMarqueeControl1.Stop()  
End Sub 'stopButton_Click  
```  
  
```csharp  
private void startButton_Click(object sender, System.EventArgs e)  
{  
    this.demoMarqueeControl1.Start();  
}  
  
private void stopButton_Click(object sender, System.EventArgs e)  
{  
    this.demoMarqueeControl1.Stop();  
}  
```  
  
1.  `MarqueeControlTest` 프로젝트를 시작 프로젝트로 설정하여 실행합니다.  `DemoMarqueeControl`을 표시하는 폼이 나타납니다.  **시작** 단추를 클릭하여 애니메이션을 시작합니다.  텍스트가 깜박이고 테두리를 따라 조명이 이동합니다.  
  
## 다음 단계  
 `MarqueeControlLibrary`는 간단하게 구현한 사용자 지정 컨트롤과 연결된 디자이너를 보여 줍니다.  다음과 같은 방법으로 이 샘플을 좀 더 복잡하게 만들 수 있습니다.  
  
-   디자이너에서 `DemoMarqueeControl`에 대한 속성 값을 변경합니다.  `MarqueBorder` 컨트롤을 더 추가하고 해당 부모 인스턴스 안에 도킹하여 중첩된 효과를 만듭니다.  `UpdatePeriod`와 조명 관련 속성에 대한 여러 가지 설정을 테스트합니다.  
  
-   `IMarqueeWidget`의 자체 구현을 작성합니다.  예를 들어, 깜박이는 "네온 사인"이나 여러 이미지를 사용한 애니메이션 사인을 만들 수 있습니다.  
  
-   디자인 타임 환경을 구체적으로 사용자 지정합니다.  <xref:System.Windows.Forms.Control.Enabled%2A>와 <xref:System.Windows.Forms.Control.Visible%2A> 이 외의 더 많은 속성에 대한 숨김을 시도할 수 있으며 새 속성을 추가할 수 있습니다.  새 디자이너 동사를 추가하여 자식 컨트롤 도킹과 같은 일반적인 작업을 단순화합니다.  
  
-   `MarqueeControl` 사용권을 얻습니다.  자세한 내용은 [방법: 구성 요소 및 컨트롤 라이센스](../Topic/How%20to:%20License%20Components%20and%20Controls.md)를 참조하십시오.  
  
-   컨트롤이 serialize되는 방법과 컨트롤의 코드가 생성되는 방법을 제어합니다.  자세한 내용은 [동적 소스 코드 생성 및 컴파일](../../../../docs/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.UserControl>   
 <xref:System.Windows.Forms.Design.ParentControlDesigner>   
 <xref:System.Windows.Forms.Design.DocumentDesigner>   
 <xref:System.ComponentModel.Design.IRootDesigner>   
 <xref:System.ComponentModel.Design.DesignerVerb>   
 <xref:System.Drawing.Design.UITypeEditor>   
 <xref:System.ComponentModel.BackgroundWorker>   
 [How to: Create a Windows Forms Control That Takes Advantage of Design\-Time Features](../Topic/How%20to:%20Create%20a%20Windows%20Forms%20Control%20That%20Takes%20Advantage%20of%20Design-Time%20Features.md)   
 [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md)   
 [Custom Designers](../Topic/Custom%20Designers.md)   
 [.NET Shape Library: A Sample Designer](http://windowsclient.net/)