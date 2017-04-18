---
title: "합성 Windows Forms 컨트롤 개발 | Microsoft Docs"
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
  - "복합 컨트롤"
  - "복합 컨트롤, Windows Forms"
  - "컨트롤[Windows Forms], 복합"
  - "사용자 지정 컨트롤[Windows Forms], 복합 컨트롤"
  - "UserControl 클래스"
ms.assetid: d086f2a3-baa3-4e09-b40c-a5bb3cfc51a6
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 합성 Windows Forms 컨트롤 개발
다른 Windows Forms 컨트롤을 결합하여 복합 Windows Forms 컨트롤을 개발할 수 있습니다.  [System.Windows.Forms.UserControl](frlrfSystemWebUIUserControlClassTopic)에서 파생되는 복합 컨트롤을 사용자 컨트롤이라고 합니다.  기본 클래스 <xref:System.Windows.Forms.UserControl>은 자식 컨트롤에 대한 키보드 라우팅을 제공하므로 자식 컨트롤이 포커스를 받을 수 있습니다.  사용자 컨트롤의 예를 보려면 [방법: Windows Forms 컨트롤에서 특성 적용](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md)에서 <xref:System.Windows.Forms.UserControl> 샘플을 참조하세요.  
  
 [!INCLUDE[vsprvsext](../../../../includes/vsprvsext-md.md)]의 Windows Forms 디자이너에서는 사용자 컨트롤 작성에 대한 다양한 디자인 타임 지원을 제공합니다.  
  
-   [방법: 도구 상자 항목 선택 대화 상자에 컨트롤 표시](http://msdn.microsoft.com/library/9yxtkx75\(v=vs.110\))  
  
-   [연습: DesignerSerializationVisibilityAttribute를 사용하여 표준 형식의 컬렉션 직렬화](http://msdn.microsoft.com/library/ms171731\(v=vs.110\))  
  
-   [연습: Visual C\#을 사용하여 Windows Forms 컨트롤에서 상속](http://msdn.microsoft.com/en-us/library/5h0k2e6x\(v=vs.110\))  
  
-   [방법: 컨트롤에 대한 도구 상자 비트맵 제공](http://msdn.microsoft.com/library/4wk1wc0a\(v=vs.110\))  
  
-   [방법: 기존 Windows Forms 컨트롤에서 상속](http://msdn.microsoft.com/library/7h62478z\(v=vs.110\))  
  
-   [연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버깅](http://msdn.microsoft.com/library/5ytx0z24\(v=vs.110\))  
  
-   [방법: Control 클래스에서 상속](http://msdn.microsoft.com/library/skcysbt2\(v=vs.110\))  
  
-   [방법: UserControl의 런타임 동작 테스트](http://msdn.microsoft.com/library/ms171738\(v=vs.110\))  
  
-   [방법: 디자인 타임에 컨트롤을 폼의 가장자리에 맞춤](http://msdn.microsoft.com/library/1fxyb15b\(v=vs.110\))  
  
-   [방법: UserControl 클래스에서 상속](http://msdn.microsoft.com/library/00ctb4z0\(v=vs.110\))  
  
-   [방법: Windows Forms 컨트롤 제작](http://msdn.microsoft.com/library/bs3yhkh7\(v=vs.110\))  
  
-   [방법: 복합 컨트롤 제작](http://msdn.microsoft.com/library/3sf86w5h\(v=vs.110\))  
  
-   [연습: Visual Basic에서 복합 컨트롤 제작](http://msdn.microsoft.com/library/c316f119\(v=vs.110\))  
  
-   [연습: Visual C\#에서 복합 컨트롤 제작](http://msdn.microsoft.com/en-us/library/a6h7e207\(v=vs.110\))  
  
-   [연습: Visual Basic을 사용하여 Windows Forms 컨트롤에서 상속](http://msdn.microsoft.com/library/w2a8y03d\(v=vs.110\))  
  
-   [방법: 디자인 타임 기능을 활용하는 Windows Forms 컨트롤 만들기](http://msdn.microsoft.com/library/307hck25\(v=vs.110\))  
  
-   [방법: 디자인 타임 기능을 활용하는 Windows Forms 컨트롤 만들기](http://msdn.microsoft.com/library/307hck25\(v=vs.120\))  
  
## 참고 항목  
 [방법: Windows Forms 컨트롤에서 특성 적용](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md)   
 [.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)   
 [사용자 지정 컨트롤의 종류](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)