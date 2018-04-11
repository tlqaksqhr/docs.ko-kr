---
title: '방법: 두 DataRepeater 컨트롤 (Visual Studio)를 사용 하 여 마스터-세부 폼 만들기'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- DataRepeater, master/detail tables
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f17cb86c3ea0ea056291a51becd7ecf9f73d0a73
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/10/2018
---
# <a name="how-to-create-a-masterdetail-form-by-using-two-datarepeater-controls-visual-studio"></a>방법: 두 DataRepeater 컨트롤을 사용하여 마스터/세부 폼 만들기(Visual Studio)
두 개 이상의 사용 하 여 관련된 데이터를 표시할 수 있습니다 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 마스터/세부 폼을 만들 컨트롤입니다. 예를 들어 하나에 고객의 목록을 표시 하려면 수 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, 사용자가 고객을 선택 하는 경우 두 번째에 해당 고객의 주문 목록을 표시 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>합니다.  
  
 동일한 마스터 테이블 노드를 공유 하는 세부 항목을 끌어 관련된 데이터를 표시할 수 있습니다는 **데이터 원본** 창으로는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다. 예를 들어 Customers 테이블과 관련된 Orders 테이블에 있는 데이터 소스를 설정한 경우 두 테이블 모두 노드로 표시 최상위 트리 뷰에 **데이터 소스** 창. 열을 볼 수 있도록 Customers 노드를 확장 합니다. Orders 테이블을 나타내는 확장 가능한 노드 목록에서 마지막 열 임을 확인 합니다. 이 노드는 고객에 대 한 관련된 주문을 나타냅니다.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-display-related-data-in-two-datarepeater-controls"></a>두 DataRepeater 컨트롤에 관련된 데이터 표시  
  
1.  두 개 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 에서 제어는 **Visual Basic PowerPacks** 탭에 **도구 상자** 폼 이나 컨테이너 컨트롤로 합니다.  
  
2.  컨트롤의 크기와 위치를 함께 위치 및 크기 조정 핸들을 끌어 합니다.  
  
3.  **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.  
  
    > [!NOTE]
    >  경우는 **데이터 소스** 창이 비어 있는 경우 데이터 소스를 추가 합니다. 자세한 내용은 [새 데이터 소스 추가](/visualstudio/data-tools/add-new-data-sources)를 참조하세요.  
  
4.  에 **데이터 소스** 창 마스터 테이블에 대 한 최상위 노드를 선택 합니다.  
  
5.  클릭 하 여 세부 정보를 마스터 테이블의 놓기 형식을 변경할 **세부 정보** 테이블 노드의 드롭다운 목록에 있습니다.  
  
6.  첫 번째 항목 템플릿 영역 마스터 테이블 노드를 끌어 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다.  
  
7.  마스터 테이블 노드를 확장 하 고 관련된 테이블에 대 한 상세 노드를 선택 합니다.  
  
8.  클릭 하 여 세부 정보를 테이블의 놓기 형식을 변경 **세부 정보** 테이블 노드의 드롭다운 목록에 있습니다.  
  
9. 이 테이블 노드를 선택 하 고 두 번째 항목 템플릿 영역으로 끌어 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [DataRepeater 컨트롤 소개](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [방법: DataRepeater 컨트롤의 바인딩된 데이터 표시](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [방법: Windows Forms 응용 프로그램에서 관련 데이터 표시](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)  
 [방법: DataRepeater 컨트롤의 모양 변경](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [DataRepeater 컨트롤 문제 해결](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
