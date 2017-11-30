---
title: "방법: Windows Forms BindingSource 구성 요소를 사용하여 ADO.NET 데이터 정렬 및 필터링"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data
- data sorting [Windows Forms], ADO.NET
- data [Windows Forms], filtering
- BindingSource component [Windows Forms], sorting and filtering data
- filtering [Windows Forms], ADO.NET
- data [Windows Forms], sorting
- ADO.NET [Windows Forms]
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 46947e314394d56b5ef0439f33910bb493012db3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a>방법: Windows Forms BindingSource 구성 요소를 사용하여 ADO.NET 데이터 정렬 및 필터링
정렬 및 필터링 기능을 노출할 수 <xref:System.Windows.Forms.BindingSource> 를 통해 제어는 <xref:System.Windows.Forms.BindingSource.Sort%2A> 및 <xref:System.Windows.Forms.BindingSource.Filter%2A> 속성입니다. 기본 데이터 원본이 때 간단한 정렬을 적용할 수 있습니다는 <xref:System.ComponentModel.IBindingList>, 및 고급 데이터 원본 경우를 정렬 및 필터링을 적용할 수는 <xref:System.ComponentModel.IBindingListView>합니다. <xref:System.Windows.Forms.BindingSource.Sort%2A> 속성 해야 표준 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 구문: 데이터 원본의 데이터의 열 이름을 나타내는 문자열 뒤 `ASC` 또는 `DESC` 목록을 오름차순 또는 내림차순으로 정렬할지 여부를 나타냅니다. 고급 정렬 또는 각 열 쉼표 구분 기호가 구분 하 여 여러 열 정렬을 설정할 수 있습니다. <xref:System.Windows.Forms.BindingSource.Filter%2A> 속성은 문자열 식을 사용 합니다.  
  
> [!NOTE]
>  암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 응용 프로그램 보안 문제가 발생할 수 있습니다. 데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다. 자세한 내용은 [연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)를 참조하세요.  
  
### <a name="to-filter-data-with-the-bindingsource"></a>BindingSource가 있는 데이터를 필터링 하려면  
  
-   설정의 <xref:System.Windows.Forms.BindingSource.Filter%2A> 속성을 원하는 식입니다.  
  
     다음 코드 예제에서는 식에는 다음에 열에 대해 원하는 값 열 이름입니다.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a>BindingSource 사용 하 여 데이터를 정렬 하려면  
  
1.  설정의 <xref:System.Windows.Forms.BindingSource.Sort%2A> 속성을 원하는 열 이름 뒤 `ASC` 또는 `DESC` 를 오름차순 또는 내림차순을 나타내는입니다.  
  
2.  여러 열을 쉼표로 구분 합니다.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a>예제  
 다음 코드 예제에 Northwind 샘플 데이터베이스의 Customers 테이블에서 데이터를 로드 한 <xref:System.Windows.Forms.DataGridView> 를 제어 하 고 필터링 하 고 표시 된 데이터를 정렬 합니다.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제를 실행 하려면 포함 된 폼에 다음 코드를 붙여넣습니다는 <xref:System.Windows.Forms.BindingSource> 라는 `BindingSource1` 및 <xref:System.Windows.Forms.DataGridView> 라는 `dataGridView1`합니다. 처리는 <xref:System.Windows.Forms.Form.Load> 폼과 호출에 대 한 이벤트 `InitializeSortedFilteredBindingSource` 부하 이벤트 처리기 메서드에서 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.BindingSource.Sort%2A>  
 <xref:System.Windows.Forms.BindingSource.Filter%2A>  
 [방법: 샘플 데이터베이스 설치](http://msdn.microsoft.com/library/ed1291f6-604c-4972-ae22-0345c6dea12e)  
 [BindingSource 구성 요소](../../../../docs/framework/winforms/controls/bindingsource-component.md)
