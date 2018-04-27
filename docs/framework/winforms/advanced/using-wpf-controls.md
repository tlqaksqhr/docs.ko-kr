---
title: WPF 컨트롤 사용
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b8225447e6c0daa7894d622616131febb6ac82b5
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="using-wpf-controls"></a>WPF 컨트롤 사용
Windows Forms 기반 응용 프로그램에서 Windows Presentation Foundation (WPF) 컨트롤을 사용할 수 있습니다. 이러한 옵션은 두 가지 서로 다른 뷰 기술, 상호 운용 되 원활 하 게 합니다.  
  
 Windows Forms 디자이너에는 Windows Presentation Foundation 컨트롤을 호스팅하기 위한 시각적 디자인 환경을 제공 합니다. 라고 하는 특수 Windows Forms 컨트롤에서 WPF 컨트롤 호스트 <xref:System.Windows.Forms.Integration.ElementHost>합니다. 이 컨트롤을는 WPF 컨트롤을 폼의 레이아웃에 관여 하 고 키보드 및 마우스 메시지를 받을 수 있습니다. 디자인 타임에 정렬할 수 있습니다는 <xref:System.Windows.Forms.Integration.ElementHost> 방법과 마찬가지로 Windows Forms 컨트롤을 제어 합니다.  
  
 WPF 기반 응용 프로그램에서 Windows Forms 컨트롤을 사용할 수도 있습니다. 자세한 내용은 참조 [WPF 디자이너](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: 디자인 타임에 ElementHost 컨트롤 복사하여 붙여넣기](../../../../docs/framework/winforms/advanced/how-to-copy-and-paste-an-elementhost-control-at-design-time.md)  
 Windows Form에 Windows Presentation Foundation 컨트롤을 복사 하는 방법을 보여 줍니다.  
  
 [연습: 디자인 타임에 Windows Forms에서 WPF 콘텐츠 정렬](../../../../docs/framework/winforms/advanced/walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)  
 Windows Presentation Foundation 컨트롤을 정렬 하려면 기준 위치 지정 및 맞춤선과 같은 Windows Forms 레이아웃 기능을 사용 하는 방법을 보여 줍니다.  
  
 [연습: 디자인 타임에 호스팅된 WPF 요소의 속성 변경](../../../../docs/framework/winforms/advanced/walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time.md)  
 Windows Forms 디자이너 간의 워크플로 표시 및 [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] WPF 컨트롤에 속성을 변경 합니다.  
  
 [연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)  
 Windows Forms 기반 응용 프로그램에서 사용 하기 위해 Windows Presentation Foundation 컨트롤을 만드는 방법을 보여 줍니다.  
  
 [연습: ElementHost 컨트롤을 복사하여 다른 Windows Forms에 붙여넣기](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 하나의 Windows Form에서 Windows Presentation Foundation 컨트롤 복사 하는 방법을 보여 줍니다.  
  
 [연습: 디자인 타임에 Windows Forms에서 WPF 콘텐츠 할당](../../../../docs/framework/winforms/advanced/walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)  
 폼에 표시 하려는 Windows Presentation Foundation 컨트롤 종류를 선택 하는 방법을 보여 줍니다.  
  
 [연습: WPF 콘텐츠 스타일 지정](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)  
 Windows Forms 디자이너 간의 워크플로 보여 줍니다. 및 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] Windows Presentation Foundation 컨트롤에 스타일을 적용 합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 Windows Forms 기반 응용 프로그램에서 호스트 Windows Presentation Foundation 컨트롤에 사용할 수 있는 클래스를 설명 합니다.  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 Windows Presentation Foundation 기반 응용 프로그램 호스트 Windows Forms 컨트롤에 사용할 수 있는 클래스를 설명 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [마이그레이션 및 상호 운용성](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 Windows Presentation Foundation 및 Windows Forms 기술 간의 상호 운용성에 설명합니다.  
  
 [WPF 디자이너](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 Visual Studio에서 Windows Presentation Foundation 컨트롤을 디자인 하는 방법에 설명 합니다.
