---
title: "방법: 디자이너를 사용하여 Windows Forms 컨트롤에 대한 선택키 만들기 | Microsoft Docs"
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
  - "선택키, 컨트롤 만들기"
  - "선택키, Windows Forms"
  - "Alt 키"
  - "바로 가기 키의 앰퍼샌드 문자"
  - "Button 컨트롤[Windows Forms], 선택키"
  - "컨트롤[Windows Forms], 선택키"
  - "대화 상자 컨트롤, 니모닉"
  - "예제[Windows Forms], 컨트롤"
  - "바로 가기 키, 컨트롤 만들기"
  - "니모닉, 대화 상자 컨트롤에 추가"
  - "Text 속성, 컨트롤 선택키 지정"
  - "Windows Forms 컨트롤, 선택키"
ms.assetid: 4c374c4c-4ca9-4a68-ac96-9dc3ab0f518a
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: 디자이너를 사용하여 Windows Forms 컨트롤에 대한 선택키 만들기
*선택키*는 메뉴, 메뉴 항목 또는 단추와 같은 컨트롤의 레이블에 있는 텍스트에서 밑줄이 그어진 문자를 말합니다.  미리 정의된 선택키와 Alt 키를 함께 누르면 사용자가 단추를 "클릭"한 경우와 같은 효과가 나타납니다.  예를 들어 어떤 단추가 폼을 인쇄하는 프로시저를 실행하기 때문에 `Text` 속성이 "Print"로 설정된 경우 "P" 문자 앞에 앰퍼샌드\(&\)를 추가하면 런타임에 이 단추 텍스트의 "P"에는 밑줄이 그어집니다.  사용자는 Alt\+P를 눌러 해당 단추와 관련된 명령을 실행할 수 있습니다.  포커스를 받을 수 없는 컨트롤에는 선택키를 사용할 수 없습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 컨트롤의 선택키를 만들려면  
  
1.  **속성** 창에서 `Text` 속성을 선택키로 사용할 문자 앞에 앰퍼샌드가 포함된 문자열로 설정합니다.  예를 들어 문자 "P"를 선택키로 설정하려면 표 형태의 창에 &Print를 입력합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Button>   
 [방법: Windows Forms 단추 클릭에 응답](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)   
 [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)