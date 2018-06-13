---
title: '연습: Visual Studio의 디자인 타임 기능을 사용하는 Windows Forms 컨트롤 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms controls, creating
- design-time functionality [Windows Forms], Windows Forms
- DocumentDesigner class [Windows Forms]
- walkthroughs [Windows Forms], controls
ms.assetid: 6f487c59-cb38-4afa-ad2e-95edacb1d626
ms.openlocfilehash: 10905df76f2b638c10b14c1dd8c181b9652ea963
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529742"
---
# <a name="walkthrough-creating-a-windows-forms-control-that-takes-advantage-of-visual-studio-design-time-features"></a>연습: Visual Studio의 디자인 타임 기능을 사용하는 Windows Forms 컨트롤 만들기
연결 된 사용자 지정 디자이너를 제작 하 여 사용자 지정 컨트롤에 대 한 디자인 타임 환경을 개선할 수 있습니다.  
  
 이 연습에서는 사용자 지정 컨트롤에 대 한 사용자 지정 디자이너를 만드는 방법을 보여 줍니다. 구현 합니다는 `MarqueeControl` 유형과 라는 연결된 된 디자이너 클래스 `MarqueeControlRootDesigner`합니다.  
  
 `MarqueeControl` 형식이 극장식 움직이는 텍스트 애니메이션된 조명 깜박이 텍스트와 같은 화면 표시를 구현 합니다.  
  
 이 컨트롤에 대 한 디자이너 디자인 환경 사용자 지정 디자인 타임 환경을 제공 하기 위해 상호 작용 합니다. 사용자 지정 디자이너를 사용 하면 사용자 지정을 어셈블할 수 `MarqueeControl` 애니메이션된 조명 및 여러 가지 조합으로 깜박이 텍스트를 구현 합니다. 다른 Windows Forms 컨트롤 같이 폼에서 어셈블된 컨트롤을 사용할 수 있습니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   프로젝트 만들기  
  
-   컨트롤 라이브러리 프로젝트 만들기  
  
-   사용자 지정 컨트롤 프로젝트 참조  
  
-   사용자 지정 컨트롤 및 해당 사용자 지정 디자이너를 정의합니다.  
  
-   사용자 지정 컨트롤의 인스턴스 만들기  
  
-   디자인 타임 디버깅에 대 한 프로젝트 설정  
  
-   사용자 지정 컨트롤 구현  
  
-   사용자 지정 컨트롤에 대 한 자식 컨트롤 만들기  
  
-   통해 자식 컨트롤 만들기  
  
-   그림자 및 필터 속성에 사용자 지정 디자이너 만들기  
  
-   구성 요소 변경 내용 처리  
  
-   사용자 지정 디자이너를 디자이너 동사를 추가합니다.  
  
-   사용자 지정 UITypeEditor 만들기  
  
