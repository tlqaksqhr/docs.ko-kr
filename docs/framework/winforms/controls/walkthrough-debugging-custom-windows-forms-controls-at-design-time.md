---
title: '연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버깅'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- custom controls [Windows Forms], walkthroughs
- visual editors
- debugging [Visual Studio], Windows Forms
- custom controls [Windows Forms], debugging
- designers
- controls [Windows Forms], debugging
- walkthroughs [Windows Forms], debugging
- design-time debugging
ms.assetid: 1fd83ccd-3798-42fc-85a3-6cba99467387
ms.openlocfilehash: b87c46b2182884f90b427498b9af696d14acac96
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-debugging-custom-windows-forms-controls-at-design-time"></a>연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버깅
사용자 지정 컨트롤을 만들 때는 경우 종종 있습니다의 디자인 타임 동작을 디버깅 하기 위해 필요 합니다. 사용자 지정 컨트롤에 대 한 사용자 지정 디자이너를 제작 하는 경우 특히 유용 합니다. 자세한 내용은 참조 [연습:는 Windows Forms 제어 하는 이점은의 Visual Studio 디자인 타임 기능을 만드는](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)합니다.  
  
 다른.NET Framework 클래스를 디버그할 때 처럼 Visual Studio를 사용 하 여 사용자 지정 컨트롤을 디버그할 수 있습니다. 차이점은 사용자 지정 컨트롤의 코드를 실행 하는 Visual Studio의 개별 인스턴스를 디버깅 합니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   사용자 지정 컨트롤을 호스트 하는 Windows Forms 프로젝트 만들기  
  
-   컨트롤 라이브러리 프로젝트 만들기  
  
-   사용자 지정 컨트롤에 속성 추가  
  
-   호스트 폼을 사용자 지정 컨트롤 추가  
  
-   디자인 타임 디버깅에 대 한 프로젝트 설정  
  
-   디자인 타임에 사용자 지정 컨트롤 디버깅  
  
 작업을 완료 하는 경우 사용자 지정 컨트롤의 디자인 타임 동작을 디버깅 하는 데 필요한 작업을 이해를 해야 합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
## <a name="creating-the-project"></a>프로젝트 만들기  
 첫 번째 단계는 응용 프로그램 프로젝트를 만드는 것입니다. 사용자 지정 컨트롤을 호스트 하는 응용 프로그램을 빌드하려면이 프로젝트를 사용 합니다.  
  
#### <a name="to-create-the-project"></a>프로젝트를 만들려면  
  
