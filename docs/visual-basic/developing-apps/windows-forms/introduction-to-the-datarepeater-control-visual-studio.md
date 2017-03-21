---
title: "DataRepeater 컨트롤 (Visual Studio) 소개 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- repeating data
- DataRepeater, overview
- DataRepeater
ms.assetid: 78a52a1d-65f0-4ecb-97ff-53bc114300c5
caps.latest.revision: 8
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 86078426494caabefc6bbfb036037007e830e1cb
ms.lasthandoff: 03/13/2017

---
# <a name="introduction-to-the-datarepeater-control-visual-studio"></a>DataRepeater 컨트롤 소개(Visual Studio)
Visual Basic Power Packs <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>표시 하는 컨트롤 데이터를 데이터베이스 테이블에 예를 들어, 행이 반복에 대 한 컨트롤은 스크롤 가능한 컨테이너.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 대 안으로 사용할 수는 <xref:System.Windows.Forms.DataGridView>데이터의 레이아웃을 제어할 수 더 필요한 경우를 제어 합니다.</xref:System.Windows.Forms.DataGridView> <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>관련된 컨트롤의 그룹을 스크롤 보기에서 여러 인스턴스를 만들어 "반복".</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 그러면 사용자가 동시에 여러 개의 레코드를 볼 수 있습니다.  
  
## <a name="overview"></a>개요  
 디자인 타임에는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>컨트롤 두 개의 섹션으로 구성 됩니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 외부 섹션은는 *뷰포트*런타임에 스크롤 데이터가 여기서 표시 됩니다. 라고 하는 내부 (위쪽) 섹션은 *항목 템플릿을*, 각 필드의 데이터 원본에 대 한 일반적으로 컨트롤 런타임에 반복 되는 컨트롤을 배치 합니다. 속성 및 항목 템플릿에 컨트롤에 캡슐화 되는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>속성.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>  
  
 런타임에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>가상에 복사 됩니다 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>각 레코드 스크롤될 때 데이터를 표시 하는 데 사용 되는 개체입니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> 개별 레코드의 표시를 사용자 지정할 수는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>이벤트, 예를 들어 여기에 포함 된 값에 따라 필드를 강조 표시 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> 자세한 내용은 참조 [하는 방법: DataRepeater 컨트롤의 모양을 변경](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)합니다.  
  
 에 대 한 가장 일반적인 용도 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>데이터베이스 테이블 또는 기타 바인딩된 데이터 소스에서 데이터를 표시 하는 컨트롤입니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 외에 [!INCLUDE[vstecado](../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)] 데이터 개체는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>제어를 구현 하는 모든 클래스에 바인딩할 수는 <xref:System.Collections.IList>(배열 포함) 인터페이스를 구현 하는 모든 클래스는 <xref:System.ComponentModel.IListSource>인터페이스를 구현 하는 클래스는 <xref:System.ComponentModel.IBindingList>인터페이스 또는 클래스를 구현 하는 <xref:System.ComponentModel.IBindingListView>인터페이스.</xref:System.ComponentModel.IBindingListView> </xref:System.ComponentModel.IBindingList> </xref:System.ComponentModel.IListSource> </xref:System.Collections.IList> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
### <a name="data-binding"></a>데이터 바인딩  
 필드를 끌어 데이터 바인딩을 수행 일반적으로 **데이터 원본** 창으로는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>제어 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 자세한 내용은 참조 [하는 방법: DataRepeater 컨트롤의 바인딩된 데이터 표시](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)합니다.  
  
 많은 양의 데이터를 사용할 때 설정할 수 있습니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>속성을 `True` 사용 가능한 데이터의 일부를 표시 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> 가상 모드 데이터 캐시를 구현 해야는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>채워지면 실행 시 데이터 캐시와의 모든 상호 작용을 제어 해야 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 자세한 내용은 참조 [DataRepeater 컨트롤의 가상 모드](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md)합니다.  
  
 에 바인딩되지 않은 컨트롤을 표시할 수도 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>제어 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 예를 들어, 각 항목에 반복 되는 이미지를 표시할 수 있습니다. 자세한 내용은 참조 [하는 방법: DataRepeater 컨트롤의 바인딩되지 않은 컨트롤 표시](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)합니다.  
  