-   디자이너에서 사용자 지정 컨트롤 테스트  
  
 완료 되 면 다음과 같은 사용자 지정 컨트롤 표시 됩니다.  
  
 ![가능한 MarqueeControl 배치](../../../../docs/framework/winforms/controls/media/demomarqueecontrol.gif "항목")  
  
 전체 코드 목록을 보려면 [하는 방법: Windows Forms 제어 하는 이점은의 디자인 타임 기능을 만드는](http://msdn.microsoft.com/library/8e0bad0e-56f3-43d2-bf63-a945c654d97c)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
-   충분 한 권한이을 만들고 Visual Studio가 설치 된 컴퓨터에서 Windows Forms 응용 프로그램 프로젝트를 실행할 수 있습니다.  
  
## <a name="creating-the-project"></a>프로젝트 만들기  
 첫 번째 단계는 응용 프로그램 프로젝트를 만드는 것입니다. 사용자 지정 컨트롤을 호스트 하는 응용 프로그램을 빌드하려면이 프로젝트를 사용 합니다.  
  
#### <a name="to-create-the-project"></a>프로젝트를 만들려면  
  
-   "MarqueeControlTest." 라는 Windows Forms 응용 프로그램 프로젝트 만들기 자세한 내용은 [방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하세요.  
  
## <a name="creating-a-control-library-project"></a>컨트롤 라이브러리 프로젝트 만들기  
 다음 단계는 컨트롤 라이브러리 프로젝트를 만드는 것입니다. 새 사용자 지정 컨트롤 및 해당 해당 사용자 지정 디자이너를 만듭니다.  
  
#### <a name="to-create-the-control-library-project"></a>컨트롤 라이브러리 프로젝트를 만들려면  
  
1.  Windows Forms 컨트롤 라이브러리 프로젝트를 솔루션에 추가 합니다. "MarqueeControlLibrary" 프로젝트 이름을  
  
2.  사용 하 여 **솔루션 탐색기**, 선택한 언어에 따라 이름이 "UserControl1.cs" 또는 "UserControl1.vb", 원본 파일을 삭제 하 여 프로젝트의 기본 컨트롤을 삭제 합니다. 자세한 내용은 참조 [NIB: 방법: 제거, 삭제 및 항목 제외](http://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73)합니다.  
  
3.  새로 추가 <xref:System.Windows.Forms.UserControl> 항목의 `MarqueeControlLibrary` 프로젝트. 새 소스 파일 "MarqueeControl"의 기본 이름 지정  
  
4.  사용 하 여 **솔루션 탐색기**에서 새 폴더 만들기는 `MarqueeControlLibrary` 프로젝트. 자세한 내용은 참조 [NIB: 방법: 새 프로젝트 항목 추가](http://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce)합니다. 새 폴더를 이름을 지정 "" 디자인 중"입니다.  
  
5.  마우스 오른쪽 단추로 클릭는 **디자인** 폴더는 새 클래스를 추가 합니다. 소스 파일 "MarqueeControlRootDesigner"의 기본 이름 지정  
  
6.  System.Design 어셈블리에서 유형을 사용 하므로이에 참조를 추가 해야 합니다는 `MarqueeControlLibrary` 프로젝트.  
  
    > [!NOTE]
    >  System.Design 어셈블리를 사용 하려면 프로젝트 정식 버전의.NET Framework 클라이언트 프로필 아님.NET Framework를 대상으로 해야 합니다. 대상 프레임 워크를 변경 하려면 참조 [하는 방법:.NET Framework의 버전을 대상](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework)합니다.  
  
## <a name="referencing-the-custom-control-project"></a>사용자 지정 컨트롤 프로젝트 참조  
 사용 하 여는 `MarqueeControlTest` 프로젝트 사용자 지정 컨트롤을 테스트 합니다. 에 대 한 프로젝트 참조를 추가할 때 테스트 프로젝트 사용자 지정 컨트롤을 인식 될는 `MarqueeControlLibrary` 어셈블리입니다.  
  
#### <a name="to-reference-the-custom-control-project"></a>사용자 지정 컨트롤 프로젝트를 참조 하려면  
  
-   에 `MarqueeControlTest` 프로젝트를 프로젝트 참조를 추가 `MarqueeControlLibrary` 어셈블리입니다. 사용 하는 **프로젝트** 탭에 **참조 추가** 참조 하는 대신 대화 상자는 `MarqueeControlLibrary` 어셈블리를 직접 합니다.  
  
## <a name="defining-a-custom-control-and-its-custom-designer"></a>사용자 지정 컨트롤 및 해당 사용자 지정 디자이너를 정의합니다.  
 사용자 지정 컨트롤에서 파생 되는 <xref:System.Windows.Forms.UserControl> 클래스입니다. 이렇게 하면 컨트롤이 다른 컨트롤을 포함 하 고 컨트롤이 있는 다양 한 기본 기능 제공.  
  
 사용자 지정 컨트롤에 연결 된 사용자 지정 디자이너를 갖습니다. 이 옵션을 사용 하면 고유한 디자인 환경을 제공 사용자 지정 컨트롤에 맞게 조정할 수 있습니다.  
  
 사용 하 여 컨트롤의 디자이너과 연결 된 <xref:System.ComponentModel.DesignerAttribute> 클래스입니다. 사용자 지정 컨트롤의 전체 디자인 타임 동작을 개발 하는 사용자 지정 디자이너 구현 됩니다는 <xref:System.ComponentModel.Design.IRootDesigner> 인터페이스입니다.  
  
#### <a name="to-define-a-custom-control-and-its-custom-designer"></a>사용자 지정 컨트롤 및 해당 사용자 지정 디자이너를 정의 하려면  
  
1.  열기는 `MarqueeControl` 소스 파일에는 **코드 편집기**합니다. 파일 맨 위에 있는 다음 네임 스페이스를 가져옵니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]  
  
2.  추가 <xref:System.ComponentModel.DesignerAttribute> 에 `MarqueeControl` 클래스 선언 합니다. 사용자 지정 컨트롤의 디자이너와 연결합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]  
  
3.  열기는 `MarqueeControlRootDesigner` 소스 파일에는 **코드 편집기**합니다. 파일 맨 위에 있는 다음 네임 스페이스를 가져옵니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]  
  
4.  선언을 변경 `MarqueeControlRootDesigner` 에서 상속 하는 <xref:System.Windows.Forms.Design.DocumentDesigner> 클래스입니다. 적용 된 <xref:System.ComponentModel.ToolboxItemFilterAttribute> 디자이너의 상호 작용을 지정 하는 **도구 상자**합니다.  
  
     **참고** 에 대 한 정의 `MarqueeControlRootDesigner` "MarqueeControlLibrary.Design." 라는 네임 스페이스에 묶여 있습니다 클래스 이 선언은 디자이너에에서 배치 특수 특수 네임 스페이스 디자인 관련 형식에 대 한 예약 합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]  
  
5.  생성자에 대 한 정의 `MarqueeControlRootDesigner` 클래스입니다. 삽입 한 <xref:System.Diagnostics.Trace.WriteLine%2A> 생성자 본문에 문의 합니다. 이 디버깅 목적으로 유용 합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]  
  
## <a name="creating-an-instance-of-your-custom-control"></a>사용자 지정 컨트롤의 인스턴스 만들기  
 폼에서 컨트롤의 인스턴스를 사용자 컨트롤의 사용자 지정 디자인 타임 동작을 관찰 정렬은 `MarqueeControlTest` 프로젝트.  
  
#### <a name="to-create-an-instance-of-your-custom-control"></a>사용자 지정 컨트롤의 인스턴스를 만들려면  
  
1.  새로 추가 <xref:System.Windows.Forms.UserControl> 항목의 `MarqueeControlTest` 프로젝트. 새 소스 파일 "항목"의 기본 이름 지정  
  
2.  열기는 `DemoMarqueeControl` 파일에 **코드 편집기**합니다. 파일 맨 위에 있는 가져오기는 `MarqueeControlLibrary` 네임 스페이스:  
  
```vb  
Imports MarqueeControlLibrary  
```  
  
```csharp  
using MarqueeControlLibrary;  
```  
  
1.  선언을 변경 `DemoMarqueeControl` 에서 상속 하는 `MarqueeControl` 클래스입니다.  
  
2.  프로젝트를 빌드합니다.  
  
3.  Windows Forms 디자이너에서 `Form1`을 엽니다.  
  
4.  찾을 **MarqueeControlTest 구성 요소** 탭에 **도구 상자** 엽니다. 끌어서는 `DemoMarqueeControl` 에서 **도구 상자** 폼으로 합니다.  
  
5.  프로젝트를 빌드합니다.  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a>디자인 타임 디버깅에 대 한 프로젝트 설정  
 사용자 지정 디자인 타임 환경을 개발 하는 경우 컨트롤 및 구성 요소를 디버그 해야 합니다. 디자인 타임에 디버깅을 허용 하도록 프로젝트를 설정 하는 간단한 방법이 있습니다. 자세한 내용은 참조 [연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버깅](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)합니다.  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a>디자인 타임 디버깅을 위해 프로젝트를 설정 하려면  
  
1.  마우스 오른쪽 단추로 클릭는 `MarqueeControlLibrary` 프로젝트를 마우스 선택 **속성**합니다.  
  
2.  "MarqueeControlLibrary 속성 페이지" 대화 상자에서 선택 된 **디버그** 페이지.  
  
