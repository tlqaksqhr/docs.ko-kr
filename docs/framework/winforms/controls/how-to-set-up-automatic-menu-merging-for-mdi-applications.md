---
title: "방법: MDI 응용 프로그램의 자동 메뉴 병합 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1e99aed38ed6c3af3424c264631f0eaf27e46af7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a>방법: MDI 응용 프로그램의 자동 메뉴 병합 설정
(Mdi 다중) 다중 문서 인터페이스 응용 프로그램에서 자동 병합을 설정 하기 위한 기본 단계를 제공 하는 다음 절차 <xref:System.Windows.Forms.MenuStrip>합니다.  
  
### <a name="to-set-up-automatic-menu-merging"></a>자동 메뉴 병합 설정 하려면  
  
1.  설정 하 여 MDI 부모 폼을 만듭니다는 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 속성을 `true`합니다.  
  
2.  추가 <xref:System.Windows.Forms.MenuStrip> 설정 MDI 부모에 해당 <xref:System.Windows.Forms.Form.MainMenuStrip%2A> 속성 <xref:System.Windows.Forms.MenuStrip>합니다.  
  
3.  MDI 자식 폼을 만들고 설정 해당 <xref:System.Windows.Forms.Form.MdiParent%2A> 속성을 부모 폼의 이름입니다.  
  
4.  추가 <xref:System.Windows.Forms.MenuStrip> MDI 자식 폼입니다.  
  
5.  자식 폼에서 설정 된 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 의 속성은 <xref:System.Windows.Forms.MenuStrip> 를 `false`합니다.  
  
6.  자식 폼의에 메뉴 항목 추가 <xref:System.Windows.Forms.MenuStrip> 부모 폼에 병합 하려는 <xref:System.Windows.Forms.MenuStrip> 자식 폼이 활성화 하는 경우.  
  
7.  사용 하 여는 <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> 자식 폼의 속성 메뉴 항목 <xref:System.Windows.Forms.MenuStrip> 부모 폼에 병합 되는 방식을 제어할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [MenuStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
