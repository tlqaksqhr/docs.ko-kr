---
title: "DataView 이벤트 처리 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataView 이벤트 처리
<xref:System.Data.DataView>의 <xref:System.Data.DataView.ListChanged> 이벤트를 사용하여 뷰가 업데이트되었는지 확인할 수 있습니다.  이벤트를 발생시키는 업데이트에는 원본으로 사용하는 테이블에서의 행 추가, 삭제 또는 수정과 원본으로 사용하는 테이블 스키마에서의 열 추가 또는 삭제, 그리고 부모 또는 자식 관계의 변경이 포함됩니다.  또한 **ListChanged** 이벤트는 응용 프로그램의 새 정렬 순서나 필터로 인해 현재 사용자가 보고 있는 행 목록이 크게 변경되었는지 여부를 알려 줍니다.  
  
 **ListChanged** 이벤트는 <xref:System.ComponentModel> 네임스페이스의 **ListChangedEventHandler** 대리자를 구현하며 <xref:System.ComponentModel.ListChangedEventArgs> 개체를 입력으로 받습니다.  **ListChangedEventArgs** 개체의 **ListChangedType** 속성에 <xref:System.ComponentModel.ListChangedType> 열거형 값을 사용하면 발생한 변경의 유형을 확인할 수 있습니다.  행이 추가, 삭제 또는 이동함에 따라 추가되거나 이동한 행의 새 인덱스와 삭제된 행의 이전 인덱스는 **ListChangedEventArgs** 개체의 **NewIndex** 속성을 사용하여 액세스할 수 있습니다.  행이 이동한 경우 **ListChangedEventArgs** 개체의 **OldIndex** 속성을 사용하여 이동한 행의 이전 인덱스에 액세스할 수 있습니다.  
  
 또한 **DataViewManager**에서는 **ListChanged** 이벤트를 노출시켜 테이블이 추가되거나 제거되었는지, 또는 원본으로 사용하는 **DataSet**의 **Relations** 컬렉션이 변경되었는지를 알려 줍니다.  
  
 다음 코드 예제에서는 **ListChanged** 이벤트 처리기를 추가하는 방법을 보여 줍니다.  
  
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
  
## 참고 항목  
 <xref:System.Data.DataView>   
 <xref:System.ComponentModel.ListChangedEventHandler>   
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)