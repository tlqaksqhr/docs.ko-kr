---
title: "디자인 타임에 Windows Forms 컨트롤 개발"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls [Windows Forms]
- Windows Forms controls, creating
- controls [Windows Forms]
- controls [Windows Forms], creating
- user controls [Windows Forms]
- custom controls [Windows Forms]
ms.assetid: e5a8e088-7ec8-4fd9-bcb3-9078fd134829
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a4f9680bb64339f2f232793beb9c47a36c07aa4a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="developing-windows-forms-controls-at-design-time"></a>디자인 타임에 Windows Forms 컨트롤 개발
.NET Framework는 컨트롤 제작자에게 다양한 컨트롤 제작 기술을 제공합니다. 제작자는 더 이상 기존 컨트롤의 컬렉션으로 작동하는 복합 컨트롤을 디자인하도록 제한되지 않습니다. 상속을 통해 기존의 복합 컨트롤 또는 Windows Forms 컨트롤에서 사용자 정의 컨트롤을 만들 수 있습니다. 또한 사용자 지정 그리기를 구현하는 사용자 정의 컨트롤을 디자인할 수 있습니다. 이러한 옵션을 사용하면 시각적 인터페이스의 디자인과 기능에 많은 유연성을 허용할 수 있습니다. 이러한 기능을 이용하려면 개체 지향 프로그래밍 개념을 잘 알고 있어야 합니다.  
  
> [!NOTE]
>  상속을 철저 하 게 파악 필요는 없지만 하 게 찾을 수 있습니다 [상속 기본 사항 (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)합니다.  
  
 Web Forms에서 사용할 사용자 지정 컨트롤을 만들려면 [사용자 지정 ASP.NET 서버 컨트롤 개발](http://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef)을 참조하세요.  
  
## <a name="in-this-section"></a>단원 내용  
 [연습: Visual Basic에서 복합 컨트롤 제작](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 Visual Basic에서 간단한 복합 컨트롤을 만드는 방법을 보여 줍니다.  
  
 [연습: Visual C#에서 복합 컨트롤 제작](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 C#에서 간단한 복합 컨트롤을 만드는 방법을 보여 줍니다.  
  
 [연습: Visual Basic을 사용하여 Windows Forms 컨트롤에서 상속](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 Visual Basic에서 상속을 사용하는 간단한 Windows Forms 컨트롤을 만드는 방법을 보여 줍니다.  
  
 [연습: Visual C#을 사용하여 Windows Forms 컨트롤에서 상속](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
 C#에서 상속을 사용하는 간단한 Windows Forms 컨트롤을 만드는 방법을 보여 줍니다.  
  
 [연습: Windows Forms 컨트롤에서 스마트 태그를 사용하여 일반 작업 수행](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)  
 Windows Forms 컨트롤에서 스마트 태그 기능을 사용하는 방법을 보여 줍니다.  
  
 [연습: DesignerSerializationVisibilityAttribute를 사용하여 표준 형식의 컬렉션 serialize](../../../../docs/framework/winforms/controls/serializing-collections-designerserializationvisibilityattribute.md)  
 사용 하는 방법을 보여 줍니다.는 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> 컬렉션을 serialize 하는 특성입니다.  
  
 [연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버깅](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
 Windows Forms 컨트롤의 디자인 타임 동작을 디버그하는 방법을 보여 줍니다.  
  
 [연습: Visual Studio의 디자인 타임 기능을 사용하는 Windows Forms 컨트롤 만들기](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 복합 컨트롤을 디자인 환경에 긴밀하게 통합하는 방법을 보여 줍니다.  
  
 [방법: Windows Forms 컨트롤 제작](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 Windows Forms 컨트롤을 구현할 때 고려해야 할 사항에 대해 간략하게 설명합니다.  
  
 [방법: 복합 컨트롤 제작](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 복합 컨트롤에서 상속하여 컨트롤을 만드는 방법을 보여 줍니다.  
  
 [방법: UserControl 클래스에서 상속](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 복합 컨트롤을 만드는 절차에 대해 간략하게 설명합니다.  
  
 [방법: 기존 Windows Forms 컨트롤에서 상속](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 상속 하 여 확장된 된 컨트롤을 만드는 방법을 보여 줍니다는 <xref:System.Windows.Forms.Button> 클래스를 제어 합니다.  
  
 [방법: Control 클래스에서 상속](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 확장 컨트롤을 만드는 방법에 대해 간략하게 설명합니다.  
  
 [방법: 디자인 타임에 컨트롤을 양식의 가장자리에 맞춤](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 사용 하는 방법을 보여 줍니다.는 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 사용자 컨트롤을 폼의 가장자리를 정렬 합니다.  
  
 [방법: 도구 상자 항목 선택 대화 상자에 컨트롤 표시](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 **도구 상자 사용자 지정** 대화 상자에 표시되도록 컨트롤을 설치하는 절차를 보여 줍니다.  
  
 [방법: 컨트롤에 대한 도구 상자 비트맵 제공](../../../../docs/framework/winforms/controls/how-to-provide-a-toolbox-bitmap-for-a-control.md)  
 사용 하는 방법을 보여 줍니다.는 <xref:System.Drawing.ToolboxBitmapAttribute> 에 사용자 지정 컨트롤 옆에 있는 아이콘을 표시 하는 **도구 상자**합니다.  
  
 [방법: UserControl의 런타임 동작 테스트](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
 **UserControl 테스트 컨테이너**를 사용하여 복합 컨트롤의 동작을 테스트하는 방법을 보여 줍니다.  
  
 [Windows Forms 디자이너의 디자인 타임 오류](../../../../docs/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer.md)  
 Windows Forms 디자이너를 로드하지 못할 때 Microsoft Visual Studio에 표시되는 디자인 타임 오류 목록의 의미와 용도에 대해 설명합니다.  
  
 [컨트롤 및 구성 요소 제작 문제 해결](../../../../docs/framework/winforms/controls/troubleshooting-control-and-component-authoring.md)  
 사용자 지정 구성 요소 또는 컨트롤을 작성할 때 발생할 수 있는 일반적인 문제를 진단하고 수정하는 방법을 보여 줍니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>  
 이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>  
 이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 .NET Framework를 사용하여 사용자 지정 컨트롤을 만드는 방법에 대해 설명합니다.  
  
 [언어 독립성 및 언어 독립적 구성 요소](../../../../docs/standard/language-independence-and-language-independent-components.md)  
 구성 요소의 생성과 사용을 간소화하도록 설계된 공용 언어 런타임을 소개합니다. 이러한 간소화의 중요한 측면은 다양한 프로그래밍 언어를 사용하여 작성된 구성 요소 간의 향상된 상호 운용성에 있습니다. CLS(공용 언어 사양)를 사용하면 여러 프로그래밍 언어를 사용하는 도구와 구성 요소를 만들 수 있습니다.  
  
 [연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 **도구 상자 사용자 지정** 대화 상자에 구성 요소 또는 컨트롤을 표시하는 방법에 대해 설명합니다.
