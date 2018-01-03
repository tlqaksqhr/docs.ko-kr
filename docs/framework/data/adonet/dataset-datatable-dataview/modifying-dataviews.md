---
title: "데이터 보기 수정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 921707b07f1e8c8a9208df7de74512325f3027d2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="modifying-dataviews"></a>데이터 보기 수정
<xref:System.Data.DataView>를 사용하여 원본 테이블의 데이터 행을 추가, 삭제 또는 수정할 수 있습니다. 사용 하는 기능은 **DataView** 의 세 가지 부울 속성 중 하나를 설정 하 여 제어 되는 원본 테이블에 데이터를 수정 하는 **DataView**합니다. 이러한 속성에는 <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> 및 <xref:System.Data.DataView.AllowDelete%2A>가 있습니다. 으로 설정 되어 **true** 기본적으로 합니다.  
  
 경우 **AllowNew** 은 **true**를 사용할 수 있습니다는 <xref:System.Data.DataView.AddNew%2A> 의 메서드는 **DataView** 새로 만들려면 <xref:System.Data.DataRowView>합니다. 새 행 내부에 추가 <xref:System.Data.DataTable> 될 때까지 <xref:System.Data.DataRowView.EndEdit%2A> 의 메서드는 **DataRowView** 호출 됩니다. 경우는 <xref:System.Data.DataRowView.CancelEdit%2A> 의 메서드는 **DataRowView** 가 호출 된 새 행이 삭제 됩니다. 또한에 참고 하나만 편집할 수 **DataRowView** 한 번에 있습니다. 호출 하는 경우는 **AddNew** 또는 **BeginEdit** 의 메서드는 **DataRowView** 보류 중인 행이 있는 동안 **EndEdit** 에 암시적으로 호출 되는 보류 중인 행입니다. 때 **EndEdit** 은 호출 내부에 변경 내용이 적용 됩니다 **DataTable** 수 나중에 커밋하거나 거부할 사용 하는 **AcceptChanges** 또는  **RejectChanges** 의 메서드는 **DataTable**, **DataSet**, 또는 **DataRow** 개체입니다. 경우 **AllowNew** 은 **false**를 호출 하면 예외가 throw 됩니다는 **AddNew** 의 메서드는 **DataRowView**합니다.  
  
 경우 **AllowEdit** 은 **true**의 콘텐츠를 수정할 수는 **DataRow** 통해는 **DataRowView**합니다. 변경 내용을 사용 하 여 원본 행을 확인할 수 있습니다 **DataRowView.EndEdit** 를 사용 하 여 변경 사항을 거부 또는 **DataRowView.CancelEdit**합니다. 행은 한 번에 하나씩만 편집할 수 있습니다. 호출 하는 경우는 **AddNew** 또는 **BeginEdit** 의 메서드는 **DataRowView** 보류 중인 행이 있는 동안 **EndEdit** 에 암시적으로 호출 보류 중인 행입니다. 때 **EndEdit** 를 호출할 제안 된 변경 내용에 배치 됩니다는 **현재** 은 기본 행 버전 **DataRow** 수 나중에 커밋하거나 거부할는 를사용하여 **AcceptChanges** 또는 **RejectChanges** 의 메서드는 **DataTable**, **DataSet**, 또는 **DataRow** 개체입니다. 경우 **AllowEdit** 은 **false**에서 값을 수정 하려고 하면 예외가 throw 되는 **DataView**합니다.  
  
 기존 **DataRowView** 편집 되는 내부 이벤트 **DataTable** 제안 된 변경 내용으로 발생 합니다. 호출 하는 경우 유의 **EndEdit** 또는 **CancelEdit** 은 기본 **DataRow**, 보류 중인 변경 내용을 적용 되거나 취소 여부에 관계 없이 될  **EndEdit** 또는 **CancelEdit** 라고 하는 **DataRowView**합니다.  
  
 경우 **AllowDelete** 은 **true**, 행을 삭제할 수는 **DataView** 를 사용 하 여는 **삭제** 의 메서드는 **DataView**  또는 **DataRowView** 개체 및 행 내부에서 삭제 됩니다 **DataTable**합니다. 나중에 커밋 또는 사용 하 여 삭제를 거부할 수 **AcceptChanges** 또는 **RejectChanges** 각각. 경우 **AllowDelete** 은 **false**, 호출 하는 경우 예외가 throw 되는 **삭제** 의 메서드는 **DataView** 또는  **DataRowView**합니다.  
  
 다음 코드 예제에서는 사용 하 여 비활성화는 **DataView** 를 delete 행과 새 행을 사용 하 여 원본 테이블을 추가 하는 **DataView**합니다.  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custView As DataView = custTable.DefaultView  
custView.Sort = "CompanyName"  
  
custView.AllowDelete = False  
  
Dim newDRV As DataRowView = custView.AddNew()  
newDRV("CustomerID") = "ABCDE"  
newDRV("CompanyName") = "ABC Products"  
newDRV.EndEdit()  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
DataView custView = custTable.DefaultView;  
custView.Sort = "CompanyName";  
  
custView.AllowDelete = false;  
  
DataRowView newDRV = custView.AddNew();  
newDRV["CustomerID"] = "ABCDE";  
newDRV["CompanyName"] = "ABC Products";  
newDRV.EndEdit();  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 <xref:System.Data.DataRowView>  
 [DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
