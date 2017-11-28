---
title: "샘플 XML 파일: 네임스페이스의 숫자 데이터3"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 51750cab-3c66-4511-90fb-b9d211308d31
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2437f22c1c76d1a24883cc2ed5b0e9c5f068e55b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="sample-xml-file-numerical-data-in-a-namespace"></a>샘플 XML 파일: 네임스페이스의 숫자 데이터
다음 XML 파일은 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 설명서의 다양한 예제에서 사용됩니다. 이 파일에는 합계 및 평균을 구하고 그룹화할 숫자 데이터가 포함되어 있습니다. XML은 네임스페이스에 있습니다.  
  
## <a name="data"></a>데이터  
  
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
  
## <a name="see-also"></a>참고 항목  
 [샘플 XML 문서(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-documents-linq-to-xml.md)