3.  에 **시작 작업** 섹션에서 **시작 외부 프로그램**합니다. 됩니다. Visual Studio의 개별 인스턴스 디버깅 이므로 줄임표를 클릭 (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton"))를 Visual Studio IDE에 대 한 찾아보기 단추입니다. 실행 파일의 이름이 devenv.exe를 하 고 경로 %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe 기본 위치에 설치한 경우.  
  
4.  대화 상자를 닫으려면 확인을 클릭 합니다.  
  
5.  마우스 오른쪽 단추로 클릭는 `MarqueeControlLibrary` 프로젝트 및 "시작 프로젝트로 설정"이 디버깅 구성을 사용 하도록 설정 하려면 선택 합니다.  
  
## <a name="checkpoint"></a>검사점  
 이제 사용자 지정 컨트롤의 디자인 타임 동작을 디버그 준비가 되었습니다. 디버깅 환경 올바르게 설정 되어 있는지를 확인 한 후에 사용자 지정 컨트롤 및 사용자 지정 디자이너 간의 연결을 테스트 합니다.  
  
#### <a name="to-test-the-debugging-environment-and-the-designer-association"></a>디버깅 환경 및 디자이너 연결을 테스트 하려면  
  
1.  열기는 `MarqueeControlRootDesigner` 소스 파일에는 **코드 편집기** 중단점을 설정 하 고는 <xref:System.Diagnostics.Trace.WriteLine%2A> 문.  
  
2.  F5 키를 눌러 디버깅 세션을 시작 합니다. Note Visual Studio의 새 인스턴스가 생성 됩니다.  
  
3.  Visual Studio의 새 인스턴스를 "MarqueeControlTest" 솔루션을 엽니다. 선택 하 여 솔루션을 쉽게 찾을 **최근에 사용한 프로젝트** 에서 **파일** 메뉴. 가장 최근에 사용 된 대로 "MarqueeControlTest.sln" 솔루션 파일을 나열 됩니다.  
  
4.  열기는 `DemoMarqueeControl` 디자이너에서 합니다. Visual Studio의 디버깅 인스턴스에 포커스를 획득 하 고 중단점에서 실행이 중지 note 합니다. F5 키를 눌러 디버깅 세션을 계속 합니다.  
  
 이 시점에서 모든 항목은에서 개발 하 고 사용자 지정 컨트롤 및 연결된 된 사용자 지정 디자이너를 디버깅할 수 있습니다. 이 연습의 나머지 부분에서는의 디자이너 및 컨트롤의 기능을 구현 세부 사항을 중점적으로 살펴봅니다.  
  
## <a name="implementing-your-custom-control"></a>사용자 지정 컨트롤 구현  
 `MarqueeControl` 은 한 <xref:System.Windows.Forms.UserControl> 와 약간의 사용자 지정 합니다. 두 개의 메서드를 노출: `Start`, 움직이는 텍스트 애니메이션을 시작 하 고 `Stop`, 애니메이션을 중지 하 합니다. 때문에 `MarqueeControl` 구현 하는 자식 컨트롤을 포함는 `IMarqueeWidget` 인터페이스를 `Start` 및 `Stop` 각 자식 컨트롤과 호출 열거는 `StartMarquee` 및 `StopMarquee` 메서드, 각 자식 컨트롤에 각각 구현 하는 `IMarqueeWidget`합니다.  
  
 모양을 `MarqueeBorder` 및 `MarqueeText` 컨트롤의 레이아웃에 따라 달라 집니다. 하므로 `MarqueeControl` 재정의 <xref:System.Windows.Forms.Control.OnLayout%2A> 메서드 및 호출 <xref:System.Windows.Forms.Control.PerformLayout%2A> 이 형식의 자식 컨트롤에 합니다.  
  
 이 범위는 `MarqueeControl` 사용자 지정 합니다. 런타임 기능에서 구현 되는 `MarqueeBorder` 및 `MarqueeText` 컨트롤 및 디자인 타임 기능에서 구현 되는 `MarqueeBorderDesigner` 및 `MarqueeControlRootDesigner` 클래스입니다.  
  
#### <a name="to-implement-your-custom-control"></a>사용자 지정 컨트롤을 구현 하려면  
  
1.  열기는 `MarqueeControl` 소스 파일에는 **코드 편집기**합니다. 구현 된 `Start` 및 `Stop` 메서드.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]  
  
2.  <xref:System.Windows.Forms.Control.OnLayout%2A> 메서드를 재정의합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]  
  
## <a name="creating-a-child-control-for-your-custom-control"></a>사용자 지정 컨트롤에 대 한 자식 컨트롤 만들기  
 `MarqueeControl` 두 종류의 자식 컨트롤을 호스팅할:는 `MarqueeBorder` 제어 및 `MarqueeText` 제어 합니다.  
  
-   `MarqueeBorder`:이 컨트롤의 가장자리 주위 "lights"의 테두리를 그립니다. 조명을 없으므로 테두리 이동할 것 표시 순서 대로 플래시 합니다. 조명을 깜박이 속도 라는 속성에 의해 제어 됩니다 `UpdatePeriod`합니다. 다른 몇 가지 사용자 지정 속성은 컨트롤의 모양의 다른 측면을 결정합니다. 라는 메서드가 2 개 `StartMarquee` 및 `StopMarquee`, 애니메이션의 시작 및 중지 시기를 제어 합니다.  
  
-   `MarqueeText`:이 컨트롤은 깜박이 문자열을 그립니다. 마찬가지로 `MarqueeBorder` 컨트롤, 텍스트 깜박이 속도 의해 제어 됩니다는 `UpdatePeriod` 속성입니다. `MarqueeText` 컨트롤에는 `StartMarquee` 및 `StopMarquee` 공통 된 메서드는 `MarqueeBorder` 제어 합니다.  
  
 디자인 타임에는 `MarqueeControlRootDesigner` 이러한 두 가지 컨트롤 형식에 추가할 수 있습니다는 `MarqueeControl` 의 조합입니다.  
  
 두 컨트롤의 일반적인 기능 이라는 인터페이스로 분석 되어 `IMarqueeWidget`합니다. 이 통해는 `MarqueeControl` 을 움직이는 텍스트와 관련 된 자식 컨트롤을 찾아 특별 한 처리를 제공 합니다.  
  
 주기적인 애니메이션 기능을 구현 하려면 사용할 <xref:System.ComponentModel.BackgroundWorker> 에서 개체는 <xref:System.ComponentModel?displayProperty=nameWithType> 네임 스페이스입니다. 사용할 수 있습니다 <xref:System.Windows.Forms.Timer> 개체 있지만 많은 `IMarqueeWidget` 개체가 단일 UI 스레드에서 애니메이션을 지속할 수 없습니다.  
  
