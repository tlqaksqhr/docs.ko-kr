---
title: "방법: Modifiers 및 GenerateMember 속성 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Designer_GenerateMember"
  - "Designer_Modifiers"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "기본 폼"
  - "폼 상속"
  - "GenerateMember 속성"
  - "상속, 폼"
  - "상속된 폼"
  - "상속된 폼, Windows Forms"
  - "Modifiers 속성"
  - "Windows Forms, 상속"
ms.assetid: 3381a5e4-e1a3-44e2-a765-a0b758937b85
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: Modifiers 및 GenerateMember 속성 사용
구성 요소를 Windows Form에 배치할 경우 디자인 환경에서 `GenerateMember` 및 `Modifiers`라는 두 속성이 제공됩니다.  `GenerateMember` 속성은 Windows Forms 디자이너에서 구성 요소의 멤버 변수를 생성할 시기를 지정합니다.  `Modifiers` 속성은 해당 멤버 변수에 할당된 액세스 한정자입니다.  `GenerateMember` 속성 값이 `false`이면 `Modifiers` 속성 값은 아무 효과가 없습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 구성 요소가 폼의 멤버인지 여부를 지정하려면  
  
1.  Windows Forms 디자이너에서 폼을 엽니다.  
  
2.  **도구 상자**를 열고 세 개의 <xref:System.Windows.Forms.Button> 컨트롤을 폼에 배치합니다.  
  
3.  각 <xref:System.Windows.Forms.Button> 컨트롤의 `GenerateMember` 및 `Modifiers` 속성을 다음 표에 따라 설정합니다.  
  
    |단추 이름|GenerateMember 값|한정자 값|  
    |-----------|----------------------|-----------|  
    |`button1`|`true`|`private`|  
    |`button2`|`true`|`protected`|  
    |`button3`|`false`|변경되지 않음|  
  
4.  솔루션을 빌드합니다.  
  
5.  **솔루션 탐색기**에서 **모든 파일 표시** 단추를 클릭합니다.  
  
6.  **Form1** 노드를 열고 **코드 편집기**에서 **Form1.Designer.vb** 또는 **Form1.Designer.cs** 파일을 엽니다.  이 파일에는 Windows Forms 디자이너에서 내보낸 코드가 들어 있습니다.  
  
7.  세 개의 단추에 대한 선언을 찾습니다.  다음 코드 예제에서는 `GenerateMember` 및 `Modifiers` 속성에서 지정한 값의 차이점을 보여 줍니다.  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]  
  
> [!NOTE]
>  기본적으로 Windows Forms 디자이너에서는 <xref:System.Windows.Forms.Panel> 등의 컨테이너 컨트롤에 `private`\(Visual Basic의 경우 `Friend`\) 수정자가 할당됩니다.  기본 <xref:System.Windows.Forms.UserControl> 또는 <xref:System.Windows.Forms.Form>에 컨테이너 컨트롤이 있는 경우 상속된 컨트롤 및 폼에 자식을 새로 추가할 수 없습니다.  이러한 경우 기본 컨테이너 컨트롤의 수정자를 `protected` 또는 `public`으로 변경해야 합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Button>   
 [Windows Forms 시각적 상속](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)   
 [연습: 시각적 상속 설명](../../../../docs/framework/winforms/advanced/walkthrough-demonstrating-visual-inheritance.md)   
 [방법: Windows Forms 상속](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)