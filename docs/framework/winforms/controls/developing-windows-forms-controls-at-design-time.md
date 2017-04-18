---
title: "디자인할 때 Windows Forms 컨트롤 개발 | Microsoft Docs"
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
  - "Windows Forms 컨트롤"
  - "Windows Forms 컨트롤, 만들기"
  - "컨트롤[Windows Forms]"
  - "만들 컨트롤 [Windows Forms]"
  - "사용자 정의 컨트롤[Windows Forms]"
  - "사용자 지정 컨트롤[Windows Forms]"
ms.assetid: e5a8e088-7ec8-4fd9-bcb3-9078fd134829
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# 디자인할 때 Windows Forms 컨트롤 개발
컨트롤 작성자를 위한.NET Framework는 다양 한 컨트롤 제작 기술을 제공 합니다. 작성자는 더 이상 기존 컨트롤의 컬렉션으로 작동 하는 복합 컨트롤을 디자인으로 제한 합니다. 상속을 통해 기존 복합 컨트롤 또는 Windows Forms 컨트롤에서 사용자 지정 컨트롤을 만들 수 있습니다. 또한 사용자 지정 그리기를 구현 하는 사용자 컨트롤을 디자인할 수 있습니다. 이러한 옵션에는 상당한 유연성을 디자인 및 시각적 인터페이스의 기능을 활성화합니다. 이러한 기능을 이용 하려면 개체 지향 프로그래밍 개념에 잘 알고 있어야 합니다.  
  
> [!NOTE]
>  상속의 완벽 한 이해를 할 필요는 없습니다 하지만 하 게 찾을 수 있습니다 [빌드에 없음: Visual Basic에서 상속](http://msdn.microsoft.com/ko-kr/e5e6e240-ed31-4657-820c-079b7c79313c)합니다.  
  
 Web Forms에서 사용 하 여, 참조 하는 사용자 지정 컨트롤을 만들려는 경우 [사용자 지정 ASP.NET 서버 컨트롤 개발](../Topic/Developing%20Custom%20ASP.NET%20Server%20Controls.md)합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [연습: Visual Basic에서 합성 컨트롤 제작](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 Visual Basic에서 간단한 복합 컨트롤을 만드는 방법을 보여 줍니다.  
  
 [연습: Visual C#에서 합성 컨트롤 제작](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 C#에서 간단한 복합 컨트롤을 만드는 방법을 보여 줍니다.  
  
 [연습: Visual Basic로 Windows Forms 컨트롤에서 상속](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 Visual Basic에서 상속을 사용 하는 간단한 Windows Forms 컨트롤을 만드는 방법을 보여 줍니다.  
  
 [연습: Visual C# Windows Forms 컨트롤에서 상속](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
 C#에서 상속을 사용 하는 간단한 Windows Forms 컨트롤을 만드는 방법을 보여 줍니다.  
  
 [연습: Windows에서 스마트 태그를 사용 하 여 일반적인 작업을 수행 Forms 컨트롤](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)  
 Windows Forms 컨트롤에서 스마트 태그 기능을 사용 하는 방법을 보여 줍니다.  
  
 [연습: DesignerSerializationVisibilityAttribute 사용 하 여 표준 형식의 컬렉션 직렬화](../../../../docs/framework/winforms/controls/serializing-collections-designerserializationvisibilityattribute.md)  
 사용 하는 방법을 보여 줍니다는 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=fullName> 컬렉션을 serialize 하는 특성입니다.  
  
 [연습: 사용자 지정 Windows Forms 컨트롤 디버깅 디자인 타임에](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
 Windows Forms 컨트롤의 디자인 타임 동작을 디버그 하는 방법을 보여 줍니다.  
  
 [연습: Visual Studio 디자인 타임 기능을 활용 하는 Windows Forms 컨트롤 만들기](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 합성 컨트롤을 디자인 환경으로 통합 하는 방법을 보여 줍니다.  
  
 [방법: Windows Forms 컨트롤 제작](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 Windows Forms 컨트롤을 구현 하기 위한 고려 사항에 간략하게 설명 합니다.  
  
 [방법: 합성 컨트롤 제작](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 합성 컨트롤에서 상속 하 여 컨트롤을 만드는 방법을 보여 줍니다.  
  
 [방법: UserControl 클래스에서 상속](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 복합 컨트롤을 만드는 절차의 개요를 제공 합니다.  
  
 [방법: 기존 Windows Forms 컨트롤에서에서 상속](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 상속 하 여 확장된 된 컨트롤을 만드는 방법을 보여 줍니다는 <xref:System.Windows.Forms.Button> 클래스를 제어 합니다.  
  
 [방법: Control 클래스에서 상속](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 확장된 된 컨트롤 만들기의 개요를 제공 합니다.  
  
 [방법: 디자인 타임에 컨트롤을 폼의 가장자리에 맞춤](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 사용 하는 방법을 보여 줍니다는 <xref:System.Windows.Forms.Control.Dock%2A> 컨트롤을 폼의 가장자리를 정렬 하는 속성입니다.  
  
 [방법: 컨트롤에 표시 된 도구 상자 항목 선택 대화 상자](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 에 표시 되도록 컨트롤을 설치 하기 위한 절차를 보여 줍니다.는 **도구 상자 사용자 지정** 대화 상자입니다.  
  
 [방법: 컨트롤에 대 한 도구 상자 비트맵 제공](../../../../docs/framework/winforms/controls/how-to-provide-a-toolbox-bitmap-for-a-control.md)  
 사용 하는 방법을 보여 줍니다는 <xref:System.Drawing.ToolboxBitmapAttribute> 에서 사용자 지정 컨트롤 옆에 있는 아이콘을 표시 하는 **도구 상자**합니다.  
  
 [방법: UserControl의 런타임 동작 테스트](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
 사용 하는 방법을 보여 줍니다는 **테스트** 합성 컨트롤의 동작을 테스트 합니다.  
  
 [Windows Forms 디자이너에서 디자인 타임 오류](../../../../docs/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer.md)  
 Windows Forms 디자이너를 로드 하지 못한 경우 Microsoft Visual Studio에 표시 되는 디자인 타임 오류 목록의 사용 및 의미에 설명 합니다.  
  
 [컨트롤 및 구성 요소 제작 문제 해결](../../../../docs/framework/winforms/controls/troubleshooting-control-and-component-authoring.md)  
 진단 및 사용자 지정 구성 요소 또는 컨트롤을 작성할 때 발생할 수 있는 일반적인 문제를 해결 하는 방법을 보여 줍니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Windows.Forms.Control?displayProperty=fullName>  
 이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=fullName>  
 이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [사용자 지정 Windows Forms 컨트롤.NET framework 개발](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 .NET Framework와 함께 사용자 지정 컨트롤을 만드는 방법에 설명 합니다.  
  
 [언어 독립성 및 언어 독립적 구성 요소](../../../../docs/standard/language-independence-and-language-independent-components.md)  
 공용 언어 런타임 생성 및 구성 요소의 사용을 간소화 하도록 설계 된를 소개 합니다. 이러한 단순화 중요 한 측면은 다양 한 프로그래밍 언어를 사용 하 여 작성 하는 구성 요소 간의 상호 운용성 향상된. 공용 언어 사양 (CLS) 도구와 여러 프로그래밍 언어를 사용 하는 구성 요소를 만들 수 있습니다.  
  
 [연습: 사용자 지정 구성 요소를 도구 상자에 자동으로 채우기](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 구성 요소 또는 컨트롤에 표시할 수 있도록 하는 방법에 설명 된 **도구 상자 사용자 지정** 대화 상자입니다.