#### <a name="to-create-a-child-control-for-your-custom-control"></a>사용자 지정 컨트롤에 대 한 자식 컨트롤을 만들려면  
  
1.  새 클래스 항목을 추가 `MarqueeControlLibrary` 프로젝트. 새 소스 파일 "IMarqueeWidget"의 기본 이름 지정  
  
2.  열기는 `IMarqueeWidget` 소스 파일에는 **코드 편집기** 에서 선언을 변경 하 고 `class` 를 `interface`:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]  
  
3.  다음 코드를 추가 하는 `IMarqueeWidget` 조작할 움직이는 텍스트 애니메이션 하는 속성을 두 개의 메서드를 노출 하는 인터페이스:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]  
  
4.  새로 추가 **사용자 지정 컨트롤** 항목의 `MarqueeControlLibrary` 프로젝트. 새 소스 파일 "통해"의 기본 이름 지정  
  
5.  끌어서는 <xref:System.ComponentModel.BackgroundWorker> 에서 구성 요소는 **도구 상자** 에 프로그램 `MarqueeText` 제어 합니다. 이 구성에서 `MarqueeText` 요소를 제어 합니다.  
  
6.  속성 창에서 설정 된 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 `WorkerReportsProgess` 및 <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> 속성을 `true`합니다. 이러한 설정을 사용 하는 <xref:System.ComponentModel.BackgroundWorker> 주기적으로 발생 하는 구성 요소는 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트 고 작업을 비동기 업데이트를 취소 합니다. 자세한 내용은 참조 [BackgroundWorker 구성 요소](../../../../docs/framework/winforms/controls/backgroundworker-component.md)합니다.  
  
7.  열기는 `MarqueeText` 소스 파일에는 **코드 편집기**합니다. 파일 맨 위에 있는 다음 네임 스페이스를 가져옵니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]  
  
8.  선언을 변경 `MarqueeText` 상속할 <xref:System.Windows.Forms.Label> 및 구현 하는 `IMarqueeWidget` 인터페이스:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]  
  
9. 노출된 된 속성에 해당 하는 인스턴스 변수를 선언 하 고 생성자에서 초기화 합니다. `isLit` 필드 텍스트에 지정 된 색에 그릴 수 있는지 여부를 결정은 `LightColor` 속성입니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]  
  
10. `IMarqueeWidget` 인터페이스를 구현합니다.  
  
     `StartMarquee` 및 `StopMarquee` 메서드 호출는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 및 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> 메서드 시작 하 고 애니메이션을 중지 합니다.  
  
     <xref:System.ComponentModel.CategoryAttribute.Category%2A> 및 <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> 특성에 적용 되는 `UpdatePeriod` "움직이는 텍스트입니다." 라는 속성 창의 사용자 지정 섹션에 나타나는 속성  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]  
  
11. 속성 접근자를 구현 합니다. 클라이언트에 두 개의 속성을 노출 합니다: `LightColor` 및 `DarkColor`합니다. <xref:System.ComponentModel.CategoryAttribute.Category%2A> 및 <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> 특성이 속성이 속성 창 "움직이는 텍스트입니다." 라는 사용자 지정 섹션에 표시 되므로 이러한 속성에 적용 됩니다  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]  
  
12. 구현에 대 한 처리기는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 <xref:System.ComponentModel.BackgroundWorker.DoWork> 및 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트입니다.  
  
     <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기에 지정 된 밀리초 수에 대 한 대기 `UpdatePeriod` 발생 하는 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트에 코드를 호출 하 여 애니메이션 중지 될 때까지 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>합니다.  
  
     <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트 처리기에 밝은 영역과 어두운 상태로 깜박임의 나타내기 위해 텍스트 해제 합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]  
  
13. 재정의 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드 애니메이션을 사용 하도록 합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]  
  
14. F6 키를 눌러 솔루션을 빌드합니다.  
  
## <a name="create-the-marqueeborder-child-control"></a>통해 자식 컨트롤 만들기  
 `MarqueeBorder` 컨트롤은 보다 약간 더 복잡는 `MarqueeText` 제어 합니다. 에 더 많은 속성 및에서 애니메이션의 <xref:System.Windows.Forms.Control.OnPaint%2A> 방법은 조금 더 복잡 합니다. 원칙적으로 유사 하지만는 `MarqueeText` 제어 합니다.  
  
 때문에 `MarqueeBorder` 컨트롤에 자식 컨트롤이 있을 수 있습니다, 알고 있어야 하는 데 필요한 <xref:System.Windows.Forms.Control.Layout> 이벤트입니다.  
  
#### <a name="to-create-the-marqueeborder-control"></a>통해를 만들려면  
  
1.  새로 추가 **사용자 지정 컨트롤** 항목의 `MarqueeControlLibrary` 프로젝트. 새 소스 파일 "통해"의 기본 이름 지정  
  
2.  끌어서는 <xref:System.ComponentModel.BackgroundWorker> 에서 구성 요소는 **도구 상자** 에 프로그램 `MarqueeBorder` 제어 합니다. 이 구성에서 `MarqueeBorder` 요소를 제어 합니다.  
  
3.  속성 창에서 설정 된 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 `WorkerReportsProgess` 및 <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> 속성을 `true`합니다. 이러한 설정을 사용 하는 <xref:System.ComponentModel.BackgroundWorker> 주기적으로 발생 하는 구성 요소는 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트 고 작업을 비동기 업데이트를 취소 합니다. 자세한 내용은 참조 [BackgroundWorker 구성 요소](../../../../docs/framework/winforms/controls/backgroundworker-component.md)합니다.  
  
