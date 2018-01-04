---
title: "방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 숨기기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], hiding
- DataGridView control [Windows Forms], column hiding
- data [Windows Forms], displaying
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 42a48ed8074901c5ee8a6dc2fd22e58e5a72be57
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 숨기기
Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤에서 사용할 수 있는 열 중 일부만 표시하려는 경우도 있습니다. 예를 들어 수 표시 하려는 직원 급여 열을 다른 사용자 로부터 숨기 려 관리 자격 증명이 있는 사용자입니다. 또는 다음 중에서 일부만 표시 하려는 많은 열을 포함 하는 데이터 원본에 컨트롤을 바인딩하는 것이 좋습니다. 이 경우 숨기기 보다는 표시에 관심이 없는 열은 일반적으로 제거 합니다. 자세한 내용은 참조 [하는 방법: 열 추가 및 제거는 Windows Forms DataGridView 컨트롤 사용 하 여 디자이너에서](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)합니다.  
  
 다음 절차를 수행 하려면는 **Windows 응용 프로그램** 포함 된 폼을 사용 하 여 프로젝트는 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 이러한 프로젝트 설정에 대 한 정보를 참조 하십시오. [하는 방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [하는 방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-hide-a-column-using-the-designer"></a>디자이너를 사용 하 여 열을 숨기려면  
  
1.  스마트 태그 문자 모양을 클릭 (![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))의 오른쪽 위 모서리에는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 다음 선택 **열 편집**합니다.  
  
2.  열을 선택 된 **선택한 열** 목록입니다.  
  
3.  에 **열 속성** 눈금 설정는 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> 속성을 `false`합니다.  
  
    > [!NOTE]
    >  선택을 취소 하 여 추가할 때 열을 숨길 수도 있습니다는 **Visible** 확인란에는 **열 추가** 대화 상자.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>  
 [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 [방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
