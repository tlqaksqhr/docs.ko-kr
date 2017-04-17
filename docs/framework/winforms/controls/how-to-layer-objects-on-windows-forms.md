---
title: "방법: Windows Forms에서 개체 계층화 | Microsoft Docs"
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
  - "컨트롤[Windows Forms], 계층 처리"
  - "컨트롤[Windows Forms], 위치 지정"
  - "Windows Forms 컨트롤, 계층 처리"
  - "z 순서"
  - "z 순서"
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: Windows Forms에서 개체 계층화
복잡한 사용자 인터페이스를 만들거나 MDI\(다중 문서 인터페이스\) 폼을 사용하는 경우 컨트롤과 자식 폼을 모두 계층화하면 더욱 복잡한 UI\(사용자 인터페이스\)를 만들 수 있습니다.  그룹의 컨텍스트에서 컨트롤과 창을 이동하고 추적하려면 z 순서를 조작합니다.  *Z 순서*는 폼의 z축\(깊이\)을 따라 폼의 컨트롤을 시각적으로 계층화한 것입니다.  z 순서의 맨 위에 있는 창은 다른 모든 창 위에 겹쳐집니다.  또한 다른 모든 창은 z 순서의 맨 아래에 있는 창 위에 겹쳐집니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 디자인 타임에 컨트롤을 계층화하려면  
  
1.  계층화할 컨트롤을 선택합니다.  
  
2.  **서식** 메뉴에서 **순서**를 가리킨 다음 **맨 앞으로 가져오기** 또는 **맨 뒤로 보내기**를 클릭합니다.  
  
### 프로그래밍 방식으로 컨트롤을 계층화하려면  
  
-   <xref:System.Windows.Forms.Control.BringToFront%2A> 및 <xref:System.Windows.Forms.Control.SendToBack%2A> 메서드를 사용하여 컨트롤의 z 순서를 조작합니다.  
  
     예를 들어, 다른 컨트롤 아래에 있는 `txtFirstName`이라는 <xref:System.Windows.Forms.TextBox> 컨트롤을 맨 위로 이동하려면 다음 코드를 사용합니다.  
  
    ```vb  
    txtFirstName.BringToFront()  
  
    ```  
  
    ```csharp  
    txtFirstName.BringToFront();  
  
    ```  
  
    ```cpp  
    txtFirstName->BringToFront();  
    ```  
  
> [!NOTE]
>  Windows Forms는 *컨트롤 포함*을 지원합니다.  즉, <xref:System.Windows.Forms.GroupBox> 컨트롤 안에 여러 개의 <xref:System.Windows.Forms.RadioButton> 컨트롤이 포함된 경우처럼 여러 개의 컨트롤을 하나의 상위 컨트롤에 포함할 수 있습니다.  그런 다음 상위 컨트롤에 포함된 컨트롤을 계층화할 수 있습니다.  컨트롤은 그룹 상자에 포함되어 있으므로 그룹 상자를 이동하면 컨트롤도 함께 이동합니다.  
  
## 참고 항목  
 [Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/index.md)   
 [Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)   
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [기능별 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)