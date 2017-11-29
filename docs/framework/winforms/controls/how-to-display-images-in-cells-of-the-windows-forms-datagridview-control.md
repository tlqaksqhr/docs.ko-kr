---
title: "방법: Windows Forms DataGridView 컨트롤의 셀에 이미지 표시"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], displaying images
- data grids [Windows Forms], displaying in grids
- DataGridView control [Windows Forms], displaying images
- data grids [Windows Forms], displaying images in cells
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b2e06298d0ead9a2dd9fa554af0c42df5d61d56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a>방법: Windows Forms DataGridView 컨트롤의 셀에 이미지 표시
그림 또는 그래픽 데이터의 행에 표시할 수 있는 값 중 하나입니다. 대부분의 경우 이러한 그래픽 직원의 사진은 또는 회사 로고의 형식을 따릅니다.  
  
 그림을 통합 하는 내에서 데이터를 표시할 때 간단는 <xref:System.Windows.Forms.DataGridView> 제어 합니다. <xref:System.Windows.Forms.DataGridView> 컨트롤이 고유 하 게 처리 하는 모든 이미지 형식에서 지원 되는 <xref:System.Drawing.Image> 클래스 뿐만 아니라 OLE 그림 일부 데이터베이스에서 사용 하는 형식입니다.  
  
 경우는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 데이터 소스에 이미지의 열, 자동으로 표시 됩니다는 <xref:System.Windows.Forms.DataGridView> 제어 합니다.  
  
 다음 코드 예제에서는 포함된 된 리소스에서 아이콘을 추출 하 고 이미지 열의 모든 셀에 표시 하기 위해 비트맵으로 변환 하는 방법을 보여 줍니다. 해당 이미지와 함께 텍스트 셀 값을 대체 하는 또 다른 예제를 보려면 [하는 방법: Windows Forms DataGridView 컨트롤에서 사용자 지정 데이터 형식](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)합니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   `dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
-   라는 포함 된 아이콘 리소스 `tree.ico`합니다.  
  
-   <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> 및 <xref:System.Drawing?displayProperty=nameWithType> 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 [Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 [방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 사용자 지정](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
