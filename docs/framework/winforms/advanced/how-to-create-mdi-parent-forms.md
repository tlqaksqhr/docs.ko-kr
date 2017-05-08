---
title: "방법: MDI 상위 폼 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "MDI, 폼 만들기"
  - "부모 폼"
ms.assetid: 12c71221-2377-4bb6-b10b-7b4b300fd462
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: MDI 상위 폼 만들기
> [!IMPORTANT]
>  이 항목에서는 <xref:System.Windows.Forms.MainMenu> 컨트롤로 대체된 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용합니다.  <xref:System.Windows.Forms.MainMenu> 컨트롤은 이전 버전과의 호환성을 유지하고 원하는 경우 이후에 사용할 수 있도록 유지됩니다.  <xref:System.Windows.Forms.MenuStrip>을 사용하여 MDI 부모 폼을 만드는 방법에 대한 자세한 내용은 [방법: MenuStrip이 포함된 MDI 창 목록 만들기](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md)를 참조하세요.  
  
 MDI\(다중 문서 인터페이스\) 부모 폼은 MDI\(다중 문서 인터페이스\) 응용 프로그램의 기반이 되는 요소로,  사용자가 MDI 응용 프로그램과 상호 작용하는 하위 창인 MDI 자식 창을 포함합니다.  MDI 부모 폼은 Windows Forms 디자이너에서 그리고 프로그래밍 방식으로 쉽게 만들 수 있습니다.  
  
### 디자인 타임에 MDI 부모 폼을 만들려면  
  
1.  Windows 응용 프로그램 프로젝트를 만듭니다.  
  
2.  **속성** 창에서 [IsMDIContainer](frlrfSystemWindowsFormsFormClassIsMDIContainerTopic) 속성을 **true**로 설정합니다.  
  
     그러면 폼이 자식 창의 MDI 컨테이너로 지정됩니다.  
  
    > [!NOTE]
    >  **속성** 창에서 속성을 설정하는 동안 원하는 경우 `WindowState` 속성을 **최대화**로 설정할 수도 있습니다. 부모 폼을 최대화하면 MDI 자식 창을 가장 쉽게 조작할 수 있기 때문입니다.  또한 MDI 부모 폼에는 <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=fullName> 속성을 사용하여 설정하는 배경색이 아니라 Windows 시스템 제어판에 설정된 시스템 색이 선택됩니다.  
  
3.  **도구 상자**에서 **MenuStrip** 컨트롤을 폼으로 끌어 옵니다.  **텍스트** 속성을 **새로 만들기\(&N\)** 및 **닫기\(&C\)** 하위 항목이 있는 **파일\(&F\)**로 설정하여 최상위 메뉴 항목을 만듭니다.  **창\(&W\)**이라는 최상위 메뉴 항목도 만듭니다.  
  
     런타임에 첫 번째 메뉴가 작성되고 메뉴 항목은 숨겨지며 두 번째 메뉴는 열려 있는 MDI 자식 창을 추적합니다.  이제 MDI 부모 창이 만들어졌습니다.  
  
4.  **F5** 키를 눌러 응용 프로그램을 실행합니다.  MDI 부모 폼 내에서 작동하는 MDI 자식 창을 만드는 방법에 대한 자세한 내용은 [방법: MDI 자식 폼 만들기](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)를 참조하세요.  
  
## 참고 항목  
 [MDI 응용 프로그램](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)   
 [방법: MDI 자식 폼 만들기](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)   
 [방법: 활성 MDI 자식 확인](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)   
 [방법: 활성 MDI 자식으로 데이터 전송](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)   
 [방법: MDI 자식 폼 정렬](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)