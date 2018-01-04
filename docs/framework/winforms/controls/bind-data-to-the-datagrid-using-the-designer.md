---
title: "방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 데이터 바인딩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, binding to a data source
- data sources [Windows Forms], binding to Windows Forms controls
- DataGridView control [Windows Forms], data binding
ms.assetid: f4f46009-cec2-441b-8668-6b5af057558b
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a31b407360467f37c2e60b1a3f4f4c72e80e13a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 데이터 바인딩
디자이너를 사용 하 여 연결할 수는 <xref:System.Windows.Forms.DataGridView> 데이터베이스, 비즈니스 개체 또는 웹 서비스를 포함 하는 여러 다른 종류의 데이터 원본에 대 한 제어 합니다. 컨트롤에 자동으로 바인딩되어 디자이너를 사용 하 여 데이터 소스에 컨트롤을 바인딩하는 경우는 <xref:System.Windows.Forms.BindingSource> 데이터 원본을 나타내는 구성 요소입니다. 또한 열은 데이터 소스에서 제공하는 스키마 정보와 일치하는 컨트롤에 자동으로 생성됩니다.  
  
 열을 생성한 후에 사용자 요구에 맞게 수정할 수 있습니다. 예를 들어 표시하지 않아도 되는 열을 제거하거나 숨길 수 있습니다. 열을 다시 정렬하거나 열 형식을 수정할 수도 있습니다. 열을 수정하는 방법에 대한 자세한 내용은 [참고 항목] 섹션에 나열된 항목을 참조하세요.  
  
 여러 바인딩할 수도 있습니다 <xref:System.Windows.Forms.DataGridView> 마스터/세부 관계를 만들기 위해 관련된 테이블에는 컨트롤입니다. 이 구성에서 하나의 컨트롤은 부모 테이블을 표시하고 다른 컨트롤은 부모 테이블에 있는 현재 행에 관련된 자식 테이블의 해당 행만을 표시합니다. 자세한 내용은 [방법: Windows Forms 응용 프로그램에서 관련 데이터 표시](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)를 참조하세요.  
  
 다음 절차를 수행 하려면는 **Windows 응용 프로그램** 포함 하는 폼을 사용 하 여 프로젝트는 <xref:System.Windows.Forms.DataGridView> 컨트롤 또는 마스터/세부 관계에 대 한 컨트롤을 두 가지입니다. 이러한 프로젝트를 시작하는 방법에 대한 정보는 [방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)를 참조하세요.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-bind-the-control-to-a-data-source"></a>데이터 소스에 컨트롤을 바인딩하려면  
  
1.  스마트 태그 문자 모양을 클릭 (![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))의 오른쪽 위 모서리에는 <xref:System.Windows.Forms.DataGridView> 제어 합니다.  
  
2.  **데이터 소스 선택** 옵션에서 드롭다운 화살표를 클릭합니다.  
  
3.  프로젝트에 데이터 소스가 아직 없는 경우 **프로젝트 데이터 소스 추가**를 클릭하고 마법사에 의해 표시된 단계를 따릅니다.  
  
     자세한 내용은 [데이터 소스 구성 마법사](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f)를 참조하세요. 새 데이터 소스은 **데이터 소스 선택** 드롭다운 창에 표시됩니다. 새 데이터 소스에 단일 데이터베이스 테이블과 같은 하나의 구성원만이 포함되는 경우 컨트롤은 해당 구성원에 자동으로 바인딩됩니다. 그렇지 않으면 다음 단계를 계속합니다.  
  
4.  **기타 데이터 소스** 및 **프로젝트 데이터 소스** 노드가 아직 확장되지 않은 경우 확장한 다음 컨트롤을 바인딩할 데이터 소스를 선택합니다.  
  
5.  데이터 소스에 두 개 이상의 멤버, 예: if 만든 경우는 <xref:System.Data.DataSet?displayProperty=nameWithType> 여러 테이블을 포함 하, 데이터 소스를 확장 한 다음에 바인딩할 특정 멤버를 선택 합니다.  
  
6.  마스터/세부 관계를 만들려면는 **데이터 소스 선택** 두 번째에 대 한 드롭다운 창 <xref:System.Windows.Forms.DataGridView> 컨트롤을 확장 하 고는 <xref:System.Windows.Forms.BindingSource> 부모 테이블에 대해 생성 한 다음 목록에서 관련된 자식 테이블을 선택 표시 됩니다.  
  
    > [!NOTE]
    >  프로젝트에 데이터 소스가 이미 있으면 **데이터 소스** 창을 사용하여 데이터 양식을 만들 수도 있습니다. 자세한 내용은 [데이터 소스 창](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.DataGridView.DataMember%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 [방법: 데이터베이스의 데이터에 연결](http://msdn.microsoft.com/library/6c56e54e-8834-4297-85aa-cc1a443ba556)  
 [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 순서 변경](../../../../docs/framework/winforms/controls/change-the-order-of-columns-in-the-datagrid-using-the-designer.md)  
 [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤의 형식 변경](../../../../docs/framework/winforms/controls/change-the-type-of-a-wf-datagridview-column-using-the-designer.md)  
 [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 고정](../../../../docs/framework/winforms/controls/freeze-columns-in-the-datagrid-using-the-designer.md)  
 [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 고정](../../../../docs/framework/winforms/controls/hide-columns-in-the-datagrid-using-the-designer.md)  
 [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열을 읽기 전용으로 설정](../../../../docs/framework/winforms/controls/make-columns-read-only-in-the-datagrid-using-the-designer.md)  
 [방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [데이터 소스 창](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)  
 [방법: Windows Forms 응용 프로그램에서 관련 데이터 표시](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)
