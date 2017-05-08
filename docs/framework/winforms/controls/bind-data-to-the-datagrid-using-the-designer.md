---
title: "방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 데이터 바인딩 | Microsoft Docs"
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
  - "데이터 소스, Windows Forms 컨트롤에 바인딩"
  - "DataGridView 컨트롤[Windows Forms], 데이터 바인딩"
  - "Windows Forms 컨트롤, 데이터 소스에 바인딩"
ms.assetid: f4f46009-cec2-441b-8668-6b5af057558b
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# 방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 데이터 바인딩
디자이너를 사용하여 <xref:System.Windows.Forms.DataGridView> 컨트롤을 데이터베이스, 비즈니스 개체, 웹 서비스 등 여러 가지 다양한 요소의 데이터 소스에 연결할 수 있습니다.  디자이너를 사용하여 컨트롤을 데이터 소스에 바인딩하는 경우 컨트롤은 데이터 소스를 나타내는 <xref:System.Windows.Forms.BindingSource> 구성 요소에 자동으로 바인딩됩니다.  또한 데이터 소스에서 제공되는 스키마 정보와 일치하도록 컨트롤에 열이 자동으로 생성됩니다.  
  
 열이 생성된 후 사용자의 필요에 맞게 열을 수정할 수 있습니다.  예를 들어, 표시하지 않으려는 열을 제거하거나 숨길 수 있으며 열을 다시 배열하거나 열 형식을 수정할 수 있습니다.  열 수정에 대한 자세한 내용은 참고 항목에 나열된 항목을 참조하십시오.  
  
 여러 <xref:System.Windows.Forms.DataGridView> 컨트롤을 관련 테이블에 바인딩하여 마스터\/세부 관계를 만들 수도 있습니다.  이 구성에서는 한 컨트롤에 부모 테이블이 표시되고 다른 컨트롤에는 부모 테이블의 현재 행과 관련된 자식 테이블의 해당 행만 표시됩니다.  자세한 내용은 [방법: Windows Forms 응용 프로그램에서 관련 데이터 표시](../Topic/How%20to:%20Display%20Related%20Data%20in%20a%20Windows%20Forms%20Application.md)를 참조하십시오.  
  
 다음 절차를 수행하려면 <xref:System.Windows.Forms.DataGridView> 컨트롤이나 마스터\/세부 관계의 두 컨트롤이 포함된 폼이 있는 **Windows 응용 프로그램** 프로젝트가 필요합니다.  이러한 프로젝트를 시작하는 방법에 대한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)를 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 컨트롤을 데이터 소스에 바인딩하려면  
  
1.  <xref:System.Windows.Forms.DataGridView> 컨트롤의 오른쪽 위 모퉁이에서 스마트 태그 문자 모양\(![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\)을 클릭합니다.  
  
2.  **데이터 소스 선택** 옵션에 대한 드롭다운 화살표를 클릭합니다.  
  
3.  프로젝트에 데이터 소스가 없는 경우 **프로젝트 데이터 소스 추가**를 클릭하고 마법사에서 지시하는 단계를 따릅니다.  
  
     자세한 내용은 [데이터 소스 구성 마법사](../Topic/Data%20Source%20Configuration%20Wizard.md)를 참조하십시오.  새 데이터 소스가 **데이터 소스 선택** 드롭다운 창에 나타납니다.  새 데이터 소스에 하나의 멤버\(예: 단일 데이터베이스 테이블\)만 있는 경우 컨트롤은 해당 멤버에 자동으로 바인딩됩니다.  그렇지 않으면 다음 단계를 계속합니다.  
  
4.  **기타 데이터 소스** 및 **프로젝트 데이터 소스** 노드가 확장되어 있지 않으면 이를 확장하고 컨트롤을 바인딩할 데이터 소스를 선택합니다.  
  
5.  여러 테이블이 포함된 <xref:System.Data.DataSet?displayProperty=fullName>을 만든 경우와 같이 데이터 소스에 두 개 이상의 멤버가 있는 경우, 데이터 소스를 확장하고 바인딩할 특정 멤버를 선택합니다.  
  
6.  마스터\/세부 관계를 만들려면 두 번째 <xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 **데이터 소스 선택** 드롭다운 창에서 부모 테이블에 대해 만든 <xref:System.Windows.Forms.BindingSource>를 확장한 다음 표시되는 목록에서 관련 자식 테이블을 선택합니다.  
  
    > [!NOTE]
    >  프로젝트에 이미 데이터 소스가 있으면 **데이터 소스** 창을 사용하여 데이터 폼을 만들 수도 있습니다.  자세한 내용은 [데이터 소스 창](../Topic/Data%20Sources%20Window.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 <xref:System.Windows.Forms.DataGridView.DataMember%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=fullName>   
 [방법: 데이터베이스의 데이터에 연결](../Topic/How%20to:%20Connect%20to%20Data%20in%20a%20Database.md)   
 [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)   
 [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 순서 변경](../../../../docs/framework/winforms/controls/change-the-order-of-columns-in-the-datagrid-using-the-designer.md)   
 [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤의 형식 변경](../../../../docs/framework/winforms/controls/change-the-type-of-a-wf-datagridview-column-using-the-designer.md)   
 [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 고정](../../../../docs/framework/winforms/controls/freeze-columns-in-the-datagrid-using-the-designer.md)   
 [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 숨기기](../../../../docs/framework/winforms/controls/hide-columns-in-the-datagrid-using-the-designer.md)   
 [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열을 읽기 전용으로 설정](../../../../docs/framework/winforms/controls/make-columns-read-only-in-the-datagrid-using-the-designer.md)   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)   
 [데이터 소스 창](../Topic/Data%20Sources%20Window.md)   
 [방법: Windows Forms 응용 프로그램에서 관련 데이터 표시](../Topic/How%20to:%20Display%20Related%20Data%20in%20a%20Windows%20Forms%20Application.md)