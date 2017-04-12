---
title: "방법: 두 DataRepeater 컨트롤 (Visual Studio)를 사용 하 여 마스터-세부 폼 만들기 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- DataRepeater, master/detail tables
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 23789bb11cab17b50928651e1dc00d5d59640c0f
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-masterdetail-form-by-using-two-datarepeater-controls-visual-studio"></a>방법: 두 DataRepeater 컨트롤을 사용하여 마스터/세부 폼 만들기(Visual Studio)
두 개 이상 사용 하 여 관련된 데이터를 표시할 수 있습니다 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>마스터/세부 폼을 만들 컨트롤.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 예를 들어 하나에 고객의 목록을 표시 하려면 수 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, 사용자가 고객을 선택 하는 경우 조금 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 해당 고객의 주문 목록을 표시 하 고</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
 동일한 마스터 테이블 노드를 공유 하는 세부 항목을 끌어 관련된 데이터를 표시할 수는 **데이터 원본** 창으로는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>제어 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 예를 들어 Customers 테이블 및 관련된 Orders 테이블에 있는 데이터 원본에 있으면 두 테이블 모두으로 표시에서 트리 뷰의 최상위 노드는 **데이터 원본** 창입니다. 열을 볼 수 있도록 Customers 노드를 확장 합니다. 목록에서 마지막 열 Orders 테이블을 나타내는 노드임이 되는지 확인 합니다. 이 노드는 고객에 대 한 관련된 주문을 나타냅니다.  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-display-related-data-in-two-datarepeater-controls"></a>두 개의 DataRepeater 컨트롤에 관련된 데이터 표시  
  
1.  두 개 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>에서 제어는 **Visual Basic PowerPacks** 탭에 **도구 상자** 폼 이나 컨테이너 컨트롤로.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
2.  컨트롤 크기를 지정 하 여 함께 배치할 위치 및 크기 조정 핸들을 끕니다.  
  
3.  **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.  
  
    > [!NOTE]
    >  하는 경우는 **데이터 원본** 창이 비어 있으면 데이터 소스를 추가 합니다. 자세한 내용은 참조 [새 데이터 소스를 추가할](https://docs.microsoft.com/visualstudio/data-tools/add-new-data-sources)합니다.  
  
4.  에 **데이터 원본** 창 마스터 테이블에 대 한 최상위 노드를 선택 합니다.  
  
5.  세부 정보를 클릭 하 여 마스터 테이블의 삭제 유형을 변경 **세부 정보** 테이블 노드의 드롭다운 목록에 있습니다.  
  
6.  첫 번째 항목 템플릿 영역 마스터 테이블 노드를 끌어 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>제어 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
7.  마스터 테이블 노드를 확장 하 고 관련된 테이블에 대 한 세부 정보 노드를 선택 합니다.  
  
8.  클릭 하 여 세부 정보를 테이블의 삭제 유형을 변경할 **세부 정보** 테이블 노드의 드롭다운 목록에 있습니다.  
  
9. 이 테이블 노드를 선택 하 고 두 번째 항목 템플릿 영역으로 끌어 옵니다 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>제어 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [DataRepeater 컨트롤 소개](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [방법: DataRepeater 컨트롤의 바인딩된 데이터 표시](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)   
 [방법: 관련 데이터에는 Windows Forms 응용 프로그램 표시](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)   
 [방법: DataRepeater 컨트롤의 모양 변경](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)   
 [DataRepeater 컨트롤 문제 해결](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
