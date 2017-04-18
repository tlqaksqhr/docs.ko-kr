---
title: "방법: 디자이너를 사용하여 Windows Forms DataGrid 컨트롤에 마스터-세부 목록 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "DataGrid 컨트롤[Windows Forms], 마스터-세부 목록"
  - "마스터-세부 목록"
  - "관계 테이블, DataGrid 컨트롤에 표시"
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 디자이너를 사용하여 Windows Forms DataGrid 컨트롤에 마스터-세부 목록 만들기
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 <xref:System.Data.DataSet>에 일련의 관련된 테이블이 포함된 경우에는 두 개의 <xref:System.Windows.Forms.DataGrid> 컨트롤을 사용하여 데이터를 마스터\-세부 형식으로 표시할 수 있습니다.  <xref:System.Windows.Forms.DataGrid> 하나는 마스터 데이터 표이고 다른 하나는 세부 데이터 표입니다.  마스터 목록에서 항목을 선택하면 관련된 자식 항목이 모두 세부 목록에 표시됩니다.  예를 들어, <xref:System.Data.DataSet>에 Customers 테이블과 이 테이블에 관련된 Orders 테이블이 있는 경우에는 Customers 테이블을 마스터 데이터 표로 지정하고 Orders 테이블을 세부 데이터 표로 지정할 수 있습니다.  마스터 데이터 표에서 고객을 선택하면 해당 고객과 관련된 Order 테이블의 모든 주문이 세부 데이터 표에 표시됩니다.  
  
 다음 절차를 수행하려면 **Windows 응용 프로그램** 프로젝트가 필요합니다.  이러한 프로젝트 설정에 대한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 디자이너에서 마스터\-세부 목록을 만들려면  
  
1.  두 개의 <xref:System.Windows.Forms.DataGrid> 컨트롤을 폼에 추가합니다.  자세한 내용은 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)를 참조하십시오.  [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)]에서는 기본적으로 <xref:System.Windows.Forms.DataGrid> 컨트롤이 **도구 상자**에 없습니다.  자세한 내용은 [How to: Add Items to the Toolbox](http://msdn.microsoft.com/ko-kr/458e119e-17fe-450b-b889-e31c128bd7e0)를 참조하십시오.  
  
    > [!NOTE]
    >  다음 단계는 **데이터 소스** 창을 사용하여 디자인 타임 데이터 바인딩을 수행하는 [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)]에는 적용되지 않습니다.  자세한 내용은 [Visual Studio에서 데이터에 컨트롤 바인딩](../Topic/Bind%20controls%20to%20data%20in%20Visual%20Studio.md) 및 [방법: Windows Forms 응용 프로그램에서 관련 데이터 표시](../Topic/How%20to:%20Display%20Related%20Data%20in%20a%20Windows%20Forms%20Application.md)를 참조하십시오.  
  
2.  **서버 탐색기**에서 두 개 이상의 테이블을 폼으로 끌어 옵니다.  
  
3.  **데이터** 메뉴에서 **데이터 집합 생성**을 선택합니다.  
  
4.  XML 디자이너를 사용하여 테이블 사이의 관계를 설정합니다.  자세한 내용은 MSDN에서 “How to: Create One\-to\-Many Relationships in XML Schemas and Datasets”를 참조하십시오.  
  
5.  **파일** 메뉴에서 **모두 저장**을 선택하여 관계를 저장합니다.  
  
6.  마스터 데이터 표로 지정할 <xref:System.Windows.Forms.DataGrid> 컨트롤을 다음과 같이 구성합니다.  
  
    1.  <xref:System.Windows.Forms.DataGrid.DataSource%2A> 속성의 드롭다운 목록에서 <xref:System.Data.DataSet>을 선택합니다.  
  
    2.  <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성에 있는 드롭다운 목록에서 마스터 테이블\(예:"Customers"\)을 선택합니다.  
  
7.  세부 데이터 표로 지정할 <xref:System.Windows.Forms.DataGrid> 컨트롤을 다음과 같이 구성합니다.  
  
    1.  <xref:System.Windows.Forms.DataGrid.DataSource%2A> 속성의 드롭다운 목록에서 <xref:System.Data.DataSet>을 선택합니다.  
  
    2.  <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성에 있는 드롭다운 목록에서 마스터 테이블과 세부 테이블 사이의 관계\(예: "Customers.CustOrd"\)를 선택합니다.  관계를 확인하려면 드롭다운 목록에서 마스터 테이블 옆에 있는 더하기\(**\+**\) 기호를 클릭하여 노드를 확장합니다.  
  
## 참고 항목  
 [DataGrid 컨트롤](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [DataGrid 컨트롤 개요](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)   
 [방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../Topic/Bind%20controls%20to%20data%20in%20Visual%20Studio.md)