---
title: "행 찾기"
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
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 43703ead9d38ea1cf02539f12479e9228d7eacd4
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="finding-rows"></a><span data-ttu-id="7a99a-102">행 찾기</span><span class="sxs-lookup"><span data-stu-id="7a99a-102">Finding Rows</span></span>
<span data-ttu-id="7a99a-103"><xref:System.Data.DataView.Find%2A>의 <xref:System.Data.DataView.FindRows%2A> 및 <xref:System.Data.DataView> 메서드를 사용하여 행의 정렬 키 값에 따라 행을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a99a-103">You can search for rows according to their sort key values by using the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView>.</span></span> <span data-ttu-id="7a99a-104">검색의 대/소문자 구분 값에 **찾을** 및 **FindRows** 메서드에 의해 결정 됩니다는 **CaseSensitive** 속성은 기본 <xref:System.Data.DataTable>합니다.</span><span class="sxs-lookup"><span data-stu-id="7a99a-104">The case sensitivity of search values in the **Find** and **FindRows** methods is determined by the **CaseSensitive** property of the underlying <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="7a99a-105">검색 값이 기존 정렬 키 값 전체와 일치해야 결과를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a99a-105">Search values must match existing sort key values in their entirety in order to return a result.</span></span>  
  
 <span data-ttu-id="7a99a-106">**찾을** 의 인덱스를 사용 하는 정수를 반환 하는 메서드는 <xref:System.Data.DataRowView> 검색 조건과 일치 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a99a-106">The **Find** method returns an integer with the index of the <xref:System.Data.DataRowView> that matches the search criteria.</span></span> <span data-ttu-id="7a99a-107">둘 이상의 행 검색 조건과 일치 하는 첫 번째 인덱스에만 일치 하는 경우 **DataRowView** 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a99a-107">If more than one row matches the search criteria, only the index of the first matching **DataRowView** is returned.</span></span> <span data-ttu-id="7a99a-108">일치 하는 경우 **찾을** -1을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a99a-108">If no matches are found, **Find** returns -1.</span></span>  
  
 <span data-ttu-id="7a99a-109">사용 하 여 여러 행과 일치 하는 검색 결과 반환 하려면는 **FindRows** 메서드.</span><span class="sxs-lookup"><span data-stu-id="7a99a-109">To return search results that match multiple rows, use the **FindRows** method.</span></span> <span data-ttu-id="7a99a-110">**FindRows** 처럼 작동은 **찾을** 메서드를 반환 한다는 점을 제외 하 고는 **DataRowView** 배열에 일치 하는 모든 행을 참조 하는 **DataView**합니다.</span><span class="sxs-lookup"><span data-stu-id="7a99a-110">**FindRows** works just like the **Find** method, except that it returns a **DataRowView** array that references all matching rows in the **DataView**.</span></span> <span data-ttu-id="7a99a-111">일치 하는 경우는 **DataRowView** 배열은 비어 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a99a-111">If no matches are found, the **DataRowView** array will be empty.</span></span>  
  
 <span data-ttu-id="7a99a-112">사용 하는 **찾을** 또는 **FindRows** 정렬을 지정 해야 하는 방법을 설정 하거나 순서 **ApplyDefaultSort** 를 **true** 또는 사용 하 여는 **정렬** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="7a99a-112">To use the **Find** or **FindRows** methods you must specify a sort order either by setting **ApplyDefaultSort** to **true** or by using the **Sort** property.</span></span> <span data-ttu-id="7a99a-113">정렬 순서를 지정하지 않으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a99a-113">If no sort order is specified, an exception is thrown.</span></span>  
  
 <span data-ttu-id="7a99a-114">**찾을** 및 **FindRows** 메서드 값의 배열을 길이가 정렬 순서에 있는 열의 수와 일치 하는 입력으로 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a99a-114">The **Find** and **FindRows** methods take an array of values as input whose length matches the number of columns in the sort order.</span></span> <span data-ttu-id="7a99a-115">하나의 열에 대해 정렬하는 경우에는 하나의 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a99a-115">In the case of a sort on a single column, you can pass a single value.</span></span> <span data-ttu-id="7a99a-116">정렬 순서에 여러 열이 포함된 경우에는 개체 배열을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="7a99a-116">For sort orders containing multiple columns, you pass an array of objects.</span></span> <span data-ttu-id="7a99a-117">여러 열에 대해 정렬, 개체 배열의 값와 일치 해야에 지정 된 열의 순서는 **정렬** 의 속성은 **DataView**합니다.</span><span class="sxs-lookup"><span data-stu-id="7a99a-117">Note that for a sort on multiple columns, the values in the object array must match the order of the columns specified in the **Sort** property of the **DataView**.</span></span>  
  
 <span data-ttu-id="7a99a-118">다음 코드 예제는 **찾을** 메서드를 호출 하는 **DataView** 단일 열 정렬 순서를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a99a-118">The following code example shows the **Find** method being called against a **DataView** with a single column sort order.</span></span>  
  