4.  속성 창의 이벤트 단추를 클릭 합니다. 연결에 대 한 처리기는 <xref:System.ComponentModel.BackgroundWorker.DoWork> 및 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트입니다.  
  
5.  열기는 `MarqueeBorder` 소스 파일에는 **코드 편집기**합니다. 파일 맨 위에 있는 다음 네임 스페이스를 가져옵니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]  
  
6.  선언을 변경 `MarqueeBorder` 상속할 <xref:System.Windows.Forms.Panel> 및 구현 하는 `IMarqueeWidget` 인터페이스입니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]  
  
7.  관리 하기 위한 두 개의 열거형 선언는 `MarqueeBorder` 컨트롤의 상태가: `MarqueeSpinDirection`는 조명 "회전" 테두리는 방향을 결정 하 및 `MarqueeLightShape`, (사각형 또는 순환) 광원의 모양을 결정 하는 합니다. 이러한 선언을 `MarqueeBorder` 클래스 선언 합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]  
  
8.  노출된 된 속성에 해당 하는 인스턴스 변수를 선언 하 고 생성자에서 초기화 합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]  
  
9. `IMarqueeWidget` 인터페이스를 구현합니다.  
  
     `StartMarquee` 및 `StopMarquee` 메서드 호출는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 및 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> 메서드 시작 하 고 애니메이션을 중지 합니다.  
  
     때문에 `MarqueeBorder` 컨트롤에는 자식 컨트롤을 포함할 수는 `StartMarquee` 메서드 열거 모든 자식 컨트롤을 호출 `StartMarquee` 에 구현 하는 `IMarqueeWidget`합니다. `StopMarquee` 메서드에 구현 방법이 비슷합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]  
  
10. 속성 접근자를 구현 합니다. `MarqueeBorder` 컨트롤에 모양을 제어 하기 위한 몇 가지 속성이 있습니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]  
  
11. 구현에 대 한 처리기는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 <xref:System.ComponentModel.BackgroundWorker.DoWork> 및 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트입니다.  
  
     <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기에 지정 된 밀리초 수에 대 한 대기 `UpdatePeriod` 발생 하는 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트에 코드를 호출 하 여 애니메이션 중지 될 때까지 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>합니다.  
  
     <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트 처리기는 다른 조명의 밝기 상태 확인 되 "기본" 밝은 테마와 호출의 위치를 증가 시킵니다.는 <xref:System.Windows.Forms.Control.Refresh%2A> 메서드를 누르면 컨트롤이 그려집니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]  
  
12. 도우미 메서드를 구현 `IsLit` 및 `DrawLight`합니다.  
  
     `IsLit` 메서드는 지정 된 위치의 광원의 색을 결정 합니다. 에 지정 된 색으로 "켜져" lights 그려집니다는 `LightColor` 속성을 "어두운" 되는 것에 지정 된 색에 그려집니다는 `DarkColor` 속성입니다.  
  
     `DrawLight` 메서드 적절 한 색, 모양 및 위치를 사용 하 여 빛을 그립니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]  
  
13. 재정의 <xref:System.Windows.Forms.Control.OnLayout%2A> 및 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.  
  
     <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드의 가장자리를 따라 조명을 `MarqueeBorder` 제어 합니다.  
  
     때문에 <xref:System.Windows.Forms.Control.OnPaint%2A> 방법은의 크기에 따라 달라 집니다는 `MarqueeBorder` 레이아웃 변경 될 때마다 호출 해야 하는 컨트롤입니다. 이를 위해 재정의 <xref:System.Windows.Forms.Control.OnLayout%2A> 호출 <xref:System.Windows.Forms.Control.Refresh%2A>합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]  
  
## <a name="creating-a-custom-designer-to-shadow-and-filter-properties"></a>그림자 및 필터 속성에 사용자 지정 디자이너 만들기  
 `MarqueeControlRootDesigner` 루트 디자이너에 대 한 구현을 제공 합니다. 작동 하는 외에도이 디자이너는 `MarqueeControl`, 특히 연결 된 사용자 지정 디자이너를 해야 합니다는 `MarqueeBorder` 제어 합니다. 이 디자이너는 사용자 지정 루트 디자이너의 컨텍스트에서 적절 한 사용자 지정 동작을 제공 합니다.  
  
 특히,는 `MarqueeBorderDesigner` "그림자" 되며에서 특정 속성을 필터링 하는 `MarqueeBorder` 컨트롤을 디자인 환경와의 상호 작용을 변경 합니다.  
  
 "숨김"으로 알려져 구성 요소의 속성 접근자에 대 한 호출을 가로채 하면 디자이너는 사용자가 설정한 값을 추적 하 고 필요에 따라 디자인 하 고 구성 요소에 해당 값을 전달 합니다.  
  
 이 예는 <xref:System.Windows.Forms.Control.Visible%2A> 및 <xref:System.Windows.Forms.Control.Enabled%2A> 속성에 의해 숨겨질 수는 `MarqueeBorderDesigner`, 과정에서 사용자를 방지 하는 `MarqueeBorder` 보이지 않는 또는 디자인 타임 동안 비활성화 된 컨트롤입니다.  
  
 또한 디자이너 추가 하 고 속성을 제거 합니다. 이 예는 <xref:System.Windows.Forms.Control.Padding%2A> 디자인 타임에 속성을 제거할 수는 `MarqueeBorder` 로 지정 된 광원의 크기에 따라 있는 안쪽 여백을 프로그래밍 방식으로 설정 하는 컨트롤은 `LightSize` 속성입니다.  
  
 에 대 한 기본 클래스 `MarqueeBorderDesigner` 은 <xref:System.ComponentModel.Design.ComponentDesigner>, 특성, 속성 및 디자인 타임에 컨트롤에서 노출 하는 이벤트를 변경할 수 있는 메서드가 있는:  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>  
  
 이러한 메서드를 사용 하는 구성 요소의 공용 인터페이스를 변경할 때는 이러한 규칙을 따라야 합니다.  
  
-   에 항목 추가 또는 제거는 `PreFilter` 만 메서드  
  
-   기존 항목을 수정할는 `PostFilter` 만 메서드  
  
-   항상 기본 구현을 먼저 호출는 `PreFilter` 메서드  
  
