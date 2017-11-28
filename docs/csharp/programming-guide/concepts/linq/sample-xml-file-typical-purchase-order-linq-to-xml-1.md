---
title: "샘플 XML 파일: 일반적인 구매 주문(LINQ to XML)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: dcbfb859-24fc-4758-b01c-51d1b6f644e6
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 90319793fadfa7f6103bec59d3b4abf535b3e882
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="sample-xml-file-typical-purchase-order-linq-to-xml"></a><span data-ttu-id="819c9-102">샘플 XML 파일: 일반적인 구매 주문(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="819c9-102">Sample XML File: Typical Purchase Order (LINQ to XML)</span></span>
<span data-ttu-id="819c9-103">다음 XML 파일은 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 설명서의 다양한 예제에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="819c9-103">The following XML file is used in various examples in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] documentation.</span></span> <span data-ttu-id="819c9-104">이 파일은 일반적인 구매 주문입니다.</span><span class="sxs-lookup"><span data-stu-id="819c9-104">This file is a typical purchase order.</span></span>  
  
## <a name="purchaseorderxml"></a><span data-ttu-id="819c9-105">PurchaseOrder.xml</span><span class="sxs-lookup"><span data-stu-id="819c9-105">PurchaseOrder.xml</span></span>  
  
```xml  
<?xml version="1.0"?>  
<PurchaseOrder PurchaseOrderNumber="99503" OrderDate="1999-10-20">  
  <Address Type="Shipping">  
    <Name>Ellen Adams</Name>  
    <Street>123 Maple Street</Street>  
    <City>Mill Valley</City>  
    <State>CA</State>  
    <Zip>10999</Zip>  
    <Country>USA</Country>  
  </Address>  
  <Address Type="Billing">  
    <Name>Tai Yee</Name>  
    <Street>8 Oak Avenue</Street>  
    <City>Old Town</City>  
    <State>PA</State>  
    <Zip>95819</Zip>  
    <Country>USA</Country>  
  </Address>  
  <DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
  <Items>  
    <Item PartNumber="872-AA">  
      <ProductName>Lawnmower</ProductName>  
      <Quantity>1</Quantity>  
      <USPrice>148.95</USPrice>  
      <Comment>Confirm this is electric</Comment>  
    </Item>  
    <Item PartNumber="926-AA">  
      <ProductName>Baby Monitor</ProductName>  
      <Quantity>2</Quantity>  
      <USPrice>39.98</USPrice>  
      <ShipDate>1999-05-21</ShipDate>  
    </Item>  
  </Items>  
</PurchaseOrder>  
```  
  
## <a name="see-also"></a><span data-ttu-id="819c9-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="819c9-106">See Also</span></span>  
 [<span data-ttu-id="819c9-107">샘플 XML 문서(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="819c9-107">Sample XML Documents (LINQ to XML)</span></span>](../../../../csharp/programming-guide/concepts/linq/sample-xml-documents-linq-to-xml.md)
