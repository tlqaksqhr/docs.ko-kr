---
title: Windows Forms DataGridView 컨트롤의 데이터 정렬
ms.date: 02/13/2018
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
ms.openlocfilehash: 1cbfb4a19e9bb0db5cbb595a91a254a3a8e3f309
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536015"
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤의 데이터 정렬

기본적으로 사용자의 데이터를 정렬할 수는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 텍스트 상자 열 머리글을 클릭 하 여 (또는.NET Framework 4.7.2 및 이상 버전에서 텍스트 상자 셀 포커스가 있을 때 F3 키를 눌러). 수정할 수 있습니다는 <xref:System.Windows.Forms.DataGridViewColumn.SortMode> 사용자가 작업을 수행 하는 경우 다른 형식의 열을 정렬할 수 있도록 특정 열 속성입니다. 임의의 열 또는 여러 열으로 프로그래밍 방식으로 데이터를 정렬할 수 수도 있습니다.

## <a name="in-this-section"></a>단원 내용

[Windows Forms DataGridView 컨트롤의 열 정렬 모드](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)  
컨트롤의 데이터 정렬에 대 한 옵션에 설명 합니다.

[방법: Windows Forms DataGridView 컨트롤의 열 정렬 모드 설정](../../../../docs/framework/winforms/controls/set-the-sort-modes-for-columns-wf-datagridview-control.md)  
사용자가 기본적으로 정렬 가능 하지 않은 열을 정렬할 수 있도록 하는 방법에 설명 합니다.

[방법: Windows Forms DataGridView 컨트롤에서 정렬 사용자 지정](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
프로그래밍 방식으로 데이터를 정렬 하는 방법 및 정렬을 사용 하 여 사용자 지정 하는 방법에 설명 된 <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> 이벤트 또는 구현 하 여는 <xref:System.Collections.IComparer> 인터페이스입니다.

## <a name="reference"></a>참조

<xref:System.Windows.Forms.DataGridView>  
<xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridView.Sort%2A> 메서드.

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 속성입니다.

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridViewColumnSortMode> 열거형입니다.

## <a name="see-also"></a>참고자료

[DataGridView 컨트롤](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
[Windows Forms DataGridView 컨트롤의 열 형식](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  