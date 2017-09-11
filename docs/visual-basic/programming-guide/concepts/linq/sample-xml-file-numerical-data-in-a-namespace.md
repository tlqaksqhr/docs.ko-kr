---
title: "샘플 XML 파일: 숫자 데이터에는 Namespace1 | Microsoft 문서"
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
ms.assetid: f01cc0a1-fb55-4b42-8380-16f4be47d6f4
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
ms.openlocfilehash: 96039a8f425d5af1b5875557c16f8decab6cc7a6
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="sample-xml-file-numerical-data-in-a-namespace"></a><span data-ttu-id="a7321-102">샘플 XML 파일: 네임스페이스의 숫자 데이터</span><span class="sxs-lookup"><span data-stu-id="a7321-102">Sample XML File: Numerical Data in a Namespace</span></span>
<span data-ttu-id="a7321-103">다음 XML 파일은 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 설명서의 다양한 예제에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7321-103">The following XML file is used in various examples in the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] documentation.</span></span> <span data-ttu-id="a7321-104">이 파일에는 합계 및 평균을 구하고 그룹화할 숫자 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7321-104">This file contains numerical data for summing, averaging, and grouping.</span></span> <span data-ttu-id="a7321-105">XML은 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7321-105">The XML is in a namespace.</span></span>  
  
## <a name="data"></a><span data-ttu-id="a7321-106">데이터</span><span class="sxs-lookup"><span data-stu-id="a7321-106">Data</span></span>  
  
```xml  
<Root xmlns='http://www.adatum.com'>  
  <TaxRate>7.25</TaxRate>  
  <Data>  
    <Category>A</Category>  
    <Quantity>3</Quantity>  
    <Price>24.50</Price>  
  </Data>  
  <Data>  
    <Category>B</Category>  
    <Quantity>1</Quantity>  
    <Price>89.99</Price>  
  </Data>  
  <Data>  
    <Category>A</Category>  
    <Quantity>5</Quantity>  
    <Price>4.95</Price>  
  </Data>  
  <Data>  
    <Category>A</Category>  
    <Quantity>3</Quantity>  
    <Price>66.00</Price>  
  </Data>  
  <Data>  
    <Category>B</Category>  
    <Quantity>10</Quantity>  
    <Price>.99</Price>  
  </Data>  
  <Data>  
    <Category>A</Category>  
    <Quantity>15</Quantity>  
    <Price>29.00</Price>  
  </Data>  
  <Data>  
    <Category>B</Category>  
    <Quantity>8</Quantity>  
    <Price>6.99</Price>  
  </Data>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a7321-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7321-107">See Also</span></span>  
 [<span data-ttu-id="a7321-108">샘플 XML 문서(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="a7321-108">Sample XML Documents (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-documents-linq-to-xml.md)
