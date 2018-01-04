---
title: "LinkLabel 컨트롤 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: LinkLabel
helpviewer_keywords:
- links [Windows Forms], LinkLabel control
- Label control [Windows Forms], about Label control
- LinkLabel control [Windows Forms], about LinkLabel control
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 73bbd04b9ef5d2d0c5457dafb794435b3a4db380
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="linklabel-control-overview-windows-forms"></a>LinkLabel 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.LinkLabel> 컨트롤 Windows Forms 응용 프로그램에 웹 스타일 링크를 추가할 수 있습니다. 사용할 수는 <xref:System.Windows.Forms.LinkLabel> 사용할 수 있는 모든 항목에 대 한 제어는 <xref:System.Windows.Forms.Label> 제어 하는 데 있습니다; 또한 파일, 폴더 또는 웹 페이지에 대 한 링크로 텍스트의 일부를 설정할 수 있습니다.  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a>LinkLabel 컨트롤으로 수행할 수 있습니다  
 모든 속성, 메서드 및 이벤트를 실행 하는 것 외에도 <xref:System.Windows.Forms.Label> 컨트롤의 <xref:System.Windows.Forms.LinkLabel> 컨트롤에 대 한 하이퍼링크와 링크 색에 대 한 속성입니다. <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 속성은 활성화 된 링크 텍스트의 영역을 설정 합니다. <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, 및 <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> 속성 링크의 색을 설정 합니다. <xref:System.Windows.Forms.LinkLabel.LinkClicked> 이벤트 링크 텍스트를 선택 하는 경우를 결정 합니다.  
  
 가장 간단한 사용 시나리오는 <xref:System.Windows.Forms.LinkLabel> 제어를 사용 하 여 단일 링크를 표시 하는 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 있지만 속성을 사용 하 여 여러 개의 하이퍼링크를 표시할 수도 있습니다는 <xref:System.Windows.Forms.LinkLabel.Links%2A> 속성입니다. <xref:System.Windows.Forms.LinkLabel.Links%2A> 속성을 사용 하면 링크의 컬렉션에 액세스할 수 있습니다. 데이터를 지정할 수도 있습니다는 <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> 속성의 각 개별 <xref:System.Windows.Forms.LinkLabel.Link> 개체입니다. 값은 <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> 속성을 표시 하는 파일의 위치 또는 웹 사이트의 주소를 저장 하려면 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.LinkLabel>  
 [Label 컨트롤 개요](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [방법: Windows Forms LinkLabel 컨트롤을 사용하여 개체 또는 웹 페이지에 연결](../../../../docs/framework/winforms/controls/link-to-an-object-or-web-page-with-wf-linklabel-control.md)  
 [방법: Windows Forms LinkLabel 컨트롤의 모양 변경](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
