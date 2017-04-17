---
title: "방법: 디자이너를 사용하여 Windows Forms DataGrid 컨트롤에 테이블 및 열 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "열[Windows Forms], DataGrid 컨트롤에 추가"
  - "DataGrid 컨트롤[Windows Forms], 테이블 및 열 추가"
  - "테이블[Windows Forms], DataGrid 컨트롤에 추가"
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 디자이너를 사용하여 Windows Forms DataGrid 컨트롤에 테이블 및 열 추가
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 <xref:System.Windows.Forms.DataGridTableStyle> 개체를 만든 다음 <xref:System.Windows.Forms.DataGrid> 컨트롤의 <xref:System.Windows.Forms.DataGrid.TableStyles%2A> 속성을 통해 액세스할 수 있는 <xref:System.Windows.Forms.GridTableStylesCollection> 개체에 추가하여 테이블과 열에 Windows Forms <xref:System.Windows.Forms.DataGrid> 컨트롤의 데이터를 표시할 수 있습니다.  각 테이블 스타일은 <xref:System.Windows.Forms.DataGridTableStyle>의 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> 속성에 어떤 데이터 테이블이 지정되든 상관없이 그 내용을 표시합니다.  기본적으로 열 스타일이 지정되지 않은 테이블 스타일은 해당 데이터 테이블 안에 있는 모든 열을 표시합니다.  각 <xref:System.Windows.Forms.DataGridTableStyle>의 <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> 속성을 통해 액세스할 수 있는 <xref:System.Windows.Forms.GridColumnStylesCollection>에 <xref:System.Windows.Forms.DataGridColumnStyle> 개체를 추가하여 표시될 테이블의 열을 제한할 수 있습니다.  
  
 다음 절차를 수행하려면 <xref:System.Windows.Forms.DataGrid> 컨트롤이 포함된 폼이 있는 **Windows 응용 프로그램** 프로젝트가 필요합니다.  이러한 프로젝트를 설정하는 방법에 대한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)를 참조하십시오.  기본적으로 [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)]에서는 <xref:System.Windows.Forms.DataGrid> 컨트롤이 **도구 상자**에 없습니다.  이 컨트롤을 추가하는 방법에 대한 자세한 내용은 [How to: Add Items to the Toolbox](http://msdn.microsoft.com/ko-kr/458e119e-17fe-450b-b889-e31c128bd7e0)를 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 디자이너에서 DataGrid 컨트롤에 테이블을 추가하려면  
  
1.  테이블의 데이터를 표시하려면 먼저 <xref:System.Windows.Forms.DataGrid> 컨트롤을 데이터 집합에 바인딩해야 합니다.  자세한 내용은 [방법: 디자이너를 사용하여 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩](../../../../docs/framework/winforms/controls/bind-wf-datagrid-control-to-a-data-source-using-the-designer.md)을 참조하십시오.  
  
2.  속성 창에서 <xref:System.Windows.Forms.DataGrid> 컨트롤의 <xref:System.Windows.Forms.DataGrid.TableStyles%2A> 속성을 선택한 다음 속성 옆에 있는 줄임표 단추\(![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\)를 클릭하여 **DataGridTableStyle 컬렉션 편집기**를 엽니다.  
  
3.  컬렉션 편집기에서 **추가**를 클릭하여 테이블 스타일을 삽입합니다.  
  
4.  **확인**을 클릭하여 컬렉션 편집기를 닫은 다음 <xref:System.Windows.Forms.DataGrid.TableStyles%2A> 속성 옆에 있는 줄임표 단추를 클릭하여 다시 엽니다.  
  
     컬렉션 편집기를 다시 열면 해당 컨트롤에 바인딩된 모든 데이터 테이블이 테이블 스타일의 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> 속성에 대한 드롭다운 목록에 나타납니다.  
  
5.  컬렉션 편집기의 **멤버** 상자에서 테이블 스타일을 클릭합니다.  
  
6.  컬렉션 편집기의 **속성** 상자에서 표시할 테이블에 대한 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> 값을 선택합니다.  
  
### 디자이너에서 DataGrid 컨트롤에 열을 추가하려면  
  
1.  **DataGridTableStyle 컬렉션 편집기**의 **멤버** 상자에서 적절한 테이블 스타일을 선택합니다.  컬렉션 편집기의 **속성** 상자에서 <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> 컬렉션을 선택한 다음 속성 옆의 줄임표 단추\(![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\)를 클릭하여 **DataGridColumnStyle 컬렉션 편집기**를 표시합니다.  
  
2.  컬렉션 편집기에서 **추가** 단추를 클릭하여 열 스타일을 삽입하거나 **추가** 단추 옆에 있는 아래쪽 화살표를 클릭하여 열 형식을 지정합니다.  
  
     드롭다운 상자에서 <xref:System.Windows.Forms.DataGridTextBoxColumn> 또는 <xref:System.Windows.Forms.DataGridBoolColumn> 형식을 선택할 수 있습니다.  
  
3.  확인을 클릭하여 **DataGridColumnStyle 컬렉션 편집기**를 닫은 다음 <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> 속성 옆에 있는 줄임표 단추를 클릭하여 다시 엽니다.  
  
     컬렉션 편집기를 다시 열면 바인딩된 데이터 테이블에 있는 데이터 열이 열 스타일의 <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> 속성에 대한 드롭다운 목록에 나타납니다.  
  
4.  컬렉션 편집기의 **멤버** 상자에서 열 스타일을 클릭합니다.  
  
5.  컬렉션 편집기의 **속성** 상자에서 표시할 열에 대한 <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> 값을 선택합니다.  
  
## 참고 항목  
 [DataGrid 컨트롤](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [방법: Windows Forms DataGrid 컨트롤에서 열 삭제 또는 숨기기](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)