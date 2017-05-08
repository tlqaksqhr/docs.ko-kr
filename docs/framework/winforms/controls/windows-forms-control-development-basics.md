---
title: "Windows Forms 컨트롤 개발 기본 사항 | Microsoft Docs"
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
  - "컨트롤[Windows Forms], 만들기"
  - "사용자 지정 컨트롤[Windows Forms], 파생 형식"
  - "프로그래밍 개념, Windows Forms 컨트롤"
ms.assetid: 6277bb81-90f7-4c5b-9f4b-b02bb42dd316
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Windows Forms 컨트롤 개발 기본 사항
Windows Forms 컨트롤은 <xref:System.Windows.Forms.Control?displayProperty=fullName>에서 직접 또는 간접적으로 파생되는 클래스입니다.  다음 목록에서는 Windows Forms 컨트롤을 개발하기 위한 일반 시나리오를 설명합니다.  
  
-   기존 컨트롤을 결합하여 복합 컨트롤을 만듭니다.  
  
     복합 컨트롤은 컨트롤로 다시 사용할 수 있는 사용자 인터페이스를 캡슐화합니다.  텍스트 상자와 원래대로 단추로 구성된 컨트롤이 복합 컨트롤의 예입니다.  비주얼 디자이너는 복합 컨트롤을 만들기 위해 다양한 기능을 지원합니다.  복합 컨트롤을 만들려면 <xref:System.Windows.Forms.UserControl?displayProperty=fullName>에서 파생하십시오.  기본 클래스 <xref:System.Windows.Forms.UserControl>에서는 자식 컨트롤에 대한 키보드 라우팅을 제공하고 자식 컨트롤이 그룹으로 작동할 수 있게 해줍니다.  자세한 내용은 [합성 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md)을 참조하십시오.  
  
-   기존 컨트롤을 확장하여 사용자 지정하거나 기능에 추가합니다.  
  
     확장된 컨트롤의 예로는 색을 변경할 수 없는 단추 및 클릭한 횟수를 추적하는 추가 속성을 가진 단추가 있습니다.  Windows Forms 컨트롤에서 파생하고 속성, 메서드 및 이벤트를 재정의하거나 추가하여 Windows Forms 컨트롤을 사용자 지정할 수 있습니다.  
  
-   기존 컨트롤을 결합하거나 확장하지 않는 컨트롤을 만듭니다.  
  
     이 시나리오에서는 기본 클래스 <xref:System.Windows.Forms.Control>에서 컨트롤을 파생하십시오.  기본 클래스의 속성, 메서드 및 이벤트를 재정의할 수 있을 뿐만 아니라 추가할 수도 있습니다.  시작하려면 [방법: 간단한 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)을 참조하십시오.  
  
 Windows Forms 컨트롤의 기본 클래스 <xref:System.Windows.Forms.Control>에서는 클라이언트 쪽 Windows 기반 응용 프로그램을 시각적으로 표시하기 위한 기능을 제공합니다.  <xref:System.Windows.Forms.Control>에서는 창 핸들을 제공하고, 메시지 라우팅을 처리하고, 마우스 및 키보드 이벤트를 비롯하여 다른 여러 가지 사용자 인터페이스 이벤트를 제공합니다.  또한 고급 레이아웃을 제공하며, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A> 등과 같은 시각적 표시와 관련된 속성을 갖고 있습니다.  이 외에도 보안, 스레딩 지원 및 ActiveX 컨트롤과의 상호 운용성을 제공합니다.  인프라 대부분을 기본 클래스에서 제공하기 때문에 사용자 자신의 Windows Forms 컨트롤을 상대적으로 쉽게 개발할 수 있습니다.  
  
## 참고 항목  
 [방법: 간단한 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)   
 [합성 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md)   
 [방법: 진행률을 보여 주는 Windows Forms 컨트롤 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)   
 [사용자 지정 컨트롤의 종류](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)