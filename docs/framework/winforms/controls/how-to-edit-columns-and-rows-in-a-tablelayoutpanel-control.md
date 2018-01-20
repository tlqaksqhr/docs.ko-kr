---
title: "방법: TableLayoutPanel 컨트롤에서 열과 행 편집"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: net.ComponentModel.StyleCollectionEditor
helpviewer_keywords:
- columns [Windows Forms], editing
- TableLayoutPanel control [Windows Forms], editing
- rows [Windows Forms], editing
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bf54a02a409bead598a4e98315d5709e55677f3b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a>방법: TableLayoutPanel 컨트롤에서 열과 행 편집
컬렉션 편집기를 사용할 수 있습니다는 <xref:System.Windows.Forms.TableLayoutPanel> 라는 컨트롤의 **열 및 행 스타일** 행과 컨트롤의 열을 편집 하려면 대화 상자.  
  
> [!NOTE]
>  여러 행 이나 열에 걸쳐 제어 설정에서 `RowSpan` 및 `ColumnSpan` 컨트롤의 속성에 있습니다. 자세한 내용은 [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)을 참조하세요.  
>   
>  사용 하 여 컨트롤의 셀 내에서 컨트롤 정렬 하려는 또는 확장을 제어 하려는 경우 <xref:System.Windows.Forms.Control.Anchor%2A> 속성입니다. 자세한 내용은 [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)을 참조하세요.  
>   
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-edit-rows-and-columns"></a>행과 열을 편집 하려면  
  
1.  끌어서는 <xref:System.Windows.Forms.TableLayoutPanel> 에서 제어는 **도구 상자** 폼으로 합니다.  
  
2.  클릭는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 스마트 태그 문자 모양 (![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))을 선택 하 고 **행 및 열 편집** 열려는  **열 및 행 스타일** 대화 상자. 또한 마우스 오른쪽 단추로 클릭할 수는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 하 고 선택 **행 및 열 편집** 바로 가기 메뉴에서.  
  
3.  를 추가 하거나 열을 제거 하려면 선택 **열** 에서 **멤버 유형을** 드롭다운 목록 상자입니다.  
  
4.  를 추가 하거나 행을 제거 하려면 선택 **행** 에서 **멤버 유형을** 드롭다운 목록 상자입니다.  
  
5.  클릭는 **추가** 의 끝에 행 또는 열을 추가 하려면 단추는 **멤버** 목록입니다.  
  
6.  클릭는 **삽입** 단추를 목록에서 행 또는 현재 선택 된 항목 앞에 열을 추가 합니다.  
  
7.  행 또는 열을 추가 하는 경우 선택 된 **크기 형식** 새로운 행 또는 열에 대 한 합니다. 자세한 내용은 <xref:System.Windows.Forms.SizeType>을 참조하세요.  
  
8.  행 또는 열을 제거 하려면 클릭는 **제거** 에서 현재 선택 된 항목을 삭제 단추는 **멤버** 목록입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.SizeType>  
 [TableLayoutPanel 컨트롤](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
