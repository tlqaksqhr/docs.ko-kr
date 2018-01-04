---
title: "방법: 디자이너를 사용하여 Windows Forms DataGrid 컨트롤에 마스터-세부 목록 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 471d76450b2a14620773cbeb8982da43f130ac59
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms DataGrid 컨트롤에 마스터-세부 목록 만들기
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다. 자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 경우에 <xref:System.Data.DataSet> 계열이 관련된 테이블의 두 사용할 수 있습니다 <xref:System.Windows.Forms.DataGrid> 마스터-세부 형식으로 데이터를 표시 하는 컨트롤입니다. 하나의 <xref:System.Windows.Forms.DataGrid> 는 마스터 데이터에 지정 된을 두 번째 세부 정보 표에서 되도록 지정 합니다. 목록에 항목을 선택 하면 관련된 자식 항목 모두 세부 목록에 표시 됩니다. 예를 들어 경우 프로그램 <xref:System.Data.DataSet> Customers 테이블 및 관련된 Orders 테이블을 포함 하는 마스터 데이터 Customers 테이블과 Orders 테이블에는 세부 정보 창 수를 지정 합니다. 마스터 모눈에서 고객을 선택 하면 Orders 테이블에서 해당 고객과 관련 된 주문의 모든 세부 정보 창에 표시 될.  
  
 다음 절차를 수행 하려면는 **Windows 응용 프로그램** 프로젝트. 이러한 프로젝트 설정에 대 한 정보를 참조 하십시오. [하는 방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-create-a-master-details-list-in-the-designer"></a>디자이너에서 마스터-세부 목록을 만들려면  
  
1.  두 개의 추가 <xref:System.Windows.Forms.DataGrid> 폼에 컨트롤을 합니다. 자세한 내용은 참조 [하는 방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)합니다. [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], <xref:System.Windows.Forms.DataGrid> 내에 **도구 상자** 기본적으로 합니다. 자세한 내용은 참조 [하는 방법: 도구 상자에 항목 추가](http://msdn.microsoft.com/en-us/458e119e-17fe-450b-b889-e31c128bd7e0)합니다.  
  
    > [!NOTE]
    >  다음 단계에 해당 하지 않는 [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)]를 사용 하는 **데이터 원본** 디자인 타임 데이터 바인딩에 대 한 창. 자세한 내용은 참조 [Visual Studio에서 데이터에 컨트롤 바인딩](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) 및 [하는 방법: Windows Forms 응용 프로그램에 관련 데이터 표시](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)합니다.  
  
2.  두 개 이상의 테이블을 끌어 **서버 탐색기** 양식입니다.  
  
3.  **데이터** 메뉴 선택 **데이터 집합 생성**합니다.  
  
4.  XML 디자이너를 사용 하 여 테이블 간의 관계를 설정 합니다. 세부 정보를 참조 하십시오. "하는 방법:-다 만들 XML 스키마 및 데이터 집합의 관계" msdn 합니다.  
  
5.  관계를 선택 하 여 저장 **모두 저장** 에서 **파일** 메뉴.  
  
6.  구성의 <xref:System.Windows.Forms.DataGrid> 컨트롤에는 마스터 데이터를 다음과 같이 지정 합니다.  
  
    1.  선택 된 <xref:System.Data.DataSet> 드롭 다운 목록에서는 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 속성입니다.  
  
    2.  마스터 테이블 (예를 들어 "Customers")에서 드롭 다운 목록에서 선택 된 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성입니다.  
  
7.  구성의 <xref:System.Windows.Forms.DataGrid> 컨트롤에는 세부 정보 창에 다음과 같이 지정 합니다.  
  
    1.  선택 된 <xref:System.Data.DataSet> 드롭 다운 목록에서는 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 속성입니다.  
  
    2.  드롭다운 목록에서 마스터 및 세부 테이블 간의 관계 (예: "Customers.CustOrd")를 선택는 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성입니다. 관계를 확인 하려면 더하기에서을 클릭 하 여 노드를 확장 (**+**) 드롭 다운 목록에서 마스터 테이블에 기호를 표시 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [DataGrid 컨트롤](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [DataGrid 컨트롤 개요](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 [Visual Studio에서 데이터에 컨트롤 바인딩](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