### <a name="events"></a>이벤트  
 에 대 한 가장 중요 한 이벤트는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>제어 되는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>새 항목은 스크롤될 때 발생 하는 이벤트 및 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged>항목이 선택 될 때 발생 하는 이벤트입니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 사용할 수는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>항목의 모양을 변경 하는 이벤트입니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> 예를 들어 음수 값을 강조 표시할 수 있습니다. 사용 된 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged>항목을 선택 하는 경우 컨트롤의 값에 액세스 하는 이벤트입니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged>  
  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>컨트롤 노출 모든 표준 컨트롤 이벤트를 코드 편집기에서.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 그러나 일부 이벤트 쓰일 수 없습니다. 키보드 및 마우스 이벤트와 같은 `KeyDown`, `Click`, 및 `MouseDown` 때문에 런타임에 발생 하지 것입니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>컨트롤 자체에 포커스가 없으므로.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>런타임에만 만들었기 때문에 디자인 타임에 이벤트를 노출 하지 않습니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> 키보드 및 마우스 이벤트를 처리 하려는 경우를 추가할 수 있습니다는 <xref:System.Windows.Forms.Panel>컨트롤을 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>에서 디자인 타임 자격 증명과 <xref:System.Windows.Forms.Panel>.</xref:System.Windows.Forms.Panel> 에 대 한 이벤트를 처리 한 다음</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> </xref:System.Windows.Forms.Panel> 자세한 내용은 참조 [DataRepeater 컨트롤 문제 해결](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)합니다.  
  
### <a name="customizations"></a>사용자 지정  
 여러 가지 방법으로 모양 및 동작을 사용자 지정 하는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>런타임 및 디자인 타임에 모두 제어 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 색을 변경, 숨기기 또는 항목 헤더를 수정할 방향을 세로에서 가로로, 비롯 한 많은에서 변경할 속성을 설정할 수 있습니다. 자세한 내용은 참조 [하는 방법: DataRepeater 컨트롤의 모양을 변경](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md), [하는 방법: DataRepeater 컨트롤의 항목 머리글 표시](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md), 및 [하는 방법: DataRepeater 컨트롤의 레이아웃을 변경](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)합니다.  
  
 Note 일부 속성이 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>제어 하는 자체 반면 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> 에 적용 하는 다른 사용자</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 에 적용 됨 속성을 설정 하기 전에 선택한 컨트롤의 올바른 섹션이 있는지 확인 합니다. 자세한 내용은 참조 [하는 방법: DataRepeater 컨트롤의 모양을 변경](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)합니다.  
  
 기타 사용자 지정 레코드 추가 또는 삭제 하는 기능 제어, 등 검색 기능 추가 마스터 / 세부 형식에 관련된 데이터를 표시 합니다. 자세한 내용은 참조 [하는 방법: 추가 사용 하지 않도록 설정 하 고 DataRepeater 항목 삭제](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md), [하는 방법: DataRepeater 컨트롤의 데이터를 검색](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md), 및 [하는 방법: 두 DataRepeater 컨트롤 사용 (Visual Studio) 하 여 마스터/세부 폼 만들기](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md).  
  
## <a name="see-also"></a>참고 항목  
 [DataRepeater 컨트롤](../../../visual-basic/developing-apps/windows-forms/datarepeater-control-visual-studio.md)   
 [연습: DataRepeater 컨트롤의 데이터 표시](../../../visual-basic/developing-apps/windows-forms/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio.md)   
 [DataRepeater 컨트롤 문제 해결](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