-   항상 기본 구현을 마지막는 `PostFilter` 메서드  
  
 이러한 규칙을 따르는에서는 디자인 타임 환경에서 모든 디자이너의 모든 구성 요소를 디자인 하 고 일관 된 보기 합니다.  
  
 <xref:System.ComponentModel.Design.ComponentDesigner> 클래스 특정 인스턴스 변수를 만들 필요는 섀도 처리 된 속성의 값을 관리 하기 위한 사전을 제공 합니다.  
  
#### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a>그림자 및 필터 속성을 사용자 지정 디자이너를 만들려면  
  
1.  마우스 오른쪽 단추로 클릭는 **디자인** 폴더는 새 클래스를 추가 합니다. 소스 파일 "MarqueeBorderDesigner"의 기본 이름 지정  
  
2.  열기는 `MarqueeBorderDesigner` 소스 파일에는 **코드 편집기**합니다. 파일 맨 위에 있는 다음 네임 스페이스를 가져옵니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]  
  
3.  선언을 변경 `MarqueeBorderDesigner` 상속할 <xref:System.Windows.Forms.Design.ParentControlDesigner>합니다.  
  
     때문에 `MarqueeBorder` 컨트롤에는 자식 컨트롤을 포함할 수 `MarqueeBorderDesigner` 에서 상속 <xref:System.Windows.Forms.Design.ParentControlDesigner>, 부모-자식 상호 작용을 처리 하 합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]  
  
4.  기본 구현을 재정의 <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]  
  
5.  <xref:System.Windows.Forms.Control.Enabled%2A> 및 <xref:System.Windows.Forms.Control.Visible%2A> 속성을 구현합니다. 이러한 구현은 컨트롤의 속성을 숨깁니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]  
  
## <a name="handling-component-changes"></a>구성 요소 변경 내용 처리  
 `MarqueeControlRootDesigner` 클래스에 대 한 사용자 지정 디자인 타임 환경을 제공 프로그램 `MarqueeControl` 인스턴스. 대부분의 디자인 타임 기능이에서 상속 되는 <xref:System.Windows.Forms.Design.DocumentDesigner> 클래스 하므로 두 개의 특정 사용자 지정을 구현 하 여 코드에서: 구성 요소 변경 내용을 처리 하 고 디자이너 동사를 추가 합니다.  
  
 사용자가 디자인으로 자신의 `MarqueeControl` 인스턴스, 루트 디자이너의 변경 내용을 추적 하는 `MarqueeControl` 및 해당 자식 컨트롤입니다. 편리 하 게 서비스를 제공 하는 디자인 타임 환경 <xref:System.ComponentModel.Design.IComponentChangeService>구성 요소의 상태 변경 사항 추적에 대 한 합니다.  
  
 이 서비스에 대 한 참조를 사용 하 여 환경에 쿼리하여 획득는 <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> 메서드. 쿼리가 성공 하는 경우 디자이너에 대 한 처리기에서 연결할 수는 <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> 이벤트 디자인 타임에 일관 된 상태로 유지 하기 위해 필요한 모든 작업을 수행 합니다.  
  
 경우에 `MarqueeControlRootDesigner` 호출 클래스는 <xref:System.Windows.Forms.Control.Refresh%2A> 각 메서드 `IMarqueeWidget` 에 포함 된 개체는 `MarqueeControl`합니다. 이렇게 하면는 `IMarqueeWidget` 그려집니다 적절 하 게 같은 부모 항목의 속성 때 개체 <xref:System.Windows.Forms.Control.Size%2A> 변경 됩니다.  
  
#### <a name="to-handle-component-changes"></a>구성 요소 변경을 처리 하려면  
  
1.  열기는 `MarqueeControlRootDesigner` 소스 파일에는 **코드 편집기** 재정의 <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> 메서드. 기본 구현을 호출 <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> 및에 대 한 쿼리는 <xref:System.ComponentModel.Design.IComponentChangeService>합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]  
  
2.  구현 된 <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A> 이벤트 처리기입니다. 보내는 구성 요소의 형식을 테스트 하 고는 `IMarqueeWidget`, 호출 해당 <xref:System.Windows.Forms.Control.Refresh%2A> 메서드.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]  
  
## <a name="adding-designer-verbs-to-your-custom-designer"></a>사용자 지정 디자이너를 디자이너 동사를 추가합니다.  
 디자이너 동사는 이벤트 처리기에 연결 된 메뉴 명령입니다. 디자이너 동사는 디자인 타임에 구성 요소의 바로 가기 메뉴에 추가 됩니다. 자세한 내용은 <xref:System.ComponentModel.Design.DesignerVerb>을 참조하세요.  
  
 두 개의 디자이너 동사를 디자이너에 추가 됩니다: **테스트 실행** 및 **테스트 중지**합니다. 이러한 동사를 사용 하면의 런타임 동작을 볼 수 있습니다는 `MarqueeControl` 디자인 타임에 있습니다. 이러한 동사에 추가 되는 `MarqueeControlRootDesigner`합니다.  
  
 때 **테스트 실행** 은 호출 동사 이벤트 처리기 호출 됩니다는 `StartMarquee` 에서 메서드는 `MarqueeControl`합니다. 때 **테스트 중지** 은 호출 동사 이벤트 처리기 호출 됩니다는 `StopMarquee` 에서 메서드는 `MarqueeControl`합니다. 구현에서 `StartMarquee` 및 `StopMarquee` 메서드를 구현 하는 포함 된 컨트롤에서 이러한 메서드를 호출 `IMarqueeWidget`하므로 포함 된 모든, `IMarqueeWidget` 컨트롤은 테스트에도 참여 합니다.  
  
#### <a name="to-add-designer-verbs-to-your-custom-designers"></a>사용자 지정 디자이너를 디자이너 동사를 추가 하려면  
  
1.  에 `MarqueeControlRootDesigner` 클래스, 이벤트 처리기 라는 추가 `OnVerbRunTest` 및 `OnVerbStopTest`합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]  
  