```vb  
Dim custView As DataView = _  
  New DataView(custDS.Tables("Customers"), "", _  
  "CompanyName", DataViewRowState.CurrentRows)  
  
Dim rowIndex As Integer = custView.Find("The Cracker Box")  
  
If rowIndex = -1 Then  
  Console.WriteLine("No match found.")  
Else  
  Console.WriteLine("{0}, {1}", _  
    custView(rowIndex)("CustomerID").ToString(), _  
    custView(rowIndex)("CompanyName").ToString())  
End If  
```  
  
```csharp  
DataView custView = new DataView(custDS.Tables["Customers"], "",   
  "CompanyName", DataViewRowState.CurrentRows);  
  
int rowIndex = custView.Find("The Cracker Box");  
  
if (rowIndex == -1)  
  Console.WriteLine("No match found.");  
else  
  Console.WriteLine("{0}, {1}",  
    custView[rowIndex]["CustomerID"].ToString(),  
    custView[rowIndex]["CompanyName"].ToString());  
```  
  
 <span data-ttu-id="7a99a-119">경우에 **정렬** 여러 열을 지정 하는 속성, 각 열에 대 한 검색 값이 포함 된 개체 배열에서 지정 된 순서 대로 전달 해야는 **정렬** 다음 코드 예제와 같이 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="7a99a-119">If your **Sort** property specifies multiple columns, you must pass an object array with the search values for each column in the order specified by the **Sort** property, as in the following code example.</span></span>  
  
```vb  
Dim custView As DataView = _  
  New DataView(custDS.Tables("Customers"), "", _  
  "CompanyName, ContactName", _  
  DataViewRowState.CurrentRows)  
  
Dim foundRows() As DataRowView = _  
  custView.FindRows(New object() {"The Cracker Box", "Liu Wong"})  
  
If foundRows.Length = 0 Then  
  Console.WriteLine("No match found.")  
Else  
  Dim myDRV As DataRowView  
  For Each myDRV In foundRows  
    Console.WriteLine("{0}, {1}", _  
      myDRV("CompanyName").ToString(), myDRV("ContactName").ToString())  
  Next  
End If  
```  
  
```csharp  
DataView custView = new DataView(custDS.Tables["Customers"], "",  
  "CompanyName, ContactName",  
  DataViewRowState.CurrentRows);  
  
DataRowView[] foundRows =   
  custView.FindRows(new object[] {"The Cracker Box", "Liu Wong"});  
  
if (foundRows.Length == 0)  
  Console.WriteLine("No match found.");  
else  
  foreach (DataRowView myDRV in foundRows)  
    Console.WriteLine("{0}, {1}", myDRV["CompanyName"].ToString(),   
      myDRV["ContactName"].ToString());  
```  
  
## <a name="see-also"></a><span data-ttu-id="7a99a-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a99a-120">See Also</span></span>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [<span data-ttu-id="7a99a-121">DataView</span><span class="sxs-lookup"><span data-stu-id="7a99a-121">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="7a99a-122">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="7a99a-122">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
