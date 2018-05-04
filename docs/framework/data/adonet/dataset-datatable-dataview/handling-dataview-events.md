---
title: DataView 이벤트 처리
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
ms.openlocfilehash: 9e67aef2a39a04adfdcc036c008aa80c9151c14b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="handling-dataview-events"></a>DataView 이벤트 처리
<xref:System.Data.DataView.ListChanged>의 <xref:System.Data.DataView> 이벤트를 사용하여 뷰가 업데이트되었는지 확인할 수 있습니다. 이벤트를 발생시키는 업데이트에는 원본으로 사용하는 테이블에서의 행 추가, 삭제 또는 수정과 원본으로 사용하는 테이블 스키마에서의 열 추가 또는 삭제, 그리고 부모 또는 자식 관계의 변경이 포함됩니다. **ListChanged** 이벤트 또한 알려 인해 새 정렬 순서 또는 필터를 적용 하는 보고 있는 행 목록이 크게 변경 된 경우.  
  
 **ListChanged** 이벤트를 구현 하는 **ListChangedEventHandler** 의 대리자는 <xref:System.ComponentModel> 입력으로 사용 하 고 네임 스페이스는 <xref:System.ComponentModel.ListChangedEventArgs> 개체입니다. 사용 하 여 어떤 유형의 변경 되었음을 확인할 수 있습니다는 <xref:System.ComponentModel.ListChangedType> 열거형 값에는 **ListChangedType** 속성은 **ListChangedEventArgs** 개체입니다. 추가 관련 된 변경 내용에 대 한 삭제 또는 이동한 행을 추가 되거나 이동한 행의 새 인덱스와 삭제 된 행의 이전 인덱스 액세스할 수 있습니다를 사용 하는 **NewIndex** 의 속성은 **ListChangedEventArgs** 개체입니다. 행이 이동한 경우 이동한 행의 이전 인덱스 액세스할 수 있습니다를 사용 하는 **OldIndex** 의 속성은 **ListChangedEventArgs** 개체입니다.  
  
 **DataViewManager** 도 노출는 **ListChanged** 테이블이 추가 되거나 제거 또는 변경 하기 위해 수행한 경우에 이벤트는 **관계** 의 컬렉션은 기본 **DataSet**합니다.  
  
 다음 코드 예제에서는 추가 하는 방법을 보여 줍니다.는 **ListChanged** 이벤트 처리기입니다.  
  
```vb  
AddHandler custView.ListChanged, _  
  New System.ComponentModel.ListChangedEventHandler( _  
  AddressOf OnListChanged)  
  
Private Shared Sub OnListChanged( _  
  sender As Object, args As System.ComponentModel.ListChangedEventArgs)  
  Console.WriteLine("ListChanged:")  
  Console.WriteLine(vbTab & "    Type = " & _  
    System.Enum.GetName(args.ListChangedType.GetType(), _  
    args.ListChangedType))  
  Console.WriteLine(vbTab & "OldIndex = " & args.OldIndex)  
  Console.WriteLine(vbTab & "NewIndex = " & args.NewIndex)  
End Sub  
```  
  
```csharp  
custView.ListChanged  += new   
  System.ComponentModel.ListChangedEventHandler(OnListChanged);  
  
protected static void OnListChanged(object sender,   
  System.ComponentModel.ListChangedEventArgs args)  
{  
  Console.WriteLine("ListChanged:");  
  Console.WriteLine("\t    Type = " + args.ListChangedType);  
  Console.WriteLine("\tOldIndex = " + args.OldIndex);  
  Console.WriteLine("\tNewIndex = " + args.NewIndex);  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Data.DataView>  
 <xref:System.ComponentModel.ListChangedEventHandler>  
 [DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