2.  해당 디자이너 동사에 이러한 이벤트 처리기를 연결 합니다. `MarqueeControlRootDesigner` 상속 된 <xref:System.ComponentModel.Design.DesignerVerbCollection> 해당 기본 클래스에서 합니다. 만들려는 두 개의 새 <xref:System.ComponentModel.Design.DesignerVerb> 개체에서이 컬렉션에 추가 하는 <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> 메서드.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]  
  
## <a name="creating-a-custom-uitypeeditor"></a>사용자 지정 UITypeEditor 만들기  
 사용자에 대 한 사용자 지정 디자인 타임 환경을 만들 때을 속성 창에서 사용자 지정 상호 작용을 만들려는 것이 좋습니다. 만들어서이 작업을 수행할 수는 <xref:System.Drawing.Design.UITypeEditor>합니다. 자세한 내용은 참조 [하는 방법: UI 형식 편집기 만들기](http://msdn.microsoft.com/library/292c6e33-8d85-4012-9b51-05835a6f6dfd)합니다.  
  
 `MarqueeBorder` 컨트롤 속성 창에서 여러 가지 속성을 노출 합니다. 이러한 속성 중 `MarqueeSpinDirection` 및 `MarqueeLightShape` 열거형으로 표시 됩니다. UI 유형 편집기의 사용을 설명 하기는 `MarqueeLightShape` 속성이 연결 된 갖는 <xref:System.Drawing.Design.UITypeEditor> 클래스입니다.  
  
#### <a name="to-create-a-custom-ui-type-editor"></a>사용자 지정 UI 형식 편집기를 만들려면  
  
1.  열기는 `MarqueeBorder` 소스 파일에는 **코드 편집기**합니다.  
  
2.  정의에 `MarqueeBorder` 클래스 라는 클래스 선언 `LightShapeEditor` 에서 파생 된 <xref:System.Drawing.Design.UITypeEditor>합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]  
  
3.  선언 된 <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> 라는 인스턴스 변수 `editorService`합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]  
  
4.  <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> 메서드를 재정의합니다. 이 구현은 <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>, 디자인 환경에서 표시 하는 방법을 지시는 `LightShapeEditor`합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]  
  
5.  <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> 메서드를 재정의합니다. 이 구현 디자인 환경에 대 한 쿼리는 <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> 개체입니다. 성공적으로 만듭니다는 `LightShapeSelectionControl`합니다. <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> 메서드를 호출을 시작 하 여 `LightShapeEditor`합니다. 이 호출의 반환 값은 디자인 환경에 반환 됩니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]  
  
## <a name="creating-a-view-control-for-your-custom-uitypeeditor"></a>사용자 지정 UITypeEditor 사용자에 대 한 View 컨트롤 만들기  
  
1.  `MarqueeLightShape` 속성에는 두 가지 유형의 밝은 셰이프 지원: `Square` 및 `Circle`합니다. 속성 창에서 이러한 값을 그래픽으로 표시 하는 목적 으로만 사용 되는 사용자 지정 컨트롤을 만듭니다. 이 사용자 지정 컨트롤에서 사용할 프로그램 <xref:System.Drawing.Design.UITypeEditor> 속성 창와 상호 작용할 수 있습니다.  
  
#### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a>컨트롤을 만들려면 보기에 대 한 사용자 지정 UI 형식 편집기  
  
1.  새로 추가 <xref:System.Windows.Forms.UserControl> 항목의 `MarqueeControlLibrary` 프로젝트. 새 소스 파일 "쿼리에 성공 합니다."의 기본 이름 지정  
  
2.  두 개 <xref:System.Windows.Forms.Panel> 에서 제어는 **도구 상자** 에 `LightShapeSelectionControl`합니다. 이름을 지정 하 여 `squarePanel` 및 `circlePanel`합니다. 나란히 놓고 정렬 합니다. 설정의 <xref:System.Windows.Forms.Control.Size%2A> 모두의 속성이 <xref:System.Windows.Forms.Panel> 하는 제어 (60, 60)입니다. 설정의 <xref:System.Windows.Forms.Control.Location%2A> 의 속성에서 `squarePanel` 제어를 (8, 10). 설정의 <xref:System.Windows.Forms.Control.Location%2A> 의 속성에서 `circlePanel` 제어를 (80, 10). 마지막으로 설정 된 <xref:System.Windows.Forms.Control.Size%2A> 속성의는 `LightShapeSelectionControl` 를 (150, 80).  
  
3.  열기는 `LightShapeSelectionControl` 소스 파일에는 **코드 편집기**합니다. 파일 맨 위에 있는 가져오기는 <xref:System.Windows.Forms.Design?displayProperty=nameWithType> 네임 스페이스:  
  
```vb  
Imports System.Windows.Forms.Design  
```  
  
```csharp  
using System.Windows.Forms.Design;  
```  
  
1.  구현 <xref:System.Windows.Forms.Control.Click> 에 대 한 이벤트 처리기는 `squarePanel` 및 `circlePanel` 컨트롤입니다. 이러한 메서드는 호출 <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> 사용자 지정 종료 <xref:System.Drawing.Design.UITypeEditor> 세션을 편집 합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]  
  
2.  선언 된 <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> 라는 인스턴스 변수 `editorService`합니다.  
  
```vb  
Private editorService As IWindowsFormsEditorService  
```  
  
```csharp  
private IWindowsFormsEditorService editorService;  
```  
  
1.  선언 된 `MarqueeLightShape` 라는 인스턴스 변수 `lightShapeValue`합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]  
  
2.  에 `LightShapeSelectionControl` 생성자 연결는 <xref:System.Windows.Forms.Control.Click> 에 이벤트 처리기는 `squarePanel` 및 `circlePanel` 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트입니다. 또한 할당 하는 생성자 오버 로드를 정의 `MarqueeLightShape` 디자인 환경에서 값의 `lightShapeValue` 필드입니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]  
  
3.  에 <xref:System.ComponentModel.Component.Dispose%2A> 메서드를 분리 된 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기입니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]  
  
4.  **솔루션 탐색기**에서 **모든 파일 표시** 단추를 클릭합니다. 기본 정의 제거 하 고 LightShapeSelectionControl.Designer.cs 또는 LightShapeSelectionControl.Designer.vb 파일을 열고는 <xref:System.ComponentModel.Component.Dispose%2A> 메서드.  
  
