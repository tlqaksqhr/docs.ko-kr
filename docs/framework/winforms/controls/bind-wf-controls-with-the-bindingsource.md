---
title: '방법: 디자이너를 사용하여 Windows Forms 컨트롤에 BindingSource 구성 요소 바인딩'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
ms.openlocfilehash: 3acbd17e8e969bb448e6deaf17dec23e44fa3bd4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527565"
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms 컨트롤에 BindingSource 구성 요소 바인딩
컨트롤은 런타임 시 사용자가 변경 하 고 수 응용 프로그램과 관련 된 데이터에 저장 되도록 폼에 컨트롤을 추가 하 고 응용 프로그램에 대 한 사용자 인터페이스를 확인 한, 후 데이터 원본에 바인딩할 수 있습니다.  
  
 사용 하 여 가장 쉬운 방법은 Windows Forms에서 컨트롤 또는 일련의 컨트롤을 바인딩하는 <xref:System.Windows.Forms.BindingSource> 폼에 컨트롤 및 데이터 원본 사이의 연결 고리로 제어 합니다.  
  
 폼에 하나 이상의 컨트롤을 데이터에 바인딩될 수 있습니다. 다음 절차에는 <xref:System.Windows.Forms.TextBox> 컨트롤이 데이터 원본에 바인딩되어 있습니다.  
  
 절차를 완료 하려면 데이터베이스에서 파생 된 데이터 원본에 바인딩 한다고 가정 합니다. 다른 데이터 저장소에서 데이터 소스를 만드는 방법에 대 한 자세한 내용은 참조 하십시오. [새 데이터 원본을 추가](/visualstudio/data-tools/add-new-data-sources)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-bind-a-control-at-design-time"></a>디자인 타임에 컨트롤을 바인딩하려면  
  
1.  끌어서는 <xref:System.Windows.Forms.TextBox> 컨트롤을 폼입니다.  
  
2.  에 **속성** 창:  
  
    1.  확장 된 **(DataBindings)** 노드.  
  
    2.  옆에 있는 화살표를 클릭는 <xref:System.Windows.Forms.TextBox.Text%2A> 속성입니다.  
  
         **DataSource** UI 형식 편집기가 열립니다.  
  
         프로젝트 또는 폼에 대 한 데이터 소스를 이전에 구성 하는 경우 표시 됩니다.  
  
3.  **프로젝트 데이터 소스 추가**를 클릭하여 데이터에 연결한 다음 데이터 소스를 만듭니다.  
  
4.  **데이터 소스 구성 마법사** 시작 페이지에서 **다음**을 클릭합니다.  
  
5.  에 **데이터 소스 형식 선택** 페이지에서 **데이터베이스**합니다.  
  
6.  에 **데이터 연결 선택** 페이지에서 사용 가능한 연결 목록에서 데이터 연결을 선택 합니다. 원하는 데이터 연결 선택 사용할 수 없는 경우 **새 연결** 새 데이터 연결을 만듭니다.  
  
7.  선택 **예, 연결을 저장** 응용 프로그램 구성 파일에서 연결 문자열을 저장 합니다.  
  
8.  응용 프로그램에 바인딩할 데이터베이스 개체를 선택합니다. 이 예에서 선택 하는 테이블에서 필드를 선택는 <xref:System.Windows.Forms.TextBox> 표시 합니다.  
  
9. 원하는 경우 기본 데이터베이스 이름을 바꿉니다.  
  
10. **마침**을 클릭합니다.  
  
11. 에 **속성** 창 옆에 있는 화살표를 클릭는 <xref:System.Windows.Forms.TextBox.Text%2A> 다시 속성입니다. 에 **DataSource** UI 형식 편집기 바인딩할 필드의 이름을 선택은 <xref:System.Windows.Forms.TextBox> 를 합니다.  
  
     **DataSource** UI 형식 편집기를 닫고 데이터 집합 <xref:System.Windows.Forms.BindingSource> 및 테이블 어댑터 관련 데이터 연결 폼에 추가 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.BindingNavigator>  
 [새 데이터 소스 추가](/visualstudio/data-tools/add-new-data-sources)  
 [데이터 소스 창](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)
