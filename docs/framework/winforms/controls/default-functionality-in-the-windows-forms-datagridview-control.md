---
title: "Windows Forms DataGridView 컨트롤의 기본 기능"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ecb8cdaa4e8eb0498259c597e0de3f80c3106549
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤의 기본 기능
Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤은 상당한 양의 기본 기능으로 사용자가 제공 합니다.  
  
## <a name="default-functionality"></a>기본 기능  
 기본적으로는 <xref:System.Windows.Forms.DataGridView> 제어:  
  
-   열 머리글 및 행 머리글 계속 표시 되는 테이블을 세로로 스크롤할 때는 자동으로 표시 됩니다.  
  
-   현재 행에 대 한 선택 표시기를 포함 하는 행 헤더를 있습니다.  
  
-   선택 영역 직사각형 첫 번째 셀에 저장 합니다.  
  
-   열 구분선을 두 번 클릭할 때 자동으로 조정할 수 있는 열이 있습니다.  
  
-   Windows XP 및 Windows Server 2003 제품군에서 비주얼 스타일을 자동으로 지원 때는 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 에서 응용 프로그램의 메서드는 `Main` 메서드.  
  
 또한의 콘텐츠는 <xref:System.Windows.Forms.DataGridView> 기본적으로 컨트롤을 편집할 수 있습니다.  
  
-   사용자가 두 번 클릭 또는 셀에서 f2 키를 누를 경우 컨트롤 자동으로 셀을 편집 모드로 전환 하 고 사용자가 셀의 내용을 업데이트.  
  
-   사용자가 눈금의 끝에 스크롤할 사용자는 새 레코드를 추가 하는 한 개의 행이 있는지 표시 됩니다. 이 행을 클릭 하면 새 행에 추가 됩니다는 <xref:System.Windows.Forms.DataGridView> 기본 값으로 제어 합니다. 사용자가 esc 키를 누르면이 새 행이 사라집니다.  
  
-   사용자가 행 머리글을 클릭 하면 전체 행이 선택 됩니다.  
  
 바인딩하는 경우는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 데이터 소스를 설정 하 여 해당 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성, 컨트롤:  
  
-   열 머리글 텍스트 데이터 원본 열의 이름을 자동으로 사용 합니다.  
  
-   데이터 원본의 내용으로 채워집니다. <xref:System.Windows.Forms.DataGridView>열은 데이터 원본의 각 열에 대해 자동으로 만들어집니다.  
  
-   테이블에 표시 되는 각 행에 대 한 행을 만듭니다.  
  
-   열 머리글을 마우스 오른쪽 단추로 클릭할 때 기본 데이터에 따라 행을 자동으로 정렬 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 [DataGridView 컨트롤](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
