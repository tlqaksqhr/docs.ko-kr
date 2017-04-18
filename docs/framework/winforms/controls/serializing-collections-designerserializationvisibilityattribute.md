---
title: "연습: DesignerSerializationVisibilityAttribute를 사용하여 표준 형식의 컬렉션 serialize | Microsoft Docs"
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
  - "컬렉션, serialize"
  - "컬렉션, 표준 형식"
  - "DesiginerSerializationVisibilityAttribute 클래스"
  - "serialization, 컬렉션"
  - "표준 형식, 컬렉션"
ms.assetid: 020c9df4-fdc5-4dae-815a-963ecae5668c
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# 연습: DesignerSerializationVisibilityAttribute를 사용하여 표준 형식의 컬렉션 serialize
사용자 지정 컨트롤에서 컬렉션을 속성으로 노출하는 경우도 있습니다.  이 연습에서는 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> 클래스를 사용하여 디자인 타임에 컬렉션이 serialize되는 방법을 제어하는 방법에 대해 설명합니다.  <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> 값을 컬렉션 속성에 적용하면 속성이 serialize됩니다.  
  
 이 항목의 코드를 단일 목록으로 복사하려면 [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](../Topic/How%20to:%20Serialize%20Collections%20of%20Standard%20Types%20with%20the%20DesignerSerializationVisibilityAttribute.md)를 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음과 같은 요건이 필요합니다.  
  
-   Visual Studio가 설치된 컴퓨터에서 Windows Forms 응용 프로그램 프로젝트를 만들고 실행할 수 있는 권한  
  
## Serializable 컬렉션이 있는 컨트롤 만들기  
 첫 번째 단계는 serializable 컬렉션을 속성으로 갖는 컨트롤을 만드는 것입니다.  **속성** 창에서 액세스할 수 있는 **컬렉션 편집기**를 사용하여 이 컬렉션의 내용을 편집할 수 있습니다.  
  
#### serializable 컬렉션이 있는 컨트롤을 만들려면  
  
