---
title: "DataView 이벤트 처리"
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
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: bf3b02227de5068a031cedb73269148c7d5262a0
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="handling-dataview-events"></a><span data-ttu-id="59c21-102">DataView 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="59c21-102">Handling DataView Events</span></span>
<span data-ttu-id="59c21-103"><xref:System.Data.DataView.ListChanged>의 <xref:System.Data.DataView> 이벤트를 사용하여 뷰가 업데이트되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59c21-103">You can use the <xref:System.Data.DataView.ListChanged> event of the <xref:System.Data.DataView> to determine if a view has been updated.</span></span> <span data-ttu-id="59c21-104">이벤트를 발생시키는 업데이트에는 원본으로 사용하는 테이블에서의 행 추가, 삭제 또는 수정과 원본으로 사용하는 테이블 스키마에서의 열 추가 또는 삭제, 그리고 부모 또는 자식 관계의 변경이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="59c21-104">Updates that raise the event include adding, deleting, or modifying a row in the underlying table; adding or deleting a column to the schema of the underlying table; and a change in a parent or child relationship.</span></span> <span data-ttu-id="59c21-105">**ListChanged** 이벤트 또한 알려 인해 새 정렬 순서 또는 필터를 적용 하는 보고 있는 행 목록이 크게 변경 된 경우.</span><span class="sxs-lookup"><span data-stu-id="59c21-105">The **ListChanged** event also notifies you if the list of rows you are viewing has changed significantly due to the application of a new sort order or a filter.</span></span>  
  
 <span data-ttu-id="59c21-106">**ListChanged** 이벤트를 구현 하는 **ListChangedEventHandler** 의 대리자는 <xref:System.ComponentModel> 입력으로 사용 하 고 네임 스페이스는 <xref:System.ComponentModel.ListChangedEventArgs> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="59c21-106">The **ListChanged** event implements the **ListChangedEventHandler** delegate of the <xref:System.ComponentModel> namespace and takes as input a <xref:System.ComponentModel.ListChangedEventArgs> object.</span></span> <span data-ttu-id="59c21-107">사용 하 여 어떤 유형의 변경 되었음을 확인할 수 있습니다는 <xref:System.ComponentModel.ListChangedType> 열거형 값에는 **ListChangedType** 속성은 **ListChangedEventArgs** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="59c21-107">You can determine what type of change has occurred using the <xref:System.ComponentModel.ListChangedType> enumeration value in the **ListChangedType** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="59c21-108">추가 관련 된 변경 내용에 대 한 삭제 또는 이동한 행을 추가 되거나 이동한 행의 새 인덱스와 삭제 된 행의 이전 인덱스 액세스할 수 있습니다를 사용 하는 **NewIndex** 의 속성은 **ListChangedEventArgs** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="59c21-108">For changes that involve adding, deleting, or moving rows, the new index of the added or moved row and the previous index of the deleted row can be accessed using the **NewIndex** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="59c21-109">행이 이동한 경우 이동한 행의 이전 인덱스 액세스할 수 있습니다를 사용 하는 **OldIndex** 의 속성은 **ListChangedEventArgs** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="59c21-109">In the case of a moved row, the previous index of the moved row can be accessed using the **OldIndex** property of the **ListChangedEventArgs** object.</span></span>  
  
 <span data-ttu-id="59c21-110">**DataViewManager** 도 노출는 **ListChanged** 테이블이 추가 되거나 제거 또는 변경 하기 위해 수행한 경우에 이벤트는 **관계** 의 컬렉션은 기본 **DataSet**합니다.</span><span class="sxs-lookup"><span data-stu-id="59c21-110">The **DataViewManager** also exposes a **ListChanged** event to notify you if a table has been added or removed, or if a change has been made to the **Relations** collection of the underlying **DataSet**.</span></span>  
  
 <span data-ttu-id="59c21-111">다음 코드 예제에서는 추가 하는 방법을 보여 줍니다.는 **ListChanged** 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="59c21-111">The following code example shows how to add a **ListChanged** event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="59c21-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59c21-112">See Also</span></span>  
 <xref:System.Data.DataView>  
 <xref:System.ComponentModel.ListChangedEventHandler>  
 [<span data-ttu-id="59c21-113">DataView</span><span class="sxs-lookup"><span data-stu-id="59c21-113">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="59c21-114">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="59c21-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
