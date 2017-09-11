---
title: "(Visual Basic) 데이터를 그룹화 합니다. | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 8f3a0871-6958-4aef-8f6f-493e189fd57d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ce4e8f924f91eed451d3b1a02cd0bcff75589537
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="grouping-data-visual-basic"></a><span data-ttu-id="e5ea7-102">데이터 그룹화 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e5ea7-102">Grouping Data (Visual Basic)</span></span>
<span data-ttu-id="e5ea7-103">그룹화는 각 그룹의 요소가 공통 특성을 공유 되도록 데이터를 그룹으로 나누는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="e5ea7-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="e5ea7-104">다음 그림에는 문자 시퀀스를 그룹화 한 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e5ea7-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="e5ea7-105">각 그룹에 대 한 키에는 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="e5ea7-105">The key for each group is the character.</span></span>  
  
 <span data-ttu-id="e5ea7-106">![LINQ 그룹화 작업](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")</span><span class="sxs-lookup"><span data-stu-id="e5ea7-106">![LINQ Grouping Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")</span></span>  
  
 <span data-ttu-id="e5ea7-107">데이터 요소를 그룹화 하는 표준 쿼리 연산자 메서드는 다음 섹션에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5ea7-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e5ea7-108">메서드</span><span class="sxs-lookup"><span data-stu-id="e5ea7-108">Methods</span></span>  
  
|<span data-ttu-id="e5ea7-109">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="e5ea7-109">Method Name</span></span>|<span data-ttu-id="e5ea7-110">설명</span><span class="sxs-lookup"><span data-stu-id="e5ea7-110">Description</span></span>|<span data-ttu-id="e5ea7-111">Visual Basic 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="e5ea7-111">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="e5ea7-112">추가 정보</span><span class="sxs-lookup"><span data-stu-id="e5ea7-112">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="e5ea7-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="e5ea7-113">GroupBy</span></span>|<span data-ttu-id="e5ea7-114">공통 특성을 공유 하는 요소를 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="e5ea7-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="e5ea7-115">각 그룹으로 표시 되는 <xref:System.Linq.IGrouping%602>개체.</xref:System.Linq.IGrouping%602></span><span class="sxs-lookup"><span data-stu-id="e5ea7-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`Group … By … Into …`|<span data-ttu-id="e5ea7-116"><xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=fullName></xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e5ea7-116"><xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="e5ea7-117"><xref:System.Linq.Queryable.GroupBy%2A?displayProperty=fullName></xref:System.Linq.Queryable.GroupBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e5ea7-117"><xref:System.Linq.Queryable.GroupBy%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="e5ea7-118">ToLookup</span><span class="sxs-lookup"><span data-stu-id="e5ea7-118">ToLookup</span></span>|<span data-ttu-id="e5ea7-119">에 요소를 삽입 하는 <xref:System.Linq.Lookup%602>키 선택기 함수에 따라 (예: 일 대 다 사전).</xref:System.Linq.Lookup%602></span><span class="sxs-lookup"><span data-stu-id="e5ea7-119">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="e5ea7-120">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="e5ea7-120">Not applicable.</span></span>|<span data-ttu-id="e5ea7-121"><xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e5ea7-121"><xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="e5ea7-122">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="e5ea7-122">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="e5ea7-123">다음 코드 예제에서는 `Group By` 짝수 또는 홀수 인지 여부에 따라 목록에서 그룹 정수로 절.</span><span class="sxs-lookup"><span data-stu-id="e5ea7-123">The following code example uses the `Group By` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
```vb  
Dim numbers As New System.Collections.Generic.List(Of Integer)(  
     New Integer() {35, 44, 200, 84, 3987, 4, 199, 329, 446, 208})  
  
Dim query = From number In numbers   
            Group By Remainder = (number Mod 2) Into Group  
  
Dim sb As New System.Text.StringBuilder()  
For Each group In query  
    sb.AppendLine(If(group.Remainder = 0, vbCrLf & "Even numbers:", vbCrLf & "Odd numbers:"))  
    For Each num In group.Group  
        sb.AppendLine(num)  
    Next  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' Odd numbers:  
' 35  
' 3987  
' 199  
' 329  
  
' Even numbers:  
' 44  
' 200  
' 84  
' 4  
' 446  
' 208  
```  
  
## <a name="see-also"></a><span data-ttu-id="e5ea7-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5ea7-124">See Also</span></span>  
 <span data-ttu-id="e5ea7-125"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="e5ea7-125"><xref:System.Linq></span></span>   
<span data-ttu-id="e5ea7-126"> [표준 쿼리 연산자 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="e5ea7-126"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="e5ea7-127"> [Group By 절](../../../../visual-basic/language-reference/queries/group-by-clause.md) </span><span class="sxs-lookup"><span data-stu-id="e5ea7-127"> [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md) </span></span>  
<span data-ttu-id="e5ea7-128"> [방법: 파일 확장명 (LINQ) (Visual Basic)으로 그룹화](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md) </span><span class="sxs-lookup"><span data-stu-id="e5ea7-128"> [How to: Group Files by Extension (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md) </span></span>  
<span data-ttu-id="e5ea7-129"> [방법: 그룹 (LINQ) (Visual Basic)를 사용 하 여 파일을 여러 파일로 분할](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)</span><span class="sxs-lookup"><span data-stu-id="e5ea7-129"> [How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)</span></span>