-   "DebuggingExample" 이라는 Windows 응용 프로그램 프로젝트를 만듭니다. 자세한 내용은 [방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하세요.  
  
## <a name="creating-a-control-library-project"></a>컨트롤 라이브러리 프로젝트 만들기  
 컨트롤 라이브러리 프로젝트를 만들고 사용자 지정 컨트롤을 설정 하는 다음 단계가입니다.  
  
#### <a name="to-create-the-control-library-project"></a>컨트롤 라이브러리 프로젝트를 만들려면  
  
1.  추가 **Windows 컨트롤 라이브러리** 프로젝트를 솔루션입니다.  
  
2.  새로 추가 **UserControl** 항목 DebugControlLibrary 프로젝트. 자세한 내용은 참조 [NIB: 방법: 새 프로젝트 항목 추가](http://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce)합니다. 새 소스 파일 "DebugControl"의 기본 이름을 지정 합니다.  
  
3.  사용 하는 **솔루션 탐색기**, 코드 파일의 기본 이름으로를 삭제 하 여 프로젝트의 기본 컨트롤 삭제 "`UserControl1`"입니다. 자세한 내용은 참조 [NIB: 방법: 제거, 삭제 및 항목 제외](http://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73)합니다.  
  
4.  솔루션을 빌드합니다.  
  
## <a name="checkpoint"></a>검사점  
 이 시점에서 사용자 지정 컨트롤을 볼 수는 **도구 상자**합니다.  
  
#### <a name="to-check-your-progress"></a>진행률을 확인 하려면  
  
-   라는 새 탭 찾기 **DebugControlLibrary 구성 요소** 및 선택 하려면 클릭 합니다. 으로 나열 된 컨트롤을 열었을 때 나타납니다 **DebugControl** 옆에 있는 기본 아이콘이 사용 됩니다.  
  
## <a name="adding-a-property-to-your-custom-control"></a>사용자 지정 컨트롤에 속성 추가  
 디자인 타임에 사용자 지정 컨트롤의 코드가 실행 되 고 작업을 보여 주기 위해 속성을 추가 쿼리하고 해당 속성을 구현 하는 코드에 중단점을 설정 합니다.  
  
#### <a name="to-add-a-property-to-your-custom-control"></a>사용자 지정 컨트롤에 속성을 추가 하려면  
  
1.  열기 **DebugControl** 에 **코드 편집기**합니다. 클래스 정의에 다음 코드를 추가 합니다.  
  
    ```vb  
    Private demoStringValue As String = Nothing  
    <BrowsableAttribute(true)>  
    Public Property DemoString() As String  
  
        Get  
            Return Me.demoStringValue  
        End Get  
  
        Set(ByVal value As String)  
            Me.demoStringValue = value  
        End Set  
  
    End Property  
    ```  
  
    ```csharp  
    private string demoStringValue = null;  
    [Browsable(true)]  
    public string DemoString  
    {  
        get  
        {  
            return this.demoStringValue;  
        }  
        set  
        {  
            demoStringValue = value;  
        }  
    }  
    ```  
  
2.  솔루션을 빌드합니다.  
  
## <a name="adding-your-custom-control-to-the-host-form"></a>호스트 폼을 사용자 지정 컨트롤 추가  
 사용자 지정 컨트롤의 디자인 타임 동작을 디버깅 하려면 사용자 지정 컨트롤 클래스의 인스턴스를 호스트 폼에 배치 합니다.  
  
#### <a name="to-add-your-custom-control-to-the-host-form"></a>사용자 지정 컨트롤 호스트 폼에 추가 하려면  
  
1.  "DebuggingExample" 프로젝트를 열고에서 Form1는 **Windows Forms 디자이너**합니다.  
  
2.  에 **도구 상자**열고는 **DebugControlLibrary 구성 요소** 탭 한 다음 끌어서는 **DebugControl** 폼 인스턴스.  
  
3.  찾을 `DemoString` 에 사용자 지정 속성의 **속성** 창. 참고 다른 속성과 마찬가지로 해당 값을 변경할 수 있습니다. 또한는 `DemoString` 속성을 선택 하면 속성의 설명 문자열의 맨 아래에 나타나고는 **속성** 창.  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a>디자인 타임 디버깅에 대 한 프로젝트 설정  
 사용자 지정 컨트롤의 디자인 타임 동작을 디버깅 하려면 사용자 지정 컨트롤의 코드를 실행 하는 Visual Studio의 개별 인스턴스를 디버깅 합니다.  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a>디자인 타임 디버깅을 위해 프로젝트를 설정 하려면  
  
1.  마우스 오른쪽 단추로 클릭는 **DebugControlLibrary** 프로젝트에 **솔루션 탐색기** 선택 **속성**합니다.  
  
2.  에 **DebugControlLibrary** 속성 시트는 **디버그** 탭 합니다.  
  
     에 **시작 작업** 섹션에서 **시작 외부 프로그램**합니다. 됩니다. Visual Studio의 개별 인스턴스 디버깅 이므로 줄임표를 클릭 (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton"))를 Visual Studio IDE에 대 한 찾아보기 단추입니다. 실행 파일의 이름은 **devenv.exe**와 경로 %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe 기본 위치에 설치한 경우.  
  
3.  **확인** 을 클릭하여 대화 상자를 닫습니다.  
  
4.  마우스 오른쪽 단추로 클릭는 **DebugControlLibrary** 프로젝트를 마우스 선택 **시작 프로젝트로 설정** 디버깅이 구성을 사용 하도록 설정 합니다.  
  
## <a name="debugging-your-custom-control-at-design-time"></a>디자인 타임에 사용자 지정 컨트롤 디버깅  
 이제 디자인 모드에서 실행 되므로 사용자 지정 컨트롤을 디버그할 준비가 되었습니다. 디버깅 세션을 시작 하면 Visual Studio의 새 인스턴스를 만들 수는, 및 "DebuggingExample" 솔루션을 로드를 사용 합니다. Form1를 열 때는 **Forms 디자이너**, 사용자 지정 컨트롤의 인스턴스 만들어지고 실행을 시작 합니다.  
  
#### <a name="to-debug-your-custom-control-at-design-time"></a>디자인 타임에 사용자 지정 컨트롤을 디버깅 하려면  
  
1.  열기는 **DebugControl** 소스 파일에는 **코드 편집기** 중단점을 설정 하 고는 `Set` 의 접근자는 `DemoString` 속성입니다.  
  
2.  F5 키를 눌러 디버깅 세션을 시작 합니다. Note Visual Studio의 새 인스턴스가 생성 됩니다. 두 가지 방법으로 인스턴스를 구별할 수 있습니다.  
  
    -   디버깅 인스턴스에서 이라는 단어가 포함 **실행** 의 제목 표시줄에  
  
    -   디버깅 인스턴스는 **시작** 단추 해당 **디버그** 사용 하지 않도록 설정 하는 도구 모음  
  
     중단점은 디버깅 인스턴스에서 설정 됩니다.  
  
3.  Visual Studio의 새 인스턴스를 "DebuggingExample" 솔루션을 엽니다. 선택 하 여 솔루션을 쉽게 찾을 **최근에 사용한 프로젝트** 에서 **파일** 메뉴. 가장 최근에 사용 된 대로 "DebuggingExample.sln" 솔루션 파일을 나열 됩니다.  
  
4.  Form1에서 열고는 **Forms 디자이너** 선택 하 고는 **DebugControl** 제어 합니다.  
  
5.  값 변경의 `DemoString` 속성입니다. 변경 내용을 커밋하는 경우 Visual Studio의 디버깅 인스턴스에 포커스를 획득 및 중단점에서 실행이 중지 note 합니다. 속성 접근자를 통해 단일 단계 수와 마찬가지로 프로그램 다른 코드입니다.  
  
6.  Visual Studio의 호스트 인스턴스를 해제 하거나 클릭 하 여 마쳤으면 디버깅 세션을 종료할 수 있습니다는 **디버깅 중지** 디버깅 인스턴스에서 단추입니다.  
  
## <a name="next-steps"></a>다음 단계  
 디자인 타임에 사용자 지정 컨트롤을 디버그할 수 있습니다, 했으므로 Visual Studio IDE와 컨트롤의 상호 작용 확장을 위한 다양 한 비즈니스 가능성이 있습니다.  
  
-   사용할 수는 <xref:System.ComponentModel.Component.DesignMode%2A> 의 속성은 <xref:System.ComponentModel.Component> 디자인 타임에만 실행 되는 코드를 작성 하는 클래스입니다. 자세한 내용은 <xref:System.ComponentModel.Component.DesignMode%2A>를 참조하세요.  
  
-   일부의 특성이 디자이너와 사용자 지정 컨트롤의 상호 작용을 조작 하는 컨트롤의 속성에 적용할 수 있습니다. 이러한 특성을 찾을 수 있습니다는 <xref:System.ComponentModel?displayProperty=nameWithType> 네임 스페이스입니다.  
  
-   사용자 지정 컨트롤에 대 한 사용자 지정 디자이너를 작성할 수 있습니다. Visual Studio에서 노출 하는 확장 가능한 디자이너 인프라를 사용 하 여 디자인 환경을 완전히 제어할 수 있습니다. 자세한 내용은 참조 [연습:는 Windows Forms 제어 하는 이점은의 Visual Studio 디자인 타임 기능을 만드는](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습: Visual Studio의 디자인 타임 기능을 사용하는 Windows Forms 컨트롤 만들기](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 [방법: 디자인 타임 서비스에 액세스](http://msdn.microsoft.com/library/c186c4b6-076c-438d-9ed3-f13da29c8c1f)  
 [방법: Windows Forms에서 디자인 타임 지원 액세스](http://msdn.microsoft.com/library/a84f8579-1f47-41b9-ba37-69030b0aff09)
