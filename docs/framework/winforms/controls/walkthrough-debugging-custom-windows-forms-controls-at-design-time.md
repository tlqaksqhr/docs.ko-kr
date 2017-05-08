---
title: "연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버깅 | Microsoft Docs"
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
  - "컨트롤[Windows Forms], 디버깅"
  - "사용자 지정 컨트롤[Windows Forms], 디버깅"
  - "사용자 지정 컨트롤[Windows Forms], 연습"
  - "디버깅[Visual Studio], 연습"
  - "디버깅[Visual Studio], Windows Forms"
  - "디자이너"
  - "디자인 타임 디버깅"
  - "비주얼 편집기"
  - "연습[Windows Forms], 디버깅"
ms.assetid: 1fd83ccd-3798-42fc-85a3-6cba99467387
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# 연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버깅
사용자 지정 컨트롤을 만들 때 디자인 타임 동작을 디버깅해야 하는 경우가 있습니다.  사용자 지정 컨트롤을 위한 사용자 지정 디자이너를 작성하는 경우에는 더욱 그렇습니다.  자세한 내용은 [연습: Visual Studio의 디자인 타임 기능을 사용하는 Windows Forms 컨트롤 만들기](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)를 참조하십시오.  
  
 다른 .NET Framework 클래스를 디버깅하는 것과 마찬가지로 Visual Studio를 사용하여 사용자 지정 컨트롤을 디버깅할 수 있습니다.  차이점은 이 경우 사용자 지정 컨트롤의 코드를 실행하는 Visual Studio의 개별 인스턴스를 디버깅한다는 점입니다.  
  
 이 연습에서 수행할 작업은 다음과 같습니다.  
  
-   사용자 지정 컨트롤을 호스팅할 Windows Forms 프로젝트 만들기  
  
-   컨트롤 라이브러리 프로젝트 만들기  
  
-   사용자 지정 컨트롤에 속성 추가  
  
-   호스트 폼에 사용자 지정 컨트롤 추가  
  
-   디자인 타임 디버깅을 위한 프로젝트 설정  
  
-   디자인 타임에 사용자 지정 컨트롤 디버깅  
  
 이 연습을 마치면 사용자 지정 컨트롤의 디자인 타임 동작을 디버깅하는 데 필요한 작업을 이해하게 됩니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 프로젝트 만들기  
 첫 번째 단계는 응용 프로그램 프로젝트를 만드는 것입니다.  사용자 지정 컨트롤을 호스팅하는 응용 프로그램을 빌드하는 데 이 프로젝트를 사용합니다.  
  
#### 프로젝트를 만들려면  
  
-   "DebuggingExample"이라는 Windows 응용 프로그램 프로젝트를 만듭니다.  자세한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하십시오.  
  
## 컨트롤 라이브러리 프로젝트 만들기  
 다음 단계에서는 컨트롤 라이브러리 프로젝트를 만들어 사용자 지정 컨트롤을 설정합니다.  
  
#### 컨트롤 라이브러리 프로젝트를 만들려면  
  
1.  솔루션에 **Windows 컨트롤 라이브러리** 프로젝트를 추가합니다.  
  
