---
title: "방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤의 형식 변경"
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
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f2c0cc5136aaed3f7465102e7e7b6d2d9c2fc920
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤의 형식 변경
Windows Forms에 이미 추가 된 열의 형식을 변경 하려면 수도 있습니다 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 예를 들어, 다음 유형의 데이터 원본에 컨트롤을 바인딩하는 경우 자동으로 생성 되는 열 중 일부를 수정 하는 것이 좋습니다. 표시 하면 테이블에 열이 관련된 테이블의 행에 외래 키가 포함 된 경우에 유용 합니다. 이 경우 다음 관련된 테이블에서 좀 더 의미 있는 값을 표시 하는 콤보 상자 열으로 이러한 외래 키를 표시 하는 텍스트 상자가 열을 대체 하는 것이 좋습니다.  
  
 다음 절차를 수행 하려면는 **Windows 응용 프로그램** 포함 된 폼을 사용 하 여 프로젝트는 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 이러한 프로젝트 설정에 대 한 정보를 참조 하십시오. [하는 방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [하는 방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-change-the-type-of-a-column-using-the-designer"></a>디자이너를 사용 하는 열의 형식을 변경 하려면  
  
1.  스마트 태그 문자 모양을 클릭 (![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))의 오른쪽 위 모서리에는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 다음 선택 **열 편집**합니다.  
  
2.  열을 선택 된 **선택한 열** 목록입니다.  
  
3.  에 **열 속성** 눈금 설정에서 `ColumnType` 속성을 새 열 형식입니다.  
  
    > [!NOTE]
    >  `ColumnType` 속성은 디자인 타임 전용 속성 열 형식을 나타내는 클래스입니다. 실제 열 클래스에 정의 된 속성이 아닙니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 [방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