1.  `SerializationDemoControlLib`라는 Windows 컨트롤 라이브러리 프로젝트를 만듭니다.  자세한 내용은 [Windows Control Library Template](http://msdn.microsoft.com/ko-kr/722f4e2d-1310-4ed5-8f33-593337ab66b4)을 참조하십시오.  
  
2.  `UserControl1`의 이름을 `SerializationDemoControl`로 변경합니다.  자세한 내용은 [How to: Rename Identifiers](http://msdn.microsoft.com/ko-kr/2430f732-2b70-4516-8cf6-a7bb71cc9724)를 참조하십시오.  
  
3.  **속성** 창에서 <xref:System.Windows.Forms.Padding.All%2A?displayProperty=fullName> 속성 값을 `10`으로 설정합니다.  
  
4.  <xref:System.Windows.Forms.TextBox> 컨트롤을 `SerializationDemoControl`에 배치합니다.  
  
5.  <xref:System.Windows.Forms.TextBox> 컨트롤을 선택합니다.  **속성** 창에서 다음 속성을 설정합니다.  
  
    |Property|다음으로 변경|  
    |--------------|-------------|  
    |**Multiline**|`true`|  
    |**Dock**|<xref:System.Windows.Forms.DockStyle>|  
    |**ScrollBars**|<xref:System.Windows.Forms.ScrollBars>|  
    |**ReadOnly**|`true`|  
  
6.  **코드 편집기**에서 `stringsValue`라는 문자열 배열 필드를 `SerializationDemoControl`에 선언합니다.  
  
     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]  
  
7.  `SerializationDemoControl`에서 `Strings` 속성을 정의합니다.  
  
> [!NOTE]
>  <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> 값은 컬렉션의 serialization을 활성화하는 데 사용됩니다.  
  
 [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
 [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
 [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]  
  
1.  F5 키를 눌러 프로젝트를 빌드하고 **UserControl Test Container**에서 컨트롤을 실행합니다.  
  
2.  **UserControl Test Container**의 <xref:System.Windows.Forms.PropertyGrid>에서 `Strings` 속성을 찾습니다.  `Strings` 속성을 클릭한 다음 줄임표\(![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) 단추를 클릭하여 **문자열 컬렉션 편집기**를 엽니다.  
  
3.  **문자열 컬렉션 편집기**에서 여러 문자열을 입력합니다.  각 문자열의 끝에서 Enter 키를 눌러 문자열을 구분합니다.  문자열 입력이 완료되면 **확인**을 클릭합니다.  
  
> [!NOTE]
>  입력한 문자열이 `SerializationDemoControl`의 <xref:System.Windows.Forms.TextBox>에 표시됩니다.  
  
## 컬렉션 속성 Serialize  
 컨트롤의 serialization 동작을 테스트하려면 해당 컬렉션을 폼에 배치하고 **컬렉션 편집기**를 사용하여 컬렉션의 내용을 변경합니다.  **Windows Forms 디자이너**에서 코드를 생성하는 특수 디자이너 파일을 조사하여 serialize된 컬렉션의 상태를 확인할 수 있습니다.  
  
#### 컬렉션을 serialize하려면  
  
1.  솔루션에 Windows 응용 프로그램 프로젝트를 추가합니다.  프로젝트 이름을 `SerializationDemoControlTest`로 지정합니다.  
  
2.  **도구 상자**에서 **SerializationDemoControlLib 구성 요소**라는 탭을 찾습니다.  이 탭에서 `SerializationDemoControl`을 찾습니다.  자세한 내용은 [연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)를 참조하십시오.  
  
3.  `SerializationDemoControl`을 폼에 배치합니다.  
  
4.  **속성** 창에서 `Strings` 속성을 찾습니다.  `Strings` 속성을 클릭한 다음 줄임표\(![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) 단추를 클릭하여 **문자열 컬렉션 편집기**를 엽니다.  
  
5.  **문자열 컬렉션 편집기**에서 여러 문자열을 입력합니다.  각 문자열의 끝에서 Enter 키를 눌러 문자열을 구분합니다.  문자열 입력이 완료되면 **확인**을 클릭합니다.  
  
> [!NOTE]
>  입력한 문자열이 `SerializationDemoControl`의 <xref:System.Windows.Forms.TextBox>에 표시됩니다.  
  
1.  **솔루션 탐색기**에서 **모든 파일 표시** 단추를 클릭합니다.  
  
2.  **Form1** 노드를 엽니다.  이 노드 아래에 **Form1.Designer.cs** 또는 **Form1.Designer.vb**라는 파일이 있습니다.  이 파일은 **Windows Forms 디자이너**에서 폼과 해당 자식 컨트롤의 디자인 타임 상태를 나타내는 코드를 생성하는 파일입니다.  **코드 편집기**에서 이 파일을 엽니다.  
  
3.  **Windows Form 디자이너에서 생성한 코드**라는 영역을 열고 **serializationDemoControl1**이라는 레이블이 지정된 섹션을 찾습니다.  이 레이블 아래에는 컨트롤의 serialize된 상태를 나타내는 코드가 있습니다.  5단계에서 입력한 문자열이 `Strings` 속성에 대한 할당으로 표시됩니다.  다음 코드 예제에서는 "red", "orange" 및 "yellow"라는 문자열을 입력한 경우 표시되는 코드와 비슷한 코드를 보여 줍니다.  
  
4.  \[Visual Basic\]  
  
    ```  
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}  
    ```  
  
5.  \[C\#\]  
  
    ```  
    this.serializationDemoControl1.Strings = new string[] {  
            "red",  
            "orange",  
            "yellow"};  
    ```  
  
6.  **코드 편집기**에서 `Strings` 속성의 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> 값을 <xref:System.ComponentModel.DesignerSerializationVisibility>으로 변경합니다.  
  
7.  \[Visual Basic\]  
  
    ```  
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _  
    ```  
  
8.  \[C\#\]  
  
    ```  
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]  
    ```  
  
9. 솔루션을 다시 빌드하고 4\-8단계를 반복합니다.  
  
> [!NOTE]
>  이 경우 **Windows Forms 디자이너**는 `Strings` 속성에 아무 것도 할당하지 않습니다.  
  
## 다음 단계  
 표준 형식 컬렉션을 serialize하는 방법을 알고 있는 경우 사용자 지정 컨트롤을 디자인 타임 환경에 보다 세부적으로 통합해 보십시오.  다음 항목에서는 사용자 지정 컨트롤의 디자인 타임 통합을 향상시키는 방법에 대해 설명합니다.  
  
-   [Design\-Time Architecture](../Topic/Design-Time%20Architecture.md)  
  
-   [Windows Forms 컨트롤의 특성](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
  
-   [Designer Serialization Overview](../Topic/Designer%20Serialization%20Overview.md)  
  
-   [연습: Visual Studio의 디자인 타임 기능을 사용하는 Windows Forms 컨트롤 만들기](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
  
## 참고 항목  
 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>   
 [Designer Serialization Overview](../Topic/Designer%20Serialization%20Overview.md)   
 [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](../Topic/How%20to:%20Serialize%20Collections%20of%20Standard%20Types%20with%20the%20DesignerSerializationVisibilityAttribute.md)   
 [연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)