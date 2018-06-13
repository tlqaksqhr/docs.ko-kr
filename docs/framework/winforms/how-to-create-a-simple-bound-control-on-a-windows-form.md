---
title: '방법: Windows Form에 단순 바인딩된 컨트롤 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
ms.openlocfilehash: ce4585a1c5c2b9acbdb7ec33c62a1e91851b720e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538834"
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a>방법: Windows Form에 단순 바인딩된 컨트롤 만들기
와 *단순 바인딩*, 컨트롤에서 데이터 집합 테이블에서 열 값과 같은 단일 데이터 요소를 표시할 수 있습니다. 컨트롤의 속성을 데이터 값에 단순 바인딩할 수 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-simple-bind-a-control"></a>단순 컨트롤을 바인딩  
  
1.  데이터 소스에 연결합니다. 자세한 내용은 참조 [데이터 원본에 연결할](../../../docs/framework/data/adonet/connecting-to-a-data-source.md)합니다.  
  
2.  양식에서 컨트롤을 선택 하 고 표시 된 **속성** 창.  
  
3.  확장 된 **(DataBindings)** 속성입니다.  
  
     가장 자주 바인딩된 속성 아래에 표시 됩니다는 **(DataBindings)** 속성입니다. 예를 들어 대부분의 컨트롤에에서는 **텍스트** 속성이 바인딩되는 가장 자주 있습니다.  
  
4.  속성 하려는 경우 바인딩 중 하나가 아닙니다 일반적인 바인딩된 속성을 클릭는 **줄임표** 단추 (![VisualStudioEllipsesButton 스크린 샷](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton") )에 **(고급)** 상자를 표시 하려면는 **서식 지정 및 고급 바인딩** 해당 컨트롤에 대 한 속성의 전체 목록을 대화 상자.  
  
5.  바인딩하고 아래의 드롭다운 화살표를 클릭 하 고 원하는 속성을 선택 **바인딩**합니다.  
  
     사용 가능한 데이터 소스 목록이 표시됩니다.  
  
6.  원하는 단일 데이터 요소를 찾을 때까지 바인딩할 데이터 소스를 확장합니다. 예를 들어 데이터 집합의 테이블에서 열 값에 바인딩할 경우 데이터 집합 이름을 확장하고 나서 테이블을 이름을 확장하여 열 이름을 표시합니다.  
  
7.  바인딩할 요소 이름을 클릭합니다.  
  
8.  작업 하는 경우는 **서식 지정 및 고급 바인딩** 대화 상자를 클릭 **확인** 돌아가려면는 **속성** 창.  
  
9. 컨트롤의 추가 속성을 바인딩할 경우 3-7 단계를 반복 합니다.  
  
    > [!NOTE]
    >  되기 때문에 단순 바인딩된 컨트롤에는 하나의 데이터 요소만 표시 Windows Form을 단순 바인딩된 컨트롤에서 탐색 논리를 포함 하는 매우 일반적인.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Binding>  
 [Windows Forms 데이터 바인딩](../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [데이터 바인딩 및 Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