2.  DebugControlLibrary 프로젝트에 새 **UserControl** 항목을 추가합니다.  자세한 내용은 [NIB:How to: Add New Project Items](http://msdn.microsoft.com/ko-kr/63d3e16b-de6e-4bb5-a0e3-ecec762201ce)를 참조하십시오.  새 소스 파일에 "DebugControl"이라는 기본 이름을 지정합니다.  
  
3.  **솔루션 탐색기**에서 기본 이름 "`UserControl1`"을 가진 코드 파일을 삭제하여 프로젝트의 기본 컨트롤을 삭제합니다.  자세한 내용은 [NIB:How to: Remove, Delete, and Exclude Items](http://msdn.microsoft.com/ko-kr/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73)를 참조하십시오.  
  
4.  솔루션을 빌드합니다.  
  
## 검사점  
 이제 사용자 지정 컨트롤이 **도구 상자**에 표시됩니다.  
  
#### 진행률을 확인하려면  
  
-   **DebugControlLibrary 구성 요소**라는 새 탭을 찾은 다음 클릭하여 선택합니다.  탭이 열리면 컨트롤이 목록에 **DebugControl**로 표시되고 그 옆에 기본 아이콘이 나타납니다.  
  
## 사용자 지정 컨트롤에 속성 추가  
 사용자 지정 컨트롤의 코드가 디자인 타임에서 실행되고 있는지 확인하려면 속성을 추가하고 해당 속성을 구현하는 코드에서 중단점을 설정합니다.  
  
#### 사용자 지정 컨트롤에 속성을 추가하려면  
  
1.  **코드 편집기**에서 **DebugControl**을 엽니다.  클래스 정의에 다음 코드를 추가합니다.  
  
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
  
## 호스트 폼에 사용자 지정 컨트롤 추가  
 사용자 지정 컨트롤의 디자인 타임 동작을 디버깅하려면 사용자 지정 컨트롤 클래스의 인스턴스를 호스트 폼에 배치합니다.  
  
#### 호스트 폼에 사용자 지정 컨트롤을 추가하려면  
  
1.  "DebuggingExample" 프로젝트의 **Windows Forms 디자이너**에서 Form1을 엽니다.  
  
2.  **도구 상자**에서 **DebugControlLibrary 구성 요소** 탭을 열고 **DebugControl** 인스턴스를 폼으로 끌어 옵니다.  
  
3.  **속성** 창에서 `DemoString` 사용자 지정 속성을 찾습니다.  다른 속성에서와 마찬가지로 이 속성의 값을 변경할 수 있습니다.  또한 `DemoString` 속성을 선택하면 속성 설명 문자열이 **속성** 창의 아래쪽에 나타납니다.  
  
## 디자인 타임 디버깅을 위한 프로젝트 설정  
 사용자 지정 컨트롤의 디자인 타임 동작을 디버깅하려면 사용자 지정 컨트롤의 코드를 실행하는 Visual Studio의 개별 인스턴스를 디버깅합니다.  
  
#### 디자인 타임 디버깅을 위해 프로젝트를 설정하려면  
  
1.  **솔루션 탐색기**에서 **DebugControlLibrary** 프로젝트를 마우스 오른쪽 단추로 클릭한 다음 **속성**을 선택합니다.  
  
2.  **DebugControlLibrary** 속성 시트에서 **디버그** 탭을 선택합니다.  
  
     **시작 작업** 섹션에서 **시작 외부 프로그램**을 선택합니다.  별도의 Visual Studio 인스턴스를 디버깅하므로 줄임표\(![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) 단추를 클릭하여 Visual Studio IDE를 찾아봅니다.  실행 파일의 이름은 **devenv.exe**이며, 기본 위치에 설치한 경우 그 경로는 %programfiles%\\Microsoft Visual Studio 9.0\\Common7\\IDE\\devenv.exe입니다.  
  
3.  **확인**을 클릭하여 대화 상자를 닫습니다.  
  
4.  **DebugControlLibrary** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **시작 프로젝트로 설정**을 선택하여 이 디버깅 구성을 활성화합니다.  
  
## 디자인 타임에 사용자 지정 컨트롤 디버깅  
 이제 디자인 모드에서 실행될 때처럼 사용자 지정 컨트롤을 디버깅할 수 있습니다.  디버깅 세션을 시작하면 Visual Studio의 새 인스턴스가 만들어지고 해당 인스턴스를 사용하여 "DebuggingExample" 솔루션을 로드합니다.  **폼 디자이너**에서 Form1을 열면 사용자 지정 컨트롤의 인스턴스가 만들어지고 자동으로 실행됩니다.  
  
#### 디자인 타임에 사용자 지정 컨트롤을 디버깅하려면  
  
1.  **코드 편집기**에서 **DebugControl** 소스 파일을 열고 `DemoString` 속성의 `Set` 접근자에 중단점을 배치합니다.  
  
2.  F5 키를 눌러 디버깅 세션을 시작합니다.  Visual Studio의 새 인스턴스가 만들어집니다.  다음과 같은 두 가지 방법으로 인스턴스를 구별할 수 있습니다.  
  
    -   디버깅 인스턴스는 제목 표시줄에 **실행 중**이라는 단어가 있습니다.  
  
    -   디버깅 인스턴스는 **디버그** 도구 모음의 **시작** 단추가 비활성화되어 있습니다.  
  
     중단점이 디버깅 인스턴스에 설정됩니다.  
  
3.  Visual Studio의 새 인스턴스에서 "DebuggingExample" 솔루션을 엽니다.  **파일** 메뉴에서 **최근에 사용한 프로젝트**를 선택하여 솔루션을 쉽게 찾을 수 있습니다.  "DebuggingExample.sln" 솔루션 파일은 최근에 사용한 파일 목록에 있습니다.  
  
4.  **폼 디자이너**에서 Form1을 열고 **DebugControl** 컨트롤을 선택합니다.  
  
5.  `DemoString` 속성 값을 변경합니다.  변경 내용을 커밋하면 Visual Studio의 디버깅 인스턴스로 포커스가 이동하고 중단점에서 실행이 중지됩니다.  다른 코드에서처럼 속성 접근자를 단일 단계로 처리할 수 있습니다.  
  
6.  디버깅 세션을 마치면 Visual Studio의 호스팅된 인스턴스를 해제하거나 디버깅 인스턴스에서 **디버깅 중지** 단추를 클릭하여 종료할 수 있습니다.  
  
## 다음 단계  
 이제 디자인 타임에서 사용자 지정 컨트롤을 디버깅할 수 있고 컨트롤의 Visual Studio IDE와의 상호 작용을 확장할 수 있는 많은 기능이 있습니다.  
  
-   <xref:System.ComponentModel.Component> 클래스의 <xref:System.ComponentModel.Component.DesignMode%2A> 속성을 사용하여 디자인 타임에서만 실행되는 코드를 작성할 수 있습니다.  자세한 내용은 <xref:System.ComponentModel.Component.DesignMode%2A>를 참조하십시오.  
  
-   컨트롤의 속성에 적용하여 사용자 지정 컨트롤과 디자이너의 상호 작용을 조작할 수 있는 몇 가지 특성이 있습니다.  이러한 특성은 <xref:System.ComponentModel?displayProperty=fullName> 네임스페이스에서 찾을 수 있습니다.  
  
-   사용자 지정 컨트롤을 위한 사용자 지정 디자이너를 작성할 수 있습니다.  그러면 Visual Studio에 의해 노출되는 확장성이 뛰어난 디자이너 인프라를 사용하여 디자인 연습을 완벽하게 제어할 수 있습니다.  자세한 내용은 [연습: Visual Studio의 디자인 타임 기능을 사용하는 Windows Forms 컨트롤 만들기](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)를 참조하십시오.  
  
## 참고 항목  
 [연습: Visual Studio의 디자인 타임 기능을 사용하는 Windows Forms 컨트롤 만들기](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)   
 [How to: Access Design\-Time Services](../Topic/How%20to:%20Access%20Design-Time%20Services.md)   
 [How to: Access Design\-Time Support in Windows Forms](../Topic/How%20to:%20Access%20Design-Time%20Support%20in%20Windows%20Forms.md)