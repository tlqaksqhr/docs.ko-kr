---
title: "System.Convert 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ca6c5b6-ea5d-4ab0-b675-f082135b342c
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 7f4ed9cc6ae4668fe978b0e7f685e360f1044e6b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="systemconvert-methods"></a><span data-ttu-id="abcb8-102">System.Convert 메서드</span><span class="sxs-lookup"><span data-stu-id="abcb8-102">System.Convert Methods</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="abcb8-103">에서는 다음 <xref:System.Convert> 메서드를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="abcb8-103"> does not support the following <xref:System.Convert> methods.</span></span>  
  
-   <span data-ttu-id="abcb8-104"><xref:System.IFormatProvider> 매개 변수를 사용하는 버전</span><span class="sxs-lookup"><span data-stu-id="abcb8-104">Versions with an <xref:System.IFormatProvider> parameter.</span></span>  
  
-   <span data-ttu-id="abcb8-105">문자 배열 또는 바이트 배열과 관련된 메서드</span><span class="sxs-lookup"><span data-stu-id="abcb8-105">Methods that involve char arrays or byte arrays:</span></span>  
  
    -   <xref:System.Convert.FromBase64CharArray%2A>  
  
    -   <xref:System.Convert.ToBase64CharArray%2A>  
  
    -   <xref:System.Convert.FromBase64String%2A>  
  
    -   <xref:System.Convert.ToBase64String%2A>  
  
-   <span data-ttu-id="abcb8-106">다음과 같은 메서드</span><span class="sxs-lookup"><span data-stu-id="abcb8-106">The following methods:</span></span>  
  
    -   <span data-ttu-id="abcb8-107">`public static <Type2> To<Type2>(<Type1> value);` </span><span class="sxs-lookup"><span data-stu-id="abcb8-107">`public static <Type2> To<Type2>(<Type1> value);` where</span></span>  
  
         <span data-ttu-id="abcb8-108">여기서 `Type1` 및 `Type2`은(는) 각각 `sbyte`, `uint`, `ulong` 또는 `ushort` 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="abcb8-108">`Type1` and `Type2` are each one of `sbyte`, `uint`, `ulong`, or `ushort`.</span></span>  
  
    -   <span data-ttu-id="abcb8-109">C#: </span><span class="sxs-lookup"><span data-stu-id="abcb8-109">C#:</span></span>  
  
         `int To<int type>(string value, int fromBase),`  
  
         `ToString(... value, int toBase)`  
  
    -   <span data-ttu-id="abcb8-110">Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="abcb8-110">Visual Basic:</span></span>  
  
         `Function To(Of [Numeric])(value as String, fromBase As Integer)`  
  
         `As [Numeric], ToString( value As …, toBase As Integer)`  
  
    -   <xref:System.Convert.IsDBNull%2A>  
  
    -   <xref:System.Convert.GetTypeCode%2A>  
  
    -   <xref:System.Convert.ChangeType%2A>  
  
## <a name="see-also"></a><span data-ttu-id="abcb8-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="abcb8-111">See Also</span></span>  
 [<span data-ttu-id="abcb8-112">데이터 형식 및 함수</span><span class="sxs-lookup"><span data-stu-id="abcb8-112">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