5.  `LightShape` 속성을 구현합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]  
  
6.  <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의합니다. 이 구현은 채워진 사각형과 원을 그려집니다. 그는 또한 강조 표시 선택 된 값 도형 둘레에 테두리를 그려서 합니다.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]  
  
## <a name="testing-your-custom-control-in-the-designer"></a>디자이너에서 사용자 지정 컨트롤 테스트  
 이 시점에서 빌드할 수 있습니다는 `MarqueeControlLibrary` 프로젝트. 상속 되는 컨트롤을 만들어 구현을 테스트는 `MarqueeControl` 클래스 및 폼에 사용 합니다.  
  
#### <a name="to-create-a-custom-marqueecontrol-implementation"></a>사용자를 만들려면  
  
1.  Windows Forms 디자이너에서 `DemoMarqueeControl`을 엽니다. 인스턴스를 만들고이 `DemoMarqueeControl` 입력 하 고 인스턴스의 표시는 `MarqueeControlRootDesigner` 유형입니다.  
  
2.  에 **도구 상자**열고는 **MarqueeControlLibrary 구성 요소** 탭 합니다. 표시 됩니다는 `MarqueeBorder` 및 `MarqueeText` 선택할 수 있는 컨트롤입니다.  
  
3.  인스턴스를 끌어는 `MarqueeBorder` 컨트롤을 끌어와 `DemoMarqueeControl` 디자인 화면입니다. 이 도킹 `MarqueeBorder` 부모 컨트롤을 제어 합니다.  
  
4.  인스턴스를 끌어는 `MarqueeText` 컨트롤을 끌어와 `DemoMarqueeControl` 디자인 화면입니다.  
  
5.  솔루션을 빌드합니다.  
  
6.  마우스 오른쪽 단추로 클릭는 `DemoMarqueeControl` 및 바로 가기 메뉴 선택에서은 **테스트 실행** 애니메이션을 시작 하는 옵션입니다. 클릭 **테스트 중지** 여 애니메이션을 중지 합니다.  
  
7.  열기 **Form1** 디자인 뷰에서 합니다.  
  
8.  두 개의 배치 <xref:System.Windows.Forms.Button> 폼에서 컨트롤입니다. 이름을 지정 하 여 `startButton` 및 `stopButton`, 변경 하 고는 <xref:System.Windows.Forms.Control.Text%2A> 속성 값을 **시작** 및 **중지**각각.  
  
9. 구현 <xref:System.Windows.Forms.Control.Click> 모두에 대 한 이벤트 처리기 <xref:System.Windows.Forms.Button> 컨트롤입니다.  
  
10. 에 **도구 상자**열고는 **MarqueeControlTest 구성 요소** 탭 합니다. 표시 됩니다는 `DemoMarqueeControl` 선택할 수 있습니다.  
  
11. 인스턴스를 끌어 `DemoMarqueeControl` 에 **Form1** 디자인 화면입니다.  
  
12. 에 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기 호출의 `Start` 및 `Stop` 에 대 한 메서드는 `DemoMarqueeControl`합니다.  
  
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
  
1.  설정의 `MarqueeControlTest` 시작 프로젝트로 프로젝트를 실행 합니다. 표시 하는 폼을 보게 프로그램 `DemoMarqueeControl`합니다. 클릭는 **시작** 단추는 애니메이션을 시작 합니다. 깜박이 텍스트와 테두리 움직이는 조명이 표시 됩니다.  
  
## <a name="next-steps"></a>다음 단계  
 `MarqueeControlLibrary` 사용자 지정 컨트롤과 연결 된 디자이너의 간단한 구현을 보여 줍니다. 여러 가지 방법으로이 샘플을 보다 정교한 만들 수 있습니다.  
  
-   에 대 한 속성 값을 변경는 `DemoMarqueeControl` 디자이너에서 합니다. 더 추가 `MarqueBorder` 제어 하 고 중첩 된 효과를 만들려면 해당 부모 인스턴스 내에 도킹 합니다. 에 대 한 다른 설정 사용 하 여 실험에서 `UpdatePeriod` 및 조명 관련 속성입니다.  
  
-   자체 구현을 작성 `IMarqueeWidget`합니다. 예를 들어 이미지가 여러 개 있는 애니메이션된 사인 또는 깜박이 "neon 로그인"을 만들 수 있습니다.  
  
-   디자인 타임 환경을 사용자 지정할. 보다 더 많은 속성을 숨김을 시도할 수 <xref:System.Windows.Forms.Control.Enabled%2A> 및 <xref:System.Windows.Forms.Control.Visible%2A>, 새 속성을 추가할 수 없습니다. 자식 컨트롤을 도킹과 같은 일반적인 작업을 간소화 하기 위해 새 디자이너 동사를 추가 합니다.  
  
-   라이선스는 `MarqueeControl`합니다. 자세한 내용은 참조 [하는 방법: 라이선스 구성 요소와 컨트롤](http://msdn.microsoft.com/library/8e66c1ed-a445-4b26-8185-990b6e2bbd57)합니다.  
  
-   컨트롤을 serialize 하는 방법 및 코드에 생성 되는 방식을 제어 합니다. 자세한 내용은 참조 [동적 소스 코드 생성 및 컴파일](../../../../docs/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.UserControl>  
 <xref:System.Windows.Forms.Design.ParentControlDesigner>  
 <xref:System.Windows.Forms.Design.DocumentDesigner>  
 <xref:System.ComponentModel.Design.IRootDesigner>  
 <xref:System.ComponentModel.Design.DesignerVerb>  
 <xref:System.Drawing.Design.UITypeEditor>  
 <xref:System.ComponentModel.BackgroundWorker>  
 [방법: 디자인 타임 기능을 활용하는 Windows Forms 컨트롤 만들기](http://msdn.microsoft.com/library/8e0bad0e-56f3-43d2-bf63-a945c654d97c)  
 [디자인 타임 지원 확장](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 [사용자 지정 디자이너](http://msdn.microsoft.com/library/ca11988e-d38e-44d8-a05d-71362ae7844d)  
 [.NET 셰이프 라이브러리: 샘플 디자이너](http://windowsforms.net/articles/shapedesigner.aspx)
