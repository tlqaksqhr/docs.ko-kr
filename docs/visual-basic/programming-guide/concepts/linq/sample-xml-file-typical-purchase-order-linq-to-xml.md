---
title: '샘플 XML 파일: 일반적인 구매 주문(LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 65321b9c-1239-45e4-af40-eb86cedf7abd
ms.openlocfilehash: 4a0d16013ba85eace6cca374f2f284c4a6e39f69
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33644903"
---
# <a name="sample-xml-file-typical-purchase-order-linq-to-xml"></a><span data-ttu-id="4010e-102">샘플 XML 파일: 일반적인 구매 주문(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="4010e-102">Sample XML File: Typical Purchase Order (LINQ to XML)</span></span>
<span data-ttu-id="4010e-103">다음 XML 파일은 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 설명서의 다양한 예제에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4010e-103">The following XML file is used in various examples in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] documentation.</span></span> <span data-ttu-id="4010e-104">이 파일은 일반적인 구매 주문입니다.</span><span class="sxs-lookup"><span data-stu-id="4010e-104">This file is a typical purchase order.</span></span>  
  
## <a name="purchaseorderxml"></a><span data-ttu-id="4010e-105">PurchaseOrder.xml</span><span class="sxs-lookup"><span data-stu-id="4010e-105">PurchaseOrder.xml</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4010e-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4010e-106">See Also</span></span>  
 [<span data-ttu-id="4010e-107">샘플 XML 문서(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="4010e-107">Sample XML Documents (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-documents-linq-to-xml.md)
