---
title: "방법: 활동 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
caps.latest.revision: 39
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 39
---
# 방법: 활동 만들기
활동은 [!INCLUDE[wf1](../../../includes/wf1-md.md)]에서 동작의 핵심 단위입니다.활동의 실행 논리는 관리 코드에서 구현하거나 다른 활동을 사용하여 구현할 수 있습니다.이 항목에서는 두 개의 활동을 만드는 방법을 보여 줍니다.첫 번째 활동은 코드를 사용하여 실행 논리를 구현하는 간단한 활동입니다.두 번째 활동의 구현은 다른 활동을 사용하여 정의됩니다.이러한 활동은 자습서의 다음 단계에서 사용됩니다.  
  
> [!NOTE]
>  자습서의 전체 버전을 다운로드하려면 [Windows Workflow Foundation\(WF45\) \- 초보자를 위한 자습서](http://go.microsoft.com/fwlink/?LinkID=248976)를 참조하십시오.  
  
### 활동 라이브러리 프로젝트를 만들려면  
  
1.  [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]을 열고 **파일** 메뉴에서 **새로 만들기**,  **프로젝트**를 선택합니다.  
  
2.  **설치됨**, **템플릿** 목록에서 **기타 프로젝트 형식** 노드를 확장하고 **Visual Studio 솔루션**을 선택합니다.  
  
3.  **Visual Studio 솔루션** 목록에서 **빈 솔루션**을 선택합니다..NET Framework 버전 드롭다운 목록에서 **.NET Framework 4.5**가 선택되어 있는지 확인합니다.**이름** 상자에 `WF45GettingStartedTutorial`을 입력하고 **확인**을 클릭합니다.  
  
4.  **솔루션 탐색기**에서 **WF45GettingStartedTutorial**을 마우스 오른쪽 단추로 클릭하고 **추가**, **새 프로젝트**를 차례로 선택합니다.  
  
    > [!TIP]
    >  **솔루션 탐색기** 창이 표시되어 있지 않으면 **보기** 메뉴에서 **솔루션 탐색기**를 선택합니다.  
  
5.  **설치됨** 노드에서 **Visual C\#**, **워크플로**\(또는 **Visual Basic**, **워크플로**\)를 차례로 선택합니다.[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 버전 드롭다운 목록에서 **.NET Framework 4.5**가 선택되어 있는지 확인합니다.**워크플로** 목록에서 **활동 라이브러리**를 선택합니다.**이름** 상자에 `NumberGuessWorkflowActivities`를 입력하고 **확인**을 클릭합니다.  
  
    > [!NOTE]
    >  **설치됨** 노드의 **다른 언어** 노드 아래에는 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]에서 기본 언어로 구성된 프로그래밍 언어에 따라 **Visual C\#** 또는 **Visual Basic** 노드가 표시될 수 있습니다.  
  
6.  **솔루션 탐색기**에서 **Activity1.xaml**을 마우스 오른쪽 단추로 클릭하고 **삭제**를 선택합니다.**확인**을 클릭하여 확인합니다.  
  
### ReadInt 활동을 만들려면  
  
1.  **프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.  
  
2.  **설치됨**, **공통 항목** 노드에서 **워크플로**를 선택합니다.**워크플로** 목록에서 **코드 활동**을 선택합니다.  
  
3.  **이름** 상자에 `ReadInt`를 입력한 다음 **추가**를 클릭합니다.  
  
