---
title: "WPF 컨트롤 사용 | Microsoft Docs"
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
  - "상호 운용성[WPF]"
  - "Windows Forms 디자이너, WPF와 상호 운용성"
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# WPF 컨트롤 사용
Windows Forms 기반 응용 프로그램에서 WPF\(Windows Presentation Foundation\) 컨트롤을 사용할 수 있습니다.  Windows Forms과 WPF는 서로 다른 뷰 기술이지만 원활하게 상호 운용됩니다.  
  
 Windows Forms 디자이너는 Windows Presentation Foundation 컨트롤을 호스팅하기 위한 시각적 디자인 환경을 제공합니다.  WPF 컨트롤은 <xref:System.Windows.Forms.Integration.ElementHost>라는 특수한 Windows Forms 컨트롤에 의해 호스팅됩니다.  이 컨트롤을 사용하면 WPF 컨트롤이 폼의 레이아웃에 참가하고 키보드 및 마우스 메시지를 받을 수 있습니다.  디자인 타임에 Windows Forms 컨트롤과 같은 방식으로 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을 정렬할 수 있습니다.  
  
 또한 Windows Forms 컨트롤을 WPF 기반 응용 프로그램에 사용할 수 있습니다.  자세한 내용은 [WPF Designer](http://msdn.microsoft.com/ko-kr/c6c65214-8411-4e16-b254-163ed4099c26)를 참조하십시오.  
  
## 단원 내용  
 [방법: 디자인 타임에 ElementHost 컨트롤 복사하여 붙여넣기](../../../../docs/framework/winforms/advanced/how-to-copy-and-paste-an-elementhost-control-at-design-time.md)  
 Windows Forms에 Windows Presentation Foundation 컨트롤을 복사하는 방법을 보여 줍니다.  
  
 [연습: 디자인 타임에 Windows Forms에서 WPF 콘텐츠 정렬](../../../../docs/framework/winforms/advanced/walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)  
 위치 고정 및 맞춤선 등의 Windows Forms 레이아웃 기능을 사용하여 Windows Presentation Foundation 컨트롤을 정렬하는 방법을 보여 줍니다.  
  
 [연습: 디자인 타임에 호스팅된 WPF 요소의 속성 변경](../../../../docs/framework/winforms/advanced/walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time.md)  
 WPF 컨트롤에서 속성을 변경하기 위한 Windows Forms 디자이너와 [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] 간의 워크플로를 보여 줍니다.  
  
 [연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)  
 Windows Forms 기반 응용 프로그램에서 사용하기 위한 Windows Presentation Foundation 컨트롤을 만드는 방법을 보여 줍니다.  
  
 [연습: ElementHost 컨트롤을 복사하여 다른 Windows Forms에 붙여넣기](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 Windows Presentation Foundation 컨트롤을 특정 Windows Forms에서 다른 Windows Forms로 복사하는 방법을 보여 줍니다.  
  
 [연습: 디자인 타임에 Windows Forms에서 WPF 콘텐츠 할당](../../../../docs/framework/winforms/advanced/walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)  
 폼에 표시할 Windows Presentation Foundation 컨트롤 형식을 선택하는 방법을 보여 줍니다.  
  
 [연습: WPF 콘텐츠 스타일 지정](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)  
 Windows Presentation Foundation 컨트롤에 스타일을 적용하기 위한 Windows Forms 디자이너와 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] 간의 워크플로를 보여 줍니다.  
  
## 참조  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 Windows Forms 기반 응용 프로그램에서 Windows Presentation Foundation 컨트롤을 호스팅하는 데 사용할 수 있는 클래스에 대해 설명합니다.  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 Windows Presentation Foundation 기반 응용 프로그램에서 Windows Forms 컨트롤을 호스팅하는 데 사용할 수 있는 클래스에 대해 설명합니다.  
  
## 관련 단원  
 [마이그레이션 및 상호 운용성](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 Windows Presentation Foundation 및 Windows Forms 기술 간의 상호 운용에 대해 설명합니다.  
  
 [WPF Designer](http://msdn.microsoft.com/ko-kr/c6c65214-8411-4e16-b254-163ed4099c26)  
 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 Windows Presentation Foundation 컨트롤을 디자인하는 방법에 대해 설명합니다.