4.  기존 `ReadInt` 정의를 다음 정의로 바꿉니다.  
  
     [!code-csharp[CFX_WF_GettingStarted#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]  
  
    > [!NOTE]
    >  `ReadInt` 활동은 코드 활동 템플릿의 기본값인 <xref:System.Activities.CodeActivity> 대신 <xref:System.Activities.NativeActivity%601>에서 파생됩니다.활동이 <xref:System.Activities.Activity%601.Result%2A> 인수를 통해 노출되는 단일 결과를 제공하는 경우 <xref:System.Activities.CodeActivity%601>를 사용할 수 있지만 <xref:System.Activities.CodeActivity%601>는 책갈피 사용을 지원하지 않으므로 <xref:System.Activities.NativeActivity%601>가 사용됩니다.  
  
### Prompt 활동을 만들려면  
  
1.  Ctrl\+Shift\+B를 눌러 프로젝트를 빌드합니다.프로젝트를 빌드하면 이 프로젝트의 `ReadInt` 활동을 사용하여 이 단계의 사용자 지정 활동을 빌드할 수 있습니다.  
  
2.  **프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.  
  
3.  **설치됨**, **공통 항목** 노드에서 **워크플로**를 선택합니다.**워크플로** 목록에서 **활동**을 선택합니다.  
  
4.  **이름** 상자에 `Prompt`를 입력한 다음 **추가**를 클릭합니다.  
  
5.  활동이 아직 표시되어 있지 않은 경우 **솔루션 탐색기**에서 **Prompt.xaml**을 두 번 클릭하여 디자이너에 활동을 표시합니다.  
  
6.  활동 디자이너 왼쪽 아래에 있는 **인수**를 클릭하여 **인수** 창을 표시합니다.  
  
7.  **인수 만들기**를 클릭합니다.  
  
8.  **이름** 상자에 `BookmarkName`을 입력하고 **방향** 드롭다운 목록에서 **안쪽**을 선택한 다음 **인수 형식** 드롭다운 목록에서 **String**을 선택하고 Enter 키를 눌러 인수를 저장합니다.  
  
9. **인수 만들기**를 클릭합니다.  
  
10. 새로 추가된 `BookmarkName` 인수 아래에 있는 **이름** 상자에 `Result`를 입력하고 **방향** 드롭다운 목록에서 **바깥쪽**을 선택한 다음 **인수 형식** 드롭다운 목록에서 **Int32**를 선택하고 Enter 키를 누릅니다.  
  
11. **인수 만들기**를 클릭합니다.  
  
12. **이름** 상자에 `Text`를 입력하고 **방향** 드롭다운 목록에서 **안쪽**을 선택한 다음 **인수 형식** 드롭다운 목록에서 **String**을 선택하고 Enter 키를 눌러 인수를 저장합니다.  
  
     이 세 가지 인수는 다음 단계에서 `Prompt` 활동에 추가되는 <xref:System.Activities.Statements.WriteLine> 및 `ReadInt` 활동의 해당 인수에 바인딩됩니다.  
  
13. 활동 디자이너 왼쪽 아래에 있는 **인수**를 클릭하여 **인수** 창을 닫습니다.  
  
14. **도구 상자**의 **흐름 제어** 섹션에서 **Sequence** 활동을 끌어 **Prompt** 활동 디자이너의 **여기에 작업 놓기** 레이블에 놓습니다.  
  
    > [!TIP]
    >  **도구 상자** 창이 표시되어 있지 않으면 **보기** 메뉴에서 **도구 상자**를 선택합니다.  
  
15. **도구 상자**의 **기본 형식** 섹션에서 **WriteLine** 활동을 끌어 **Sequence** 활동의 **여기에 작업 놓기** 레이블에 놓습니다.  
  
16. **속성** 창에서 **C\# 식 입력** 또는 **VB 식 입력** 상자에 `Text`를 입력하여 **WriteLine** 활동의 **Text** 인수를 **Prompt** 활동의 **Text** 인수에 바인딩한 다음 Tab 키를 두 번 누릅니다.그러면 IntelliSense 목록 멤버 창이 사라지고 속성에서 선택 항목을 이동하여 속성 값이 저장됩니다.활동 자체에서 **C\# 식 입력** 또는 **VB 식 입력** 상자에 `Text`를 입력하여 이 속성을 설정할 수도 있습니다.  
  
    > [!TIP]
    >  **속성 창**이 표시되지 않은 경우 **보기** 메뉴에서 **속성 창**을 선택합니다.  
  
17. **도구 상자**의 **NumberGuessWorkflowActivities** 섹션에서 **ReadInt** 활동을 끌어 **Sequence** 활동의 **WriteLine** 활동 뒤에 놓습니다.  
  
18. **속성 창**에서 **BookmarkName** 인수 오른쪽의 **VB 식 입력** 상자에 `BookmarkName`을 입력하여 **ReadInt** 활동의 **BookmarkName** 인수를 **Prompt** 활동의 **BookmarkName** 인수에 바인딩한 다음 Tab 키를 두 번 눌러 IntelliSense 목록 멤버 창을 닫고 속성을 저장합니다.  
  
19. **속성 창**에서 **Result** 인수 오른쪽의 **VB 식 입력** 상자에 `Result`를 입력하여 **ReadInt** 활동의 **Result** 인수를 **Prompt** 활동의 **Result** 인수에 바인딩한 다음 Tab 키를 두 번 누릅니다.  
  
20. Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
     이러한 활동을 사용하여 워크플로를 만드는 방법에 대한 지침은 자습서의 다음 단계인 [방법: 워크플로 만들기](../../../docs/framework/windows-workflow-foundation//how-to-create-a-workflow.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Activities.CodeActivity>   
 <xref:System.Activities.NativeActivity%601>   
 [사용자 지정 활동 디자인 및 구현](../../../docs/framework/windows-workflow-foundation//designing-and-implementing-custom-activities.md)   
 [초보자를 위한 자습서](../../../docs/framework/windows-workflow-foundation//getting-started-tutorial.md)   
 [방법: 워크플로 만들기](../../../docs/framework/windows-workflow-foundation//how-to-create-a-workflow.md)   
 [사용자 지정 활동 디자이너에서 ExpressionTextBox 사용](../../../docs/framework/windows-workflow-foundation/samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)